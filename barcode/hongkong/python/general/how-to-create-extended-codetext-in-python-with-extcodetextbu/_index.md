---
category: general
date: 2026-10-28
description: 學習如何在 Python 中使用 ExtCodetextBuilder 建立擴充代碼文字。內容包括純文字與 ECI 編碼資料、逐步程式碼示範以及最佳實踐技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: zh-hant
lastmod: 2026-10-28
og_description: 使用 ExtCodetextBuilder 在 Python 中建立擴展代碼文字。本教學展示純文字與 ECI 編碼資料的處理、完整可執行的程式碼，以及常見陷阱。
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: 在 Python 中創建擴展程式碼文本 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: 如何使用 ExtCodetextBuilder 在 Python 中建立擴充程式碼文字
url: /zh-hant/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 ExtCodetextBuilder 建立擴充碼文字

如果您需要為條碼或 Data‑Matrix 應用程式 **建立擴充碼文字**，本指南將逐步說明如何在 Python 中完成。您將會看到如何結合純文字、為 Unicode 字元加入 ECI（Extended Channel Interpretation）區段，並取得一個已正確格式化、可直接編碼的字串。

本教學涵蓋從安裝所需函式庫到處理不支援的 ECI 值等邊緣情況的全部內容。完成後，您將擁有一個可重複使用的模式，能夠直接套用於任何需要 **建立擴充碼文字** 的專案。

## 您將學會

* 在建構混合編碼字串時 `ExtCodetextBuilder` 的角色。  
* 如何在同一個 builder 實例中 **加入純碼文字** 與 **加入 ECI 碼文字**。  
* 如何驗證最終輸出並排除常見陷阱。  
* 其他字元集的變體（例如 ISO‑8859‑1、Shift‑JIS）。  

### 前置條件

* Python 3.8 或更新版本。  
* `extcodetext` 套件（或提供 `ExtCodetextBuilder` 的類似函式庫）。使用以下方式安裝：

```bash
pip install extcodetext
```

* 對 Unicode 與 ECI 值有基本了解 – ECI 3 對應 UTF‑8，ECI 4 對應 ISO‑8859‑1，依此類推。

> **專業提示：** 隨手備有 ECI 編號參考表，可避免聲明的編碼與實際位元組序列不符的情況。

## 了解 ExtCodetextBuilder

`ExtCodetextBuilder` 是一個小工具，可串接多段文字片段，同時自動插入所需的 ECI 標記。ECI 標記會告訴後端條碼編碼器，接下來的位元組應使用哪種字元集。若沒有此標記，非 ASCII 字元將會被誤解。

此 builder 以三個簡單階段運作：

1. **建立** builder 實例。  
2. **附加** 純文字或 ECI 編碼的片段。  
3. **取得** 合併後的擴充碼文字字串。

以下將以具體程式碼說明每個階段。

## 步驟 1：建立 ExtCodetextBuilder 實例

第一行會建立用來保存所有片段的物件，此時不需要任何設定。

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*為何重要*：實例化 builder 會分配內部緩衝區。所有後續的 `add_*` 呼叫皆作用於該緩衝區，確保您指定的順序。

## 步驟 2：附加純文字（未編碼）資料

純文字資料指屬於預設字元集（通常為 ASCII）的字元。對此類片段使用 `add_plain_codetext`。

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*說明*：字串 `"ABC123"` 只包含 ASCII 字元，故不需要 ECI 標記。此方法僅將原始位元組附加至內部緩衝區。

## 步驟 3：附加需以 ECI 為前置的資料

當您需要嵌入 Unicode 字元（例如西里爾字母、日文或表情符號）時，必須告訴編碼器使用哪種字元集。這可透過 `add_eci_codetext(eci, text)` 完成。第一個參數是數值型的 ECI 編號；第二個參數則是實際文字。

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*為何使用 ECI 3*：根據 ISO/IEC 18004 規範，ECI 3 代表 UTF‑8。插入此標記後，條碼讀取器會以 UTF‑8 解碼後續位元組，從而保留西里爾字元。

### 處理其他編碼

