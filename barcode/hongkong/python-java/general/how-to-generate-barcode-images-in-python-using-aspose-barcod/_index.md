---
category: general
date: 2026-11-23
description: 如何使用 Aspose.BarCode 在 Python 中生成條碼圖像。學習建立 Planet 條碼、調整 X 尺寸，並輸出空條碼 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: zh-hant
lastmod: 2026-11-23
og_description: 如何在 Python 中使用 Aspose.BarCode 產生條碼。本教學將帶領您建立帶有空白條的 Planet 條碼，並將其儲存為
  PNG 圖像。
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: 如何在 Python 中生成條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: 如何在 Python 中使用 Aspose.BarCode 生成條碼圖像
url: /zh-hant/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.BarCode 產生條碼影像

在 Python 中產生條碼影像非常簡單，只要使用 Aspose.BarCode 函式庫。本教學將一步步說明如何使用 Planet 符號產生條碼、調整 X‑dimension，並產出空條樣式的 PNG 檔案。

您將看到一個完整、可直接執行的腳本，您可以將其複製到自己的專案中。教學同時也涵蓋常見的變化情境，例如切換不同的符號或輸出格式，讓您能依需求自行調整解決方案。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* 可使用的終端機或命令提示字元。
* 有效的 Aspose.BarCode for Python 授權（免費評估版可用於測試）。
* 基本的 Python 套件管理知識（`pip`）。

## 步驟 1：安裝 Aspose.BarCode 套件

Aspose 透過 PyPI 發佈其 Python API。使用標準套件管理員安裝：

```bash
pip install asposebarcode
```

> **小技巧：** 使用虛擬環境（`python -m venv venv`）可將相依性與其他專案隔離。

## 步驟 2：匯入所需的 Aspose.BarCode 類別

匯入語句會載入產生器、符號列舉以及影像格式列舉。

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` 用於建立條碼物件。
* `EncodeTypes` 列舉所有支援的符號——此處我們使用 `Planet`。
* `BarCodeImageFormat` 定義輸出檔案類型（PNG、JPEG 等）。

## 步驟 3：為 Planet 符號建立條碼產生器

以欲使用的符號與要編碼的資料建立產生器實例。

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`Planet` 符號會產生圓形圖案，適合用於裝飾或品牌化目的。

## 步驟 4：調整 X‑dimension（模組寬度）

X‑dimension 控制最小條（模組）的寬度。設定為 4 像素即可得到清晰的高解析度影像。

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

在需要條碼在列印或螢幕顯示時具備良好縮放性的情況下，調整 X‑dimension 非常有用。

## 步驟 5：停用實心條以產生空條樣式

空條樣式的條碼只顯示條的輪廓，適合設計感較強的應用。

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

當 `filled_bars` 為 `False` 時，產生器會繪製空心形狀而非實心。

## 步驟 6：將條碼影像儲存為 PNG 檔案

最後，將條碼寫入磁碟。PNG 為無損且廣受支援的格式。

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

`save` 方法會在目標目錄不存在時自動建立。

## 完整範例 – 可直接執行的腳本

將上述所有步驟組合起來，即可得到一個自包含的程式，您可以立即執行：

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**預期輸出：** 執行腳本後，`output/PlanetEmptyBars.png` 會產生一張 200 × 200 像素的 Planet 條碼影像，條桿為空心。使用任何影像檢視器開啟，即可看到圓形圖案與內部編碼的數值。

## 常見變化與例外情況

### 切換至其他符號

若需要 QR code、Code 128 或其他格式，只需將 `EncodeTypes.Planet` 替換為相應的列舉值：

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### 變更影像格式

Aspose.BarCode 支援 PNG、JPEG、BMP 與 TIFF。若要產生 JPEG：

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### 在不失真的情況下調整影像尺寸

您可以透過 `resolution` 屬性或同時調整 X‑dimension 與 Y‑dimension 來控制整體影像大小。若要列印高解析度圖像，請設定較高的 DPI：

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### 處理過長的資料字串

Planet 符號的資料容量有限（最多 8 個字元）。若嘗試編碼更長的字串，產生器會拋出例外。請在建立條碼前先驗證長度：

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## 小技巧與常見陷阱

* **授權啟用：** 在正式環境使用時，請於腳本開頭使用 `asposebarcode.License().set_license("Aspose.Total.lic")` 載入授權檔。若省略此步驟，輸出影像會帶有浮水印。
* **執行緒安全性：** `BarcodeGenerator` 實例不是執行緒安全的。若在平行產生條碼，請為每個執行緒建立獨立實例。
* **效能最佳化：** 透過 `barcode.value = "new data"` 重新設定值，比每次重新建立物件更快。
* **檔案路徑：** 使用 `os.path.join` 生成跨平台的路徑，特別是在 Linux 或 macOS 部署時。

## 結論

現在您已掌握如何在 Python 中使用 Aspose.BarCode 產生條碼影像、調整 X‑dimension、產生空條樣式，並將結果儲存為 PNG。完整範例可依需求套用至其他符號、輸出格式與視覺樣式，為您的應用程式提供彈性且強大的條碼功能基礎。

**後續步驟：** 嘗試不同編碼方式，探索 *Python barcode generation*、*barcode image PNG* 壓縮設定，或將產生的影像整合至 Flask 或 FastAPI 網路服務中。祝您開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索替代實作方式。

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}