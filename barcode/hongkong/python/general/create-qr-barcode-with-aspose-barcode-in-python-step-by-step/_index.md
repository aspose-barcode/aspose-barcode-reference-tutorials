---
category: general
date: 2026-08-09
description: 使用 Aspose.BarCode 在 Python 中建立 QR 條碼。了解如何構建擴展代碼文字、調整外觀以及儲存圖像——一次完整教學。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: zh-hant
lastmod: 2026-08-09
og_description: 使用 Aspose.BarCode 在 Python 中建立 QR 條碼。本指南說明如何構建擴充代碼文字、設定視覺參數，並匯出圖像。
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: 使用 Aspose.BarCode 在 Python 中建立 QR 條碼 – 完整程式碼範例
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: 使用 Aspose.BarCode 在 Python 中建立 QR 條碼 – 逐步指南
url: /zh-hant/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Python 中建立 QR 條碼 – 步驟指南

如果您需要在 Python 中 **建立 QR 條碼**，本教學將帶您一步步使用 Aspose.BarCode 函式庫完成整個流程。無論是編碼產品編號、多語言文字或自訂資料，您都會看到如何組合延伸的 codetext、調整視覺設定，並在單一可執行腳本中儲存最終影像。

範例同時示範如何顯示函式庫版本，協助您確認使用的是相容的發行版。完成本指南後，您將擁有可直接使用的 QR 條碼影像，並清楚了解每個設定選項的作用。

## 前置條件

在開始之前，請確保您已具備：

- 已安裝 Python 3.8 以上版本。
- `aspose-barcode` 套件（可透過 `pip install aspose-barcode` 安裝）。
- 基本的 Python 語法概念。
- 對將要儲存 PNG 檔案的輸出目錄具有寫入權限。

> **專業小技巧：** 使用虛擬環境可避免與其他專案的版本衝突。

## 第一步：驗證 Aspose.BarCode 函式庫版本

顯示函式庫版本可確保您使用的發行版支援延伸 codetext 與 QR 編碼。

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**為什麼這很重要：**  
較舊的發行版可能缺少 `ExtCodetextBuilder` 類別，該類別是混合純文字與 ECI 區段所必需的。確認版本可避免在後續流程中發生執行時錯誤。

## 第二步：建構延伸 codetext 字串

延伸 codetext 讓您可以將純 ASCII 資料與 Unicode（ECI）區段結合，這對於多語言 QR 條碼至關重要。

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**為什麼這很重要：**  
`add_plain_codetext` 方法會以標準 ASCII 儲存資料，而 `add_eci_codetext` 會在 Unicode 區塊前加上相應的 ECI 指示符。此做法確保 QR 掃描器正確解讀日文文字，避免出現亂碼。

### 常見變化

- **多個 ECI 區段：** 多次呼叫 `add_eci_codetext` 即可混合多種語言。
- **不同的 ECI 識別碼：** 依目標編碼使用 `27`（ISO‑8859‑1）、`28`（ISO‑8859‑2）等。

## 第三步：使用延伸 codetext 產生 QR 條碼

現在已有正確格式的字串，我們即可建立 QR Code。

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**為什麼這很重要：**  
`EncodeTypes.QR` 讓 Aspose.BarCode 使用 QR 符號。直接傳入 `extended_codetext` 可將混合資料映射到 QR 矩陣中，保留純文字與 Unicode 部分。

## 第四步：調整視覺外觀（可選但建議）

微調條碼的視覺參數可提升掃描可靠性，並符合品牌指引。

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**為什麼這很重要：**  
- **`x_dimension`** 控制每個 QR 模組的大小；過小可能在低解析度裝置上產生讀取錯誤。  
- **`border_width`** 增加靜區。部分掃描器要求至少 4 個模組的靜區；函式庫會自動加入，但您可自行增大以提升安全性。

### 邊緣情況處理

- **高密度資料：** 若編碼資料過大，可能需要增大 `x_dimension` 或選擇較高的錯誤更正等級（透過 `qr_generator.parameters.qr.error_correction_level`）。  
- **透明背景：** 設定 `qr_generator.parameters.barcode.bg_color = Color.Transparent` 可為 PNG 產生含 alpha 通道的透明背景。

## 第五步：儲存 QR 條碼影像

最後，將影像寫入磁碟，使用您偏好的格式。

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**為什麼這很重要：**  
以 PNG 儲存可保留無損品質，對於需要清晰邊緣的 QR 條碼而言是最佳選擇。若您的 Web 應用需要其他格式，只要更改 `BarCodeImageFormat` 列舉即可。

### 驗證結果

使用任何影像檢視器開啟已儲存的檔案。您應該會看到一個 QR Code，掃描後會回傳結合的字串：

```
ABC12345
こんにちは
```

大多數現代 QR 掃描應用會先顯示純文字區段，接著正確呈現日文問候語。

---

## 完整可執行腳本

將下方整段程式碼複製到名為 `create_qr_barcode.py` 的檔案中，並以 `python create_qr_barcode.py` 執行。請將 `YOUR_DIRECTORY` 替換為您機器上可寫入的資料夾路徑。

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

執行此腳本會列印版本資訊、延伸 codetext，並確認 PNG 檔案已成功建立。

---

## 結論

您現在已掌握如何在 Python 中使用 Aspose.BarCode **建立 QR 條碼** 影像。本教學涵蓋：

1. 驗證函式庫版本。  
2. 使用純文字與 ECI（Unicode）區段建構延伸 codetext。  
3. 產生 QR Code。  
4. 客製化視覺參數（如模組大小與靜區寬度）。  
5. 以 PNG 格式儲存最終影像。

接下來您可以探索：

- 更改錯誤更正等級（`qr_generator.parameters.qr.error_correction_level`）。  
- 加入商標或背景圖（`qr_generator.parameters.qr.logo`）。  
- 匯出為 SVG 等可縮放的網頁圖形格式。  
- 將產生器整合至 Flask 或 Django 端點，以實現即時 QR 產生。

嘗試不同的資料負載與視覺設定，讓您的應用符合品牌形象與掃描需求。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並探索在專案中使用的其他實作方式。

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}