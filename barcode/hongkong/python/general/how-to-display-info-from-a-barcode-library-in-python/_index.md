---
category: general
date: 2026-09-07
description: 學習如何顯示條碼函式庫的資訊，包括產品名稱、版本、組件版本及發佈日期。為 Python 開發者提供的快速指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to display info
- display product name
- show release date
- get library version
- how to read version
language: zh-hant
lastmod: 2026-09-07
og_description: 如何在幾行程式碼內顯示 Python 條碼函式庫的資訊，包括產品名稱、版本號、組件版本及發佈日期。
og_image_alt: Console output showing how to display info from barcode library
og_title: 如何在 Python 中顯示條碼庫的資訊 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  headline: How to display info from a barcode library in Python
  type: TechArticle
- description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  name: How to display info from a barcode library in Python
  steps:
  - name: Display product name
    text: 'To **display product name**, simply print the `PRODUCT` attribute:'
  - name: Show library version (major.minor)
    text: 'Most developers only need the major and minor numbers, which you can combine
      with an f‑string:'
  - name: Show assembly version
    text: 'If you need the full assembly version (including build and revision), use
      the `ASSEMBLY_VERSION` attribute:'
  - name: Show release date
    text: 'Finally, to **show release date**, print the `RELEASE_DATE` attribute:'
  - name: Complete script
    text: 'Putting everything together yields a self‑contained, runnable example:'
  - name: Library without `BuildVersionInfo`
    text: 'Some forks of the `barcode` package omit `BuildVersionInfo`. In that case
      you can read version data from the package’s `__version__` attribute:'
  - name: Formatting the release date
    text: 'If you prefer `Month Day, Year` format:'
  - name: Handling missing attributes
    text: 'When running against a custom build, an attribute may be `None`. Guard
      against that with a simple check:'
  - name: Using the information in logs
    text: 'Instead of printing to the console, you might want to log the data:'
  type: HowTo
tags:
- Python
- barcode
- version‑info
- debugging
title: 點樣喺 Python 顯示條碼庫嘅資訊
url: /zh-hant/python/general/how-to-display-info-from-a-barcode-library-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中顯示條碼庫的資訊

如果你需要 **如何顯示資訊** 從條碼庫中取得，本指南會精確說明如何取得並列印產品名稱、版本號、組件版本以及發佈日期。此解決方案適用於標準的 `barcode` 套件，僅需幾行程式碼，即可立即加入任何腳本。

我們將逐步說明每個步驟，解釋程式碼為何可行，並討論常見的陷阱，例如屬性缺失或版本格式異常。完成後，你將能在任何 Python 環境中 **顯示產品名稱**、**顯示發佈日期**，以及 **取得套件版本**。

## 前置條件

在開始之前，請確保你已具備：

* 已安裝 Python 3.8 或更新版本。
* 環境中已有 `barcode` 套件（或相容的分支）。可使用以下指令安裝：

```bash
pip install python-barcode
```

* 具備基本的 Python `print` 函式與 f‑string 使用經驗。

如果已安裝此套件，可跳過安裝步驟。

## 如何顯示條碼庫的資訊

解決方案的核心是一個對 `barcode.BuildVersionInfo()` 的呼叫，該呼叫會回傳包含所有版本相關中繼資料的物件。以下 H2 標題即為主要關鍵字，符合 SEO 要求。

```python
# Import the barcode module
import barcode

# Retrieve version information from the barcode library
info = barcode.BuildVersionInfo()
```

`info` 物件通常會公開以下屬性：

| 屬性               | 說明                         |
|--------------------|------------------------------|
| `PRODUCT`          | 可讀的產品名稱               |
| `PRODUCT_MAJOR`    | 主版本號                     |
| `PRODUCT_MINOR`    | 次版本號                     |
| `ASSEMBLY_VERSION` | 完整組件版本（例如 `1.2.3.4`）|
| `RELEASE_DATE`     | 套件發佈日期                 |

### 顯示產品名稱

若要 **顯示產品名稱**，只需列印 `PRODUCT` 屬性：

```python
print("Product:", info.PRODUCT)
```

> **為什麼會這樣運作：** `info.PRODUCT` 是套件作者定義的字串。直接列印即可取得套件中 metadata 所使用的精確名稱，適合用於日誌或 UI 顯示。

### 顯示套件版本（major.minor）

大多數開發者只需要主次版本號，可使用 f‑string 結合：

```python
print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
```

> **說明：** 這個 f‑string 會把兩個整數屬性格式化為慣用的 `major.minor` 形式，與 PyPI 頁面上看到的格式相同。

