---
category: general
date: 2026-11-27
description: 學習如何在 Python 中使用 RM4SCC 格式建立郵政條碼。本教學涵蓋 X 尺寸、條碼高度，以及將圖像儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- RM4SCC barcode
- barcode X dimension
- barcode bar height
- save barcode as PNG
language: zh-hant
lastmod: 2026-11-27
og_description: 使用 Python 透過 RM4SCC 建立郵政條碼。調整 X 尺寸、條碼高度，並匯出為 PNG，提供完整可執行的腳本。
og_image_alt: Screenshot of a generated RM4SCC postal barcode saved as a PNG file
og_title: 在 Python 中建立郵政條碼 – 完整 RM4SCC 範例
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create postal barcode in Python using the RM4SCC format.
    This tutorial covers X dimension, bar height, and saving the image as PNG.
  headline: How to create postal barcode with RM4SCC in Python – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- Python
- Aspose
title: 如何在 Python 中使用 RM4SCC 建立郵政條碼 – 一步一步指南
url: /zh-hant/python-java/general/how-to-create-postal-barcode-with-rm4scc-in-python-step-by-s/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 RM4SCC 建立郵政條碼 – 步驟說明指南

如果您需要 **建立郵政條碼** 供郵寄系統使用，本指南將逐步說明如何在 Python 中產生 RM4SCC 條碼。您將看到如何設定 X 尺寸、設定自訂條碼高度，並將結果儲存為 PNG 圖片——全部只需一個自包含的腳本。

產生 **郵政條碼** 是物流、電商與大量郵寄解決方案的常見需求。以下程式碼使用 Aspose.BarCode for Python 套件，實作許多郵政服務所需的 RM4SCC 符號。完成本教學後，您將得到可直接列印於信封或貼於包裹的 PNG 檔案。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* 有效的 Aspose.BarCode for Python 授權（或免費評估金鑰）。  
  使用 `pip install aspose-barcode` 安裝套件。
* 對將要儲存 PNG 的目錄具有寫入權限。

不需要額外的系統函式庫；此套件會在內部處理所有影像運算。

## 步驟 1：匯入 Aspose.BarCode 類別並建立產生器

第一件事是匯入必要的類別，並為 RM4SCC 格式實例化 `BarcodeGenerator`。**RM4SCC 條碼** 會編碼一個 6 位數字字串，代表郵遞路由碼。

```python
# Step 1: Import and create a barcode generator for RM4SCC
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# The data "123456" is a sample postal routing number.
barcode_generator = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
```

**為什麼這很重要：**  
`EncodeTypes.RM4SCC` 讓套件套用皇家郵件 4‑State Customer Code 所定義的符號規則。使用正確的類型可確保條碼能被郵政設備掃描。

## 步驟 2：設定 X 尺寸（模組寬度）

**條碼 X 尺寸** 控制最小條形元素的寬度。將其設為 4 像素，可在大多數標籤印表機上取得可讀性與緊湊度的平衡。

```python
# Step 2: Set the X dimension (module width) to 4 pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

**為什麼這很重要：**  
較小的 X 尺寸會縮減條碼總寬度，而較大的數值則提升對印刷缺陷的容忍度。請依印表機 DPI 與標籤可用空間調整此值。

## 步驟 3：定義條碼高度

**條碼高度** 決定每根條形的垂直長度。100 像素的高度可為光學掃描器提供足夠對比，同時不會佔用過多標籤空間。

```python
# Step 3: Set the bar height to 100 pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

**為什麼這很重要：**  
郵政掃描器需要最低條碼高度才能可靠偵測四種狀態的圖樣。若高度設定過低，掃描器可能無法分辨條與空白之間的細微差異。

## 步驟 4：將條碼儲存為 PNG 圖片

