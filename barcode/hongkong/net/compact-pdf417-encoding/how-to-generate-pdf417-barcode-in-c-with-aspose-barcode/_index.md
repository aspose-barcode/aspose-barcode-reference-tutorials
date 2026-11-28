---
category: general
date: 2026-11-27
description: 學習如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼。調整尺寸、設定列數，並以少量程式碼儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: zh-hant
lastmod: 2026-11-27
og_description: 即時在 C# 中產生 PDF417 條碼。本教學示範如何設定尺寸、欄位數，並將結果儲存為 PNG 圖像。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: 在 C# 中生成 PDF417 條碼 – Aspose.BarCode 快速指南
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 產生 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 使用 Aspose.BarCode 產生 PDF417 條碼

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本指南將為您展示一個簡潔、完整的解決方案。您將看到如何建立條碼、微調其尺寸，並將結果寫入 PNG 檔案——全部使用 Aspose.BarCode 函式庫。

在需要將大量資料編碼以供行動裝置掃描、登機證或庫存標籤使用時，產生 PDF417 條碼是相當常見的需求。完成本教學後，您將擁有一個可直接執行的主控台程式，能產生高品質的 PNG 圖像。

## Prerequisites

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* 最近版本的 **Aspose.BarCode for .NET**（NuGet 套件 `Aspose.BarCode`）  
* 任一 IDE 或編輯器（Visual Studio、VS Code、Rider 等）  

由於 Aspose.BarCode 支援跨平台，程式碼可在 Windows、Linux 與 macOS 上執行。

## Step 1: Create a new console project

在終端機中執行：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

此指令會建立一個名為 **Pdf417Demo** 的最小 C# 專案，並加入 `Aspose.BarCode` 相依性。

## Step 2: Write the barcode generation code

開啟 **Program.cs**，將內容取代為以下程式碼：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Why each line matters

* **BarcodeGenerator** – 核心類別，用於產生條碼影像。傳入 `EncodeTypes.Pdf417` 即選擇 PDF417 符號。
* **XDimension.Pixels** – 決定最小條寬。數值較小會縮小影像，較大則提升低解析度掃描器的可讀性。
* **Pdf417.Columns** – 控制資料欄位數。欄位越多條碼越短但較高，欄位越少則條碼較寬。
* **ErrorCorrectionLevel** – 較高的等級會加入冗餘資料，使條碼對損壞更具容錯性，但會增加尺寸。
* **Save(..., BarCodeImageFormat.Png)** – 以 PNG 格式寫入磁碟，PNG 為無損格式，適合後續處理或嵌入文件。

## Step 3: Build and run the program

在終端機執行：

```bash
dotnet run
```

您應該會看到：

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

專案資料夾中會出現名為 **Pdf417Basic.png** 的檔案。開啟後可見清晰的 PDF417 條碼，編碼文字為 *“Sample text for PDF417 barcode”*。

![已產生的 PDF417 條碼已儲存為 PNG 檔案](pdf417-barcode-example.png "已產生的 PDF417 條碼 PNG 格式")

*圖片說明：已產生的 PDF417 條碼 PNG 檔案之螢幕截圖，示範產生 PDF417 條碼教學的結果。*

## Step 4: Common variations and edge cases

### Changing the encoded data

將 `BarcodeGenerator` 的第二個參數替換為任意 UTF‑8 字串，例如：

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

產生器會自動將資料分割至多列多欄。

### Adjusting image size without losing quality

若需更大的列印影像，請提升 `XDimension.Pixels`：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Handling very long inputs

PDF417 最多可編碼 1 850 個字元。對於極長字串，您可能需要增加欄位數：

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

若內容超過最大容量，Aspose.BarCode 會拋出 `ArgumentException`。請將產生程式碼包在 try‑catch 區塊中，以提供友善的錯誤訊息。

### Saving in other formats

Aspose.BarCode 支援 BMP、JPEG、TIFF 與 SVG。可如下變更輸出格式：

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Step 5: Verify the barcode

您可以使用任何 PDF417 讀取器應用程式（例如支援條碼掃描的手機相機 App）掃描條碼，以確認其有效性。解碼後的文字應與您傳入產生器的字串相同。

若掃描失敗：

* 確認影像未被壓縮（使用 PNG 或無損 SVG）。  
* 檢查 `ErrorCorrectionLevel` 是否足夠符合使用環境。  
* 確認條碼尺寸符合掃描器的解析度需求。

## Conclusion

現在您已掌握如何在 C# 中使用 Aspose.BarCode **產生 PDF417 條碼**、自訂尺寸、設定欄位數，並將結果匯出為 PNG 影像。此方法適用於行動票證、庫存管理等各種情境。

接下來，您可以探索：

* 使用 `BarCodeReader` **讀取** PDF417 條碼。  
* 產生其他符號，例如 QR Code 或 DataMatrix。  
* 將 PNG 嵌入 PDF、報表或網頁中。  

歡迎嘗試不同的錯誤更正等級、影像格式與資料內容，以符合您專案的需求。祝開發順利！

## What Should You Learn Next?

以下教學與本指南緊密相關，能進一步深化您對相關 API 功能的掌握，並提供其他實作方式的範例：

- [如何在 C# 使用 Aspose.BarCode BarcodeGenerator 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [如何產生 PDF417 條碼並將其渲染為 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [如何在 C# 產生 PDF417 條碼並設定條碼尺寸](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}