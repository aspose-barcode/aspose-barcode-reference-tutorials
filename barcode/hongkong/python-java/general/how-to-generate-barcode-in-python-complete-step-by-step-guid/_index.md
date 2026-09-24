---
category: general
date: 2026-08-12
description: 如何使用 Python 快速產生條碼。學習從資料建立條碼，並使用單一函式庫匯出條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode from data
- export barcode image
- Python barcode generation
- Aspose.BarCode tutorial
language: zh-hant
lastmod: 2026-08-12
og_description: 如何使用 Aspose.BarCode 在 Python 中生成條碼。請參考本指南，從資料建立條碼並將條碼圖像匯出為 PNG。
og_image_alt: Screenshot showing how to generate barcode with Python code
og_title: 如何在 Python 中生成條碼 – 快速、可靠指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  headline: How to generate barcode in Python – complete step‑by‑step guide
  type: TechArticle
- description: How to generate barcode quickly using Python. Learn to create barcode
    from data and export barcode image with a single library.
  name: How to generate barcode in Python – complete step‑by‑step guide
  steps:
  - name: 1. Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 2. Create barcode from data
    text: The first step is to **create barcode from data**. The `BarcodeGenerator`
      constructor takes the symbology and the raw string you want to encode.
  - name: 3. Adjust the X‑dimension (module width)
    text: The X‑dimension controls the width of each barcode module (the thin bar).
      Setting it to 4 pixels gives a clear, readable image without making the file
      too large.
  - name: 4. Export barcode image (filled style)
    text: Now you can **export barcode image** using the `save` method. The example
      saves a PNG file, but you can choose JPEG, BMP, or TIFF by changing the `BarCodeImageFormat`
      enum.
  - name: 5. Create a second generator for an outline‑only barcode
    text: If you need an outline version (empty bars), you must create a new generator
      because the `filled_bars` flag cannot be toggled after the image is saved.
  - name: 6. Apply the same X‑dimension setting
    text: When you create a second generator, you must repeat any visual settings
      you want to keep consistent.
  - name: 7. Disable filled bars for an outline barcode
    text: Setting `filled_bars` to `False` tells the renderer to draw only the outlines
      of each module, producing a lighter image that can be useful for design purposes.
  - name: 8. Export the outline barcode image
    text: Finally, **export barcode image** again, this time storing the outline version.
  - name: Next steps
    text: '* Explore other symbologies such as QR, Code‑128, or DataMatrix by swapping
      `EncodeTypes.Planet` with the desired value. * Integrate the generated PNG files
      into PDF reports using libraries like `ReportLab` or `PyPDF2`. * Experiment
      with dynamic X‑dimension values to adapt barcode size based on scre'
  type: HowTo
tags:
- barcode
- Python
- image export
title: 如何在 Python 中生成條碼 – 完整逐步指南
url: /zh-hant/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中產生條碼 – 完整逐步指南

如果您需要在 Python 應用程式中 **產生條碼**，本教學會展示您所需的完整程式碼。您將學會 **從資料建立條碼**、調整其外觀，並將 **匯出條碼影像** 為 PNG 檔案——全部只需不到十行程式碼。

產生條碼感覺好像與其他業務邏輯無關，但只要使用單一函式庫，就能將此流程直接整合到現有程式碼中。接下來的章節會示範完整可執行的範例、說明每一行程式碼的意義，並探討常見的變化，例如調整模組寬度或繪製僅輪廓的條碼。

## 使用 Aspose.BarCode 函式庫產生條碼

Aspose.BarCode 函式庫（透過 .NET）為多種條碼符號提供直觀的 API，本文使用的 Planet 條碼即是其中之一。開始之前，請先確定已安裝套件：

```bash
pip install aspose-barcode
```

> **專業提示：** 使用虛擬環境以避免與其他專案的版本衝突。

### 1. 匯入所需類別

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

這些匯入讓您可以存取產生器類別、條碼類型列舉，以及儲存結果時使用的影像格式列舉。

### 2. 從資料建立條碼

第一步是 **從資料建立條碼**。`BarcodeGenerator` 建構子接受條碼符號與您想編碼的原始字串。

```python
# Step 1: Create a barcode generator for the Planet symbology with data "123456"
barcode_filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

`EncodeTypes.Planet` 會選擇 Planet 條碼，而 `"123456"` 則是最終影像中顯示的資料。

### 3. 調整 X‑dimension（模組寬度）

X‑dimension 控制每個條碼模組（細條）的寬度。將其設為 4 像素即可產生清晰、易讀的影像，同時不會使檔案過大。

```python
# Step 2: Set the X‑dimension (module width) to 4 pixels
barcode_filled.parameters.barcode.x_dimension.pixels = 4
```

> **為什麼重要：** 較大的 X‑dimension 可提升低解析度印表機的掃描可靠性，而較小的數值則可減少網路使用的檔案大小。

### 4. 匯出條碼影像（實心樣式）

現在您可以使用 `save` 方法 **匯出條碼影像**。範例會儲存為 PNG 檔案，您也可以透過變更 `BarCodeImageFormat` 列舉改為 JPEG、BMP 或 TIFF。

```python
# Step 3: Save the barcode using the default filled‑bars style
barcode_filled.save("YOUR_DIRECTORY/PlanetFilled.png", BarCodeImageFormat.Png)
```

`PlanetFilled.png` 檔案包含完整實心的 Planet 條碼，可直接列印或嵌入 PDF 中。

### 5. 為僅輪廓條碼建立第二個產生器

若需要僅輪廓版本（空白條），必須建立新產生器，因為 `filled_bars` 旗標在影像儲存後無法再切換。

```python
# Step 4: Create a second generator for the same data to illustrate empty bars
barcode_empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