若需 ISO‑8859‑1（西歐）可使用 `add_eci_codetext(4, "¡Hola!")`。對於 Shift‑JIS（日本）則使用 ECI 值 20：

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

務必確認目標條碼函式庫支援所選的 ECI 值；不支援的 ECI 會導致編碼失敗。

## 步驟 4：取得合併後的擴充碼文字字串

在加入所有片段後，呼叫 `get_extended_codetext()` 以取得最終字串。此字串會包含所有必要的 ECI 逸出序列。

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**預期輸出**（以 Python `repr` 方式顯示以利清晰）：

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*細部說明*：

- `ABC123` – 純 ASCII 片段。  
- `\x1B\x1D\x03` – UTF‑8 的 ECI 逸出序列（ESC GS 0x03）。  
- `Привет` – UTF‑8 編碼的西里爾文字。

實際的逸出位元組可能因函式庫實作而異，但邏輯順序始終為 *純文字 → ECI 標記 → Unicode 文字*。

## 完整可執行範例

將所有步驟整合起來，以下是一個可自行執行的腳本，您可以直接複製貼上為 `create_extended_codetext.py` 並立即執行。

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

執行此腳本會印出合併後的字串，可直接供任何接受擴充碼文字輸入的條碼編碼器使用。

## 常見陷阱與避免方法

| 症狀 | 可能原因 | 解決方法 |
|---|---|---|
| `UnicodeEncodeError` 在呼叫 `add_eci_codetext` 時 | 提供的字串包含在所選 ECI 中無法表示的字元 | 確認 ECI 與字串的實際編碼相符（例如，任何 UTF‑8 文字皆使用 ECI 3）。 |
| 最終輸出缺少 ECI 標記 | 不小心對非 ASCII 資料使用 `add_plain_codetext` | 對任何超出 ASCII 範圍的字元改用 `add_eci_codetext`。 |
| 條碼掃描器顯示亂碼 | 掃描器不支援所選的 ECI 值 | 選擇普遍支援的 ECI（UTF‑8 支援度高），或在目標語言允許時退回使用 ISO‑8859‑1。 |
| `get_extended_codetext` 回傳空字串 | 呼叫方法前未加入任何片段 | 確保至少執行一次 `add_*` 呼叫。 |

### 邊緣情況：空字串

呼叫 `add_plain_codetext("")` 或 `add_eci_codetext(3, "")` 並不會有問題；builder 只會忽略空的片段。然而，重複的空呼叫可能會產生不必要的 ECI 標記。請在加入前先檢查字串長度以避免此情況。

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## 擴充模式以因應動態資料

在實務應用中，您常會從使用者輸入或資料庫記錄組合擴充碼文字。以下程式碼示範一個迴圈，處理 `(type, value)` 元組的列表，其中 `type` 為 `"plain"` 或 `"eci"`。

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

此作法具備良好擴充性：您可以從 JSON、CSV 或 API 讀取片段定義，而無需變更核心建構邏輯。

## 測試輸出

簡單的單元測試可確保 builder 如預期運作。使用 `pytest`：

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

執行 `pytest` 應通過，證實 ECI 標記正確出現在預期位置。

## 相關概念，您可以進一步探索

* **條碼編碼函式庫** – 例如 `python-barcode`、`zxing` 綁定，直接接受擴充碼文字字串。  
* **ECI 表格參考** – ISO/IEC 18004 公布完整的數值 ECI 列表，可存為 Python 字典以供查詢。  
* **錯誤更正等級** – 產生 QR Code 時，將擴充碼文字與適當的錯誤更正等級（L、M、Q、H）結合，以提升掃描穩定性。  

## 結論

您現在已了解如何在 Python 中使用 `ExtCodetextBuilder` **建立擴充碼文字**。步驟相當簡單：

1. 建立 builder 實例。  
2. 根據需求附加純文字與 ECI 編碼的片段。  
3. 取得最終字串，並將其傳入條碼產生器。

依循上述模式，您即可處理任何 ASCII 與 Unicode 混合的資料，避免常見的編碼錯誤，並產生可在各種掃描器上正常運作的條碼字串。可嘗試不同的 ECI、將 builder 整合至資料流程中，為所有擴充碼文字需求奠定堅實基礎。

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}