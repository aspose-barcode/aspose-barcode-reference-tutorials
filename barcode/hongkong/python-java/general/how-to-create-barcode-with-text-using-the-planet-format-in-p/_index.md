---
category: general
date: 2026-11-27
description: 學習如何在 Python 中建立帶文字的條碼並產生 Planet 條碼——一步一步的教學，提供高解析度 PNG 輸出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: zh-hant
lastmod: 2026-11-27
og_description: 在 Python 中建立帶文字的條碼並產生星球條碼。跟隨此完整指南輸出高解析度 PNG。
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: 在 Python 中建立帶文字的條碼 – 輕鬆生成 Planet 條碼
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: 如何在 Python 中使用 Planet 格式建立帶文字的條碼
url: /zh-hant/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Planet 格式建立帶文字的條碼

如果您需要為郵件系統 **create barcode with text**，本教學將完整示範操作步驟。您將看到一個簡潔的端對端範例，產生 Planet 條碼、調整解析度，並將結果儲存為 PNG 圖片。

產生條碼是物流、庫存與票券應用的常見需求。在本指南中，您不僅會學會 **how to generate barcode** 檔案，還會了解每個設定步驟的原因，以及如何避免常見的陷阱。

## 您將學會

* 使用自訂文字設定 Planet 條碼產生器  
* 調整 X‑dimension 以提升影像清晰度  
* 將條碼儲存為 PNG 檔，可直接列印或於網頁顯示  
* 將範例延伸至其他條碼類型或輸出格式  

**先備條件**

* Python 3.8 或更新版本  
* `aspose-barcode` 套件（或任何提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的相容函式庫）  
* 基本的 Python 腳本撰寫經驗  

您可以使用以下指令安裝所需套件：

```bash
pip install aspose-barcode
```

---

## 步驟 1：建立帶文字的條碼 – 初始化產生器

首先必須建立一個 `BarcodeGenerator` 實例，告訴程式使用哪種符號系統以及要編碼的文字。對於 Planet 條碼而言，`EncodeTypes.Planet` 列舉值會讓函式庫遵循 USPS Planet 規範。

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**為什麼這很重要：**  
`BarcodeGenerator` 物件封裝了條碼的所有設定。於建構時即提供文字，可確保編碼值在後續過程中保持不變，避免因意外變更而產生不匹配。

---

## 步驟 2：調整設定 – 產生更高解析度的條碼

低解析度的條碼在標籤印表機上列印時會顯得模糊。X‑dimension（模組寬度）決定每條單位條的大小。將其設為 4 像素即可產生清晰的高解析度影像，適用於大多數現代印表機。

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**說明：**  
* `gen.parameters.barcode.x_dimension.pixels` 直接對應單一模組的實體寬度。  
* 設為 **4** 表示每條寬度為四個像素，約等於 300 dpi 時的 0.127 mm，符合 USPS Planet 條碼的建議範圍。  

**小技巧：** 若需要不同的 DPI，請依比例計算像素寬度（例如 150 dpi 時使用 2 像素，600 dpi 時使用 8 像素）。

---

## 步驟 3：儲存影像 – 產生 Planet 條碼 PNG

完成產生器設定後，即可將條碼渲染為影像檔。PNG 為無損格式，可確保模組圖樣完整保留。

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**結果：**  
執行腳本後會產生名為 `PostalPlanetBarHeightNone.png` 的檔案，內含編碼字串「123456」的 Planet 條碼。影像尺寸大約為 200 × 100 像素，實際大小取決於您設定的 X‑dimension。

---

## 可選：目視驗證條碼

您可以使用任何圖像檢視器快速開啟產生的 PNG，確認條碼是否清晰且文字顯示在圖樣下方。

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

若影像看起來模糊，請回到 **步驟 2**，提升 X‑dimension 直至條紋明顯。

---

## 常見變化與邊緣情況

| 情境 | 調整方式 |
|-----------|------------|
| **不同文字長度** | Planet 條碼支援最多 12 位數字字符。超過此長度會拋出例外。 |
| **其他輸出格式** | 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp` 以因應不同需求。 |
| **自訂前景/背景顏色** | 使用 `gen.parameters.barcode.barcode_color = Color.Blue` 以及 `gen.parameters.barcode.back_color = Color.White`。 |
| **不顯示可讀文字** | 設定 `gen.parameters.barcode.hide_code_text = True` 以產生不含底部說明的條碼。 |
| **批次產生** | 迭代字串清單，為每個字串建立新的 `BarcodeGenerator`，並以唯一檔名儲存。 |

透過這些變化，您可以 **generate planet barcode** 檔案，滿足各種商業需求。

---

## 完整腳本 – 可直接執行

以下提供完整、獨立的腳本，您可以直接複製、貼上並執行。內含所有匯入、錯誤處理與註解。

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**腳本說明**

* `create_planet_barcode` 函式封裝了三個核心步驟，提升程式碼可重用性。  
* 輸入驗證確保符合 Planet 規範（僅限數字，最多 12 位）。  
* 函式會自動建立輸出資料夾，免除手動管理目錄的麻煩。  
* 產生後，腳本使用 Pillow (`PIL`) 開啟影像，即時驗證結果。

---

## 結論

現在您已掌握如何 **create barcode with text** 以及 **generate planet barcode** 檔案於 Python 中。指南涵蓋了初始化、解析度調校與檔案輸出，並提供可選的客製化與常見邊緣情況說明。

接下來您可以：

* 將 `EncodeTypes.Planet` 替換為其他符號系統（例如 `EncodeTypes.Code128`），套用相同流程。  
* 將此函式整合至 Web 服務，依需求即時回傳條碼影像。  
* 嘗試批次處理，為大量郵寄產生上千張條碼。

歡迎依專案需求調整腳本，並在留言區分享您的成果。祝開發順利！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步深化您對 API 功能的掌握，並探索其他實作方式：

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}