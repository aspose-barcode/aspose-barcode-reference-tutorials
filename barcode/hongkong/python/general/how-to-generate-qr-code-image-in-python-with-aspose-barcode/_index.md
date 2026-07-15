---
category: general
date: 2026-07-15
description: 如何在 Python 中使用 Aspose.Barcode 產生 QR Code 圖像。一步一步學習 QR Code 的建立，支援擴充編碼文字、ECI
  編碼及 Unicode。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate qr code image
- Aspose.Barcode QR
- Python barcode generation
- extended codetext builder
- ECI encoding in QR
- QR code with Unicode
language: zh-hant
lastmod: 2026-07-15
og_description: 如何在 Python 中使用 Aspose.Barcode 產生 QR Code 圖像。本指南將逐步說明如何使用擴展碼文字、ECI
  編碼和 Unicode 字元來建立 QR Code。
og_image_alt: Python script generating a QR code image with extended codetext via
  Aspose.Barcode
og_title: 如何在 Python 中生成 QR 碼圖像 – Aspose.Barcode 完整教學
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  headline: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  type: TechArticle
- description: How to generate QR code image in Python using Aspose.Barcode. Learn
    step‑by‑step QR code creation with extended codetext, ECI encoding, and Unicode
    support.
  name: How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide
  steps:
  - name: 1. *What if I need more than two segments?*
    text: Simply call `add_plain_codetext` or `add_eci_codetext` as many times as
      you like. The builder maintains the correct ordering, so the QR code will contain
      each segment in the sequence you add them.
  - name: 2. *Can I embed emojis?*
    text: "Yes—emojis are just Unicode characters. Use the UTF‑8 ECI (value 26) and
      pass the emoji string, e.g., `builder.add_eci_codetext(26, \"\U0001F680\")`.
      The QR will display the rocket emoji on supporting scanners."
  - name: 3. *What if the QR becomes too dense?*
    text: 'QR codes have version limits. If you exceed the data capacity, Aspose will
      automatically bump the version up to the next size, but the image might become
      larger. To control size, you can lower the error correction level:'
  - name: 4. *Do I need to worry about character sets other than UTF‑8?*
    text: Only if you have legacy systems that require a specific encoding (e.g.,
      ISO‑8859‑1). In that case, replace `26` with the appropriate ECI value (see
      Aspose’s ECI table). For most modern apps, UTF‑8 is the safest bet.
  - name: 5. *How do I add a logo in the center?*
    text: 'Aspose.Barcode supports `barcode.generator.QRCodeParameters.logo_image`.
      Load an image with Pillow (`from PIL import Image`) and assign it:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
title: 如何在 Python 中使用 Aspose.Barcode 產生 QR Code 圖像 – 完整指南
url: /zh-hant/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 Aspose.Barcode 產生 QR Code 圖片 – 完整指南

有沒有想過 **如何在 Python 中產生 QR code 圖片**，卻不必搜尋上百個函式庫？你並不孤單。許多開發者需要可靠的方式在 QR code 中嵌入多語言文字——例如俄文、阿拉伯文或表情符號——而內建的函式庫往往無法滿足需求。

事實上，Aspose.Barcode for Python 讓這件事變得相當簡單。在本教學中，我們將逐步說明從安裝套件到打造結合普通 ASCII 與 ECI 編碼 Unicode 的延伸編碼文字（extended codetext）字串。完成後，你將得到一張可直接使用的 QR code 圖片，已儲存於磁碟上。

## 本指南涵蓋內容

- 安裝 **Aspose.Barcode** for Python（相容於 Python 3.8 以上）
- 建立結合普通與 Unicode 區段的 **extended codetext**
- 使用 **ECI 編碼** 正確呈現俄文字符
- 設定 `BarcodeGenerator` 產生 QR code
- 以 PNG 格式儲存輸出圖像
- 小技巧、常見陷阱與後續想法（例如加入商標或調整錯誤更正等）

不需要任何 Aspose 使用經驗；只要有基本的 Python 環境與對 QR code 的好奇心即可。

---

## 前置條件

在開始之前，請確保你已具備以下條件：

