---
category: general
date: 2026-10-15
description: 使用 Aspose.Barcode for Python 從字串建立條碼。學習如何產生條碼、設定尺寸，並在數分鐘內儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- how to generate barcode
- barcode generator example
- generate postal barcode
- aspose barcode python
language: zh-hant
lastmod: 2026-10-15
og_description: 使用 Aspose.Barcode for Python 從字串建立條碼。本教學逐步說明如何產生郵政條碼並將其儲存為 PNG。
og_image_alt: Screenshot of a generated postal barcode saved as PNG
og_title: 在 Python 中從字串建立條碼 – Aspose 指南
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string with Aspose.Barcode for Python. Learn how
    to generate barcode, set dimensions, and save as PNG in minutes.
  headline: How to create barcode from string in Python using Aspose
  type: TechArticle
tags:
- barcode
- python
- Aspose
title: 如何使用 Aspose 在 Python 中從字串建立條碼
url: /zh-hant/python-java/general/how-to-create-barcode-from-string-in-python-using-aspose/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose 從字串建立條碼

如果您需要快速 **create barcode from string**，Aspose.Barcode for Python 讓這變得簡單。在本指南中，您將會看到如何 **how to generate barcode** 圖片、調整 X‑dimension，並將結果儲存為 PNG 檔案——只需幾行程式碼。

您還會獲得完整的 **barcode generator example**，可以直接複製貼上到自己的專案中。無需外部腳本或複雜設定，且本教學適用於目前的 Aspose.Barcode 23.10 版本。

## 前置條件

- 已在機器上安裝 Python 3.8+  
- 具備有效的 Aspose.Barcode for Python 授權（免費試用可用於評估）  
- 在虛擬環境中執行 `pip install aspose-barcode`

上述項目可確保程式碼在執行時不會出現匯入錯誤。

## 使用 Aspose.Barcode (Python) 從字串建立條碼

第一步是使用欲使用的條碼類型實例化 `BarcodeGenerator`——本例中為 **Planet** 郵政條碼，並傳入您想要編碼的字串。

```python
# Step 1: Import the required classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a barcode generator for the Planet symbology with data "123456"
# This is the core of the "create barcode from string" operation.
generator = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**為什麼這很重要：**  
`EncodeTypes.Planet` 告訴 Aspose 使用 Planet 郵政條碼規格，該規格適用於多國的郵件分揀。第二個參數 (`"123456"`) 為將被編碼成條碼的原始字串。變更此值即可 **create barcode from string** 任意郵遞區號或追蹤號碼。

## 如何以自訂尺寸產生條碼

郵政條碼的模組寬度（X‑dimension）常需符合列印規格。Aspose 允許您以像素設定寬度，同時自動計算高度。

```python
# Step 3: Set the X dimension (module width) in pixels; height is calculated automatically
generator.parameters.barcode.x_dimension.pixels = 4
```

**為什麼可能需要調整：**  
較大的 X‑dimension 會使條紋變粗，提升低解析度印表機的掃描可靠性。相反地，較小的數值可減少網頁使用的影像大小。此行示範了 **how to generate barcode** 圖片以符合精確尺寸需求。

## 儲存條碼影像

在設定完生成器後，只需呼叫 `save`。此方法接受輸出路徑與您想要的影像格式。

```python
# Step 4: Save the generated barcode as a PNG image
output_path = "YOUR_DIRECTORY/PostalPlanetAuto.png"
generator.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_path}")
```

**您將得到：**  
一個名為 `PostalPlanetAuto.png` 的 PNG 檔，內含編碼為 `"123456"` 的 Planet 條碼。您可使用任何影像檢視器開啟此檔案以驗證結果。

![已產生的郵政條碼 PNG 截圖](barcode_example.png){.align-center alt="已產生的郵政條碼 PNG 截圖"}

## 完整條碼生成器範例

以下為完整、可直接執行的腳本，包含上述所有步驟。將其複製到名為 `generate_postal_barcode.py` 的檔案中，然後執行 `python generate_postal_barcode.py`。

```python
# generate_postal_barcode.py
# -------------------------------------------------
# Complete example that shows how to create barcode from string,
# set custom dimensions, and save the result as PNG using Aspose.Barcode for Python.
# -------------------------------------------------

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_postal_barcode(data: str, output_file: str, x_dim_pixels: int = 4):
    """
    Generates a Planet postal barcode from the supplied string.

    Args:
        data: The raw string to encode (e.g., "123456").
        output_file: Full path where the PNG image will be saved.
        x_dim_pixels: Desired X dimension in pixels (default = 4).

    Returns:
        None. The PNG file is written to disk.
    """
    # Validate data length for Planet symbology (6‑digit numeric is standard)
    if not data.isdigit() or len(data) != 6:
        raise ValueError("Planet barcode requires a 6‑digit numeric string.")

    # Create the generator (this is the core of create barcode from string)
    generator = BarcodeGenerator(EncodeTypes.Planet, data)

    # Adjust module width; height is calculated automatically
    generator.parameters.barcode.x_dimension.pixels = x_dim_pixels

    # Save as PNG
    generator.save(output_file, BarCodeImageFormat.PNG)
    print(f"Barcode saved to {output_file}")

