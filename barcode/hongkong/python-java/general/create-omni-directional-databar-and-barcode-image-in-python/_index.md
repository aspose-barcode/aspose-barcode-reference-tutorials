---
category: general
date: 2026-08-12
description: 使用 Python 建立全方向 DataBar 條碼，並學習如何使用 Aspose.BarCode 在 Python 中產生條碼圖像。跟隨逐步指南，即可獲得完整解決方案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: zh-hant
lastmod: 2026-08-12
og_description: 使用 Python 建立全向 DataBar，並在數分鐘內產生條碼圖像。此教學提供完整且可執行的範例。
og_image_alt: example of create omni directional databar barcode image in Python
og_title: 建立全向資料條 – 完整 Python 指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: 在 Python 中產生全向 DataBar 與條碼圖像
url: /zh-hant/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中建立全向 DataBar 與條碼圖像

如果您需要在 Python 專案中 **建立全向 DataBar**，本指南將示範如何操作，同時說明如何使用 Aspose.BarCode 函式庫 **建立條碼圖像（Python）**。您將獲得一個可直接執行的腳本，產生兩個具有不同長寬比的 PNG 檔案。

產生符合全向規範的 DataBar 是零售與物流應用的常見需求。本教學涵蓋安裝、X‑dimension 設定、長寬比調整，以及最終圖像的儲存。無需外部服務，全部在本機執行。

## 您需要的條件

在開始之前，請確保您具備：

* 已在機器上安裝 Python 3.8 或更新版本。
* 可使用終端機或命令提示字元。
* 具有寫入條碼圖像儲存資料夾的權限。

唯一的第三方相依性是 **Aspose.BarCode for Python via .NET**，它內建支援全向 DataBar 類型。

## 步驟 1：安裝 Aspose.BarCode for Python

Aspose.BarCode 提供範例程式碼中使用的 `BarcodeGenerator` 類別。使用 `pip` 安裝套件：

```bash
pip install aspose-barcode
```

此套件已包含必要的 .NET 執行時綁定，無需額外安裝 .NET SDK。

## 步驟 2：匯入函式庫並建立產生器

腳本的第一行會為堆疊式全向 DataBar 建立產生器。範例資料使用 GTIN‑14 值 `(01)12345678901231`。

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Why this step matters*: `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` 常數告訴函式庫將值編碼為全向 DataBar，這是許多 POS 掃描器所要求的格式。

## 步驟 3：設定 X‑dimension（模組寬度）

X‑dimension 定義最小條模組的寬度。設定為 `2` 像素即可產生清晰、易讀的條碼，同時不會產生過大的檔案。

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Why this step matters*: 調整 X‑dimension 可在可讀性與圖像尺寸之間取得平衡。若 X‑dimension 設定過小，低解析度印表機的列印效果可能不佳。

## 步驟 4：設定長寬比並儲存第一張圖像

長寬比會影響 DataBar 相對於寬度的整體高度。設定為 `15` 可產生緊湊的視覺風格。

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Pro tip**: 使用 `pathlib.Path` 來建立輸出路徑，系統會自動建立缺失的目錄。

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## 步驟 5：變更長寬比以產生第二種視覺樣式並儲存另一張圖像

將長寬比改為 `30` 會產生較高的條碼，某些掃描硬體可能需要此尺寸。

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Why this step matters*: 不同零售商與掃描設備有各自的尺寸限制。一次腳本同時提供兩種長寬比，可在不重複程式碼的情況下產出所需樣式。

## 完整腳本 – 在 Python 中建立全向 DataBar 與條碼圖像

以下為完整、可執行的範例，結合前述所有步驟。將其儲存為 `generate_databar.py`，並以 `python generate_databar.py` 執行。

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### 預期輸出

執行腳本後會產生以下檔案：

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

兩張圖像皆為可被標準零售設備掃描的有效全向 DataBar。

![在 Python 中建立全向 DataBar 條碼圖像範例](example_databar.png "在 Python 中建立全向 DataBar 條碼圖像")

*上圖僅為示意圖，展示兩個已儲存的 PNG 檔案。*

## 常見問題處理

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| `ImportError: No module named aspose` | Aspose.BarCode 未安裝或安裝於不同的環境。 | 啟動正確的虛擬環境，並執行 `pip install aspose-barcode`。 |
| `PermissionError` when saving | 腳本缺乏目標資料夾的寫入權限。 | 選擇您擁有寫入權限的目錄，或以適當的權限執行腳本。 |
| Barcode does not scan | X‑dimension 太低或長寬比與掃描器不相容。 | 將 `x_dimension.pixels` 提升至 3 或 4，並測試不同的 `aspect_ratio`（例如 20、25）。 |
| Missing .NET runtime | Aspose.BarCode 依賴 Windows/Linux 上的 .NET 執行時。 | 從 Microsoft 官方網站安裝最新的 .NET 執行時；套件文件提供平台特定的指引。 |

## 擴充範例

您可以將腳本改寫為產生其他 DataBar 變體（例如 `DATABAR_STACKED`、`DATABAR_EXPANDED`），只需相應替換 `EncodeTypes` 常數：

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

若需將條碼嵌入 PDF，Aspose.PDF for Python 可直接匯入 PNG 檔，或使用 `save` 方法搭配 `BarCodeImageFormat.Pdf`。

## 結論

本教學示範了如何使用 Aspose.BarCode **建立全向 DataBar** 以及 **建立條碼圖像（Python）**。您現在擁有一個完整且可重現的腳本，能產生兩個不同長寬比的 PNG 檔案，處理常見問題，且可延伸至其他條碼格式。

接下來，您可以探索產生 QR Code、將條碼加入 PDF 發票，或為大型商品目錄自動化批次處理。上述主題皆以本範例中的 `BarcodeGenerator` 模式為基礎。祝開發順利！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南技術緊密相關的主題，每篇都提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [產生條碼圖像 – GS1 Coupon UPC-A DataBar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [建立 DotCode 條碼圖像 – 行與列（Aspose.BarCode）](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何在 Java 中建立條碼圖像並渲染](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}