1. 已在機器上安裝 **Python 3.8 或更新版本**。  
2. **虛擬環境**（非必須但建議）以保持相依套件整潔。  
3. 能使用 **pip** 安裝 `aspose-barcode` 套件。  
4. 具有寫入權限的資料夾，用來儲存產生的 PNG 檔案。

如果上述任一項你不熟悉，請先暫停並完成設定——一旦準備就緒，接下來的步驟會非常簡單。

---

## 步驟 1：安裝 Aspose.Barcode for Python

第一件事是取得函式庫。Aspose 於 PyPI 發佈套件，只要執行以下 `pip` 指令即可：

```bash
pip install aspose-barcode
```

> **Pro tip:** 若你在虛擬環境中執行，能避免汙染全域 site‑packages。若遇到權限錯誤，可在指令前加上 `--user`，或使用 `sudo`（但在現代環境中通常不需要）。

安裝完成後，可使用以下指令驗證版本：

```python
import aspose.barcode as barcode
print(barcode.__version__)   # Should print something like 23.12.0
```

若能順利印出版本號，代表安裝成功，接下來就可以繼續。

---

## 步驟 2：建立 **Extended Codetext Builder** 實例

Aspose.Barcode 提供 `ExtCodetextBuilder` 類別，用來組合複雜的 QR 負載。它就像一個小型文字編輯器，會自動在每個區段前加上正確的控制字元。

```python
# Step 2: Initialise the builder
builder = barcode.generation.ExtCodetextBuilder()
```

為什麼要使用 Builder？直接手動串接原始位元組非常容易出錯；Builder 會保證正確的 ECI（Extended Channel Interpretation）切換，讓 QR 掃描器能正確解碼每種語言。

---

## 步驟 3：重新開始（可選，但建議）

如果你重複使用同一個 Builder 實例，呼叫 `clear()` 會清除先前的資料。這是一層安全網，避免舊有區段意外流入下一個 QR。

```python
# Step 3: Ensure the builder is empty
builder.clear()
```

第一次執行腳本時可以省略這行，但保留它能讓程式具備冪等性——在函式內部被多次呼叫時特別有用。

---

## 步驟 4：加入普通（未編碼）區段

大多數 QR code 會以簡單的 ASCII 字串開頭——可能是識別碼或 URL。`add_plain_codetext` 方法正是用來加入這類文字，且不會加入任何 ECI 標記。

```python
# Step 4: Add plain ASCII text
builder.add_plain_codetext("HelloWorld")
```

此範例使用 `"HelloWorld"` 作為佔位字串。請自行替換成你需要的內容，例如產品 SKU 或簡短訊息。

---

## 步驟 5：加入 **ECI‑編碼** 區段（UTF‑8 = 26）

接下來處理多語言部分。ECI 值 **26** 代表 UTF‑8，這是 Unicode 的事實標準。將 `26` 與俄文片語一起傳入，即可告訴 QR 掃描器在讀取後續字符前切換至 UTF‑8。

```python
# Step 5: Append a Russian phrase using UTF‑8 ECI (value 26)
builder.add_eci_codetext(26, "Привет")   # "Privet" means "Hello" in Russian
```

若需其他編碼，可將 `26` 換成其他 ECI 值（例如 `27` 代表 ISO‑8859‑1），Builder 會自動插入正確的控制字元。

---

## 步驟 6：取得合併後的 Extended Codetext

所有區段加入完畢後，取回最終字串供 QR 產生器使用。此字串內含不可見的控制序列，仍可列印以供除錯。

```python
# Step 6: Get the full extended codetext
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

在主控台上會看到雜亂的字元（因為內嵌了控制位元組），這是正常現象。關鍵是 Builder 已正確把普通與 Unicode 部分串接在一起。

---

## 步驟 7：設定 Barcode Generator

現在把延伸編碼文字交給 Aspose 的 `BarcodeGenerator`。將條碼類型設為 `QR`，並把合併後的字串指派給 `code_text`。

```python
# Step 7: Initialise the QR code generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR          # Choose QR symbology
generator.code_text = extended_codetext           # Use the extended codetext
```

此處亦可調整其他屬性，例如 `resolution`、`error_correction_level` 或 `foreground_color`。這些選項在 Aspose 文件中都有說明，但對於基本圖像而言，預設值已足夠。

---

## 步驟 8：儲存產生的 QR Code 圖片

最後，將 QR code 寫入磁碟。`save` 方法接受檔案路徑與可選的格式；PNG 是最安全的預設。

```python
# Step 8: Persist the QR code as a PNG file
output_path = "qr_extended.png"   # Adjust path as needed
generator.save(output_path)
print(f"QR code saved to {output_path}")
```

使用任何影像檢視器開啟 `qr_extended.png`。用智慧型手機掃描，應會分別顯示兩段訊息：「HelloWorld」與「Привет」。大多數現代 QR 讀取器會自動處理 ECI 切換。

---

## 完整範例程式

以下是可直接複製貼上執行的完整腳本：

```python
import aspose.barcode as barcode

