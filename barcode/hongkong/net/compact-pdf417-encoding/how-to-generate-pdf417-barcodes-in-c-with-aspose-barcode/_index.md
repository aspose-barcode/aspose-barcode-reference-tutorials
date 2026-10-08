---
category: general
date: 2026-09-10
description: 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼。遵循一步一步的指南建立 Macro PDF417、調整參數，並匯出為
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: zh-hant
lastmod: 2026-09-10
og_description: 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼。了解從設定到儲存宏式 PDF417 PNG 圖像的完整工作流程。
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: 如何在 C# 中生成 PDF417 條碼 – 完整的 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: 如何在 C# 中使用 Aspose.BarCode 生成 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼

如果您需要在 .NET 專案中 **產生 PDF417**，本教學將展示完整的工作流程。您將看到如何建立 Macro PDF417 條碼、微調其設定，並將結果匯出為 PNG 圖像——全部使用 Aspose.BarCode for .NET。

在物流、票務及安全文件流程中，產生 PDF417 條碼相當常見。完成本指南後，您將擁有一個可直接使用的 C# 條碼產生器，能嵌入任何應用程式中。

## 您需要的環境

- **Visual Studio 2022**（或任何 C# IDE）  
- **.NET 6.0** 或更新版本  
- **Aspose.BarCode for .NET** NuGet 套件 (`Install-Package Aspose.BarCode`)  
- 具備基本的 C# 語法知識  

> **專業提示：** 使用最新的 Aspose.BarCode 版本，以取得最新的 Macro PDF417 功能與錯誤修正。

---

## 在 C# 中產生 PDF417 條碼的方法  

以下是一個可完整執行的範例，會建立 **Macro PDF417** 條碼、設定其宏專屬欄位，並將圖像儲存。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### 為何每一步都很重要

1. **建立 Macro PDF417 產生器** – `EncodeTypes.MacroPdf417` 告訴 Aspose.BarCode 使用 PDF417 的宏版本，支援將大型資料分割成多個符號。  
2. **調整基本外觀** – `XDimension` 控制模組（點）寬度；`Columns` 定義每個符號的欄位數量，影響尺寸與可讀性。  
3. **設定宏專屬欄位** – 這些屬性（`MacroPdf417FileID`、`MacroPdf417SegmentID` 等）是 PDF417 宏規範所要求，用於在掃描器端重新組合原始資料。  
4. **匯出圖像** – `BarCodeImageFormat.Png` 提供無損圖像，適用於網頁、列印與行動裝置等情境。

---

## 設定 Aspose.BarCode for .NET（C# 條碼產生器）

在執行上述程式碼之前，您必須將 Aspose.BarCode 函式庫加入專案中：

```bash
dotnet add package Aspose.BarCode
```

*此 NuGet 套件已包含所有相依性，無需額外的 DLL。*  
如果您以 .NET Framework 為目標，於套件管理員主控台執行相同的 `Install-Package Aspose.BarCode` 指令即可。

### 常見陷阱

- **缺少授權** – 預設情況下 Aspose 以評估模式執行，會在條碼上加上浮水印。註冊授權檔案 (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) 以移除浮水印。  
- **`EncodeTypes` 設定錯誤** – 使用 `EncodeTypes.Pdf417` 而非 `EncodeTypes.MacroPdf417` 會忽略所有宏欄位，導致多段重組失敗。

---

## 設定 Macro PDF417 條碼參數

宏欄位允許您將大型文件分割成多個 PDF417 符號。以下是快速參考表：

| 屬性 | 用途 | 常見範圍 |
|----------|---------|---------------|
| `MacroPdf417FileID` | 完整檔案的唯一識別碼 | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | 目前段的索引（從 0 開始） | 0‑254 |
| `MacroPdf417SegmentsCount` | 檔案中段的總數 | 1‑255 |
| `MacroPdf417FileName` | 可選的人類可讀名稱 | 0‑255 characters |
| `MacroPdf417Checksum` | 用於錯誤偵測的 CCITT‑16 檢查碼 | 0‑65535 |
| `MacroPdf417FileSize` | 原始檔案大小（位元組） | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | 建立時間戳記（可選） | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 可選的路由中繼資料 | Any string |
| `MacroPdf417Terminator` | 指示最後一段（`Set` 或 `Unset`） | `Pdf417MacroTerminator` enum |

依據您要編碼的資料調整這些數值。例如，若將 2 MB 檔案分成 20 段，請將 `MacroPdf417FileSize` 設為 `2_000_000`，`MacroPdf417SegmentsCount` 設為 `20`。

---

## 將條碼匯出為 PNG 圖像（條碼圖像匯出）

將條碼儲存為 PNG 是最常見的匯出格式，因為它能保留清晰的邊緣並支援透明度。Aspose.BarCode 亦支援 JPEG、BMP、GIF 與 TIFF——可依您的後續流程選擇合適的格式。

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**高品質輸出的技巧**

- 在高解析度媒介列印時，提升 `XDimension.Pixels` 以取得較大的模組。  
- 使用 `BarCodeImageFormat.Tiff` 搭配 CCITT Group 4 壓縮，以產生適用於傳真之 PDF。  
- 若需特定 DPI（例如列印用 300 dpi），請設定 `generator.Parameters.ImageOptions.Resolution`。

---

## 測試與除錯您的 PDF417 條碼

1. **視覺驗證** – 在任何圖像檢視器中開啟 `MacroPdf417.png`。您應該會看到一組堆疊的垂直條紋，並帶有小文字說明（編碼資料）。  
2. **掃描器測試** – 使用支援 PDF417 的手機條碼掃描應用程式。掃描圖像後，應返回原始的「Sample text」以及宏中繼資料（檔案 ID、段 ID 等）。  
3. **錯誤處理** – 若掃描器回報「checksum error」，請再次確認 `MacroPdf417Checksum`，並確保最後一段的 `MacroPdf417Terminator` 設定正確。  
4. **效能** – 在迴圈中產生大量段落會消耗 CPU。重複使用單一 `BarcodeGenerator` 實例，僅在儲存之間更新宏欄位，可提升處理速度。

---

## 結論

您現在已了解如何使用 Aspose.BarCode 在 C# 中 **產生 PDF417** 條碼，從安裝函式庫、設定 Macro PDF417 欄位到匯出乾淨的 PNG 圖像。完整解決方案展示了：

- 使用 Macro PDF417 類型設定 **C# 條碼產生器**  
- 為多段資料自訂 **PDF417 條碼參數**  
- 執行 **條碼圖像匯出** 以供後續使用  

接下來，您可以探索進階主題，例如將條碼嵌入 PDF 文件、產生 QR‑code 輔助條碼，或自動化大量檔案的批次處理。

**下一步**

- 嘗試不同的 `BarCodeImageFormat` 值（例如 `Tiff` 用於高解析度列印）。  
- 使用 `generator.Parameters.Barcode.Symbology` 將 Macro PDF417 與其他符號結合於同一文件中。  
- 查閱 [Aspose.BarCode 文件](https://docs.aspose.com/barcode/net/)，了解更深入的自訂選項，如錯誤更正等級與編碼模式。

祝編程愉快！

## 接下來您應該學習什麼？

以下教學涵蓋與本指南技術緊密相關的主題，並以完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [產生帶文字的條碼 – 完整 PDF417 Macro 指南](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [調整條碼大小 – C# 產生 PDF417 條碼指南](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [如何產生 PDF417 條碼 – 完整程式設計指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}