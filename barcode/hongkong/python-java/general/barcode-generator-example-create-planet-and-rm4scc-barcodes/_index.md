---
category: general
date: 2026-10-24
description: 條碼產生器範例，示範如何使用 Python 建立 Planet 條碼以及設定條碼高度。請依照步驟指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: zh-hant
lastmod: 2026-10-24
og_description: 條碼產生器範例，示範如何在 Python 中建立 Planet 條碼以及設定條碼高度。取得完整、可執行的解決方案。
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: 條碼產生器範例 – 建立 Planet 與 RM4SCC 條碼
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: 條碼產生器範例 – 建立 Planet 與 RM4SCC 條碼並自訂高度
url: /zh-hant/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器範例 – 使用自訂高度建立 Planet 與 RM4SCC 條碼

如果您在尋找 **barcode generator example**，本指南提供完整、可直接執行的解決方案。您將會看到 **how to create planet barcode** 圖片的製作方式、學習 **how to set barcode height** 的設定方法，並了解自動與手動尺寸之間的細微差異。

本教學示範兩個實務情境：使用預設（自動）高度的 Planet 條碼，以及將高度強制為 100 px 的 RM4SCC 條碼。完成後，您即可使用單一且一致的 API 為任何支援的條碼類型產生 PNG 檔案。

## Prerequisites

在開始之前，請確保您已具備：

* 已安裝 Python 3.8 或更新版本。
* `aspose-barcode` 套件（或任何提供 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 的函式庫）。可使用以下指令安裝  

  ```bash
  pip install aspose-barcode
  ```
* 具備寫入 PNG 檔案之資料夾的寫入權限。

不需要額外的系統相依性。

## Overview of the solution

**barcode generator example** 的核心由三個可重複使用的步驟組成：

1. **Instantiate** 一個 `BarcodeGenerator`，並指定欲使用的 `EncodeTypes` 值與資料字串。
2. **Configure** X‑dimension（模組寬度），必要時設定條碼高度。
3. **Save** 圖片至磁碟，格式為 PNG。

兩個範例皆共用第 1 步與第 3 步；第 2 步因 Planet 條碼使用函式庫的自動高度計算，而 RM4SCC 條碼則示範 **how to set barcode height** 的手動設定方式，故有所不同。

以下為高階流程圖示：

![條碼產生器範例，展示不同高度的 Planet 與 RM4SCC 條碼](barcode-example.png)

*Alt text: 條碼產生器範例，展示不同高度的 Planet 與 RM4SCC 條碼。*

## How to create planet barcode – automatic height

Planet 條碼屬於多國郵政服務常用的郵件條碼族群。大多情況下，您只需讓 SDK 自行決定高度，即可確保不同資料長度下的視覺比例正確。

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Why this works**

* `EncodeTypes.Planet` 告訴函式庫使用 Planet 符號。
* 將 `x_dimension.pixels` 設為 4，讓每個模組寬度為 4 px，這是列印標籤的常見預設值。
* 未明確設定高度；SDK 會根據資料與 X‑dimension 計算最佳高度，這也是最簡單的 **barcode generator example** 用於郵遞編碼的原因。

**Expected result**

會產生一個名為 `PostalPlanetBarHeightAuto.png` 的 2‑D PNG 檔案，內含清晰的 Planet 條碼。高度約為 30 px（視函式庫版本而定），寬度則為 4 px × 模組數量。

## How to set barcode height – custom RM4SCC example

RM4SCC 是另一種常見的郵件條碼，通常需要固定高度以符合標籤範本。本段說明 **how to set barcode height** 為精確的像素值。

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Why this works**

* `EncodeTypes.RM4SCC` 選擇 RM4SCC 符號。
* X‑dimension 保持 4 px，以確保兩種條碼的模組大小一致。
* `bar_height.pixels = 100` 強制條碼高度為 100 px，覆寫自動計算。當版面需求特定尺寸時，這是建議的 **how to set barcode height** 做法。

**Expected result**

會產生一個名為 `PostalRM4SCCBarHeight100Pixels.png` 的 PNG 檔案，顯示高度為 100 px 的 RM4SCC 條碼。寬度仍受 X‑dimension 控制，而高度固定為 100 px，適合高解析度標籤印表機。

## Full script – combine both examples

若您希望使用單一腳本同時產生兩張圖片，請將以下程式碼複製至 `generate_barcodes.py` 並執行。

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Explanation of the script**

* 兩個輔助函式讓程式碼符合 DRY（Don’t Repeat Yourself）原則，亦方便未來擴充其他符號。
* `if __name__ == "__main__":` 判斷式可讓此檔案作為模組匯入而不會立即執行產生流程，對單元測試相當有用。
* 所有參數（資料字串、X‑dimension、height）皆明確寫出，使此腳本成為未來專案的參考 **barcode generator example**。

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| *What if I need a different X‑dimension?* | 將 `x_dimension.pixels` 改為想要的模組寬度。較大的數值會成比例放大整體條碼尺寸。 |
| *Can I generate other image formats?* | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpg`、`Bmp` 或 `Gif`（視函式庫的列舉而定）。 |
| *What happens if the data string contains invalid characters?* | 產生器會拋出 `ArgumentException`。在呼叫建構子前，請先依符號的字元集驗證資料。 |
| *Is it possible to set a minimum height while keeping auto‑scaling?* | 若 SDK 提供 `min_pixels` 屬性，可使用 `gen.parameters.barcode.bar_height.min_pixels = <value>`。這樣可防止條碼縮小至難以辨識的尺寸。 |
| *Do I need to dispose of the generator?* | `BarcodeGenerator` 在 .NET 中實作 `IDisposable`；在 Python 中則交由垃圾回收機制處理，若在迴圈中大量建立實例，可自行呼叫 `gen.dispose()` 以釋放資源。 |

## Tips for production use

* **Pro tip:** 將 X‑dimension 與 height 參數寫入設定檔，方便在不重新編譯的情況下調整。
* **Watch out for:** 設定過小的高度會導致掃描器無法讀取條碼。
* **Performance note:** 若要大量產生條碼，重複使用同一個 `BarcodeGenerator` 實例，僅在儲存前變更 `code_text` 屬性，可提升效能。

## Conclusion

此 **barcode generator example** 同時示範了 **how to create planet barcode** 圖片的自動尺寸設定，以及 **how to set barcode height** 的手動設定方式。依循本步驟指南，您即可在任何 Python 應用程式中整合條碼產生、客製化尺寸，並產出適合列印或數位顯示的 PNG 檔案。

### Next steps

* 探索其他符號，如 `EncodeTypes.Postnet` 或 `EncodeTypes.Code128` —— 同樣的模式皆適用。
* 嘗試 **how to set barcode height** 在 QR Code 或 DataMatrix 符號上的應用；大多函式庫皆提供類似的 `bar_height` 屬性。
* 結合 PDF 函式庫，直接將條碼嵌入發票或運單 PDF 中。

歡迎自行調整腳本、分享成果，並告訴我們您接下來會加入哪些條碼類型！

## What Should You Learn Next?

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並提供其他實作方式的範例：

- [如何在 Python 中從條碼產生器範例儲存 PNG](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [如何使用 Python 產生 Planet 條碼 PNG](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [如何使用 C# 條碼產生器建立 Planet 條碼](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}