---
category: general
date: 2026-08-12
description: 快速在 Python 中配置 Databar 條碼佈局。學習設定欄位、列，並使用條碼產生器函式庫儲存圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: zh-hant
lastmod: 2026-08-12
og_description: 在 Python 中配置 Databar 條碼佈局，以控制列、行和圖像輸出。按照本指南即可獲得可直接執行的解決方案。
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: 在 Python 中設定 Databar 條碼佈局 – 完整教學
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: 在 Python 中設定 Databar 條碼版面 – 步驟指南
url: /zh-hant/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中配置 Databar 條碼佈局 – 步驟指南

如果您需要 **在 Python 中配置 Databar 條碼佈局**，本指南將帶您完整操作。您將了解如何為 Databar Expanded Stacked 條碼設定欄位（columns）或列（rows）的數量，以及如何僅透過一次呼叫條碼產生器函式庫即保存產生的圖像。

在窄小的包裝、收據或行動裝置螢幕上嵌入條碼時，控制佈局尤為重要。以下各節將說明必要的匯入、兩種佈局選項（欄位與列），以及保存乾淨 PNG 圖像的最佳實踐。

## 您需要的環境

在開始之前，請確保您已具備：

* Python 3.8 或更新版本
* 已安裝 `aspose.barcode`（或任何相容的條碼產生套件）  
  ```bash
  pip install aspose-barcode
  ```
* 具寫入權限的資料夾，用於存放 PNG 檔案

不需要額外的外部工具——函式庫會在內部處理渲染、縮放與圖像編碼。

## 如何在 Python 中配置 Databar 條碼佈局

解決方案的核心是 `BarcodeGenerator` 類別。它接受一個 `EncodeTypes` 列舉，用以指定條碼符號系統——此例為 `EncodeTypes.DatabarExpandedStacked`。建立產生器後，您可以透過設定 `data_bar` 參數物件的 `columns` 或 `rows` 屬性來調整佈局。

### 步驟 1：匯入必要的類別

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

上述匯入讓您可以存取產生器、Databar 類型的列舉，以及 PNG 圖像格式常數。

### 步驟 2：為 Databar Expanded Stacked 建立條碼產生器

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*為什麼要這麼做？*  
`EncodeTypes.DatabarExpandedStacked` 告訴函式庫產生 **Databar Expanded Stacked** 符號，該符號可容納較長的數字字串，同時保持緊湊的佔位空間。第二個參數是要編碼的資料；只要符合 Databar 規範的字串皆可。

### 步驟 3：設定欄位數量（水平佈局）

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** 是此操作的關鍵語句。當您增加欄位數時，條碼會水平展開，適合寬標籤使用。函式庫會自動重新計算模組寬度，以維持整體尺寸的一致性。

#### 專業提示
Databar Expanded Stacked 的最大欄位數為 8。設定超過上限的值會被限制為最大值，但建議事先驗證輸入。

### 步驟 4：使用欄位佈局保存條碼圖像

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** 為將渲染好的條碼寫入磁碟的動作。PNG 為無損格式，可保留掃描所需的銳利邊緣。

### 步驟 5：為相同條碼類型建立第二個產生器（列佈局）

如果您偏好垂直堆疊，則使用列（rows）而非欄位（columns）。以下程式碼重新使用相同的資料值，但會建立全新的 `BarcodeGenerator` 實例，以避免欄位與列設定混用。

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### 步驟 6：設定列數量（垂直佈局）

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** 會將條碼模組垂直排列。三列佈局會降低每個堆疊的高度，使條碼適用於窄收據或行動螢幕。

#### 邊緣情況
若將 `rows` 設為 1，函式庫會產生單列 Databar（等同於標準 Databar）。小於 1 的值會被忽略，並重設為預設值（1 列）。

### 步驟 7：使用列佈局保存條碼圖像

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

同樣，我們 **save barcode image**，使用 PNG 以保持輸出清晰。

## 完整可執行範例

將所有片段組合起來，即可得到一個可直接放入任何 Python 專案的自包含腳本。

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**預期輸出**

執行腳本後會產生兩個 PNG 檔案：

* `output/ExpandedCols4.png` – 以四欄方式展開的條碼  
* `output/ExpandedRows3.png` – 以三列方式壓縮的條碼  

兩張圖皆可在任何圖像檢視器中開啟，或直接匯入 PDF 發票、標籤範本或網頁。

## 常見問題與疑難排解

| 問題 | 解答 |
|----------|--------|
| *條碼看起來模糊怎麼辦？* | 在呼叫 `save` 前，透過設定 `barcode_generator.parameters.image_width` 與 `image_height` 來提升圖像解析度。 |
| *可以使用其他圖像格式嗎？* | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif` 即可。 |
| *資料長度有上限嗎？* | Databar Expanded Stacked 最多支援 74 個數字字元。超過上限會拋出 `ArgumentException`。 |
| *如何變更前景顏色？* | 使用 `barcode_generator.parameters.barcode.color = Color.Blue`（需匯入 `System.Drawing.Color`）。 |
| *可以同時使用欄位與列嗎？* | 不行。API 將欄位與列視為互斥的佈局模式，每個條碼實例只能選擇其一。 |

## 後續步驟

既然您已能 **配置 Databar 條碼佈局**，不妨進一步探索以下相關主題：

* **加入文字說明** – 使用 `barcode_generator.parameters.barcode.code_text` 在圖像下方顯示編碼值。  
* **將條碼嵌入 PDF** – 結合產生的 PNG 與 `aspose.pdf`，建立可列印的文件。  
* **動態尺寸調整** – 在執行時根據標籤尺寸計算最佳的欄位或列數。  
* **批次處理** – 迭代 CSV 中的產品代碼，自動產生條碼圖像庫。

嘗試不同的欄位與列設定，觀察它們對目標裝置掃描可靠性的影響。測試越多，您對條碼大小、可讀性與空間限制之間的取捨就越了解。

---

*祝編程愉快！若本教學對您有幫助，請與同事分享，或留下您在佈局上遇到的挑戰評論。*


## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，能在本篇示範的技巧之上，協助您掌握更多 API 功能並探索其他實作方式：

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}