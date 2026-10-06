---
category: general
date: 2026-08-19
description: 使用 Aspose.BarCode 於 C# 產生條碼，建立帶有自訂文字的 Macro PDF417，並儲存為影像檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: zh-hant
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 於 C# 產生條碼，學習如何產生 PDF417、加入自訂文字，並儲存條碼圖像檔案。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: 產生條碼 C# – Macro PDF417 指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: 使用 Macro PDF417 於 C# 產生條碼 – 完整範例
url: /zh-hant/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Macro PDF417 產生條碼 C# – 完整範例

如果您需要為 Macro PDF417 格式 **generate barcode C#**，本指南提供一個可直接執行的解決方案。您將看到如何 **how to generate pdf417**、嵌入自訂文字，以及 **generate barcode image file**，全部在單一自足的程式中。

本教學涵蓋從安裝 Aspose.BarCode 函式庫到設定 Macro PDF417 中繼資料的所有步驟，讓您可以直接將程式碼複製到專案中，立即看到結果。

## 前置條件

- .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 執行）
- Visual Studio 2022（或任何支援 C# 的 IDE）
- Aspose.BarCode for .NET 授權（免費試用版可用於評估）
- 具備基本的 C# 語法知識

> **Pro tip:** 透過 CLI 安裝 NuGet 套件以避免版本不匹配：  
> `dotnet add package Aspose.BarCode`

## 步驟 1：設定專案並匯入函式庫

建立一個新的主控台應用程式，並加入所需的 `using` 指令。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**為什麼此步驟重要：**  
`Aspose.BarCode.Generation` 命名空間提供 `BarcodeGenerator` 類別，這是建立任何條碼類型（包括 Macro PDF417）的入口點。匯入 `System` 可取得 `DateTime` 以用於時間戳記中繼資料。

## 步驟 2：使用自訂文字建立 Macro PDF417 產生器

將佔位符註解替換為產生器的初始化程式碼。此範例示範 **create barcode custom text**，同時選擇正確的編碼類型。

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**說明：**  
- `EncodeTypes.MacroPdf417` 告訴 Aspose 產生支援宏功能（檔案分段、檢查碼等）的 PDF417 條碼。  
- 文字 `"Åspóse.Barcóde©"` 顯示 Unicode 字元得到完整支援，這在國際化應用中常見。

## 步驟 3：設定外觀與 Macro PDF417 中繼資料

微調條碼尺寸，並設定分段檔案處理所需的宏特定欄位。

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**為什麼這些設定重要：**

| 設定 | 目的 |
|---------|---------|
| `XDimension.Pixels` | 控制視覺密度；2 px 可產生清晰、可掃描的影像。 |
| `Columns` | 決定每列顯示多少資料欄位，影響條碼大小。 |
| `MacroPdf417FileID` | 唯一識別跨所有段的邏輯檔案。 |
| `MacroPdf417SegmentID` / `SegmentsCount` | 允許從多個條碼重建原始檔案。 |
| `MacroPdf417FileName` | 以人類可讀的名稱儲存在條碼內，供後續處理使用。 |
| `MacroPdf417Checksum` | 使用 CCITT‑16 CRC 演算法提供錯誤偵測。 |
| `MacroPdf417FileSize` | 協助解碼器判斷何時已收到完整檔案。 |
| `MacroPdf417TimeStamp` | 記錄條碼產生時間，對稽核追蹤有用。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 可供業務工作流程使用的選用欄位。 |
| `MacroPdf417Terminator` | 表示此段為最後一段（`Set`）。 |

## 步驟 4：將條碼儲存為影像檔案

最後，將條碼寫入 PNG 檔案，以便您檢視或嵌入其他地方。

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**您將看到的結果：**  
一個名為 `ExtPDF417Meta.png` 的 PNG 影像，內含編碼自訂文字與上述所有中繼資料欄位的 Macro PDF417 條碼。此影像可使用任何標準檢視器開啟，或插入 PDF、報告或網頁中。

## 完整原始碼（可直接複製貼上）

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 預期輸出

執行程式會輸出：

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

開啟 `ExtPDF417Meta.png` 後會看到一個乾淨的 Macro PDF417 條碼，使用任何 PDF417 讀取器皆能正確掃描，且保留了自訂文字 `"Åspóse.Barcóde©"` 與您定義的宏中繼資料。

## 常見問題與邊緣案例

- **我可以產生其他影像格式嗎？**  
  可以。視需求將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。

- **如果我的資料超過單一條碼的容量怎麼辦？**  
  Macro PDF417 為分段設計。為每個部分調整 `MacroPdf417SegmentsCount` 與 `MacroPdf417SegmentID`，然後將掃描結果串接起來。

- **Unicode 支援是否有保證？**  
  Aspose.BarCode 完全支援 Unicode。請確保您的原始檔案以 UTF‑8 編碼儲存，以免字元損壞。

- **正式環境需要授權嗎？**  
  授權版會移除評估水印並提供完整功能。試用版可用於測試與學習。

## 結論

您現在已了解如何使用 Aspose.BarCode **generate barcode C#** 產生 Macro PDF417、**how to generate pdf417** 搭配豐富中繼資料、**create barcode custom text**，以及 **generate barcode image file**。完整且可執行的範例示範了所有必要步驟——從專案設定到儲存最終的 PNG 影像。

### 後續步驟

- 嘗試其他 PDF417 設定，例如 `ErrorCorrectionLevel` 與 `CompactPdf417`，以產生較小的符號。  
- 使用 Aspose.PDF 將產生的條碼整合至 PDF 報告中。  
- 探索批次產生：對檔案集合迴圈，產生一系列分段的 Macro PDF417 條碼。

隨意將程式碼套用到您的工作流程，讓條碼產生成為 C# 應用程式中順暢的一環。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題，並以完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}