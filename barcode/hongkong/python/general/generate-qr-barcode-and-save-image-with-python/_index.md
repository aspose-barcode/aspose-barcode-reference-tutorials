---
category: general
date: 2026-11-27
description: 使用 Aspose.Barcode 在 Python 中產生 QR 條碼，並學習如何快速將條碼圖像儲存至磁碟。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: zh-hant
lastmod: 2026-11-27
og_description: 使用 Aspose.Barcode 在 Python 中生成 QR 二維條碼並即時儲存條碼圖像。遵循完整範例以建立、客製化及儲存 QR
  代碼。
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: 使用 Python 產生 QR 條碼並儲存圖像 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: 使用 Python 產生 QR 條碼並儲存圖像
url: /zh-hant/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Python 產生 QR 條碼並儲存影像

如果您需要在 Python 應用程式中**產生 QR 條碼**，本指南將示範如何使用 Aspose.Barcode 程式庫來完成。您還會學習如何正確**儲存條碼影像**至本機資料夾、取得程式庫版本資訊，以及處理延伸文字段落。

產生 QR 代碼是票務系統、行動支付與產品追蹤等常見需求。完成本教學後，您將擁有一個可直接執行的腳本，能產生 QR 條碼影像檔並列印版本資訊，以供除錯或合規使用。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* `aspose-barcode` 套件。可使用 `pip install aspose-barcode` 安裝。
* 具備寫入條碼影像儲存目錄的權限。

不需要額外的外部服務；整個流程皆在本機執行。

## 步驟 1：使用 `ExtCodetextBuilder` 建立延伸文字段落

延伸文字段落允許在單一 QR 代碼中混合純文字與 ECI（Extended Channel Interpretation）段落。當您需要嵌入不同字元集的字元，例如歐元符號時，這非常有用。

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**為什麼此步驟重要：**  
`ExtCodetextBuilder` 會組合 QR 編碼器將要處理的最終字串。若未建立延伸文字段落，條碼僅會包含純 ASCII 字元，無法表示特定語系的符號。

## 步驟 2：取得合併後的延伸文字段落字串

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

輸出結果如下：

```
Extended codetext: ABC123[ECI3]€123
```

方括號 `[ECI3]` 標記告訴 QR 編碼器在後續字元切換至指定的字元集。

## 步驟 3：使用延伸文字段落產生 QR 條碼

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**說明：**  
`BarcodeGenerator` 會接收兩個參數：條碼類型（`QR`）與要編碼的資料（`extended_codetext`）。產生器會準備所有渲染所需的內部結構。

## 步驟 4：儲存產生的條碼影像

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**為什麼建議使用此方式：**  
直接呼叫 `save` 會依檔案副檔名自動判斷格式並寫入磁碟。此方法支援 PNG、JPEG、BMP 與 TIFF，讓您可彈性因應不同的下游使用者。

### 驗證已儲存的影像

使用任何影像檢視器開啟 `output/qr_extended.png` 檔案。您應該會看到一個 QR 代碼，掃描後會回傳字串 `ABC123€123`。大多數現代手機 QR 掃描器會自動處理 ECI 段落。

## 步驟 5：查詢 Aspose.BarCode 版本資訊（可選但有用）

了解 Aspose.BarCode 程式庫的確切版本，有助於回報錯誤或驗證相容性。

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

典型輸出：

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## 完整腳本 – 複製、貼上並執行

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

執行腳本會產生 QR 代碼影像，並在主控台列印延伸文字段落與版本資訊。

## 常見變化與邊緣情況

| 情況 | 建議調整 |
|-----------|------------------------|
| **不同字元集** | 將傳遞給 `add_eci_codetext` 的 ECI 識別碼改為其他值。若使用 UTF‑8，請使用 `5`。 |
| **更高錯誤更正等級** | 在呼叫 `save` 前，設定 `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H`。 |
| **自訂影像尺寸** | 使用 `barcode.parameters.image_width` 與 `barcode.parameters.image_height` 來控制像素尺寸。 |
| **非 PNG 輸出** | 將 `output_path` 的副檔名改為 `.jpg` 或 `.bmp`。程式庫會自動選擇正確的編碼器。 |

## 專業提示

* **程式化建立輸出資料夾**（若可能不存在）：

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **驗證 QR 代碼**：生成後使用 `aspose.barcode.BarcodeReader` 讀回條碼。此步驟可確保編碼資料符合預期，特別是在使用 ECI 段落時。

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **效能提示** – 若需在迴圈中產生大量 QR 代碼，請重複使用同一個 `BarcodeGenerator` 實例。只需重設 `code_text` 屬性，而非每次迭代都建立新物件。

## 結論

您現在已了解如何在 Python 中使用 Aspose.Barcode **產生 QR 條碼**、建立混合純文字與 ECI 段落的延伸文字段落，並正確 **儲存條碼影像**至磁碟。此腳本亦示範如何取得程式庫版本資訊以便除錯。

接下來您可以探索的步驟包括：

* 在 QR 代碼上加入標誌覆蓋或自訂顏色。
* 使用 Aspose.PDF 將 QR 條碼直接嵌入 PDF。
* 為大型資料集自動化批次產生。

歡迎嘗試不同的資料內容、錯誤更正等級與影像格式。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何在 Python 中使用 Aspose.Barcode 產生 QR 代碼影像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [如何產生 Code 128 條碼並使用 Aspose.BarCode 儲存條碼影像](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [如何在 Python 中使用 Aspose.BarCode 產生 DataMatrix 條碼](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}