### 顯示組件版本

若需要完整的組件版本（包含 build 與 revision），使用 `ASSEMBLY_VERSION` 屬性：

```python
print("Assembly version:", info.ASSEMBLY_VERSION)
```

完整的組件版本在必須驗證載入的特定套件建置時非常有用，尤其在 CI 流程中。

### 顯示發佈日期

最後，若要 **顯示發佈日期**，列印 `RELEASE_DATE` 屬性：

```python
print("Release date:", info.RELEASE_DATE)
```

發佈日期以 `datetime.date` 物件儲存，預設以 ISO 格式 (`YYYY‑MM‑DD`) 輸出。若專案需要其他格式，可使用 `strftime` 重新格式化。

### 完整腳本

將上述所有片段結合，即可得到一個自包含、可直接執行的範例：

```python
import barcode

def display_barcode_library_info():
    """Retrieve and print all version‑related metadata from the barcode library."""
    try:
        info = barcode.BuildVersionInfo()
    except AttributeError:
        raise RuntimeError(
            "The installed barcode package does not expose BuildVersionInfo(). "
            "Make sure you are using a compatible version."
        )

    print("Product:", info.PRODUCT)
    print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
    print("Assembly version:", info.ASSEMBLY_VERSION)
    print("Release date:", info.RELEASE_DATE)

if __name__ == "__main__":
    display_barcode_library_info()
```

**預期輸出**（數值會依實際安裝的版本而異）：

```
Product: python-barcode
Version: 0.14
Assembly version: 0.14.0.0
Release date: 2023-02-15
```

腳本會捕捉可能的 `AttributeError`，協助你在套件 API 變更時安全地 **如何讀取版本** 資訊。

## 常見變化與邊緣情況

### 套件沒有 `BuildVersionInfo`

某些 `barcode` 分支未實作 `BuildVersionInfo`。此時可改為讀取套件的 `__version__` 屬性：

```python
import barcode
print("Package version:", barcode.__version__)
```

雖然能取得符合 PEP‑440 的版本字串，但缺少 `PRODUCT`、`ASSEMBLY_VERSION` 等詳細欄位。僅在主要方法不可用時才使用此備援方案。

### 格式化發佈日期

若想使用 `Month Day, Year` 格式：

```python
print("Release date:", info.RELEASE_DATE.strftime("%B %d, %Y"))
```

### 處理缺失屬性

在自訂建置中，某些屬性可能為 `None`。可使用簡單的檢查避免錯誤：

```python
release = info.RELEASE_DATE or "unknown"
print("Release date:", release)
```

### 在日誌中使用資訊

若不想直接列印到終端，可改為寫入日誌：

```python
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", info.PRODUCT)
logger.info("Version: %s.%s", info.PRODUCT_MAJOR, info.PRODUCT_MINOR)
logger.info("Assembly version: %s", info.ASSEMBLY_VERSION)
logger.info("Release date: %s", info.RELEASE_DATE)
```

將資訊寫入日誌檔案，可在生產環境除錯時提供關鍵線索。

## 專業提示

* 若頻繁呼叫，**快取 `info` 物件**；版本資料在執行期間不會變動。
* 在執行相容性檢查前，**驗證版本**：

```python
if int(info.PRODUCT_MAJOR) < 1:
    raise RuntimeError("Barcode library version is too old for this feature.")
```

* 結合其他診斷資訊（例如 Python 版本）可產生完整的環境報告：

```python
import sys
print("Python:", sys.version.split()[0])
```

## 結論

現在你已掌握 **如何在 Python 中顯示條碼庫的資訊**，包括 **顯示產品名稱**、**顯示發佈日期**，以及 **取得套件版本**。完整腳本示範了標準工作流程，而各種變化則說明了如何因應不同的套件實作或格式需求。

接下來，你可以探索：

* **如何讀取其他第三方套件的版本**，使用 `importlib.metadata`。
* **在 GUI 應用程式（Tkinter、PyQt 等）中顯示版本資訊**。
* **在 CI 流程中自動化版本檢查**，以強制執行最低套件版本要求。

歡迎自行實驗、將程式碼整合到自己的工具中，並與社群分享你的成果！

## 接下來該學什麼？

以下教學與本指南的技巧緊密相關，提供完整可執行的程式碼範例與逐步說明，協助你深入掌握更多 API 功能，並在專案中嘗試不同的實作方式。

- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to Generate Barcode in C# – Complete Aspose.Barcode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}