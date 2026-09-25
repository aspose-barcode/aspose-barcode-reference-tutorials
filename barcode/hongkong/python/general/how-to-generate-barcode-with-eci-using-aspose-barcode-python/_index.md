---
category: general
date: 2026-08-19
description: 如何使用 Aspose.Barcode for Python 產生帶有 ECI 的條碼。學習如何加入 ECI 資料、混合純文字，並將圖像儲存，一目了然的完整指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: zh-hant
lastmod: 2026-08-19
og_description: 如何使用 Aspose.Barcode for Python 產生帶有 ECI 的條碼。請跟隨本教學了解如何加入 ECI 資料、客製化外觀，並儲存結果。
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: 使用 Aspose.Barcode Python 生成帶 ECI 的條碼 – 逐步說明
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: 使用 Aspose.Barcode Python 生成帶 ECI 的條碼
url: /zh-hant/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Barcode Python 產生含 ECI 的條碼

如果您想了解 **如何產生條碼**，且條碼同時包含普通字元與 ECI 編碼資料，本指南將完整說明整個流程。您將會看到 **如何加入 eci** 區段、調整尺寸，並以單一可執行腳本將影像寫入磁碟的步驟。

本教學涵蓋：

* 取得 Aspose.Barcode 函式庫版本（可選，但對除錯很有幫助）。  
* 建立混合普通與 ECI 編碼字元的擴充碼文字字串。  
* 為支援擴充碼文字的條碼符號建立條碼產生器。  
* 自訂條碼尺寸並儲存最終的 PNG 檔案。

不需要額外文件；只要複製程式碼、執行，即可得到包含以 ECI 26（UTF‑8）編碼之中文字符的條碼影像。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。  
* `aspose-barcode` 套件已安裝（`pip install aspose-barcode`）。  
* 對欲儲存 PNG 檔案之資料夾具寫入權限。

如果您使用虛擬環境，請先啟動它，以保持相依套件的隔離。

## 步驟 1：驗證 Aspose.Barcode 版本（可選）

了解確切的函式庫版本有助於回報錯誤或在不同版本間比較功能。

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*為什麼這很重要*：版本輸出可確認執行環境與您參考的文件相符。不同版本可能支援不同的 ECI 值，因此這是一個快速的 sanity check（檢查）。

## 步驟 2：使用普通與 ECI 編碼部分建立擴充碼文字

Aspose.Barcode 提供 `ExtCodetextBuilder` 以串接普通資料與 ECI 編碼段落。在本例中，我們將數字字串與中文字符混合。

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*說明*：  
* `add_plain_codetext` 插入條碼符號視為普通字元的資料。  
* `add_eci_codetext` 告訴產生器在提供的文字前加上 ECI 指示符（此處為 **26**，對應 UTF‑8）。這正是 **如何加入 eci** 資料到條碼的方式。

您可以多次呼叫 `add_eci_codetext` 以嵌入多個不同語言的區塊。建構器會自動處理所需的跳脫序列。

## 步驟 3：選擇支援擴充碼文字的條碼符號

並非所有條碼類型都能儲存 ECI 區段。Code 128、QR 與 Data Matrix 是常見的選擇。範例使用 Code 128，因其支援度高且適合混合字母數字資料。

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*為什麼選擇 Code 128*：它接受完整的 ASCII 範圍以及建構器產生的 ECI 跳脫序列，因而非常適合本「如何產生條碼」的情境，混合普通與編碼文字。

## 步驟 4：調整條碼外觀

您可以透過 `parameters` 物件控制尺寸、高度、邊距以及其他多項視覺屬性。

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*提示*：若您打算列印條碼，請按比例提升 `x_dimension` 與 `bar_height`，以確保在目標 DPI 下的可讀性。

## 步驟 5：儲存條碼影像

最後，將產生的影像寫入檔案。Aspose.Barcode 支援 PNG、JPEG、BMP 以及其他多種格式。

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

在呼叫 `save` 前，請確保 `output` 資料夾已存在，或使用 `os.makedirs("output", exist_ok=True)` 建立它。

### 預期結果

當您開啟 `extended_codetext.png` 時，應會看到一個 Code 128 條碼，編碼了數字字串 `1234567890`，其後接著中文字符「特殊字符」。使用支援 ECI 的現代掃描器掃描此條碼，將會回傳原始的混合字串。

![Barcode generated with how to generate barcode example](https://example.com/images/barcode-sample.png){: .align-center alt="使用「如何產生條碼」範例產生的條碼"}

## 常見問題與邊緣情況

### 如果需要不同的字元集該怎麼辦？

從 ISO/IEC 18004 表格中選擇相應的 ECI 值。例如，ECI 27 代表 ISO‑8859‑1（Latin‑1）。請相應地在 `add_eci_codetext` 中替換數字識別碼。

### 可以嵌入多個 ECI 區塊嗎？

可以。多次呼叫 `add_eci_codetext` 即可。建構器會在區塊之間插入必要的 ECI 切換碼，並保留您加入的順序。

### 產生器支援帶有 ECI 的 QR 代碼嗎？

當然可以。將 `barcode.Symbology.CODE_128` 替換為 `barcode.Symbology.QR`，並透過 `generator.parameters.qr` 調整任何 QR 專屬參數（例如錯誤更正等級）。

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### 如何處理非常長的資料字串？

對於像 Code 128 這樣的線性條碼，使用擴充碼文字時最大長度約為 80 個字元。若超過此長度，建議改用二維條碼（如 QR 或 Data Matrix），其可儲存數千個字元。

## 完整、可執行的腳本

以下是完整程式碼，您可直接複製貼上至名為 `generate_extended_barcode.py` 的檔案並執行。

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 產生帶有補充空間自訂的條碼影像](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [如何在 Java 中使用 Aspose.BarCode 產生條碼影像](/barcode/english/java/barcode-rendering-techniques/)
- [如何在 .NET 中使用 Aspose.BarCode 產生 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}