---
category: general
date: 2026-11-17
description: 如何使用 Aspose.BarCode 建立 PDF417 條碼 – 逐步指南，亦示範如何在 C# 中建立 Aspose 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: zh-hant
lastmod: 2026-11-17
og_description: 如何使用 Aspose.BarCode 建立 PDF417 條碼。本教學將逐步說明如何建立條碼、設定 Macro PDF417 中繼資料，並儲存圖像。
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: 如何使用 Aspose.BarCode 建立 PDF417 條碼 – 完整 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: 如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼

如果您需要 **如何建立 PDF417** 條碼以用於庫存、運輸或文件追蹤，本指南將示範使用 Aspose.BarCode 的完整步驟。您將看到如何建立條碼、設定 Macro PDF417 欄位，並將結果匯出為 PNG 圖像——全部在一個可執行的 C# 程式中。

建立 PDF417 條碼在需要以緊湊、機器可讀的格式編碼大量資料時相當常見。Aspose.BarCode 讓此過程變得簡單，您可以微調尺寸、欄位數以及完整的 Macro PDF417 中繼資料集合。完成本教學後，您將擁有一個完整、獨立的範例，可直接放入任何 .NET 專案中使用。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本（程式碼亦相容於 .NET Framework 4.7 以上）。
* 有效的 Aspose.BarCode for .NET 授權（免費評估版可用於測試）。
* Visual Studio 2022、VS Code，或任何支援 C# 的 IDE。
* 基本的 C# 語法與 `using` 陳述式的熟悉度。

> **專業提示：** 若在未授權的情況下執行範例，Aspose 會在產生的圖像上加上小水印。

## 如何使用 Aspose.BarCode 建立 PDF417 條碼

以下章節將實作分為四個清晰步驟。每一步皆包含程式碼片段、說明 **為何** 需要此程式碼，以及可套用於您專案的實用技巧。

### 步驟 1：設定專案並匯入 Aspose.BarCode

建立一個新的 Console 專案，並加入 Aspose.BarCode NuGet 套件：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

接著開啟 `Program.cs`，加入必要的命名空間：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Why this matters:* 匯入 `Aspose.BarCode.Generation` 後，即可使用 `BarcodeGenerator` 與 `EncodeTypes` 列舉，這兩者是條碼產生的核心類別。

### 步驟 2：為 Macro PDF417 初始化 `BarcodeGenerator`

`BarcodeGenerator` 建構式接受條碼類型與欲編碼的文字。對於 Macro PDF417，使用 `EncodeTypes.MacroPdf417`。

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Why this matters:* `using` 陳述式可確保非受控資源（如 GDI+ 句柄）即時釋放，避免長時間執行服務時發生記憶體泄漏。

### 步驟 3：設定外觀與 Macro PDF417 中繼資料

#### 3.1 調整視覺參數

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 填寫 Macro PDF417 欄位

Macro PDF417 允許將大型文件切割成多個條碼段落。以下欄位為選填，但在物流或文件管理系統中常被需求。

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Why these fields are useful:*  
* **FileID** 將所有段落串聯起來，以便重組。  
* **SegmentID** 與 **SegmentsCount** 讓掃描器了解順序及系列是否完整。  
* **Checksum** 與 **FileSize** 提供快速完整性檢查，無需解碼整個負載。

> **注意：** `MacroPdf417FileID` 必須在同一邏輯文件內保持唯一。對不相關的檔案重複使用相同 ID 會導致重組錯誤。

### 步驟 4：儲存條碼圖像

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Why PNG?* PNG 能完整保留像素資料且不會產生壓縮雜訊，對依賴銳利邊緣的條碼掃描器而言是最佳選擇。

### 完整、可執行範例

將上述所有步驟整合，以下即為可直接編譯執行的完整程式：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Expected output:** 執行程式後，您會在專案資料夾中找到 `MacroPdf417.png`。開啟該圖像即可看到一個密集且高對比度的 PDF417 條碼，內含「Sample text for PDF417」以及您提供的 Macro 中繼資料。

## 常見問題與邊緣情況處理

| Question | Answer |
|----------|--------|
| *我可以在迴圈中產生多個段落嗎？* | Yes. Increment `MacroPdf417SegmentID` for each iteration, keep `MacroPdf417FileID` constant, and update `MacroPdf417SegmentsCount` only after you know the total number of segments. |
| *如果資料超過單一 PDF417 符號怎麼辦？* | Macro |

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，並提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中使用 Aspose.BarCode 建立 Macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 中使用 Aspose.BarCode 建立 Micro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [如何使用 Aspose.BarCode 建立 Compact PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}