if __name__ == "__main__":
    # Example usage – you can change the values to test other strings
    try:
        create_postal_barcode(
            data="123456",
            output_file="PostalPlanetAuto.png",
            x_dim_pixels=4
        )
    except Exception as e:
        print(f"Error generating barcode: {e}")
```

### 預期輸出

執行腳本會產生：

```
Barcode saved to PostalPlanetAuto.png
```

… 並建立一個 `PostalPlanetAuto.png` 檔案，其外觀如下：

![已產生的 Planet 條碼 PNG 截圖](barcode_example.png){.align-center alt="已產生的 Planet 條碼 PNG 截圖"}

## 常見變體與邊緣情況

| 情況 | 要變更的項目 | 原因 |
|-----------|----------------|-----|
| **不同的條碼類型**（例如 Code128） | 將 `EncodeTypes.Planet` 替換為 `EncodeTypes.Code128` | 允許您 **generate barcode** 用於庫存標籤，而不僅是郵政編碼。 |
| **較長的資料字串** | 確保所選條碼類型支援該長度；對於 Planet 必須保持 6 位數字。 | 避免執行時拋出 `ValueError`。 |
| **較高解析度** | 將 `x_dimension.pixels` 提升至 6 或 8。 | 在高 DPI 列印時產生較粗的條紋。 |
| **其他影像格式** | 使用 `BarCodeImageFormat.JPEG` 或 `BarCodeImageFormat.GIF`。 | 當 PNG 不適合您的工作流程時很有用。 |
| **在 Web 服務中執行** | 將檔案系統的 `save` 呼叫改為 `BytesIO` 串流並回傳位元組。 | 可在 Flask 或 Django 中即時產生條碼。 |

**專業提示：** 在呼叫 `BarcodeGenerator` 前務必驗證輸入字串。無效資料（長度錯誤、Planet 的非數字字元）會拋出例外，導致應用程式中斷。

## 如何在 Flask 端點中產生條碼（可選的下一步）

如果您想將 **barcode generator example** 以 REST API 形式公開，可將 `create_postal_barcode` 函式包裝起來：

```python
from flask import Flask, send_file, request, abort
import io

app = Flask(__name__)

@app.route("/barcode", methods=["GET"])
def barcode_endpoint():
    data = request.args.get("data", "123456")
    try:
        # Generate barcode into an in‑memory stream
        stream = io.BytesIO()
        generator = BarcodeGenerator(EncodeTypes.Planet, data)
        generator.parameters.barcode.x_dimension.pixels = 4
        generator.save(stream, BarCodeImageFormat.PNG)
        stream.seek(0)
        return send_file(stream, mimetype="image/png", as_attachment=False)
    except Exception as exc:
        abort(400, str(exc))

if __name__ == "__main__":
    app.run(debug=True)
```

此程式碼片段示範了如何即時 **generate barcode** 而不寫入磁碟，對微服務非常便利。

## 結論

現在您已了解如何在 Python 中使用 Aspose.Barcode **create barcode from string**、如何以自訂尺寸 **generate barcode**，以及如何 **save** 結果為 PNG 檔案。完整的 **barcode generator example** 包含輸入驗證、錯誤處理，以及可在大型應用程式中重複使用的函式。

接下來，探索其他條碼類型（`EncodeTypes.Code128`、`EncodeTypes.QR`）或將生成器嵌入 Flask、Django 等 Web 框架。這兩個步驟將加深您對 **aspose barcode python** 函式庫的了解，並擴展您在實務專案中 **generate postal barcode** 圖片的應用方式。

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在本篇示範的技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能並在專案中探索替代實作方式。

- [如何在 Python 中產生條碼 – 完整步驟指南](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [在 Python 中建立條碼 PNG – 完整 Aspose.Barcode 指南](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)
- [如何使用 Aspose.Barcode Python 產生帶 ECI 的條碼](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}