---
category: general
date: 2026-09-29
description: 在 Python 中顯示產品名稱，同時列印發佈日期，並從條碼函式庫取得版本資訊。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: zh-hant
lastmod: 2026-09-29
og_description: 在 Python 中顯示產品名稱，並學習如何列印發佈日期、取得版本號，以及以簡短程式碼顯示次要版本。
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: 在 Python 中顯示產品名稱與版本資訊
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: 在 Python 中顯示產品名稱與版本資訊
url: /zh-hant/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Python 中顯示產品名稱與版本資訊

如果您需要 **顯示套件的產品名稱**，本指南將一步步教您如何做到。您亦會學會 **列印發佈日期**、**取得版本號**，以及 **顯示次要版本** 的簡潔 Python 程式寫法。

許多開發者在整合條碼掃描或產生功能時，必須將套件的中繼資料呈現給使用者或寫入日誌。本教學涵蓋取得並可靠呈現這些資訊的全部要點。

## 您將學會

* 從 `barcode` 套件取得版本資訊。  
* **顯示產品名稱** 以及主要與次要版本號。  
* **以人類可讀的格式列印發佈日期**。  
* 優雅地處理屬性缺失的情況。  

**先決條件**  
* Python 3.8 或更新版本。  
* 已安裝 `barcode` 套件（可使用 `pip install python-barcode` 或提供 `BuildVersionInfo` 的相應函式庫）。  

---

## 如何在 Python 中顯示產品名稱與版本資訊

第一步是匯入套件，並呼叫回傳版本資訊物件的方法。該物件包含 `PRODUCT`、`PRODUCT_MAJOR`、`PRODUCT_MINOR`、`RELEASE_DATE` 等屬性。

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**為什麼這樣可行**  
`BuildVersionInfo()` 會回傳一個輕量級物件，屬性在匯入時即已填入。直接存取屬性可避免額外 I/O，且保證顯示的資料與實際使用的套件版本相符。

### 預期輸出

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

實際數值會依安裝的 barcode 套件版本而異。

---

## 如何從 barcode 套件取得版本號

如果您只需要版本號，完全可以省略產品名稱的列印，直接關注數值欄位。

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*`PRODUCT_MAJOR` 與 `PRODUCT_MINOR` 屬性遵循語意化版本號規範，讓您能以程式方式比較版本。*

---

## 如何列印發佈日期

發佈日期以 `YYYY‑MM‑DD` 文字格式儲存。若要以其他語系呈現，先將其轉換為 `datetime` 物件。

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**小技巧：** 在解析前先驗證日期字串，避免套件變更格式時拋出 `ValueError`。

---

## 同時顯示次要版本與主要版本

有時需要單獨顯示次要版本，例如在記錄相容性警告時。

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**進階技巧：** 可利用次要版本觸發功能旗標：

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## 處理屬性缺失（邊緣情況）

較舊版本的 barcode 套件可能不會公開全部屬性。使用 `getattr` 搭配合理的預設值來包裝屬性存取。

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

此模式可確保腳本不會因缺少欄位而當機，對於可能同時使用多個套件版本的 CI 流程特別穩健。

---

## 完整、可執行的範例

以下是結合所有最佳實踐的完整腳本：屬性驗證、日期格式化與清晰輸出。

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

在已安裝 barcode 套件的系統上執行此腳本，會得到與前述範例類似的輸出，同時具備防止缺少欄位的保護，且日期會以友善的方式呈現。

---

## 結論

您現在已掌握如何 **顯示產品名稱**、**列印發佈日期**、**取得版本號**、**列印產品資訊**，以及 **顯示次要版本** 的簡易 Python 工作流程。完整範例示範了可靠的屬性存取、日期處理與版本比較——這些技巧可套用於任何提供中繼資料物件的第三方套件。

**後續步驟**

* 探索 barcode 套件的其他中繼資料方法，例如 `BuildCommitInfo()`。  
* 將輸出整合至日誌框架（例如 `logging.info`）。  
* 以程式方式比較版本，強制應用程式的最低版本需求。

歡迎嘗試不同的輸出格式，或將資訊寫入檔案以作審計用途。祝開發愉快！  

![顯示產品名稱與版本細節的終端機輸出](image.png "終端機輸出")

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能在此基礎上進一步擴展技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並探索在專案中實作的其他方式。

- [使用 Python barcode 套件顯示產品名稱 – 步驟說明指南](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [如何在 Python 中列印 Aspose.Barcode 版本](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [如何在 Python 中使用 Aspose.BarCode 產生條碼](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}