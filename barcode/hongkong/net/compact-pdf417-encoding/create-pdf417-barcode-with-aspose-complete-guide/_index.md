---
category: general
date: 2026-07-21
description: 使用 Aspose 在 C# 中建立 PDF417 條碼。了解如何僅透過幾個步驟產生帶有中繼資料的 PDF417 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: zh-hant
lastmod: 2026-07-21
og_description: 使用 Aspose 快速生成 PDF417 條碼。本指南將逐步說明如何產生 PDF417 條碼、設定宏元資料，並儲存圖像。
og_image_alt: Screenshot showing a generated PDF417 barcode created with Aspose
og_title: 使用 Aspose 建立 PDF417 條碼 – 步驟教學
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Create PDF417 barcode using Aspose in C#. Learn how to generate PDF417
    barcode with metadata in just a few steps.
  headline: Create PDF417 Barcode with Aspose – Complete Guide
  type: TechArticle
tags:
- barcode
- Aspose
- PDF417
title: 使用 Aspose 創建 PDF417 條形碼 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose 建立 PDF417 條碼 – 完整指南

是否曾需要 **建立 PDF417 條碼**，卻不確定哪個函式庫能輕鬆處理宏資訊？你並不孤單。在本教學中，我們將示範如何使用 Aspose.BarCode 函式庫 **產生 PDF417 條碼**，設定所有宏欄位，並將結果儲存為 PNG——只需幾行 C# 程式碼。

我們將逐步說明完整流程，從安裝 Aspose.BarCode 到微調條碼外觀，讓你可以將程式碼直接放入任何 .NET 專案並立即看到效果。完成後，你將能熟練使用 Aspose 建立條碼，並為實際掃描情境自訂宏參數。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 上執行）
- 有效的 Aspose.BarCode for .NET 授權（免費試用版可用於評估）
- Visual Studio 2022 或你喜愛的 IDE
- 基本的 C# 知識——不需要高階技巧，只要一般的 `using` 陳述式

如果缺少上述任何項目，請立即取得 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

就這樣——不需要額外的相依套件。

## 步驟 1：初始化條碼產生器（此處出現主要關鍵字）

首先，你需要建立一個 `BarcodeGenerator` 實例，目標為 **PDF417** 符號。Aspose 稱之為 `EncodeTypes.Pdf417`，但若要產生支援宏的條碼，則使用 `EncodeTypes.MacroPdf417`。

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the text you want to encode
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the steps are inside this using block
        }
    }
}
```

*為什麼這很重要*：`using` 陳述式確保產生器正確釋放，釋放本機資源。此外，選擇 `MacroPdf417` 後即可嵌入檔案層級的中繼資料——對於大型文件工作流程相當便利。

## 步驟 2：定義基本外觀（次要關鍵字 – 如何產生 pdf417 條碼）

過小或過於擁擠的條碼將難以辨識。Aspose 提供對模組大小、欄位數量等細緻的控制。

```csharp
// Set the module (X) dimension – each bar will be 2 pixels wide
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a reasonable column count for readability
generator.Parameters.Barcode.Pdf417.Columns = 5;

// Optional: tweak error correction level if you need higher resilience
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // 0‑8 range
```

這三行程式碼即是 **如何產生 PDF417 條碼** 的核心，能在大多數裝置上可靠掃描。請根據資料大小與掃描環境調整 `Columns` 與 `ErrorCorrectionLevel`。

## 步驟 3：加入 Macro PDF417 中繼資料（主要關鍵字 – 建立 pdf417 條碼）

Macro PDF417 允許你直接將文件層級資訊嵌入條碼。這正是你真正 *建立 PDF417 條碼*，讓其承載的不僅僅是簡單字串。

```csharp
// File identifier – must be unique across all segments
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

// Segment identifier – this is segment 12 of the whole file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

// Total number of segments in the file
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

// Human‑readable file name (optional but nice for debugging)
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

// Optional CCITT‑16 checksum for extra integrity checking
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

// Approximate file size in bytes – helpful for large PDFs
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

// Timestamp when the file was generated
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

// Add address fields – these are free‑form strings
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

// Define the macro terminator (whether this is the last segment)
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*為什麼需要這個*：支援 Macro PDF417 的掃描器能從多個條碼段重建原始檔案，透過檢查碼驗證完整性，甚至顯示寄件人/收件人資訊。這對物流、文件歸檔，或任何單一條碼無法容納完整資料的情境都相當適合。

## 步驟 4：將條碼儲存為影像（次要關鍵字 – 使用 aspose 建立條碼）

最後，將條碼寫入 PNG 檔案（或任何 Aspose 支援的格式）。`BarCodeImageFormat` 列舉讓此操作變得簡單。

```csharp
// Choose a folder you have write access to
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";

// Save the barcode – PNG keeps the crisp edges
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

這就是完整的 **使用 Aspose 建立條碼** 流程。執行程式後，開啟 PNG 檔案——你應該會看到帶有宏欄位的清晰 PDF417 符號。

![Create PDF417 barcode example](image.png "Create PDF417 barcode example")

*提示*：若需要其他影像格式（JPEG、BMP、SVG），只要將 `BarCodeImageFormat.Png` 換成相應的列舉值即可。

## 完整範例

將所有部件組合起來，以下是一個可直接執行的主控台應用程式：

```csharp
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Initialise generator for Macro PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // Basic appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

            // Macro metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save as PNG
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

執行程式，開啟產生的影像，你將看到一個完美形成、可供掃描的 PDF417 條碼。

## 常見問題與邊緣案例

**如果我的資料超過單一 PDF417 符號的容量會怎樣？**  
若啟用 `MacroPdf417`，Aspose 會自動將資料分割成多個宏段。只要確保 `SegmentsCount` 反映總段數即可。

**我可以更改條碼顏色嗎？**  
當然可以。使用 `generator.Parameters.Barcode.BarColor` 與 `BackgroundColor` 以任意方式著色。

**支援 Unicode 嗎？**  
支援——範例中使用了 `Å` 與 `©` 等字元。Aspose 內部處理 UTF‑8 編碼，因而可嵌入幾乎任何語言。

**大量產生條碼的效能如何？**  
對於中等工作量，每個條碼建立一個產生器是可接受的。若需批次處理，請重複使用同一個 `BarcodeGenerator` 實例，僅在儲存間變更 `CodeText` 屬性。

## 結論

現在你已掌握使用 Aspose **如何建立 PDF417 條碼**、設定宏層級中繼資料，並將結果匯出為高品質 PNG。此方法——*建立 pdf417 條碼*，具備精細外觀調整與嵌入檔案資訊，既穩健又易於整合至現有 .NET 服務。

準備好進一步了嗎？試著產生一系列分段條碼以表示多兆位元組的 PDF，或是實驗不同的錯誤更正等級，觀察掃描可靠性的變化。若你對其他符號感興趣，可參考 Aspose 關於 QR code 產生或 DataMatrix 的指南。

祝程式開發順利，願你的掃描永遠零錯誤！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，建立在所示技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立緊湊型 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 建立緊湊型 PDF417 條碼（西班牙語）](/barcode/spanish/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 創建緊湊型 PDF417 條碼](/barcode/chinese/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}