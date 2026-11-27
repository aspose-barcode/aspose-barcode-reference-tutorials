---
category: general
date: 2026-11-27
description: 了解如何在 DataBar Omni‑Directional 條碼產生器中調整條碼條的高度。逐步程式碼示範將高度設定為 30 像素和 60
  像素。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: zh-hant
lastmod: 2026-11-27
og_description: 使用 Python 在 DataBar Omni‑Directional 條碼產生器中調整條碼條高度。遵循完整指南設定高度、X 方向尺寸，並儲存
  PNG 圖像。
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: 在 DataBar 全向產生器中調整條碼條高度
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: 如何在 DataBar Omni‑Directional 產生器中調整條碼條高度
url: /zh-hant/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 DataBar Omni‑Directional 產生器中調整條碼條高度

如果您需要 **調整條碼條高度** 於 DataBar Omni‑Directional 條碼，本指南將精確說明操作方式。您將看到一個完整、可執行的 Python 範例，將條高度從 30 px 變更為 60 px，同時保持 X‑dimension 與影像格式一致。

變更條碼的視覺尺寸是常見需求，尤其當條碼必須符合特定標籤尺寸或設計規範時。除了條高度外，您也可能想調整 **X‑dimension**（模組大小）或選擇不同的 **barcode image format**，例如 PNG 或 JPEG。

在本教學中您將：

* 安裝所需的函式庫（GroupDocs.Barcode for Python）
* 建立 DataBar Omni‑Directional 條碼產生器
* 使用 `XDimension` 設定模組大小
* 調整條高度屬性兩次
* 將產生的影像以所需的 **BarCodeImageFormat** 儲存

不需要先前的 GroupDocs API 經驗——只要具備基本的 Python 知識即可。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本
* `groupdocs.barcode` 套件（`pip install groupdocs-barcode`）  
* 對將儲存 PNG 檔案的資料夾具有寫入權限

如果您不熟悉 **DataBar Omni‑Directional barcode**，它會編碼 14 位數的 GTIN，且廣泛用於零售業，以支援任意方向的掃描。

## 步驟 1：設定 DataBar Omni‑Directional 條碼產生器

首先，匯入必要的類別，並以您想編碼的 GTIN 資料實例化產生器。

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*此處重要性說明：* `EncodeTypes.DatabarOmniDirectional` 常數告訴函式庫產生 Omni‑Directional 符號。資料字串包含 AI `(01)`，標示 GTIN‑14 值。

## 步驟 2：定義 X‑dimension（模組大小）

X‑dimension 控制最窄條的寬度。螢幕渲染的常見值為 **每個模組 2 px**。

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

使用一致的 **set XDimension** 可確保條碼在不同印表機與掃描器上正確縮放。

## 步驟 3：將條高度調整為 30 px 並儲存影像

現在我們變更條高度屬性。第一個使用的高度為 **30 px**，適用於小型標籤。

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

`BarCodeImageFormat.Png` 常數選擇 **barcode image format** PNG，能保留無損品質。

### 預期結果

檔案 `DatabarBarHeight30Pixels.png` 包含一個條條高度為 30 px 的 DataBar Omni‑Directional 條碼。以下為佔位預覽圖：

![DataBar barcode with 30 px bar height](images/databar_30px.png "DataBar barcode with 30 px bar height")

> **提示：** 若您在影像編輯器中開啟 PNG，會看到精確的條高度。窄條寬度為 2 px，如前所述。

## 步驟 4：將條高度變更為 60 px 以產生較高條碼

對於需要較大視覺佔位的應用——例如貨運標籤——您可以將條高度提升至 **60 px**。

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

僅變更 `BarHeight` 屬性；X‑dimension 與編碼保持不變，條碼仍可掃描。

## 步驟 5：儲存更新後的條碼影像

最後，將較高的條碼寫入第二個 PNG 檔案。

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### 預期結果

檔案 `DatabarBarHeight60Pixels.png` 顯示相同的編碼資料，但每條條高度已提升至 60 px。以下示意視覺差異：

![DataBar barcode with 60 px bar height](images/databar_60px.png "DataBar barcode with 60 px bar height")

## 完整、可執行範例

將所有步驟整合在一起，以下是完整腳本，您可直接複製貼上至名為 `adjust_barcode_height.py` 的檔案並執行。

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

執行腳本：

```bash
python adjust_barcode_height.py
```

您應該會在 `output` 資料夾中看到兩個 PNG 檔案，分別反映您設定的條高度。

## 常見問題與邊緣案例

| 問題 | 答案 |
|----------|--------|
| **我可以使用 JPEG 取代 PNG 嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。JPEG 為有損壓縮，若需精確掃描建議使用 PNG。 |
| **如果條高度不是 10 的倍數該怎麼辦？** | `BarHeight.Pixels` 屬性接受任何整數值。只需指定想要的像素數（例如 `45`）。 |
| **變更條高度會影響編碼資料嗎？** | 不會。僅改變視覺呈現，底層資料字串保持不變。 |
| **如何在儲存第一張影像後變更 X‑dimension？** | 您可在呼叫 `save()` 前的任何時刻修改 `gen.parameters.barcode.x_dimension.pixels`。此變更將套用於之後的影像。 |
| **產生器是執行緒安全的嗎？** | `BarcodeGenerator` 實例未保證執行緒安全。若同時產生條碼，請為每個執行緒建立獨立的實例。 |

## 結論

您現在已了解如何在 DataBar Omni‑Directional 條碼產生器中使用 Python **調整條碼條高度**。本教學涵蓋了建立產生器、設定 **X‑dimension**、修改 **barcode bar height** 屬性，以及以所需的 **barcode image format** 儲存影像。

接下來您可以嘗試其他高度、不同的模組大小，或切換至其他影像格式，如 JPEG 或 BMP。您亦可探索更多 **barcode generator python** 功能，例如加入可讀文字或變更配色方案。

祝程式開發順利，讓您的條碼保持清晰且尺寸完美！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何設定寬度與調整 GS1 DataBar Omni‑Directional 條碼的高度](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [在 Python 中建立 omni directional databar 與條碼影像](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net 條碼產生器 – 變更條碼高度](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}