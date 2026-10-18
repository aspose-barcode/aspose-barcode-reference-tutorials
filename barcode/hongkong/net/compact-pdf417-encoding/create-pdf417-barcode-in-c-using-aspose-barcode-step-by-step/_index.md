---
category: general
date: 2026-10-18
description: 學習如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼。本教學涵蓋基本、緊湊、宏與微型 PDF417 產生，並提供完整程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: zh-hant
lastmod: 2026-10-18
og_description: 使用 C# 及 Aspose.BarCode 建立 PDF417 條碼。按照本指南逐步生成基本、緊湊、宏和微型 PDF417 條碼。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: 在 C# 中建立 PDF417 條碼 – 完整 Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: 使用 Aspose.BarCode 在 C# 中建立 PDF417 條碼 – 步驟指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 使用 Aspose.BarCode 建立 PDF417 條碼 – 步驟說明指南

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼**，本教學將逐步帶您完成整個流程。您將會看到如何產生基本條碼、啟用緊湊模式、加入宏資料，以及產生微型變體——全部提供清晰說明與可執行的程式碼。

在物流、票務與文件管理等領域，產生 PDF417 條碼相當常見。完成本指南後，您即可在任何 C# 專案中整合條碼產生功能，無需額外工具。

## 前置條件

* .NET 6.0 或更新版本（程式碼亦相容於 .NET Framework 4.7+）
* Visual Studio 2022 或任何 C# IDE
* **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 對將儲存產生 PNG 檔案的資料夾具有寫入權限

不需要額外設定；此函式庫會處理所有低階編碼細節。

## 步驟 1：建立基本 PDF417 條碼

第一步會建立一個具有自訂尺寸與欄位數的標準 PDF417 條碼。

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**為何這些設定重要**

* `XDimension.Pixels` 控制每個條碼元素的實體大小。設定為 2 時，可在大多數螢幕與印表機上產生清晰圖像。
* `Pdf417.Columns` 決定條碼包含多少資料欄位。欄位較少會減少寬度，欄位較多則提升資料容量。

執行程式碼會產生 `Pdf417Basic.png`，其外觀為典型的 PDF417 符號，包含三個資料欄位與右側完整的中繼資料欄位。

## 步驟 2：啟用緊湊（截斷）模式

緊湊模式會移除右側的中繼資料欄位，使條碼變窄。當空間受限且資料仍可從剩餘列重建時，此模式相當有用。

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**為何要截斷？**  
當 `Truncate` 為 `true` 時，產生器會省略儲存錯誤更正與檔案層級中繼資料的可選右側欄位。產生的條碼佔用較少欄位，同時仍可被大多數 PDF417 讀取器掃描。

## 步驟 3：建立帶有檔案層級中繼資料的 Macro PDF417 條碼

Macro PDF417 透過段落識別碼擴充標準格式，讓大型文件可分割為多個條碼。此功能適用於編碼長字串或多頁檔案。

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**宏欄位說明**

| 屬性 | 用途 |
|----------|---------|
| `MacroPdf417FileID` | 整個檔案的唯一識別碼；所有段落共用此值。 |
| `MacroPdf417SegmentID` | 目前段落的索引（從 1 開始）。 |
| `MacroPdf417SegmentsCount` | 組成完整資料集的段落總數。 |

能辨識 Macro PDF417 的掃描器可透過讀取所有段落並使用這些識別碼，重新組合出原始資料。

## 步驟 4：為短資料建立 Micro PDF417 條碼

Micro PDF417 是為小容量資料（最高 90 個字元）設計的緊湊版。它將欄位範圍限制在 1‑4，適用於小型標籤或顯示區域受限的裝置。

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**何時使用 Micro PDF417**  
當資料負載較短且需要盡可能小的條碼時，可使用此變體。它非常適合庫存標籤、門禁卡，或任何螢幕空間寶貴的情境。

## 完整範例程式

以下是一個獨立的主控台應用程式，可一次產生四種條碼。將程式碼複製到新的 C# 專案，將 `YOUR_DIRECTORY` 替換為現有資料夾路徑，然後執行。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**預期輸出**

執行程式會在指定的資料夾中產生四個 PNG 檔案：

* `Pdf417Basic.png` – 具有三個欄位的標準條碼
* `CompactPdf417.png` – 相同資料，右側欄位被截斷
* `MacroPdf417.png` – 含有段落中繼資料的宏條碼
* `MicroPdf417.png` – 用於短字串的緊湊微型條碼

使用圖像檢視器開啟任一圖片，即可看到明顯的 PDF417 圖樣。使用行動條碼閱讀器（如 ZXing、Scandit）掃描它們，會回傳原始文字字串。

## 常見問題與技巧

* **如果條碼看起來模糊怎麼辦？**  
  將 `XDimension.Pixels` 提升至 3 或 4。較大的模組尺寸會產生較高解析度的圖像，但檔案會變大。

* **可以輸出 SVG 而非 PNG 嗎？**  
  可以。將 `Save` 呼叫中的 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Svg`。

* **需要手動設定錯誤更正等級嗎？**  
  Aspose.BarCode 會自動選擇最佳等級。若有特殊需求，可調整 `Pdf417.ErrorCorrectionLevel`。

* **如何將條碼嵌入 PDF 文件？**  
  使用 `Aspose.Pdf` 將產生的 PNG 或 SVG 作為圖像元件加入 PDF 頁面。

* **此函式庫是執行緒安全的嗎？**  
  每個 `BarcodeGenerator` 實例彼此獨立；您可在多個執行緒上建立生成器而不會共享狀態。

## 結論

您現在已了解如何在 C# 使用 Aspose.BarCode **建立 PDF417 條碼**，涵蓋基本、緊湊、宏與微型等變體。

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與步驟說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 建立 pdf417 條碼 – 步驟說明指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 使用緊湊模式建立 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [如何在 C# 使用 Aspose.BarCode 建立 macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}