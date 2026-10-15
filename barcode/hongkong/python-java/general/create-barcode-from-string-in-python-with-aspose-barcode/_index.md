---
category: general
date: 2026-10-15
description: 使用 Aspose.BarCode 在 Python 中從字串建立條碼，學習如何生成 Code 128 條碼並僅用幾行程式碼將條碼保存為
  PNG 圖片。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from string
- generate code 128 barcode
- how to save barcode
- generate barcode png
- encode data into barcode
language: zh-hant
lastmod: 2026-10-15
og_description: 使用 Python 從字串建立條碼，將資料編碼為 Code 128 條碼，並使用 Aspose.BarCode 儲存為 PNG 檔案。
og_image_alt: Screenshot of a generated Code 128 barcode saved as a PNG image
og_title: 在 Python 中從字串生成條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode from string in Python using Aspose.BarCode, learn how
    to generate Code 128 barcode and save barcode PNG in just a few lines.
  headline: Create barcode from string in Python with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Replace `EncodeTypes.CODE_128` with another enum value such as `EncodeTypes.QR`,
      `EncodeTypes.EAN_13`, or `EncodeTypes.PDF_417`. The rest of the code remains
      the same.
    question: What if I need a different symbology?
  - answer: Code 128 supports the full 128‑character ASCII set. For Unicode data,
      consider using QR Code (`EncodeTypes.QR`) which handles UTF‑8 natively.
    question: Can I generate a barcode from non‑ASCII characters?
  - answer: Pass a different member of `BarCodeImageFormat` to `save`, e.g., `BarCodeImageFormat.JPEG`
      or `BarCodeImageFormat.BMP`.
    question: How do I change the image format?
  - answer: Wrap the `save` call in a try/except block and handle `PermissionError`
      gracefully, perhaps by prompting the user for an alternative path.
    question: What if the output directory is read‑only?
  type: FAQPage
tags:
- barcode
- Python
- Aspose
- Code128
title: 使用 Aspose.BarCode 在 Python 中從字串建立條碼
url: /zh-hant/python-java/general/create-barcode-from-string-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Python 中從字串建立條碼

如果您需要在 Python 中 **從字串建立條碼**，本指南將示範使用 Aspose.BarCode 的完整步驟。您將學會如何 **產生 Code 128 條碼**、調整外觀，並 **將條碼 PNG 儲存** 到磁碟。此解決方案可在任何支援 Python 3.9+ 的平台上執行，且只需少量程式碼。

以程式方式產生條碼可避免手動輸入錯誤，並簡化庫存追蹤、票券發行、標籤列印等工作流程。完成本教學後，您將能 **將資料編碼成條碼**、自訂尺寸，並將影像儲存至任意位置。

## 前置條件

開始之前，請確保您已具備：

- 已安裝 Python 3.9 或更新版本  
- 可連網以下載 Aspose.BarCode 套件  
- 具有寫入欲儲存 PNG 檔案之目錄的權限  

若您使用虛擬環境（強烈建議），請立即啟動它。

## 安裝 Aspose.BarCode Python 套件

Aspose 提供純 Python 的函式庫，支援所有常見條碼符號，包括 Code 128。使用 pip 安裝：

```bash
pip install aspose-barcode
```

*小技巧：* 建議固定版本（例如 `aspose-barcode==23.9`），以避免在正式環境中遭遇意外的重大變更。

## 在 Python 中從字串建立條碼

第一步是匯入必要的類別，並為目標符號建立產生器。此範例使用 **Code 128**，適合編碼英數字資料。

```python
# Step 1: Import the Aspose.BarCode classes
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 2: Create a generator for Code 128 and provide the data string
barcode_generator = BarcodeGenerator(EncodeTypes.CODE_128, "1234567890")
```

**為什麼這很重要：** `EncodeTypes.CODE_128` 告訴函式庫使用哪種條碼標準，而第二個參數（`"1234567890"`）則是 **您想要編碼成條碼的字串**。您可將其替換為任意長度不超過 80 個字元的 ASCII 字串（適用於 Code 128）。

## 產生 Code 128 條碼

產生器就緒後，即可在記憶體中產生條碼影像。函式庫會根據提供的資料自動渲染條碼。

```python
# Step 3: Render the barcode to an image object (in memory)
barcode_image = barcode_generator.generate_barcode_image()
```

此時 `barcode_image` 為 `System.Drawing.Image`（在 Windows 上）或其他平台相容的影像物件。您可以直接在 GUI 中顯示、嵌入 PDF，或繼續自訂它。

## 調整條碼外觀

微調視覺屬性可確保條碼在您的環境中可靠掃描。常見的調整項目包括 X‑dimension（最窄條的寬度）與整體條高。

