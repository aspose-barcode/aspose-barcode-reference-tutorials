---
category: general
date: 2026-07-18
description: 使用 extcodetextbuilder aspose 來建立結合普通 ASCII 與 UTF‑8 俄文文字的 QR 代碼。學習在 Python
  中使用 Aspose.Barcode 產生 QR 代碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: zh-hant
lastmod: 2026-07-18
og_description: 使用 ExtCodeTextBuilder，Aspose 讓您在 QR Code 中混合純文字和 UTF‑8 編碼的片段。請參考此
  Python 版 Aspose.Barcode 的逐步指南。
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: 使用 extcodetextbuilder aspose – 建立含混合 ECI 文字的 QR 码
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 使用 extcodetextbuilder aspose：產生含混合 ECI 文字的 QR 碼
url: /zh-hant/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 extcodetextbuilder aspose – 建立混合 ECI 文字的 QR Code

有沒有想過要 **使用 extcodetextbuilder aspose** 把純英文與西里爾字元同時嵌入同一個 QR Code？你並不孤單。許多開發者在需要混合 ASCII 與非 ASCII 資料時會卡關，尤其當目標掃描器需要正確的 ECI（Extended Channel Interpretation）標記時更是如此。

在本教學中，我們將一步步示範如何使用 Aspose.Barcode 的 Python API，建立一個同時攜帶「HELLO123」 **以及** 俄文「Привет」的 QR Code。完成後，你將擁有可直接執行的腳本，了解每個呼叫的意義，並知道如何為其他語言或資料格式微調此流程。

## 你將學會

- 如何 **初始化 ExtCodetextBuilder** 並加入純文字與 ECI 編碼的片段。  
- 為何 **ECI 編碼** 值 `3` 代表 UTF‑8，且它如何影響掃描結果。  
- 設定 **Aspose.Barcode QR Code 產生器** 的完整順序。  
- 如何儲存產生的影像並驗證混合內容。  

**先備條件** – 需要 Python 3.8 以上、已安裝 `aspose-barcode` 套件（`pip install aspose-barcode`），以及一個可寫入影像的資料夾。除此之外不需要其他東西。

---

## 使用 extcodetextbuilder aspose 來建立混合 codetext

首先，我們需要一個 `ExtCodetextBuilder` 實例。它就像建造者模式，會在背後自動插入正確的 ECI 標記，將不同的文字片段串接起來。

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**為什麼這很重要：**  
- `add_plain_codetext` 會保持資料原樣，非常適合數字或英文字母。  
- `add_eci_codetext` 會在提供的字串前插入 ECI 段落（`[ECI:3]`），告訴任何符合規範的讀取器，接下來的位元組是 UTF‑8。若未使用此方法，掃描器會把西里爾位元組當成雜訊。

> **小技巧：** 若需要其他字元集，只要依照 ECI 表格更改 `eci_encoding` 的值（例如 `26` 代表 ISO‑8859‑1）。

---

## 初始化 Aspose.Barcode QR Code 產生器

現在我們已擁有正確格式的 `extended_codetext`，可以把它交給 QR Code 產生器。Aspose.Barcode 會抽象掉底層的 QR 矩陣產生，讓你只需關注資料本身。

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**這裡發生了什麼？**  
- `BarcodeGenerator()` 會建立一個使用預設設定（尺寸、解析度等）的全新產生器物件。  
- `set_symbology` 告訴引擎我們要產生 QR Code，而非例如 Code128。  

如果需要更高的錯誤更正等級，可在指定 codetext 前呼叫 `qr_generator.parameters.barcode.qr_error_level = ...`。

---

## 將擴充 codetext 指派給 QR 產生器

產生器準備好後，只要把先前組好的混合字串塞入即可。

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**為什麼不用 `set_codetext`？**  
`set_codetext` 會把輸入視為純文字，會移除所有 ECI 標記。`set_extended_codetext` 則會保留原始位元組，包括 ECI 段落，確保掃描器正確切換語言。

---

## 儲存 QR Code 影像並驗證結果

最後，我們把 QR Code 寫入磁碟。Aspose.Barcode 支援 PNG、JPEG、BMP 等格式；PNG 是安全的預設選擇，因為它保留無損資料。

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

執行完畢後，你應該會在指定位置看到一個 PNG 檔。使用任何支援 ECI 的 QR 掃描 App（大多數現代智慧手機皆支援）開啟它。第一次掃描會看到「HELLO123」，再次掃描（或使用顯示原始資料的掃描器）則會看到「Привет」。兩段文字會以單一 payload 形式呈現，正如我們所建構的那樣。

![使用 extcodetextbuilder aspose QR code 範例](YOUR_DIRECTORY/qr_extended.png)

*圖片替代文字：使用 extcodetextbuilder aspose QR code 範例，展示混合 ECI 文字*

---

## 完整、可直接執行的腳本

把前面的步驟全部整合起來，以下就是可以直接貼到 `qr_mixed_eci.py` 檔案中的完整程式碼：

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

執行方式：

```bash
python qr_mixed_eci.py
```

執行後會在主控台顯示儲存路徑訊息，PNG 檔也會出現在你指定的目錄中。

---

## 常見問題與邊緣案例

### 掃描器無法辨識俄文部分該怎麼辦？
請確認掃描 App 有宣稱支援 ECI。較舊的硬體可能會忽略 ECI 段落，將位元組當成 ISO‑8859‑1 處理，導致字元亂碼。

### 可以加入超過兩個片段嗎？
當然可以。只要多次呼叫 `add_plain_codetext` 或 `add_eci_codetext` 即可。建構器會依照呼叫順序依次串接。

### 如何變更 QR Code 大小或前景顏色？
使用 `qr_generator.parameters` 物件：

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### 能否同時嵌入二進位資料（例如小檔案）與文字？
可以。使用 `add_binary_codetext` 搭配位元組陣列，並視需要加入相應的 ECI（若二進位資料代表特定字元集）。建構器會自動處理模式切換。

---

## 結論

現在你已掌握 **如何使用 extcodetextbuilder aspose** 來製作同時結合純 ASCII 與 UTF‑8 編碼俄文的 QR Code。透過 `ExtCodetextBuilder`、正確的 **ECI 編碼**，再把結果交給 **Aspose.Barcode QR Code 產生器**，即可得到符合標準、在現代掃描器上可正常讀取的單一影像。

接下來，你可以嘗試將 `eci_encoding=3` 換成其他語言代碼，或加入更多純文字片段以建立多語言 payload。若需要向量圖形，也可以探索 `BarCodeImageFormat` 輸出 SVG 或 PDF 的選項。

祝開發順利，若在實作過程中遇到任何問題，歡迎留言討論——你的回饋能讓這些指南變得更好！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步擴展你的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能或探索替代實作方式。

- [產生條碼 Java – 使用 Aspose.BarCode 設定代碼文字](/barcode/english/java/text-and-styling/setting-code-text/)
- [建立條碼 .NET – 設定 DataMatrix 代碼文字](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec 代碼文字編碼 – Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}