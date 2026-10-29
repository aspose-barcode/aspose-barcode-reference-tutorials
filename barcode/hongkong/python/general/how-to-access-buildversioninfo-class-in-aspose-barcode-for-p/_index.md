---
category: general
date: 2026-10-28
description: 學習如何在 Aspose.Barcode Python SDK 中存取 BuildVersionInfo 類別，以取得產品名稱、版本與發佈日期。包括完整程式碼範例與最佳實踐。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- access buildversioninfo class
- Aspose Barcode Python
- retrieve library version
- BuildVersionInfo example
- barcode SDK metadata
language: zh-hant
lastmod: 2026-10-28
og_description: 存取 Aspose.Barcode Python SDK 中的 BuildVersionInfo 類別，以取得產品名稱、版本與發佈日期。請參考此完整指南，內含可執行程式碼。
og_image_alt: Console output showing product name, version and release date from BuildVersionInfo
  class
og_title: 如何在 Aspose.Barcode for Python 中存取 BuildVersionInfo 類別
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to access BuildVersionInfo class in Aspose.Barcode Python
    SDK to retrieve product name, version and release date. Includes full code example
    and best practices.
  headline: How to access BuildVersionInfo class in Aspose.Barcode for Python
  type: TechArticle
- description: Learn how to access BuildVersionInfo class in Aspose.Barcode Python
    SDK to retrieve product name, version and release date. Includes full code example
    and best practices.
  name: How to access BuildVersionInfo class in Aspose.Barcode for Python
  steps:
  - name: Import the class that provides build information
    text: '```python # Step 1: Import the class that provides build information from
      aspose.barcode import BuildVersionInfo ```'
  - name: Create an instance to access the library's metadata
    text: '```python # Step 2: Create an instance to access the library''s metadata
      build_info = BuildVersionInfo() ```'
  - name: Display the product name
    text: '```python # Step 3: Display the product name print("Product:", build_info.PRODUCT)
      ```'
  - name: Show the major and minor version numbers
    text: '```python # Step 4: Show the major and minor version numbers print("Version:",
      f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}") ```'
  - name: Output the release date of this build
    text: '```python # Step 5: Output the release date of this build print("Release
      date:", build_info.RELEASE_DATE) ```'
  - name: Full script
    text: 'Putting all steps together yields a concise, self‑contained script:'
  - name: Verifying the SDK version at runtime
    text: 'In CI/CD pipelines you may want to abort the build if the installed version
      does not match a required minimum. The following snippet demonstrates a simple
      guard:'
  - name: Dealing with missing attributes
    text: 'Although `BuildVersionInfo` is stable, older releases (pre‑20.0) used slightly
      different attribute names. To maintain compatibility, you can fall back gracefully:'
  - name: Logging instead of printing
    text: 'For production services, replace `print` with a structured logger:'
  type: HowTo
tags:
- Aspose
- Python
- Barcode
- SDK
title: 如何在 Aspose.Barcode for Python 中存取 BuildVersionInfo 類別
url: /zh-hant/python/general/how-to-access-buildversioninfo-class-in-aspose-barcode-for-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Barcode for Python 中存取 BuildVersionInfo 類別

如果您需要 **存取 BuildVersionInfo 類別**（BuildVersionInfo class）於 Aspose.Barcode Python SDK，本指南將提供完整、可直接執行的解決方案。了解精確的產品名稱、版本號碼與發行日期，可協助您驗證已部署的程式庫版本是否正確，這對於除錯與合規性檢查相當重要。

在本教學中，您將學會如何匯入此類別、建立實例，並顯示其提供的中繼資料。我們也會說明安裝步驟、常見陷阱，以及如何將程式碼套用於自動化建置檢查。完成後，您即可以程式方式取得程式庫版本，並將資訊整合至日誌或 UI 面板中。

## 前置條件

在開始之前，請確保您已具備：

* 在開發機上安裝 **Python 3.8** 或更新版本。  
* 可連網下載 Aspose.Barcode 套件（自 PyPI）。  
* 具備基本的命令列執行 Python 腳本的經驗。

Aspose.Barcode 為純 Python 發行版，無需額外系統相依性。

## 安裝 Aspose.Barcode for Python

第一步是將 Aspose.Barcode 套件加入您的環境。使用 `pip` 安裝最新的穩定版：

```bash
pip install aspose-barcode
```

> **小技巧：** 若您在虛擬環境中工作（建議），請先啟動該環境再執行上述指令，以免污染全域 site‑packages。

`aspose-barcode` wheel 已內建原生二進位檔，您不必自行編譯任何程式。

## 如何存取 BuildVersionInfo 類別

SDK 安裝完成後，即可直接使用 `BuildVersionInfo` 類別。以下各節將逐行說明程式碼、解釋其必要性，並示範預期的輸出結果。

### 步驟 1：匯入提供建置資訊的類別

```python
# Step 1: Import the class that provides build information
from aspose.barcode import BuildVersionInfo
```

