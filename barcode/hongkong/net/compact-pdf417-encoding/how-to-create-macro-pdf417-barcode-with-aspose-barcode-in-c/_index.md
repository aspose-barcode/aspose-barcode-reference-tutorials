---
category: general
date: 2026-11-20
description: 學習如何在 C# 中使用 Aspose.BarCode 建立 macro PDF417 條碼。本指南涵蓋中繼資料、參數以及儲存圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: zh-hant
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中建立宏 PDF417 條碼。請參考此完整教學設定中繼資料、配置參數，並匯出 PNG。
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: 在 C# 中建立宏式 PDF417 條碼 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 建立宏式 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立 macro PDF417 條碼

如果您需要在 .NET 應用程式中 **建立 macro PDF417 條碼**，本教學將示範完整步驟。您將看到如何設定 macro 專屬的中繼資料、調整視覺設定，並將結果儲存為 PNG 檔案。

產生 macro PDF417 條碼在您想將大量資料分割成多個符號，同時保留全檔案識別碼時非常有用。以下範例使用 Aspose.BarCode 函式庫，該函式庫提供流暢的 API 以支援所有 PDF417 功能。

閱讀完本指南後，您將擁有一個可直接執行的主控台程式，產生包含完整 macro 資訊的條碼影像。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本。
* Visual Studio 2022（或任何支援 C# 的 IDE）。
* **Aspose.BarCode for .NET** NuGet 套件（`Aspose.BarCode`）。

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：為 macro PDF417 初始化條碼產生器

第一步是以 `EncodeTypes.MacroPdf417` 列舉值建立 `BarcodeGenerator` 實例。這會告訴函式庫將條碼視為 macro PDF417 符號。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*為什麼這很重要*：選取 `MacroPdf417` 後，`Pdf417` 參數物件的所有 macro 相關屬性皆會啟用。

## 步驟 2：設定基本視覺外觀

可讀的條碼需要適當的模組大小與欄位數。`XDimension.Pixels` 屬性控制單一模組的寬度，而 `Pdf417.Columns` 定義每列包含多少資料欄位。

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

調整這些數值會同時影響掃描器的可靠度與影像大小。

## 步驟 3：定義 macro 檔案識別細節

macro PDF417 需要檔案識別碼、段落識別碼以及總段落數。這三個欄位讓掃描器能重新組合原始資料集。

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

這些 **macro PDF417 參數** 是 macro 功能的核心。若缺少它們，掃描器將無法將符號串聯起來。

## 步驟 4：加入可選的 macro 中繼資料

除了必填的識別碼外，macro 格式還支援額外欄位，如檢查碼、檔案大小、時間戳記、收件人、寄件人以及終止旗標。提供這些資料可提升錯誤偵測能力，並為下游系統提供上下文資訊。

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*小技巧*：如果您的工作流程不需要某個欄位，可保留其預設值。函式庫會自動從條碼中省略對應的資料元素。

## 步驟 5：儲存條碼影像

完成所有參數設定後，呼叫 `Save` 以匯出條碼。範例會將 PNG 檔案存放在使用者指定的目錄下。

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

程式執行完畢後，`ExtPDF417Meta.png` 內即包含一個 macro PDF417 條碼，編碼文字為 `"Åspóse.Barcóde©"`，同時攜帶全部 macro 中繼資料。

## 完整原始程式碼

以下是完整、獨立的程式範例。將它複製到新的主控台專案中，安裝 Aspose.BarCode NuGet 套件後即可執行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### 預期輸出

執行程式時會在主控台印出類似以下的確認訊息：

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

開啟 PNG 檔案即可看到密集且高對比度的條碼。使用相容 PDF417 的掃描器讀取後，會回傳原始文字以及所有 macro 欄位。

## 常見問題與特殊情況

### 如果需要超過 20 個段落怎麼辦？

`MacroPdf417SegmentsCount` 屬性最高可設定為 `255`。請確保接收系統能處理較大的段落數，並考慮將資料切分為可管理的符號數量。

### 檢查碼對掃描有何影響？

CCITT‑16 檢查碼（`MacroPdf417Checksum`）提供額外的錯誤檢測層級。若掃描器偵測到不匹配，將會拒絕此條碼。若工作流程不需要檢查碼，可將其省略。

### 可以不使用 Aspose 產生 PDF417 macro 條碼嗎？

可以，其他函式庫（例如 ZXing.Net、Dynamsoft）亦支援 PDF417，但通常缺少 macro 專屬欄位。Aspose.BarCode 提供最完整的 macro 中繼資料實作。

### 支援哪些影像格式儲存？

`Save` 方法接受 `BarCodeImageFormat` 中定義的任何格式，如 `Png`、`Jpeg`、`Gif`、`Bmp` 與 `Tiff`。請依您的下游處理流程選擇合適的格式。

## 結論

現在您已掌握如何在 C# 中使用 Aspose.BarCode **建立 macro PDF417 條碼**。本教學涵蓋了產生器初始化、視覺設定、macro 檔案識別碼、可選中繼資料以及影像匯出。憑藉此基礎，您可以在庫存系統、文件追蹤或任何需要分段資料傳輸的情境中嵌入 macro PDF。

接下來可嘗試調整不同的 `XDimension` 以取得更高解析度、調整錯誤更正等級，或將條碼整合至回傳 PNG 串流的 Web API 中。相關主題請參考 **barcode generator example**、**PDF417 macro parameters** 與 **macro PDF417 metadata** 的教學。

祝開發順利！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，或探索在專案中實作的其他方式。

- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}