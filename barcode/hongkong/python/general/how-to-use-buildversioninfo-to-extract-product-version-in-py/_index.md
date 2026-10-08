---
category: general
date: 2026-09-13
description: 學習如何在 Aspose.BarCode for Python 中使用 BuildVersionInfo，僅需簡單幾步即可提取產品版本及其他元資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use buildversioninfo
- extract product version
language: zh-hant
lastmod: 2026-09-13
og_description: 在 Aspose.BarCode for Python 中使用 BuildVersionInfo 提取產品版本、組件版本和發佈日期，並提供清晰的逐步指南。
og_image_alt: Screenshot showing use BuildVersionInfo output with version details
og_title: 在 Python 中使用 BuildVersionInfo – 快速提取產品版本
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to use BuildVersionInfo in Aspose.BarCode for Python to extract
    product version and other metadata in a few simple steps.
  headline: How to use BuildVersionInfo to extract product version in Python
  type: TechArticle
tags:
- Aspose
- Python
- Barcode
- VersionInfo
title: 如何在 Python 中使用 BuildVersionInfo 提取產品版本
url: /zh-hant/python/general/how-to-use-buildversioninfo-to-extract-product-version-in-py/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Python 中使用 BuildVersionInfo 取得產品版本

如果您需要 **使用 BuildVersionInfo** 讀取 Aspose.BarCode 的中繼資料，本指南將逐步說明如何操作。完成本教學後，您將能夠 **提取產品版本** 資訊、組件版本、檔案版本以及發佈日期，只需幾行程式碼。

許多開發者將版本資訊視為事後才處理的項目，但在執行時取得正確的版本有助於除錯、記錄與合規性檢查。本教學將說明如何安裝套件、建立 `BuildVersionInfo` 物件、取得各屬性，並列印整潔的報告。無需參考外部文件——所有資訊皆在此處。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* 取得 **Aspose.BarCode for Python via .NET** 套件（`aspose.barcode` 模組）。
* 具備 Python 匯入與 `print` 陳述式的基本概念。

如果尚未安裝此函式庫，請執行以下指令：

```bash
pip install aspose-barcode
```

以下步驟假設套件已在您的環境中可用。

## 步驟 1：匯入 Aspose.BarCode 套件

首先必須匯入 `aspose.barcode` 命名空間。這樣即可存取所有類別，包括 `BuildVersionInfo`。

```python
# Step 1: Import the Aspose.BarCode package
import aspose.barcode as bc
```

> **為何重要：** 匯入套件會向 Python 註冊 .NET 組件，使得 `BuildVersionInfo` 類別能被實例化。若省略匯入，會拋出 `ModuleNotFoundError`。

## 步驟 2：使用 BuildVersionInfo 取得函式庫中繼資料

現在您可以 **使用 BuildVersionInfo** 查詢 Aspose 在建置時嵌入的版本細節。建立此物件不需要任何參數。

```python
# Step 2: Create a BuildVersionInfo object to query library metadata
version_info = bc.BuildVersionInfo()
```

> **說明：** `BuildVersionInfo` 建構函式會從底層組件載入靜態欄位。它是一個輕量且唯讀的物件，您可以安全地在整個應用程式中重複使用。

## 步驟 3：提取產品版本細節

取得 `version_info` 實例後，您可以 **提取產品版本** 以及相關屬性。每個屬性皆回傳字串，您可以將其儲存、記錄或比較。

```python
# Step 3: Retrieve individual version properties from the object
assembly_version = version_info.ASSEMBLY_VERSION   # e.g., "23.12.0.0"
file_version     = version_info.FILE_VERSION       # e.g., "23.12.0.0"
product_title    = version_info.PRODUCT            # e.g., "Aspose.BarCode for Python via .NET"
major_version    = version_info.PRODUCT_MAJOR      # e.g., "23"
minor_version    = version_info.PRODUCT_MINOR      # e.g., "12"
release_date     = version_info.RELEASE_DATE       # e.g., "2023-12-01"
```

> **為何需要每個欄位**
> * **Assembly version** – 識別執行時載入的精確二進位版本。
> * **File version** – 與檔案的版本資源相符；在 Windows 檔案屬性檢查時很有用。
> * **Product title** – 可在人機介面日誌中顯示的可讀名稱。
> * **Major / Minor version** – 讓您能根據版本範圍實作條件邏輯。
> * **Release date** – 協助您驗證正在執行的是否為近期建置，對安全修補至關重要。

### 邊緣情況：屬性缺失

