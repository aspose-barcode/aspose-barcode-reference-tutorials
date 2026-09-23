---
category: general
date: 2026-09-23
description: 學習如何使用 Aspose.BarCode 在 Python 中產生 Code 128 條碼並儲存條碼圖像 – 步驟說明指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: zh-hant
lastmod: 2026-09-23
og_description: 使用 Aspose.BarCode 在 Python 中產生 Code 128 條碼並儲存條碼圖像。請參考此完整範例，了解如何建立、客製化及匯出條碼為
  PNG 檔案。
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: 生成 Code 128 條碼並儲存條碼圖像 – Python 指南
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: 如何使用 Aspose.BarCode 生成 Code 128 條碼並保存條碼圖像
url: /zh-hant/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 產生 Code 128 條碼並儲存條碼圖像

如果你需要在 Python 專案中 **產生 Code 128 條碼** 並 **儲存條碼圖像**，本教學會示範完整步驟。使用 Aspose.BarCode 的 `ExtCodetextBuilder`，你可以在單一載荷中嵌入純文字與 Unicode 片段，然後將結果渲染為 PNG 檔案。

你將看到完整可執行的腳本、每行程式碼的說明，以及處理常見陷阱（例如 ECI 編碼或選擇正確輸出資料夾）的提示。無需額外文件——只要複製、貼上並執行即可。

## 前置條件

* 已安裝 Python 3.8 以上。
* `aspose.barcode` 套件（使用 `pip install aspose-barcode` 安裝）。
* 具有寫入 PNG 將被儲存之目錄的權限。

此程式碼可用於 Aspose.BarCode 支援的任何條碼類型，但本範例聚焦於 **Code 128**，因為它能有效編碼字母數字資料，且支援擴充字元集。

## 步驟 1：匯入所需類別

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*此步驟的目的？* 匯入類別後，你即可使用擴充 codetext 的建構器、產生圖像的 writer，以及在除錯函式庫更新時可能有用的版本輔助工具。

## 步驟 2：建立擴充 codetext

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` 允許你在單一條碼載荷中混合純 ASCII 與 Unicode 資料。ECI（Extended Channel Interpretation）位元 `0x03` 告訴掃描器，隨後的位元組採用 UTF‑8 編碼，這對俄文、中文或阿拉伯文等語言至關重要。

## 步驟 3：為 Code 128 設定條碼 writer

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

將 `encode_type` 設為 `CODE_128` 會指示 writer 產生 **Code 128 條碼**。`code_text` 屬性會接收前一步建立的擴充字串。

## 步驟 4：將條碼圖像儲存為 PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

`save` 方法會將條碼寫入檔案。使用 `BarCodeImageFormat.PNG` 可確保無損壓縮，且在網頁與行動應用程式中具廣泛相容性。

## 步驟 5（可選）：驗證 Aspose.BarCode 函式庫版本

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

了解確切的函式庫版本有助於回報錯誤或比較不同版本之間的行為差異。

## 預期輸出

執行腳本會在主控台產生類似以下的輸出：

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

產生的 PNG（`extended_codetext.png`）如下所示：

![Python 產生的 Code 128 條碼已儲存為 PNG 圖像](images/code128_extended.png)

*此圖顯示一個 Code 128 條碼，編碼了 ASCII 字串 `ABC123` 與俄文單詞 “Пример”。*

## 常見問題與邊緣案例處理

| Question | Answer |
|----------|--------|
| **我可以使用其他條碼類型嗎？** | 可以。將 `BarCodeEncodeMode.CODE_128` 替換為其他支援的模式，例如 `QR`、`EAN_13` 或 `PDF_417`。 |
| **如果我的 Unicode 文字包含表情符號怎麼辦？** | 表情符號同樣是 UTF‑8 字元，因此相同的 `add_eci_codetext` 呼叫仍然適用。請確保目標掃描器支援你使用的 ECI。 |
| **如何調整圖像尺寸？** | 在呼叫 `save` 前設定 `writer.x_dimension` 與 `writer.bar_height`。 |
| **`output_path` 應該使用哪個資料夾？** | 任何 Python 程序可寫入的資料夾。可使用 `os.makedirs` 並將 `exist_ok=True` 以自動建立。 |

## 專業技巧

* **避免硬編碼路徑。** 使用 `os.path.join` 以及 `pathlib` 模組中的 `Path` 以確保跨平台相容性。
* **驗證條碼。** 儲存後，你可以使用 `barcode.BarCodeReader` 讀回圖像，以確認編碼文字與 `extended_codetext` 相符。
* **效能提示。** 若在迴圈中產生大量條碼，請重複使用同一個 `BarCodeWriter` 實例，並於每次迭代只更新 `code_text`。

## 結論

現在你已了解如何使用 Aspose.BarCode 在 Python 中 **產生混合 ASCII 與 Unicode 資料的 Code 128 條碼**，以及 **將條碼圖像儲存為 PNG**。完整腳本涵蓋了建立擴充 codetext、設定 writer、匯出圖像以及檢查函式庫版本的步驟。

接下來你可以探索：

* 加入前景/背景顏色 (`writer.back_color`, `writer.fore_color`)。
* 使用 `Aspose.PDF` 將條碼嵌入 PDF。
* 使用 `BarCodeReader` 類別解碼已儲存的圖像，並自動驗證內容。

祝程式開發順利，歡迎隨意嘗試其他條碼類型與圖像格式！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [使用 Aspose.Barcode Python 產生 Code128 條碼 – 完整指南](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [如何在 Python 中產生條碼 – 完整逐步指南](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [使用 Aspose.Barcode 在 Python 中產生 QR Code 圖像 – 完整指南](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}