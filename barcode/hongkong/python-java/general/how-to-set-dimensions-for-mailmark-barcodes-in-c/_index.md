---
category: general
date: 2026-08-22
description: 學習如何在 C# 中設定 Mailmark 條碼的尺寸，並將其儲存為 PNG 圖像。包括完整程式碼、說明與技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: zh-hant
lastmod: 2026-08-22
og_description: 如何在 C# 中設定 Mailmark 條碼的尺寸，並將其匯出為 PNG 檔案。跟隨完整範例，避免常見陷阱。
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: 在 C# 中設定 Mailmark 條碼尺寸的逐步指南
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: 如何在 C# 中設定 Mailmark 條碼的尺寸
url: /zh-hant/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中設定 Mailmark 條碼的尺寸

如果您需要在 C# 中 **設定尺寸** Mailmark 條碼，本指南會示範完整步驟。您將會看到如何設定 X‑dimension（模組寬度）與條碼高度，然後將條碼儲存為 PNG 圖片，無需額外工具。

產生郵件條碼是開發郵寄標籤軟體時的常見工作，但預設尺寸往往無法符合印表機或版面需求。完成本教學後，您將能精確控制條碼尺寸，並產出兩種有效的 Mailmark 類型（C‑type 與 L‑type），即可直接列印。

**您將學會**

* 如何為 `BarcodeGenerator` 設定 X‑dimension（模組寬度）與條碼高度。
* 如何使用 `BarCodeImageFormat` 將產生的條碼儲存為 PNG 檔案。
* 常見的問題，例如資料夾路徑無效或不支援的尺寸值。
* 在多個條碼間重複使用相同設定的技巧。

## 前置條件

* .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.6+）。
* **Aspose.BarCode for .NET** NuGet 套件（或任何提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的相容函式庫）。
* 具備基本的 C# 語法與檔案 I/O 知識。

> **專業提示：** 使用 CLI 指令  
> `dotnet add package Aspose.BarCode` 安裝套件，讓專案保持整潔。

## 第一步：定義輸出資料夾

在建立任何條碼之前，必須先決定 PNG 檔案要寫入的資料夾。使用絕對路徑可避免在不同機器上產生意外。

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*為什麼這很重要*：如果資料夾不存在，`Save` 會拋出 `IOException`。`Directory.CreateDirectory` 為冪等操作——若資料夾已存在則不會執行任何動作。

## 第二步：建立 Mailmark C‑type 條碼並 **設定尺寸**

Mailmark C‑type 會編碼 20 個字元的英數字串。初始化產生器後，可透過 `Parameters.Barcode` 物件 **設定尺寸**。

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### 為什麼選擇這些數值？

* **X‑dimension** 控制最小條（「模組」）的寬度。`4` 像素的設定可讓大多數雷射印表機輕鬆辨識，同時保持檔案大小適中。
* **BarHeight** 決定條碼的垂直高度。`50` 像素是標準郵寄標籤的常見高度，若需較大版面可自行調整。

> **邊緣情況：** 某些印表機要求最小條高為 30 px。若設定低於印表機的最小高度，可能導致條碼無法辨識。

## 第三步：建立 Mailmark L‑type 條碼並 **設定尺寸**

L‑type 使用較長的資料字串（最長 30 個字元）。相同的尺寸設定方式同樣適用。

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### 重複使用設定

若需要大量產生尺寸相同的條碼，建議將設定抽取成輔助方法：

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

呼叫 `ApplyStandardDimensions(mailmarkC)` 與 `ApplyStandardDimensions(mailmarkL)` 可減少程式碼重複，未來若要改為 5 像素模組，只需修改一行即可。

## 第四步：驗證產生的 PNG 檔案

執行程式後，使用任意圖像檢視器開啟兩個 PNG 檔案。您應該會看到兩個不同的 Mailmark 條碼，模組寬度皆為 4 px，條碼高度為 50 px。

*預期輸出*

| 檔案名稱                     | 大約尺寸 (px) |
|-----------------------------|----------------|
| `PostalMailmarkCType.png`   | 4 px × 模組 × N 個模組 |
| `PostalMailmarkLType.png`   | 4 px × 模組 × N 個模組 |

實際寬度取決於編碼資料的長度，但高度會固定為 **50 px**，因為我們使用 `BarHeight.Pixels` 進行設定。

## 常見問題與避免方式

| 問題                                 | 症狀                                            | 解決方式 |
|--------------------------------------|------------------------------------------------|----------|
| 資料夾路徑無效                       | `IOException: Could not find a part of the path` | 使用 `Path.Combine` 搭配 `Environment.SpecialFolder`，或確認路徑字串正確。 |
| X‑dimension 設為 0 或負數            | 條碼顯示為實心方塊                              | 確保 `XDimension.Pixels` 為正整數（最小值 1）。 |
| 不支援 `EncodeTypes.Mailmark`        | 建構產生器時拋出 `ArgumentException`            | 確認使用的 Aspose.BarCode 版本已支援 Mailmark。 |
| 使用錯誤的影像格式儲存                | PNG 檔案損毀                                    | 使用 `BarCodeImageFormat.Png`（若需其他格式可改為 `Jpeg`）。 |

## 延伸範例

* **不同尺寸** – 將 `XDimension.Pixels` 改為 3 可產生更緊湊的條碼，或將 `BarHeight.Pixels` 提升至 70 以適用較大標籤。
* **批次產生** – 迭代資料字串集合，在每次迭代中套用相同的尺寸設定。
* **其他影像格式** – 如工作流程需要，可將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。

## 結論

您現在已掌握 **如何在 C# 中設定 Mailmark 條碼的尺寸**，並將其匯出為 PNG 檔案。透過設定 `XDimension.Pixels` 與 `BarHeight.Pixels`，即可控制 C‑type 與 L‑type 條碼的視覺大小，確保符合印表機規格與版面需求。  

接下來，您可以嘗試不同的尺寸值，將程式碼整合至更大的郵寄標籤系統，或批次產生條碼以支援大量郵寄作業。

---

*下一步*：探索 **BarcodeGenerator** 在 QR Code 上的尺寸設定，或閱讀 Aspose.BarCode 文件中關於 **設定 DPI** 以進行高解析度列印的說明。若需將條碼嵌入 PDF，可結合 **Aspose.PDF** 函式庫，打造完整的端對端解決方案。


## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步擴展您的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您熟悉更多 API 功能，並探索在專案中的其他實作方式。

- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)
- [How to Configure Patch Code Barcodes with Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}