如果未來的 Aspose 版本移除某個屬性，存取時會拋出 `AttributeError`。可使用帶預設值的 `getattr` 來防護：

```python
assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
```

## 步驟 4：顯示收集的版本資訊

最後，將收集的資料以整齊對齊的格式列印。此步驟為可選，但可示範在應用程式啟動時如何記錄版本資訊。

```python
# Step 4: Display the gathered version information
print("Assembly version :", assembly_version)
print("File version     :", file_version)
print("Product title    :", product_title)
print("Major version    :", major_version)
print("Minor version    :", minor_version)
print("Release date     :", release_date)
```

**預期輸出**（根據已安裝的函式庫版本，值會不同）：

```
Assembly version : 23.12.0.0
File version     : 23.12.0.0
Product title    : Aspose.BarCode for Python via .NET
Major version    : 23
Minor version    : 12
Release date     : 2023-12-01
```

> **專業提示：** 將此輸出重新導向至日誌檔案，或嵌入應用程式的「About」對話框，讓最終使用者快速取得版本資訊。

## 完整、可執行的範例

將所有部件組合在一起，以下是一個可直接複製貼上並立即執行的獨立腳本：

```python
import aspose.barcode as bc

def show_aspose_version():
    """
    Retrieves and prints Aspose.BarCode version information using BuildVersionInfo.
    """
    version_info = bc.BuildVersionInfo()

    # Safely fetch each attribute, falling back to 'unknown' if the field vanishes
    assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
    file_version     = getattr(version_info, "FILE_VERSION", "unknown")
    product_title    = getattr(version_info, "PRODUCT", "unknown")
    major_version    = getattr(version_info, "PRODUCT_MAJOR", "unknown")
    minor_version    = getattr(version_info, "PRODUCT_MINOR", "unknown")
    release_date     = getattr(version_info, "RELEASE_DATE", "unknown")

    print("Assembly version :", assembly_version)
    print("File version     :", file_version)
    print("Product title    :", product_title)
    print("Major version    :", major_version)
    print("Minor version    :", minor_version)
    print("Release date     :", release_date)

if __name__ == "__main__":
    show_aspose_version()
```

在已安裝 `aspose-barcode` 的機器上執行此腳本，即會列印先前顯示的版本區塊。

## 常見問題與變化

| Question | Answer |
|----------|--------|
| **如果我需要在 JSON payload 中取得版本？** | 將字典序列化：<br>`import json; print(json.dumps({...}, indent=2))` |
| **我可以在程式中比較版本嗎？** | 將 `major_version` 與 `minor_version` 轉為整數，並根據需要使用 `<` 或 `>` 進行比較。 |
| **這在 Linux/macOS 上可用嗎？** | 可以。Aspose.BarCode 使用的 .NET core 執行環境是跨平台的，因此相同的 Python 程式碼可在任何地方執行。 |
| **如何處理缺少 Aspose 安裝的情況？** | 將匯入包裹在 try/except 區塊，並提供友善的錯誤訊息：<br>`except ImportError: print("Aspose.BarCode is not installed. Run pip install aspose-barcode")` |

## 生產環境使用技巧

* **快取 `BuildVersionInfo` 物件**：如果需要多次取得版本資料，將其快取在模組層級變數中成本低廉。
* **在正常執行時使用 INFO 級別記錄**，需要更細節的輸出時切換至 DEBUG。
* **結合其他 Aspose 診斷**（例如 `License.IsValid`）以建立完整的健康檢查端點。

## 結論

現在您已了解如何在 Python 中 **使用 BuildVersionInfo** 來 **提取產品版本** 以及 Aspose.BarCode 函式庫的相關中繼資料。完整腳本示範了跨平台、具防禦性的寫法，並能因應 API 未來可能的變更。

接下來，您可以探索：

* 使用取得的版本號在啟用高級條碼功能前強制最低版本要求。
* 將版本檢查整合至 CI/CD 流程，自動驗證已部署最新的 Aspose.BarCode 建置。
* 擴充腳本以取得授權資訊（`bc.License`），完成完整的執行時診斷報告。

祝開發愉快，並讓您的應用程式保持版本感知！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何列印 Aspose.Barcode（Python）版本](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [如何在 Aspose.BarCode for Python 中設定授權 – 完整指南](/barcode/english/python/general/how-to-set-license-in-aspose-barcode-for-python-complete-gui/)
- [在 Python 中建立條碼 PNG – 完整 Aspose.Barcode 指南](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}