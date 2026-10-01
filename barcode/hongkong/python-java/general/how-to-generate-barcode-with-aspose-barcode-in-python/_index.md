---
category: general
date: 2026-07-30
description: 如何在 Python 中使用 Aspose.BarCode 產生條碼——學習如何設定尺寸、更改填色，並在數分鐘內儲存 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to set dimensions
- how to change fill
- generate barcode with aspose
language: zh-hant
lastmod: 2026-07-30
og_description: 如何在 Python 中使用 Aspose.BarCode 快速生成條碼。了解如何設定尺寸、變更填充，並將 PNG 檔匯出至任何應用程式。
og_image_alt: Screenshot showing a filled Planet barcode and an empty Planet barcode
  generated with Aspose.BarCode
og_title: 如何使用 Aspose.BarCode 生成條碼 – Python 指南
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  headline: How to generate barcode with Aspose.BarCode in Python
  type: TechArticle
- description: How to generate barcode using Aspose.BarCode in Python – learn how
    to set dimensions, change fill, and save PNG images in minutes.
  name: How to generate barcode with Aspose.BarCode in Python
  steps:
  - name: Why set `x_dimension.pixels`?
    text: Even though the default works, you often need to **how to set dimensions**
      to match printer DPI or UI constraints. The `x_dimension` property controls
      the width of a single bar in pixels; larger numbers yield a thicker barcode,
      while smaller numbers make it more compact.
  - name: Expected output
    text: 'Running the script prints something like:'
  - name: 5.1 Making the barcode larger for print
    text: 'If you’re printing on a 300 dpi label printer, a 4‑pixel bar might look
      tiny. Increase the `x_dimension` to, say, 8 pixels:'
  - name: 5.2 Making the barcode smaller for mobile screens
    text: Conversely, for a mobile app you might want a tighter barcode. Setting `x_dimension`
      to 2 pixels reduces the width without breaking readability (Aspose handles the
      scaling automatically).
  type: HowTo
tags:
- barcode
- Aspose
- Python
title: 如何在 Python 中使用 Aspose.BarCode 產生條碼
url: /zh-hant/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.BarCode 產生條碼

有沒有想過在 Python 專案中 **如何產生條碼**，卻不想與低階影像函式庫糾纏？你並不是唯一有此疑問的人。無論你是要建立運送標籤系統、票務平台，或只是需要一個快速的 QR Code 來示範，掌握條碼產生技術都能為你節省大量的試錯時間。

在本教學中，我們將逐步示範一個完整、可直接執行的範例，說明如何使用 Aspose.BarCode 函式庫 **產生條碼**、如何設定尺寸，以及如何變更填充方式。完成後，你會在輸出資料夾中得到兩個 PNG 檔案——一個是實心條碼，另一個是空心條碼。

## 前置條件

* 已安裝 Python 3.8+（程式碼可在 Windows、macOS 與 Linux 上執行）
* 擁有有效的 Aspose.BarCode for Python via .NET 授權（可先使用免費試用版）
* `pip install aspose-barcode` 已在你的虛擬環境中執行
* 一個可寫入的資料夾——在範例中我們稱之為 `YOUR_DIRECTORY`

不需要其他第三方套件。

## 步驟 1：安裝並匯入 Aspose.BarCode

首先，我們需要安裝函式庫本身。請在終端機執行一次以下指令：

```bash
pip install aspose-barcode
```

現在我們可以匯入將要使用的類別。這正是 **產生條碼** 真正開始的地方，因為若沒有正確的匯入，就無法呼叫產生器。

```python
# Import the required Aspose.BarCode classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

> **小技巧：** 若你使用虛擬環境，請在執行 `pip install` 前先啟動它。這樣可以保持全域的 Python 環境整潔。

## 步驟 2：建立 Planet 條碼 – 預設（實心）版本

Planet 條碼是郵政服務常用的經典 2‑of‑5 符號。讓我們從最簡單的情況開始：實心條碼。此步驟示範 **產生條碼** 的預設設定。

```python
# Step 2: Create a Planet barcode with filled bars (default)
filled_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
filled_barcode.parameters.barcode.x_dimension.pixels = 4   # default width per bar
filled_barcode.save("YOUR_DIRECTORY/PostalPlanetFilled.png", BarCodeImageFormat.Png)
```

### 為什麼要設定 `x_dimension.pixels`？

即使預設值可用，你仍常需要 **設定尺寸** 以符合印表機 DPI 或 UI 限制。`x_dimension` 屬性控制單根條的寬度（以像素為單位）；數值越大條碼越粗，數值越小則條碼更緊湊。

## 步驟 3：建立 Planet 條碼（空心條） 

現在來回答 **如何變更填充** 的問題。透過切換 `filled_bars` 旗標，我們可以將實心黑條切換為仍能編碼相同資料的空心條。

```python
# Step 3: Create a Planet barcode with empty (unfilled) bars
empty_barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
empty_barcode.parameters.barcode.x_dimension.pixels = 4   # keep dimensions consistent
empty_barcode.parameters.barcode.filled_bars = False     # turn off fill
empty_barcode.save("YOUR_DIRECTORY/PostalPlanetEmpty.png", BarCodeImageFormat.Png)
```

當你同時開啟 `PostalPlanetFilled.png` 與 `PostalPlanetEmpty.png` 時，會看到視覺差異：實心版本為純黑，空心版本則以輪廓顯示條形。這在需要較輕量 UI 疊加時相當實用。

## 步驟 4：完整可執行腳本（完整解決方案）

以下是完整程式碼，你可以直接複製貼上至名為 `generate_planet_barcodes.py` 的檔案中。它涵蓋從匯入到儲存影像的所有步驟，讓你不必再尋找遺漏的部份。

```python
#!/usr/bin/env python3
"""
Complete example: generate filled and empty Planet barcodes using Aspose.BarCode.
Demonstrates how to generate barcode, how to set dimensions, and how to change fill.
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

def ensure_output_dir(path: str) -> None:
    """Create the output directory if it doesn't exist."""
    if not os.path.isdir(path):
        os.makedirs(path)
        print(f"Created output directory: {path}")