# Initialise the extended codetext builder
builder = barcode.generation.ExtCodetextBuilder()
builder.clear()                                   # Ensure a clean start
builder.add_plain_codetext("HelloWorld")          # Plain ASCII segment
builder.add_eci_codetext(26, "Привет")            # Russian UTF‑8 segment
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# Configure the QR generator
generator = barcode.generation.BarcodeGenerator()
generator.symbology = barcode.Symbology.QR
generator.code_text = extended_codetext

# Save the image
output_file = "qr_extended.png"
generator.save(output_file)
print(f"QR code image saved as {output_file}")
```

**預期輸出**（主控台）：

```
Extended codetext: <binary data>   # appears garbled due to ECI markers
QR code image saved as qr_extended.png
```

開啟 `qr_extended.png` → 掃描 → 會看到「HelloWorld」接著「Привет」。

---

## 常見問題與邊緣案例

### 1. *如果需要超過兩個區段怎麼辦？*  
只要多次呼叫 `add_plain_codetext` 或 `add_eci_codetext` 即可。Builder 會維持正確的順序，QR code 會依加入的順序呈現每個區段。

### 2. *可以嵌入表情符號嗎？*  
可以——表情符號本身就是 Unicode 字元。使用 UTF‑8 ECI（值 26）並傳入表情字串，例如 `builder.add_eci_codetext(26, "🚀")`。支援的掃描器會顯示火箭表情。

### 3. *如果 QR 變得太密集怎麼處理？*  
QR code 有版本上限。若資料容量超過，Aspose 會自動升級至較大的版本，但圖像尺寸會變大。若想控制大小，可降低錯誤更正等級：

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorCorrectionLevel.L
```

### 4. *除了 UTF‑8，還需要考慮其他字元集嗎？*  
只有在必須配合舊系統使用特定編碼（例如 ISO‑8859‑1）時才需要。此時將 `26` 換成相對應的 ECI 值（請參考 Aspose 的 ECI 表）。對於大多數現代應用，UTF‑8 是最安全的選擇。

### 5. *如何在中心加入商標？*  
Aspose.Barcode 支援 `barcode.generator.QRCodeParameters.logo_image`。先用 Pillow 載入圖像（`from PIL import Image`），再指派：

```python
from PIL import Image
logo = Image.open("logo.png")
generator.parameters.qr.logo_image = logo
```

商標會被疊加，同時 Aspose 會自動調整安靜區以維持可掃描性。

---

## 生產環境使用小技巧

- **快取 Builder**：若同一筆資料會重複產生 QR，快取已建好的 Builder 可避免每次重新組合字串。  
- **驗證輸出**：使用單元測試搭配 `zxing` 或 `pyzbar` 解碼 QR，確保 ECI 切換正確。  
- **使用決定性的檔名**：可將 payload 的雜湊值加入檔名，避免覆寫既有圖檔。  
- **注意授權**：Aspose.Barcode 為商業軟體。開發階段的免費評估版足以測試，正式上線前需購買授權。

---

## 後續步驟與相關主題

現在你已掌握 **如何產生 QR code**，以下教學提供進一步的技巧與替代實作方式，幫助你在專案中發揮更多 API 功能。

- [如何在 Java 中使用 Aspose.BarCode 產生條碼圖片](/barcode/english/java/barcode-rendering-techniques/)
- [如何在 .NET 中使用 Aspose.BarCode 產生自訂長寬比例的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何在 .NET 中使用 Aspose.BarCode 建立 dotcode 延伸編碼文字](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}