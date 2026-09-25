---
category: general
date: 2026-08-03
description: 快速使用本指南建立條碼 PNG。了解如何使用 Aspose.BarCode 產生條碼圖像以及產生 Planet 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode image
- generate planet barcode
- Python barcode generation
- Aspose.BarCode tutorial
language: zh-hant
lastmod: 2026-08-03
og_description: 即時產生條碼 PNG。本教學示範如何產生條碼圖像以及使用 Aspose.BarCode 產生 Planet 條碼。
og_image_alt: Example of a Planet barcode saved as a PNG image
og_title: 在 Python 中建立條碼 PNG – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  headline: Create barcode PNG in Python – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG quickly with this guide. Learn how to generate barcode
    image using Aspose.BarCode and generate planet barcode.
  name: Create barcode PNG in Python – step‑by‑step guide
  steps:
  - name: 1. Install the Aspose.BarCode package
    text: 'Aspose provides a pure‑Python package that wraps its .NET core engine.
      Install it with `pip`:'
  - name: 2. Import required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: 3. Create a barcode generator for the Planet symbology
    text: '```python # Step 1: Create a barcode generator for the Planet symbology
      with the desired data barcode_generator = BarcodeGenerator(EncodeTypes.Planet,
      "123456") ```'
  - name: 4. Set the X dimension (module width) in pixels
    text: '```python # Step 2: Set the X dimension (module width) in pixels barcode_generator.parameters.barcode.x_dimension.pixels
      = 4 ```'
  - name: 5. Define a manual bar height in pixels
    text: '```python # Step 3: Define a manual bar height in pixels barcode_generator.parameters.barcode.bar_height.pixels
      = 100 ```'
  - name: 6. Save the generated barcode as a PNG image
    text: '```python # Step 4: Save the generated barcode as a PNG image output_path
      = "output/PlanetBarHeight100.png" barcode_generator.save(output_path, BarCodeImageFormat.Png)
      print(f"Barcode saved to {output_path}") ```'
  - name: 7. Verify the output (optional)
    text: '```python from PIL import Image'
  - name: ' ## What Should You Learn Next?


      The following tutorials cover closely related topics that build on the techniques
      demonstrated in this guide. Each resource includes complete working code examples
      with step-by-step explanations to help you master additional API features and
      explore alternative implementation approaches in your own projects.

      - [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
      - [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
      - [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

      {{< /blocks/products/pf/tutorial-page-section >}}'
    text: '{{< /blocks/products/pf/main-container >}} {{< /blocks/products/pf/main-wrap-class
      >}} {{< blocks/products/products-backtop-button >}}'
  type: HowTo
tags:
- barcode
- PNG
- Python
- Aspose
title: 在 Python 中建立條碼 PNG – 步驟教學
url: /zh-hant/python-java/general/create-barcode-png-in-python-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中建立條碼 PNG – 步驟指南

如果你需要從 Python 應用程式 **建立條碼 PNG** 檔案，本教學會精確說明操作步驟。我們將示範如何使用 Aspose.BarCode **產生條碼影像**，並特別 **產生自訂尺寸的 Planet 條碼**。

你將學會如何安裝函式庫、設定 Planet 符號、調整尺寸參數，並將結果儲存為高品質 PNG。此指南假設具備基本的 Python 知識，且使用較新版的 Python 3（3.8 或更新）。不需要先前的條碼標準經驗。

---

## 使用 Aspose.BarCode 建立條碼 PNG 的方法

本節包含建立 **條碼 PNG** 所需的核心步驟。每個步驟都附有程式碼片段、說明其重要性，以及可立即套用的實用技巧。

### 1. 安裝 Aspose.BarCode 套件

Aspose 提供純 Python 套件，封裝其 .NET 核心引擎。使用 `pip` 安裝：

```bash
pip install aspose-barcode
```

*此步驟的重要性：* 此套件提供在範例中使用的 `BarcodeGenerator` 類別。全域安裝可確保直譯器在執行時能找到組件。

### 2. 匯入所需類別

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

*提示：* 只匯入必要的符號；這樣可保持命名空間整潔，並加快模組載入速度。

### 3. 為 Planet 符號建立條碼產生器

```python
# Step 1: Create a barcode generator for the Planet symbology with the desired data
barcode_generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

*此步驟的重要性：* `EncodeTypes.Planet` 告訴引擎使用 Planet 條碼標準，第二個參數則提供要編碼的資料。變更符號（例如 `EncodeTypes.Code128`）會產生完全不同的視覺圖樣。

### 4. 設定 X 維度（模組寬度）像素值

```python
# Step 2: Set the X dimension (module width) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 4
```

*說明：* X 維度控制窄條的寬度。設定為 4 像素可產生適度密集的條碼，且在大多數裝置上仍可掃描。

### 5. 定義手動條碼高度（像素）

```python
# Step 3: Define a manual bar height in pixels
barcode_generator.parameters.barcode.bar_height.pixels = 100
```

*調整原因：* 某些零售印表機需要較高的條碼以確保掃描可靠性。預設高度通常為 50 px；將其提升至 100 px 可提升可讀性，同時不會大幅增加檔案大小。

### 6. 將產生的條碼儲存為 PNG 影像

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "output/PlanetBarHeight100.png"
barcode_generator.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

*結果：* 會在 `output` 資料夾產生名為 **PlanetBarHeight100.png** 的 PNG 檔案。PNG 為無損格式，適合列印及嵌入網頁。

### 7. 驗證輸出（可選）

```python
from PIL import Image

with Image.open(output_path) as img:
    img.show()   # Opens the default image viewer
    print(f"Image size: {img.size} (width, height)")
```

*提示：* 檢視影像可確認尺寸是否符合設定參數。若條碼顯示扭曲，請重新檢查 X 維度或條碼高度設定。

---

## 以 PNG 格式產生條碼影像（替代設定）

如果需要其他影像格式，或稍後想將條碼嵌入 PDF，可變更 `BarCodeImageFormat` 列舉：

```python
# Save as JPEG instead of PNG
barcode_generator.save("output/PlanetBar.jpeg", BarCodeImageFormat.Jpeg)

# Save as BMP for legacy Windows applications
barcode_generator.save("output/PlanetBar.bmp", BarCodeImageFormat.Bmp)
```

*此步驟的重要性：* PNG 保留每個像素，對高對比度條碼至關重要。JPEG 會產生壓縮雜訊，可能影響掃描，而 BMP 則提供與舊工具的相容性。

---

## 使用自訂顏色產生 Planet 條碼（進階）

除了尺寸外，還可以自訂前景與背景顏色：

```python
from aspose.barcode import Color

# Set foreground to dark blue and background to light gray
barcode_generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
barcode_generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

barcode_generator.save("output/PlanetColored.png", BarCodeImageFormat.Png)
```

*實用提示：* 高對比度的顏色組合（深色在淺色上）可提升掃描器的可靠性。避免前景與背景使用相近色調。

---

## 常見陷阱與避免方法

| 症狀 | 原因 | 解決方案 |
|---------|-------|-----|
| 條碼無法掃描 | X 維度過小 (≤ 2 px) | 將 `x_dimension.pixels` 提升至至少 3 px |
| 圖像模糊 | PNG 以低 DPI 儲存 | 使用 `barcode_generator.save(..., BarCodeImageFormat.Png, 300)` 指定 300 DPI（若支援） |
| 例外 `ImportError` | 未安裝 Aspose.BarCode | 在與腳本相同的環境執行 `pip install aspose-barcode` |
| 符號錯誤 | 使用 `EncodeTypes.Code128` 而非 `EncodeTypes.Planet` | 建立產生器時改為 `EncodeTypes.Planet` |

---

## 完整解決方案回顧

以下為完整、可執行的腳本，從頭到尾 **建立條碼 PNG**：

```python
# full_example.py
# -------------------------------------------------
# Demonstrates how to generate a Planet barcode PNG
# -------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create generator with Planet symbology
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")

# 2️⃣ Configure dimensions
generator.parameters.barcode.x_dimension.pixels = 4          # module width
generator.parameters.barcode.bar_height.pixels = 100        # bar height

# 3️⃣ Optional: set colors (uncomment to use)
# from aspose.barcode import Color
# generator.parameters.barcode.barcode_color = Color(0, 0, 139)   # DarkBlue
# generator.parameters.barcode.back_color = Color(211, 211, 211) # LightGray

# 4️⃣ Save as PNG
png_path = os.path.join(output_dir, "PlanetBarHeight100.png")
generator.save(png_path, BarCodeImageFormat.Png)

print(f"✅ Barcode PNG created at: {png_path}")

# 5️⃣ Verify (opens the image on most OSes)
try:
    from PIL import Image
    with Image.open(png_path) as img:
        img.show()
        print(f"Image size: {img.size}")
except Exception as e:
    print(f"Verification step skipped: {e}")
```

執行此腳本會產生清晰的 **Planet 條碼 PNG**，可嵌入 HTML、附加於電子郵件，或列印於產品標籤上。

---

## 往後步驟與相關主題

* **Integrate with Flask or Django** – 直接從 Web 端點提供產生的 PNG。  
* **Batch generation** – 針對產品 ID 清單迴圈，建立包含條碼 PNG 檔案的資料夾。  
* **Combine with PDF generation** – 使用 `aspose-pdf` 將 PNG 放入發票或運送標籤。  
* **Explore other symbologies** – 將 `EncodeTypes.Planet` 替換為 `EncodeTypes.QR`、`EncodeTypes.DataMatrix` 或 `EncodeTypes.Code128`，以符合不同業務需求。

掌握上述步驟後，你現在已了解如何以程式方式 **產生條碼影像**，且可將此模式擴展至 Aspose.BarCode 支援的任何條碼標準。

###

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}