def generate_filled_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate a filled Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    file_path = os.path.join(output_dir, "PostalPlanetFilled.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

def generate_empty_barcode(output_dir: str, data: str = "123456", x_dim: int = 4) -> str:
    """Generate an empty (unfilled) Planet barcode and return the file path."""
    generator = BarcodeGenerator(EncodeTypes.Planet, data)
    generator.parameters.barcode.x_dimension.pixels = x_dim
    generator.parameters.barcode.filled_bars = False
    file_path = os.path.join(output_dir, "PostalPlanetEmpty.png")
    generator.save(file_path, BarCodeImageFormat.Png)
    return file_path

if __name__ == "__main__":
    # Define where the PNG files will be stored
    output_folder = "YOUR_DIRECTORY"
    ensure_output_dir(output_folder)

    filled_path = generate_filled_barcode(output_folder)
    empty_path = generate_empty_barcode(output_folder)

    print(f"Filled barcode saved to: {filled_path}")
    print(f"Empty barcode saved to: {empty_path}")
```

### 預期輸出

執行腳本時會印出類似以下內容：

```
Created output directory: YOUR_DIRECTORY
Filled barcode saved to: YOUR_DIRECTORY/PostalPlanetFilled.png
Empty barcode saved to: YOUR_DIRECTORY/PostalPlanetEmpty.png
```

使用任何影像檢視器開啟這兩個 PNG 檔案，你應該會看到經典的 Planet 條碼——一個實心、一個空心。兩者皆編碼字串 `123456`。

## 步驟 5：調整尺寸以因應不同使用情境

既然你已了解 **設定尺寸** 的方法，接下來探討幾個常見情境。

### 5.1 為列印放大條碼

若在 300 dpi 標籤印表機上列印，4 像素的條可能過小。將 `x_dimension` 提升至例如 8 像素：

```python
filled_barcode.parameters.barcode.x_dimension.pixels = 8
```

### 5.2 為行動裝置螢幕縮小條碼

相反地，若在行動應用程式中，你可能需要更緊湊的條碼。將 `x_dimension` 設為 2 像素即可在不影響可讀性的前提下降低寬度（Aspose 會自動處理縮放）。

```python
empty_barcode.parameters.barcode.x_dimension.pixels = 2
```

請記得，條碼的高度會根據符號規格自動調整，你只需關注寬度即可。

## 步驟 6：進階填充選項與其需求原因

除了簡單的 `filled_bars` 布林值外，Aspose.BarCode 還允許自訂條碼顏色、背景顏色，甚至加入漸層。如果你需要 **變更填充** 超過「實心 vs 空心」的需求，可以這樣做：

```python
filled_barcode.parameters.barcode.barcode_color = System.Drawing.Color.from_argb(255, 0, 0, 255)  # blue bars
filled_barcode.parameters.barcode.back_color = System.Drawing.Color.from_argb(255, 255, 255, 255)   # white background
```

*(註：上述使用 .NET 顏色結構；在純 Python 中則使用相應的 Aspose 列舉。)* 這對於品牌化相當有用——想像在條碼背景中巧妙嵌入公司標誌。

## 常見陷阱與避免方法

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| 條碼在儲存的 PNG 中看起來模糊 | `x_dimension` 對目標 DPI 太低 | 提高 `x_dimension` 或在儲存後放大影像 |
| 掃描器無法讀取空心條碼 | `filled_bars = False` 不被某些舊版掃描器支援 | 為了最高相容性，請使用預設的實心版本 |
| `ImportError: cannot import name 'BarcodeGenerator'` | Aspose.BarCode 未安裝或 .NET 執行環境不匹配 | 使用 `pip install aspose-barcode` 重新安裝，並確保已安裝 .NET Core 執行環境 |

## 重點回顧：我們涵蓋了什麼

* **如何產生條碼** 使用 Aspose.BarCode 於 Python
* **如何設定尺寸** 使用 `x_dimension.pixels`
* **如何變更填充** 透過 `filled_bars` 旗標（並簡要提及顏色自訂）
* 完整、可直接複製貼上的腳本，讓你能針對任何資料字串進行調整

## 接下來呢？（後續步驟與相關主題）

如果你覺得本指南有幫助，建議進一步探索：

* **產生 QR Code** (`EncodeTypes.QR`) – 非常適合 URL 與聯絡資訊。
* **在條碼下方加入文字說明** (`parameters.caption`) 以提供人類可讀的值。
* **匯出至其他格式** 如 SVG 或 PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`) – 適合向量圖形。
* **批次產生** – 迭代 CSV 中的商品 ID，一次產生整個條碼目錄。

上述所有主題皆與我們的次要關鍵字相關：*generate barcode with aspose* 與 *how to set dimensions*，適用於不同的輸出格式。

如果在操作過程中遇到任何問題，或想分享自己的變化，歡迎留言。祝你條碼製作愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何產生條碼 - 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)
- [如何在 Java 中使用 Aspose.BarCode 建立 code128 條碼影像](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [如何在 Java 中使用 Aspose.BarCode 為條碼影像上色](/barcode/english/java/image-manipulation/colorizing-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}