---
category: general
date: 2026-11-20
description: 學習如何使用 ECI、從文字產生 QR、清空建構器，並使用 Python 條碼函式庫儲存 QR 圖片。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: zh-hant
lastmod: 2026-11-20
og_description: 如何使用 ECI 從文字產生 QR 碼、清除 QR 產生器及儲存 QR 圖像——完整的逐步教學
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: 如何在 Python 中使用 ECI 產生 QR 碼
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: 如何在 Python 中使用 ECI 生成 QR 碼
url: /zh-hant/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 ECI 產生 QR Code

如果您在建立 QR Code 時需要 **how to use eci**，本教學將示範完整步驟。您將看到如何從文字 **generate QR from text**、清除建構器，最後儲存 QR 圖片——全部只需幾行 Python 程式碼。

包含多語言資料的 QR Code 通常需要加入 Extended Channel Interpretation（ECI）段，以讓掃描器知道使用哪種字元集。本教學將帶您一步步建立擴充的 codetext、在重複使用時清除建構器，並將結果保存為 PNG 檔案。

## 前置條件

開始之前，請確保您已具備：

- 已安裝 Python 3.8 以上版本。
- Aspose.BarCode for Python via .NET 套件（或任何提供 `ExtCodetextBuilder` 與 `BarcodeGenerator` 的相容 `barcode` 函式庫）。
- 基本的 QR Code 概念認識。

使用 pip 安裝函式庫：

```bash
pip install aspose-barcode
```

> **小技巧：** 建議使用虛擬環境，以避免版本衝突。

## 步驟 1：匯入所需類別

主要會使用的類別是 `ExtCodetextBuilder`（用於建構擴充 codetext）與 `BarcodeGenerator`（用於產生 QR Code）。

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

這些匯入讓您可以使用建構器的方法（`add_plain_codetext`、`add_eci_codetext` 等）以及產生器的 `set_code_text`、`set_symbology`、`save` 等功能。

## 步驟 2：建立並設定 ExtCodetextBuilder

建立新的建構器實例是 **how to use eci** 的第一個具體範例。之後若需要重複使用，也可以先清除建構器。

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

呼叫 `clear()` 可確保建構器從乾淨的狀態開始，這在迴圈中產生多個 QR Code 時尤為重要。

## 步驟 3：加入純文字（非 ECI）段落

純文字不需要 ECI 段落。使用 `add_plain_codetext` 來加入 ASCII 相容的字串。

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

此時建構器已包含純文字段落 `"HelloWorld"`。

## 步驟 4：加入 ECI 編碼段落

這就是 **how to use eci** 的核心：指定 ECI 值（UTF‑8 為 26）並提供欲編碼的 Unicode 字串。如此 QR Code 即可攜帶俄文、中文或其他未被 ISO‑8859‑1 預設字集涵蓋的語言。

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **為什麼重要：** 若未加入 ECI 指示，掃描器會使用預設字元集解讀位元組，導致非 ASCII 文字顯示為亂碼。

## 步驟 5：取得合併後的擴充 codetext 字串

加入所有必需段落後，取得最終要傳給 QR 產生器的字串。

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

印出的結果大致如下：

```
Extended codetext: [ECI26]ПриветHelloWorld
```

具體格式視函式庫而定，重要的是 ECI 標記（`[ECI26]`）會位於 UTF‑8 負載之前。

## 步驟 6：使用合併後的文字產生 QR Code

現在您可以 **generate QR from text**，只要把擴充 codetext 傳入 `BarcodeGenerator` 即可。

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

開啟 `qr_extended.png` 後，會看到一個同時編碼英文純文字與俄文問候語的 QR Code。使用現代 QR 掃描器掃描時，會正確顯示 “HelloWorld” 與 “Привет”。

### 為什麼在重複使用建構器前要呼叫 `clear()`

若在迴圈中產生多個 QR Code 而忘記清除建構器，舊的段落會與新的段落串接，導致產生無效的碼。以下是一個快速範例：

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

此程式碼示範了 **how to clear builder** 以及 **how to generate QR from text** 的重複使用方式。

## 邊緣情況與常見陷阱

| 情況 | 需要注意的地方 | 處理方式 |
|-----------|-------------------|---------------|
| **不支援的 ECI 值** | 函式庫會拋出 `InvalidArgumentException`。 | 僅使用規範中列出的 ECI 值（例如 26 代表 UTF‑8、20 代表 Shift‑JIS）。 |
| **合併文字過長** | QR 版本可能超出最大容量。 | 自動提升 QR 版本 (`qr_generator.set_qr_version(QRVersion.AUTO)`) 或將資料分割至多個 QR Code。 |
| **檔案系統權限錯誤** | `save` 失敗並拋出 `IOError`。 | 確認目標目錄已存在且程式具有寫入權限。 |
| **字元集顯示不正確** | 掃描器顯示亂碼。 | 核對使用的 ECI 值是否與字串實際編碼相符。 |

## 完整可執行範例

以下是一個獨立腳本，您可以直接複製、貼上並執行。內含所有匯入、錯誤處理與說明註解。

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

執行此腳本後會產生 `output/qr_extended.png`，一個正確編碼英文與俄文文字的 QR Code。

## 結論

現在您已掌握 **how to use eci** 於 QR Code 建構的技巧，了解 **clear the QR builder** 在重複使用前的必要性，會使用 **generate QR from text**，以及如何以 Python **save QR image**。依照上述模式，您可以將任意 Unicode 字串嵌入 QR Code，同時保持建構器狀態可預測。

### 接下來可以做什麼？

- 探索其他語言的 ECI 值，例如中文（ECI 20）或 ISO‑8859‑5。
- 調整錯誤更正等級（`qr_generator.set_error_correction_level`）以提升掃描可靠度。
- 在同一 QR Code 中結合多個 ECI 段落，實現混合語言訊息。

祝編程愉快，盡情打造多語言 QR Code！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步延伸本指南所示的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [How to generate barcode with ECI using Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}