---
category: general
date: 2026-09-10
description: 在 QR 碼中編碼非 ASCII 字元，並使用簡易的 Python 建構器儲存 QR 碼圖像。按照使用 ExtCodetextBuilder
  與 BarcodeGenerator 的逐步指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: zh-hant
lastmod: 2026-09-10
og_description: 使用 Python 將非 ASCII 字元編碼至 QR 碼並儲存 QR 碼圖像。本教學示範如何建立擴充的代碼文字、產生 QR 碼以及儲存圖像。
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: 在 QR 碼中編碼非 ASCII 字元並儲存 QR 碼圖像 – 步驟式 Python 指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: 將非 ASCII 字元編碼至 QR Code 並儲存 QR Code 圖像
url: /zh-hant/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 QR 码中編碼非 ASCII 字元並儲存 QR 码圖像

如果您需要在 QR 码中**編碼非 ASCII 字元**，本指南會逐步說明如何操作，並將**儲存 QR 码圖像**至磁碟。無論您處理俄文、中文或表情符號資料，ExtCodetextBuilder 都能讓您在不手動處理位元組的情況下混合純文字與 ECI 編碼段落。

您將學習如何建立擴充編碼文字字串、產生能理解該字串的 QR 码，最後將條碼圖像寫入檔案。本教學假設您具備基本的 Python 知識，且已安裝 `barcode` SDK。

## 前置條件

* 已安裝 Python 3.8+。
* `barcode` Python 套件（或相應的 SDK），提供 `ExtCodetextBuilder`、`CodetextEncodingType` 以及 `BarcodeGenerator`。
* 具有寫入您想**儲存 QR 码圖像**之目錄的權限。

您可以使用 pip 安裝 SDK（將 `barcode-sdk` 替換為實際的套件名稱）：

```bash
pip install barcode-sdk
```

## 步驟 1：建立擴充編碼文字建構器

第一步是實例化 `ExtCodetextBuilder`。此物件會收集多個文字段落，並產生 QR 码符號可解讀的單一字串。

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*為什麼這很重要*：QR 码支援**擴充編碼文字**，這表示您可以在同一條碼中嵌入多種編碼模式（純文字、ECI 等）。建構器抽象化了 QR 規範所需的低階格式化工作。

## 步驟 2：加入純文字段落

純文字是預設模式，適用於 ASCII 字元。先加入它可為忽略 ECI 的掃描器提供可讀的備援。

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

如果省略此步驟，QR 码將僅包含 ECI 段落，某些較舊的讀取器可能無法正確解碼。

## 步驟 3：加入非 ASCII 字元的 ECI 編碼段落

若要包含 ASCII 範圍外的字元（例如西里爾文、中文或表情符號），必須指定 ECI（Extended Channel Interpretation）編碼。此處我們使用 UTF‑8 來編碼俄文單字 “Привет”。

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*為什麼這有效*：QR 規範定義了 ECI 值，告訴掃描器使用哪種字元集。若未加入 ECI 標記，原始位元組會被解讀為 ISO‑8859‑1，導致亂碼。

## 步驟 4：取得合併後的擴充編碼文字字串

在加入所有所需段落後，呼叫 `get_extended_codetext()` 以取得條碼產生器所需的最終字串。

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

印出的值看起來像是一連串控制字元，後面接著實際文字，但您不需要手動解析它。

## 步驟 5：使用擴充編碼文字產生 QR 码

現在建立 `BarcodeGenerator`，將符號設定為 QR（唯一支援擴充編碼文字的常見 2‑D 符號），並輸入合併後的字串。

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*提示*：若將相同流程套用於 Code‑128 或 DataMatrix，SDK 會拋出例外，因為這些格式無法解讀 ECI 標記。

## 步驟 6：儲存 QR 码圖像

最後，將條碼寫入 PNG 檔案。這就是您**儲存 QR 码圖像**以供日後使用的地方。

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

請確保 `output` 資料夾已存在，或在呼叫 `save` 前使用 `os.makedirs('output', exist_ok=True)` 建立它。

### 完整可執行範例

將所有步驟整合在一起，即可得到一個可立即執行的獨立腳本：

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**預期輸出**（主控台）：

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

使用任何 QR 掃描器開啟 `qr_extended.png`，將會顯示 `HelloWorldПривет`。能理解 ECI 的掃描器會正確呈現西里爾字元；其他則僅顯示 ASCII 部分。

## 常見問題與邊緣情況

| 問題 | 答案 |
|----------|--------|
| *我可以使用其他編碼如 Shift‑JIS 嗎？* | 可以。將 `CodetextEncodingType.UTF_8` 替換為 `CodetextEncodingType.SHIFT_JIS`，並提供相應的文字。 |
| *如果合併後的資料超過 QR 容量怎麼辦？* | QR 码的版本有上限（最高 177 × 177 模組）。若建構器拋出尺寸例外，您可以提升錯誤更正等級或將資料分割至多個 QR 码。 |
| *我需要設定特定的 QR 版本嗎？* | SDK 會自動選擇最小能容納資料的版本。如有需要，可使用 `qr_generator.set_qr_version(10)` 強制指定版本。 |
| *圖像會是透明的嗎？* | 預設情況下 SDK 會產生白色背景的 PNG。若需要透明，請在 `save` 前使用 `qr_generator.set_background_color(Color.Transparent)`。 |

## 結論

在本教學中，您學會了如何使用 `ExtCodetextBuilder` **編碼非 ASCII 字元**於 QR 码，並使用 `BarcodeGenerator` **儲存 QR 码圖像**。此流程包括建立擴充編碼文字字串、加入純文字與 ECI 編碼段落、產生 QR 符號，最後寫入圖像檔案。

接下來您可以探索：

* 加入更多 ECI 段落（不同語言或表情符號）。
* 調整 QR 錯誤更正等級以提升可靠性。
* 將產生的 PNG 嵌入 PDF 或網頁。

祝開發順利，盡情打造多語言 QR 码吧！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立於本教學所示技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何在 Python 中使用 Aspose.Barcode 產生 QR 码圖像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [使用 Aspose.Barcode Python 產生 Code128 條碼 – 完整指南](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [使用 Python 條碼函式庫顯示產品名稱 – 步驟指南](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}