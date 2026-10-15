---
category: general
date: 2026-10-15
description: 學習如何在 C# 中使用 Macro‑PDF417 參數產生 PDF417 條碼、設定條碼尺寸，並儲存為 PNG。附有完整程式碼範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: zh-hant
lastmod: 2026-10-15
og_description: 如何在 C# 中產生 PDF417 條碼，具備完整的 Macro‑PDF417 設定、尺寸控制與 PNG 輸出。請參考完整範例。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: 如何在 C# 中產生 PDF417 條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: 如何在 C# 中使用 Macro‑PDF417 設定產生 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Macro‑PDF417 設定產生 PDF417 條碼

如果您需要 **how to generate PDF417 barcode** 用於文件工作流程，本指南會向您展示完整步驟。您將看到如何設定 Macro‑PDF417 參數、設定條碼尺寸，並將結果匯出為 PNG 圖像——全部在一個可執行的 C# 程式中。

產生 PDF417 條碼不需要多個函式庫或複雜的後處理。透過使用 Aspose.Barcode for .NET，您可以控制條碼的每個面向，從模組寬度到校驗碼，並產生適合列印或掃描的高品質影像。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0（或更新）SDK 已安裝  
* Visual Studio 2022 或您偏好的任何 C# IDE  
* Aspose.Barcode for .NET NuGet 套件 (`Install-Package Aspose.Barcode`)  

這些前置條件可確保程式碼在不需額外設定的情況下編譯通過。

## Step 1: Create a barcode generator for a Macro‑PDF417 barcode

第一個操作會建立一個 `BarcodeGenerator` 實例，目標格式為 `EncodeTypes.MacroPdf417`。建構子會接收您想要編碼的資料——此例中為字串 `"Sample text"`。

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

建立產生器會設定內部的 `Parameters` 物件，您將使用它來調整 **C# PDF417 barcode** 屬性。

## Step 2: Set basic barcode appearance – set barcode dimensions

控制條碼的視覺大小可提升掃描的可靠性。`XDimension.Pixels` 屬性定義模組（點）寬度，而 `Pdf417.Columns` 則決定條碼的欄位數量。

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

設定這些尺寸可確保條碼符合一般標籤尺寸，並符合掃描器規格。

## Step 3: Provide Macro‑PDF417 file identification

Macro‑PDF417 於標準 PDF417 條碼上加入檔案層級的中繼資料。您必須指定唯一的檔案 ID、段落 ID、總段落數以及可讀的檔案名稱。

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

這些 **Macro PDF417 parameters** 讓下游系統能從多個條碼段重建原始檔案。

## Step 4: Add additional macro metadata – include barcode checksum

除了識別資訊外，Macro‑PDF417 還能儲存校驗碼、檔案大小、時間戳記、收件人、寄件人以及結束旗標。提供校驗碼可在解碼時提升資料完整性檢查。

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

加入 **barcode checksum** 及其他中繼資料，使條碼具備自我描述的特性，對自動化文件處理流程非常有價值。

## Step 5: Save the generated barcode as a PNG image – choose barcode image format

最後一步將條碼寫入檔案。`Save` 方法接受檔案路徑與 `BarCodeImageFormat` 列舉。PNG 提供無損壓縮，保留清晰邊緣以確保掃描可靠。

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

執行完畢後，檔案 `MacroPdf417.png` 會包含一個清晰的 PDF417 條碼，可嵌入 PDF、列印於標籤或顯示於螢幕上。

## Expected output

開啟 `C:/Barcodes/MacroPdf417.png` 後會看到一個矩形條碼，編碼文字為 “Sample text”。條碼包含您設定的宏中繼資料，可使用任何支援 Macro‑PDF417 的 PDF417 掃描器驗證。影像尺寸反映模組寬度 (2 px) 與欄位數 (5)，形成緊湊且易讀的條碼。

## Common variations and edge cases

| 情況 | 調整 |
|-----------|------------|
| **不同的資料長度** | 將 `"Sample text"` 替換為任意 UTF‑8 字串；產生器會自動調整條碼大小。 |
| **較高解析度** | 將 `XDimension.Pixels` 提升至 3 或 4，以取得較大的模組，適用於低解析度印表機。 |
| **更多段落** | 將 `MacroPdf417SegmentsCount` 改為您計畫產生的條碼部件總數。 |
| **替代影像格式** | 若下游系統偏好其他格式，可使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 |
| **自訂錯誤更正** | 修改 `generator.Parameters.Barcode.Pdf417.ErrorLevel`（範圍 0‑8），以在資料密度與錯誤容忍度之間取得平衡。 |

**Pro tip:** 在投入生產前，務必使用實體掃描器驗證產生的條碼。掃描器可能對模組寬度或欄位數有韌體特定的限制。

## Full source code

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

執行此程式會在 `C:/Barcodes` 資料夾中產生 `MacroPdf417.png`，主控台會顯示成功產生的訊息。

## Conclusion

您現在已了解 **how to generate PDF417 barcode** 在 C# 中的完整 Macro‑PDF417 控制方式，知道如何 **set barcode dimensions**，如何嵌入 **barcode checksum** 及其他宏中繼資料，並且能以選定的 **barcode image format** 匯出結果。完整範例可直接複製到任何 .NET 專案，依不同資料負載進行修改，並整合至更大的文件自動化流程中。

### Next steps

* 探索 **C# PDF417 barcode** 的錯誤更正等級，以提升掃描可靠性。  
* 結合多個 Macro‑PDF417 段落，以編碼大型檔案（如 PDF 或影像）。  
* 將 **barcode image format** 轉換為 SVG，以在 Web 應用中使用可縮放向量圖形。  

歡迎自行嘗試各項參數，並在評論或社群論壇分享您的成果。祝開發順利！

## What Should You Learn Next?

以下教學涵蓋與本指南技術緊密相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並探索在自有專案中的替代實作方式。

- [產生 C# 條碼（Macro PDF417）– 完整範例](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [如何產生 PDF417 條碼 – 完整程式設計指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [如何在 C# 中使用自訂尺寸產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}