---
category: general
date: 2026-08-22
description: 學習在 Python 中產生 DataMatrix 條碼，並使用 Aspose.BarCode 編碼俄文文字 – 步驟教學指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate DataMatrix barcode
- encode Russian text
language: zh-hant
lastmod: 2026-08-22
og_description: 在 Python 中生成 DataMatrix 條碼，並使用 Aspose.BarCode 編碼俄文文字。遵循完整範例，即可立即執行。
og_image_alt: Python script that generate DataMatrix barcode with encoded Russian
  text
og_title: 在 Python 中生成 DataMatrix 條碼 – 完整的 Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  headline: How to generate DataMatrix barcode in Python with Aspose.BarCode
  type: TechArticle
- description: Learn to generate DataMatrix barcode in Python and encode Russian text
    using Aspose.BarCode – step‑by‑step guide.
  name: How to generate DataMatrix barcode in Python with Aspose.BarCode
  steps:
  - name: '**ABC123** – the plain identifier.'
    text: '**ABC123** – the plain identifier.'
  - name: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
    text: '**Привет** – the Russian greeting, correctly decoded as UTF‑8.'
  - name: Open the PNG file in an image viewer.
    text: Open the PNG file in an image viewer.
  - name: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
    text: Use any DataMatrix scanning app (many mobile apps support it) or a hardware
      scanner.
  - name: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
    text: The decoded string should display `ABC123Привет` (or the two parts separated
      depending on the scanner UI).
  type: HowTo
tags:
- Aspose.BarCode
- Python
- barcode generation
title: 如何在 Python 中使用 Aspose.BarCode 生成 DataMatrix 條碼
url: /zh-hant/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.BarCode 產生 DataMatrix 條碼

如果您需要在 Python 中 **產生 DataMatrix 條碼** 並 **編碼俄文文字**，本指南會向您展示完整步驟。您將看到一個完整、可執行的範例，該範例會建立擴充的 codetext、設定條碼，並在單一腳本中儲存圖像。

建立包含非 ASCII 字元的條碼時，常會遇到字元集與資料編碼的問題。透過使用 Aspose.BarCode 的 `ExtCodetextBuilder`，您可以安全地在 DataMatrix 符號中嵌入 UTF‑8 文字，例如西里爾字元。此結果可於任何支援 DataMatrix 標準的掃描器上使用。

在本教學中您將：

* 安裝所需的 Aspose.BarCode 套件。
* 建立混合純資料與俄文文字的擴充 codetext。
* **產生 DataMatrix 條碼** 使用擴充字串。
* 調整條碼參數，例如模組大小。
* 將條碼儲存為 PNG 檔案。

不需要任何外部服務；所有操作皆在本機本地執行。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* 擁有有效的 Aspose.BarCode for Python 授權（免費試用版可用於開發）。
* 具備 Python 腳本的基本知識。

您可以透過 pip 安裝 Aspose.BarCode 函式庫：

```bash
pip install aspose-barcode
```

## 步驟 1：建立擴充 codetext 字串

第一個任務是建立一個同時包含純產品識別碼與俄文片語的單一字串。`ExtCodetextBuilder` 允許您串接不同的 codetext 部分，同時保留其編碼資訊。

```python
# Import required Aspose.BarCode classes
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

# Initialize the extended codetext builder
builder = ExtCodetextBuilder()

# Add a plain ASCII identifier – this could be a SKU, part number, etc.
builder.add_plain_codetext("ABC123")

# Add Russian text using ECI (Extended Channel Interpretation) encoding.
# The eci_encoding value 3 corresponds to UTF‑8.
builder.add_eci_codetext(eci_encoding=3, codetext="Привет")

# Retrieve the combined string that Aspose.BarCode will use.
extended_text = builder.get_extended_codetext()
print("Generated extended codetext:", extended_text)
```

**此步驟的重要性** – DataMatrix 符號儲存原始位元組。當您需要混合不同字母表時，必須告訴編碼器每個段落使用的字元集。`add_eci_codetext` 方法會在俄文文字前插入 ECI 指示符，確保掃描器將位元組解讀為 UTF‑8。若未使用 ECI，西里爾字元將顯示為亂碼。

## 步驟 2：建立 DataMatrix 條碼產生器

擁有擴充 codetext 後，建立 `BarcodeGenerator` 並指定 `EncodeTypes.DATA_MATRIX` 類型。

```python
# Create a DataMatrix barcode generator using the extended codetext
generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)
```

**為什麼選擇 DataMatrix？** – DataMatrix 是一種二維條碼，可儲存最多 2,335 個字母數字字元或 1,556 位元組。它非常適合小型物件、工業零件，以及需要嵌入多語言文字的情境。

## 步驟 3：（可選）設定條碼參數

Aspose.BarCode 提供許多參數。對於大多數使用情境，預設設定即可產生可讀的符號。然而，您可能需要控制每個模組（矩陣中最小的方格）的大小，以符合列印需求。