最後，**將條碼儲存為 PNG**，以取得適合列印的無損影像。PNG 會保留您設定的精確像素尺寸，對條碼的準確性至關重要。

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to {output_path}")
```

**為什麼這很重要：**  
PNG 被標籤設計軟體與印表機廣泛支援。此檔案可直接嵌入 PDF、Word 文件，或使用一般影像列印工具列印。

### 預期輸出

執行腳本後會產生名為 `PostalRM4SCCBarHeight100Pixels.png` 的檔案。開啟影像即可看到一個具備 4 像素模組與 100 像素條碼高度的清晰 RM4SCC 條碼，適合放置於郵寄標籤上。

## 完整原始碼 – 可直接複製執行

以下提供完整、可執行的範例，結合所有步驟。請將 `YOUR_DIRECTORY` 替換為您希望儲存 PNG 的絕對或相對路徑。

```python
"""
Complete example: create postal barcode (RM4SCC) in Python,
configure X dimension and bar height, and save as PNG.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_postal_barcode(data: str,
                            x_dim_pixels: int = 4,
                            bar_height_pixels: int = 100,
                            output_file: str = "PostalRM4SCC.png") -> None:
    """
    Generates an RM4SCC postal barcode with custom dimensions.

    Args:
        data: Six‑digit numeric string for the postal routing code.
        x_dim_pixels: Width of the smallest bar element (default 4).
        bar_height_pixels: Height of the bars in pixels (default 100).
        output_file: Path where the PNG image will be saved.
    """
    # Create generator for RM4SCC
    generator = BarcodeGenerator(EncodeTypes.RM4SCC, data)

    # Apply custom dimensions
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels
    generator.parameters.barcode.bar_height.pixels = bar_height_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.Png)

    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage
    generate_postal_barcode(
        data="123456",
        x_dim_pixels=4,
        bar_height_pixels=100,
        output_file="YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png"
    )
```

**函式說明：**

* `generate_postal_barcode` 將條碼產生邏輯抽離，使其在不同專案中可重複使用。
* 預設參數與步驟說明中的數值相同，您亦可傳入其他數字以配合不同標籤規格。
* 函式會印出確認訊息，方便在批次產生多筆條碼時追蹤。

## 常見變化與邊緣案例

| 情境 | 建議的變更 |
|-----------|--------------------|
| **不同的路由號碼長度** | RM4SCC 必須恰好 6 位數。若收到較短的字串，請使用 `data.zfill(6)` 以零填補前置。 |
| **高解析度印表機** | 將 `x_dim_pixels` 提升至 6 或 8，以保持條寬與 DPI 成比例。 |
| **需要透明背景** | 將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.PngTransparent`（若支援），或設定 `generator.parameters.image.transparent_background = True`。 |
| **批次產生** | 迭代路由號碼清單，對每筆呼叫 `generate_postal_barcode`，並將結果存入指定資料夾。 |
| **非數字資料** | RM4SCC 不接受字母。請在呼叫產生器前驗證輸入，以避免執行時錯誤。 |

## 提升郵政條碼列印可靠性的專業技巧

* 在建立條碼前 **驗證資料長度**；若字串不是六位數，會拋出例外。
* **使用實體掃描器測試列印結果**，再投入正式環境。印表機墨水密度的細微差異可能影響可讀性。
* **保持 PNG 檔案未壓縮**（預設 PNG 壓縮為無損）。若重新壓縮為 JPEG，會產生破壞條碼的雜訊。
* **使用一致的輸出目錄**，以簡化與期待特定資料夾結構的標籤設計工具的整合。

## 結論

現在您已掌握如何在 Python 中使用 RM4SCC 符號 **建立郵政條碼**、調整 **條碼 X 尺寸**、設定 **條碼高度**，以及 **將條碼儲存為 PNG**。完整腳本可整合至任何運送標籤工作流程，且模組化函式讓您輕鬆自動產生數百筆條碼。

接下來，您可以探索以下相關主題，如 **為追蹤 URL 產生 QR Code**、**在 PDF 發票中嵌入條碼**，或 **使用其他郵政符號如 POSTNET**。這些皆建立在本指南示範的相同原則：選擇正確的編碼類型、設定視覺參數，並匯出高品質影像。

歡迎自行嘗試不同的尺寸、顏色或檔案格式，以符合您的列印環境。祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何在 Python 中使用 Aspose.BarCode 建立郵政條碼](/barcode/english/python-java/general/how-to-create-postal-barcode-in-python-with-aspose-barcode/)
- [在 Python 中產生條碼 PNG – 完整指南](/barcode/english/python-java/general/create-barcode-png-in-python-complete-guide/)
- [如何在 Python 中建立 Planet 條碼 PNG](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}