`BuildVersionInfo` 類別位於 `aspose.barcode` 命名空間。將其單獨匯入，可將中繼資料功能與條碼 API 其他部分分離，讓腳本保持輕量。

### 步驟 2：建立實例以取得程式庫的中繼資料

```python
# Step 2: Create an instance to access the library's metadata
build_info = BuildVersionInfo()
```

此類別的建構子不需要任何參數，因為中繼資料已於建置時嵌入於組件中。建立的物件會公開數個唯讀屬性。

### 步驟 3：顯示產品名稱

```python
# Step 3: Display the product name
print("Product:", build_info.PRODUCT)
```

`PRODUCT` 會回傳類似 `"Aspose.Barcode for Python via .NET"` 的可讀字串，指出確切的產品系列。

### 步驟 4：顯示主要與次要版本號

```python
# Step 4: Show the major and minor version numbers
print("Version:", f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}")
```

`PRODUCT_MAJOR` 與 `PRODUCT_MINOR` 為整數欄位，合併即構成 SDK 的語意版本（例如 `23.9`）。使用 f‑string 可保證輸出為 `major.minor` 格式。

### 步驟 5：輸出此建置的發行日期

```python
# Step 5: Output the release date of this build
print("Release date:", build_info.RELEASE_DATE)
```

`RELEASE_DATE` 以 `YYYY-MM-DD` 格式提供二進位檔封裝的日期，對於產出合規報告相當有用。

### 完整腳本

將上述步驟整合，即可得到簡潔且自包含的腳本：

```python
# access_buildversioninfo_example.py

# Install the SDK first:
#   pip install aspose-barcode

from aspose.barcode import BuildVersionInfo

def main() -> None:
    """Retrieve and print Aspose.Barcode library metadata."""
    build_info = BuildVersionInfo()

    print("Product:", build_info.PRODUCT)
    print("Version:", f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}")
    print("Release date:", build_info.RELEASE_DATE)

if __name__ == "__main__":
    main()
```

#### 預期輸出

以目前（2026 年 10 月）最新的 SDK 執行腳本，會產生類似以下內容：

```
Product: Aspose.Barcode for Python via .NET
Version: 23.9
Release date: 2026-09-15
```

若您看到的數字不同，表示您使用的是較舊或較新的建置——可利用此輸出驗證生產環境中的版本是否符合預期。

## 處理例外情況與最佳實踐

### 在執行時驗證 SDK 版本

在 CI/CD 流程中，若安裝的版本未達最低要求，可直接中止建置。以下程式碼示範簡易的防護機制：

```python
MIN_MAJOR = 23
MIN_MINOR = 8

if (build_info.PRODUCT_MAJOR, build_info.PRODUCT_MINOR) < (MIN_MAJOR, MIN_MINOR):
    raise RuntimeError(
        f"Unsupported Aspose.Barcode version {build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}. "
        f"Minimum required is {MIN_MAJOR}.{MIN_MINOR}."
    )
```

### 應對缺少屬性的情況

雖然 `BuildVersionInfo` 已相當穩定，但早期版本（20.0 之前）使用的屬性名稱略有差異。為維持相容性，可採取以下容錯寫法：

```python
product = getattr(build_info, "PRODUCT", "Unknown")
major = getattr(build_info, "PRODUCT_MAJOR", 0)
minor = getattr(build_info, "PRODUCT_MINOR", 0)
release = getattr(build_info, "RELEASE_DATE", "N/A")
```

### 使用日誌取代直接印出

於正式服務中，建議將 `print` 改為結構化日誌：

```python
import logging

logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", build_info.PRODUCT)
logger.info("Version: %s.%s", build_info.PRODUCT_MAJOR, build_info.PRODUCT_MINOR)
logger.info("Release date: %s", build_info.RELEASE_DATE)
```

此做法可無縫整合至 `loguru` 或雲端原生觀測堆疊等框架。

## 相關概念，供您進一步探索

* **使用 Aspose.Barcode 產生條碼** – 了解如何建立 QR Code、Code128、DataMatrix 等影像。  
* **讀取條碼中繼資料** – 使用 `BarCodeReader` 從影像中擷取編碼資料。  
* **在 UI 中嵌入版本資訊** – 於 Flask 或 FastAPI 的 Web 儀表板上顯示 SDK 版本。

上述主題皆以 **取得程式庫版本資訊** 為基礎，確保您隨時掌握執行的版本。

## 結論

您現在已掌握如何在 Aspose.Barcode Python SDK 中 **存取 BuildVersionInfo 類別**，取得產品名稱、主要/次要版本號以及發行日期，並能處理常見的例外情況。將此中繼資料整合至日誌或 UI 元件，可讓您確信使用的 SDK 建置正確，這對除錯、合規以及自動化測試皆相當關鍵。

歡迎將範例套用於您的 CI 流程、加入更進階的版本檢查，或與其他 Aspose.Barcode 功能結合使用。祝開發順利！

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}