```python
# Step 4: Adjust appearance – X dimension and bar height
barcode_generator.parameters.barcode.x_dimension.pixels = 2   # width of the smallest bar
barcode_generator.parameters.barcode.bar_height.pixels = 100  # height of the bars (optional)
```

*為什麼要調整這些值？*  
- **X dimension** 影響條碼密度；數值較小會產生較緊湊的條碼，適合小尺寸標籤。  
- **Bar height** 影響可讀性；條碼較高時，掃描器在較遠距離也較易偵測。

您亦可透過 `parameters` 物件變更顏色、加入邊距，或加入可讀文字。完整選項請參考 Aspose.BarCode 文件。

## 如何將條碼儲存為 PNG

將產生的影像寫入檔案系統是 **從字串建立條碼** 工作流程的最後一步。函式庫支援多種格式，PNG 為無損且廣受支援。

```python
# Step 5: Save the barcode image to a PNG file
output_path = "output/barcode.png"
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

`save` 方法會依您指定的格式寫入檔案。若目標目錄（本例中的 `output/`）不存在，Python 會拋出 `FileNotFoundError`。請事先建立目錄或捕捉例外：

```python
import os

output_dir = os.path.dirname(output_path)
os.makedirs(output_dir, exist_ok=True)   # ensures the directory exists
barcode_generator.save(output_path, BarCodeImageFormat.PNG)
```

**預期結果：** 執行腳本後，`output/barcode.png` 內會有一張清晰的 Code 128 條碼，編碼內容為 `"1234567890"`。以任何影像檢視器開啟，即可看到黑白條碼，隨時可供掃描。

## 完整可執行範例

以下是一個可直接複製、貼上並執行的完整腳本，將所有步驟整合在一起：

```python
"""
Complete example: create barcode from string, generate Code 128 barcode,
customize appearance, and save barcode PNG using Aspose.BarCode.
"""

import os
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1. Define input data and output location
data_to_encode = "1234567890"
output_path = "output/barcode.png"

# 2. Ensure the output directory exists
os.makedirs(os.path.dirname(output_path), exist_ok=True)

# 3. Initialise the generator for Code 128
generator = BarcodeGenerator(EncodeTypes.CODE_128, data_to_encode)

# 4. Optional: tweak visual parameters
generator.parameters.barcode.x_dimension.pixels = 2
generator.parameters.barcode.bar_height.pixels = 100

# 5. Save as PNG
generator.save(output_path, BarCodeImageFormat.PNG)

print(f"Barcode saved to {output_path}")
```

使用 `python create_barcode.py` 執行腳本。若環境設定正確，您會看到：

```
Barcode saved to output/barcode.png
```

開啟 PNG 檔案，並使用任意條碼掃描應用程式驗證條碼與原始字串相符。

## 常見問題與邊緣情況

- **如果需要其他符號該怎麼辦？**  
  將 `EncodeTypes.CODE_128` 替換為其他列舉值，例如 `EncodeTypes.QR`、`EncodeTypes.EAN_13` 或 `EncodeTypes.PDF_417`。其餘程式碼保持不變。

- **能否產生非 ASCII 字元的條碼？**  
  Code 128 只支援完整的 128‑字符 ASCII 集。若需 Unicode 資料，建議使用 QR Code（`EncodeTypes.QR`），它原生支援 UTF‑8。

- **如何變更影像格式？**  
  在 `save` 時傳入 `BarCodeImageFormat` 的其他成員，例如 `BarCodeImageFormat.JPEG` 或 `BarCodeImageFormat.BMP`。

- **若輸出目錄為唯讀該怎麼處理？**  
  將 `save` 呼叫包在 try/except 區塊，捕捉 `PermissionError`，並提示使用者輸入其他路徑。

- **效能小技巧：**  
  大量迴圈產生條碼時會消耗 CPU。可重複使用同一個 `BarcodeGenerator` 實例，僅在迭代間更新 `generator.parameters.barcode.code_text`。

## 結論

現在您已掌握如何在 Python 中使用 Aspose.BarCode **從字串建立條碼**、**產生 Code 128 條碼**、自訂尺寸，並 **將條碼 PNG 儲存** 到磁碟。這套端對端的解決方案讓您能快速且可靠地 **將資料編碼成條碼**，方便整合至庫存系統、票券平台或任何需要機器可讀識別碼的應用程式。

**後續步驟**

- 探索其他符號（如 QR 或 DataMatrix）的產生方式（`generate code 128 barcode` 替代方案）。  
- 為腳本加入錯誤處理機制，使其在正式環境中更具韌性（`how to save barcode` 失敗處理）。  
- 將產生的 PNG 嵌入 PDF 或 HTML 報表（`generate barcode png` 用於網頁）。  

祝開發順利，享受程式化產生條碼的簡易與高效！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並探索其他實作方式。

- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}