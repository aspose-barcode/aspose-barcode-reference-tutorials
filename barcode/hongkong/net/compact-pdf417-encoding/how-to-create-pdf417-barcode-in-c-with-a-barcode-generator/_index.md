---
category: general
date: 2026-11-17
description: 學習如何在 C# 中建立 PDF417 條碼 – 完整指南，教您如何使用 C# 條碼產生器從字串產生條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: zh-hant
lastmod: 2026-11-17
og_description: 快速在 C# 中建立 PDF417 條碼。本教學示範如何使用 C# 條碼產生器從字串產生條碼，並附上完整原始碼。
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: 在 C# 中建立 PDF417 條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: 如何使用條碼產生器在 C# 中建立 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器建立 PDF417 條碼

如果您需要在 .NET 應用程式中**建立 PDF417 條碼**，本指南將一步一步說明如何操作。您將學會**從純文字字串產生條碼**、設定符號尺寸，並將結果儲存為 PNG 檔案——全部使用可靠的 C# 條碼產生器。

以程式方式產生條碼可省去手動步驟，並確保品質一致。在本教學中，我們會從專案設定說明到最終影像產出，讓您今天就能將條碼產生整合到任何 C# 解決方案中。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本（程式碼同樣適用於 .NET Core 與 .NET Framework）
* Visual Studio 2022（或任何支援 C# 的 IDE）
* **Aspose.BarCode for .NET** 的授權或免費試用版——本教學範例所使用的函式庫
* 基本的 C# 語法概念

不需要額外的套件；NuGet 套件 `Aspose.BarCode` 已包含所有必須的類別。

## Step 1 – 設定 C# 條碼產生器

在**建立 PDF417 條碼**時，第一件事就是實例化 `BarcodeGenerator` 物件。此物件代表**c# 條碼產生器**，負責編碼、渲染與儲存。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*為什麼這很重要*：`EncodeTypes.Pdf417` 列舉告訴函式庫使用 PDF417 符號，這正是身分證與運輸標籤所採用的標準。字串 `"(01)12345678901234"` 是一個**從字串產生條碼**的範例，同時示範了**建立 GS1 條碼**資料的方式。

## Step 2 – 設定 X‑dimension（模組寬度）

X‑dimension 控制最小條（模組）的寬度。螢幕顯示時常用的值為 2 像素。

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

明確設定 X‑dimension 可避免產生器使用預設值，防止條碼對某些掃描器而言過小。

## Step 3 – 定義欄位數量

PDF417 允許調整欄位數量，這會影響條碼的形狀與資料容量。對於緊湊的標籤而言，四欄通常表現良好。

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

如果需要較高的條碼，只要增加欄位數量；函式庫會自動計算所需的列數。

## Step 4 – 將條碼儲存為影像

最後，將條碼匯出為 PNG 檔案。PNG 能保留清晰的邊緣並支援透明度。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

執行程式後會產生 `output/Gs1Pdf417.png`。使用任何影像檢視器開啟檔案，即可看到一個乾淨的**PDF417 條碼**，其編碼內容為您提供的 GS1 資料。

### Expected output

![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="使用 C# 條碼產生器產生的 PDF417 條碼（顯示 GTIN (01)12345678901234）"}

*上圖示範了完整程式碼範例的產出結果。此條碼可被任何相容 PDF417 的讀取器掃描。*

## Additional options and common variations

### Changing the image format

如果您偏好 JPEG 或 BMP，只需將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。其餘程式碼保持不變。

### Adjusting error correction level

PDF417 支援 0‑8 的錯誤更正等級。等級越高冗餘度越大，但條碼也會變大。

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generating other GS1 barcodes

相同的 `BarcodeGenerator` 也能為其他符號產生**建立 GS1 條碼**，例如 `EncodeTypes.Gs1DataMatrix` 或 `EncodeTypes.Gs1Qr`。只要交換列舉值即可：

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Handling empty or null data

在**從字串產生條碼**時，務必先驗證輸入：

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

這可避免執行時例外，並確保條碼符合 GS1 格式規範。

## Complete, runnable example

以下是完整程式碼，您可直接複製貼上至新的主控台專案。程式碼已包含所有必要的 `using` 指令、資料夾建立與錯誤處理。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**執行程式**（`dotnet run`）後，您會在 *output* 資料夾內找到 `Gs1Pdf417.png`。使用任何 PDF417 讀取器掃描，即可驗證 GTIN `(01)12345678901234` 已正確編碼。

## Frequently asked questions

**Q: 我可以在 .NET Framework 4.6 上使用這段程式碼嗎？**  
A: 可以。Aspose.BarCode 函式庫目標為 .NET Standard 2.0，與 .NET Framework 4.6 及以上版本相容。

**Q: 如果需要更高解析度的影像該怎麼辦？**  
A: 在儲存之前設定 `Resolution` 屬性：

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: 若不包含 GS1 應用程式識別碼，條碼仍然有效嗎？**  
A: 它仍會是標準的 PDF417 條碼，但不會被視為符合 GS1 規範的符號。當需要**建立 GS1 條碼**相容性時，請保留 `(01)` 前綴。

## Conclusion

您現在已掌握如何使用強大的**c# 條碼產生器**在 C# 中**建立 PDF417 條碼**。本教學涵蓋：

* 使用 GS1 資料實例化 `BarcodeGenerator`  
* 設定 X‑dimension 與欄位數量  
* 將結果儲存為 PNG 影像  
* 透過錯誤更正、不同格式與輸入驗證擴充解決方案  

有了這個基礎，您可以直接從字串產生任何 PDF417 或 GS1 條碼，將其嵌入報表，或傳送至印表機。探索 Aspose.BarCode API，加入顏色、邊距，或將多個條碼合併成單一影像。

**Next steps**：嘗試為 DataMatrix **建立 GS1 條碼**、實驗動態欄位計算，或將產生器整合至 ASP.NET Core 網路服務，讓它即時回傳條碼影像。

Happy coding!

## What Should You Learn Next?

以下教學與本指南的技術緊密相關，能進一步深化您的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索其他實作方式。

- [How to generate PDF417 barcode in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}