### 6. 套用相同的 X‑dimension 設定

建立第二個產生器時，必須再次設定所有想保持一致的視覺參數。

```python
# Step 5: Apply the same X‑dimension setting
barcode_empty.parameters.barcode.x_dimension.pixels = 4
```

### 7. 停用實心條以產生輪廓條碼

將 `filled_bars` 設為 `False` 會讓渲染器只繪製每個模組的輪廓，產生較輕的影像，適合設計用途。

```python
# Step 6: Disable filled bars to produce an outline‑only barcode
barcode_empty.parameters.barcode.filled_bars = False
```

### 8. 匯出輪廓條碼影像

最後，再次 **匯出條碼影像**，這次儲存為輪廓版本。

```python
# Step 7: Save the outline barcode
barcode_empty.save("YOUR_DIRECTORY/PlanetEmpty.png", BarCodeImageFormat.Png)
```

現在您擁有兩個 PNG 檔案：一個實心條碼 (`PlanetFilled.png`) 與一個僅輪廓條碼 (`PlanetEmpty.png`)。

## 以其他格式匯出條碼影像（可選）

`save` 方法支援多種格式。若要以 90% 品質匯出 JPEG：

```python
barcode_filled.save(
    "YOUR_DIRECTORY/PlanetFilled.jpg",
    BarCodeImageFormat.Jpeg,
    quality=90
)
```

若需要透明背景以供網頁使用，請選擇具 alpha 通道的 PNG：

```python
barcode_filled.parameters.background_color = None  # disables background fill
barcode_filled.save("YOUR_DIRECTORY/PlanetTransparent.png", BarCodeImageFormat.Png)
```

## 常見變化與邊緣情況

| 情境 | 需要的變更 | Code snippet |
|----------|---------------|--------------|
| **不同的符號系統**（例如 QR） | 使用不同的 `EncodeTypes` 值 | `BarcodeGenerator(EncodeTypes.QR, "https://example.com")` |
| **自訂前景色** | 設定 `fore_color` | `barcode_filled.parameters.barcode.fore_color = Color.Blue` |
| **較高解析度** | 透過 `image_width` 與 `image_height` 提升 DPI | `barcode_filled.parameters.image_width = 300; barcode_filled.parameters.image_height = 150` |
| **大型資料字串** | 確保資料長度符合符號系統規範 | Validate length before creating the generator |

> **注意：** 提供超過所選符號系統最大長度的資料會拋出執行時例外。請務必驗證字串長度或捕獲 `ArgumentException`。

## 完整、可執行的範例

以下是完整腳本，您可以直接複製貼上至名為 `generate_planet_barcode.py` 的檔案。請將 `YOUR_DIRECTORY` 調整為您機器上實際存在的資料夾路徑。

```python
# generate_planet_barcode.py
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def generate_barcodes(output_dir: str):
    # Filled‑bars barcode
    filled = BarcodeGenerator(EncodeTypes.Planet, "123456")
    filled.parameters.barcode.x_dimension.pixels = 4
    filled.save(f"{output_dir}/PlanetFilled.png", BarCodeImageFormat.Png)

    # Outline‑only barcode
    empty = BarcodeGenerator(EncodeTypes.Planet, "123456")
    empty.parameters.barcode.x_dimension.pixels = 4
    empty.parameters.barcode.filled_bars = False
    empty.save(f"{output_dir}/PlanetEmpty.png", BarCodeImageFormat.Png)

if __name__ == "__main__":
    import os
    output_path = "YOUR_DIRECTORY"
    os.makedirs(output_path, exist_ok=True)
    generate_barcodes(output_path)
    print("Barcodes generated successfully.")
```

執行此腳本會在指定目錄產生兩個 PNG 檔案。打開任意影像檢視器確認輸出，兩者皆應顯示編碼為 `123456` 的 Planet 條碼。

## 結論

您現在已了解如何使用 Aspose.BarCode 在 Python 中 **產生條碼**、**從資料建立條碼**，以及如何 **匯出條碼影像**（實心與輪廓兩種樣式）。相同的模式同樣適用於其他符號系統、影像格式與視覺自訂，為您在應用程式中加入任何條碼相關功能提供彈性基礎。

### 後續步驟

* 探索其他符號系統，如 QR、Code‑128 或 DataMatrix，只需將 `EncodeTypes.Planet` 替換為目標值。  
* 使用 `ReportLab` 或 `PyPDF2` 等函式庫，將產生的 PNG 檔案整合至 PDF 報告中。  
* 嘗試動態調整 X‑dimension，以因應螢幕解析度或印表機 DPI 的不同需求。

祝程式開發順利，隨時依需求調整範例以符合您的專案。

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，能在您掌握本篇示範的技巧後，進一步學習更多 API 功能與替代實作方式。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您在自己的專案中靈活運用。

- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [How to Generate Barcode Java – Complete Configuration Guide](/barcode/english/java/barcode-configuration/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}