```python
# Set the module (pixel) size to 2.5 points – adjust as needed for your printer DPI
generator.parameters.barcode.x_dimension = 2.5
```

其他有用的參數包括錯誤更正等級、邊距與背景顏色。僅在目標掃描環境需要特定容差時才調整它們。

## 步驟 4：儲存條碼影像

最後，將條碼寫入檔案。`save` 方法支援 PNG、JPEG、BMP 以及多種向量格式。

```python
# Save the barcode image to the desired folder
output_path = "YOUR_DIRECTORY/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

當您開啟 `extended_codetext.png` 時，會看到清晰的 DataMatrix 符號。使用標準 DataMatrix 讀取器掃描它會返回兩個部分：

1. **ABC123** – 純文字識別碼。
2. **Привет** – 俄文問候語，正確以 UTF‑8 解碼。

## 完整、可執行範例

以下是完整腳本，您可以複製貼上至名為 `generate_datamatrix.py` 的檔案。將 `YOUR_DIRECTORY` 替換為系統中已存在的資料夾路徑。

```python
# generate_datamatrix.py
# -------------------------------------------------
# Complete example: generate DataMatrix barcode and encode Russian text
# -------------------------------------------------

import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BarcodeGenerator, EncodeTypes

def main():
    # Step 1: Build extended codetext
    builder = ExtCodetextBuilder()
    builder.add_plain_codetext("ABC123")
    builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_text = builder.get_extended_codetext()
    print("Generated extended codetext:", extended_text)

    # Step 2: Create DataMatrix generator
    generator = BarcodeGenerator(EncodeTypes.DATA_MATRIX, extended_text)

    # Step 3: Optional parameters (adjust module size if needed)
    generator.parameters.barcode.x_dimension = 2.5

    # Step 4: Save the image
    output_path = "YOUR_DIRECTORY/extended_codetext.png"
    generator.save(output_path)
    print(f"Barcode saved as {output_path}")

if __name__ == "__main__":
    main()
```

從命令列執行腳本：

```bash
python generate_datamatrix.py
```

您應該會看到類似以下的主控台輸出：

```
Generated extended codetext: (ECI:3)ПриветABC123
Barcode saved as YOUR_DIRECTORY/extended_codetext.png
```

## 驗證結果

為了確認條碼正確編碼俄文片語，請執行以下步驟：

1. 在圖像檢視器中開啟 PNG 檔案。
2. 使用任何 DataMatrix 掃描應用程式（許多手機應用程式支援）或硬體掃描器。
3. 解碼後的字串應顯示 `ABC123Привет`（或根據掃描器介面分開顯示兩個部分）。

若俄文字符顯示為亂碼，請再次確認掃描器支援 ECI UTF‑8。大多數現代讀取器皆支援，但舊版設備可能需要明確設定。

## 常見陷阱與避免方法

| Issue | Cause | Fix |
|-------|-------|-----|
| 西里爾字元顯示為亂碼 | 缺少 ECI 指示符 | 使用 `add_eci_codetext` 並設定 `eci_encoding=3`。 |
| 條碼對印表機太小 | 預設模組大小對低 DPI 太細 | 增加 `x_dimension`（例如 `3.0` 或 `4.0`）。 |
| 檔案未儲存 | 目錄路徑無效 | 確保 `YOUR_DIRECTORY` 已存在且可寫入。 |
| 掃描器無法讀取 | 資料密度過高 | 減少編碼資料量或提升錯誤更正等級（`generator.parameters.barcode.error_correction_level`）。 |

## 擴充範例

您可以將此模式套用於其他語言或資料類型：

* **編碼日文或阿拉伯文** – 將 `eci_encoding` 改為相應的值（例如 ISO‑8859‑5 為 5，ISO‑8859‑7 為 6）。  
* **加入多個 ECI 段落** – 多次呼叫 `add_eci_codetext`，每次使用不同的編碼。  
* **改為產生 QR code** – 將 `EncodeTypes.DATA_MATRIX` 替換為 `EncodeTypes.QR`。  

其他步驟保持相同，因為 `ExtCodetextBuilder` 抽象化了低階位元組處理。

## 結論

您現在已了解如何在 Python 中 **產生 DataMatrix 條碼** 並使用 Aspose.BarCode 的擴充 codetext 功能 **編碼俄文文字**。完整腳本僅以少量程式碼即可處理字元集協商、條碼建立與影像輸出。

接下來，您可以探索其他條碼符號（PDF417、Aztec）或將產生器整合至即時回傳 PNG 圖像的 Web 服務中。相同的原則——建立擴充 codetext 並選擇適當的 `EncodeTypes`——適用於整個 Aspose.BarCode 系列。

祝程式開發順利，盡情體驗多語言條碼產生的強大功能！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [在 Aspose.BarCode for .NET (C#) 中以 ASCII 模式產生 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}