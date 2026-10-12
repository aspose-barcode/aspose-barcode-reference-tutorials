---
category: general
date: 2026-10-02
description: 学习如何使用 C# 从图像读取条形码，并通过完整示例展示如何使用 Aspose.BarCode 解码 PDF417 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: zh
lastmod: 2026-10-02
og_description: 使用 Aspose.BarCode 在 C# 中读取图像中的条形码。本教程解释了如何解码 PDF417 条码并提取扩展元数据。
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: 使用 C# 从图像读取条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 Aspose.BarCode 在 C# 中读取图像中的条形码
url: /zh/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中读取图像中的条形码

如果您需要 **在 C# 中读取图像中的条形码**，本指南将为您提供完整、可运行的解决方案。您将学习如何解码 PDF417 条形码、访问其扩展宏数据，并将结果打印到控制台。

从图像读取条形码是库存系统、票据验证和文档处理的常见需求。本教程涵盖您所需的一切：必备包、代码说明、边缘情况处理以及预期输出。无需外部文档；示例可直接使用 Aspose.BarCode .NET 运行。

## 前置条件

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本已安装  
* Visual Studio 2022（或任意 C# IDE）  
* 对 **Aspose.BarCode** 的 NuGet 引用（版本 23.10 或更新）  
* 包含 PDF417 条形码的图像文件，例如 `ExtPDF417Meta.png`

如果缺少上述任意项，请安装 .NET SDK，使用 `dotnet add package Aspose.BarCode` 添加 NuGet 包，并将图像放置在项目可引用的文件夹中。

## 如何在 C# 中读取图像条形码 – 步骤详解

以下章节将实现过程拆分为逻辑步骤。每一步均包含代码片段、**为何**该步骤重要的说明，以及可在实际项目中应用的技巧。

### 步骤 1：为 PDF417 图像创建 `BarCodeReader`

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**为何重要** – `BarCodeReader` 构造函数接受图像路径和期望的条形码类型。指定 `MacroPdf417` 可缩小搜索范围，从而提升性能并在图像包含多种符号时减少误报。

**专业提示**：如果不确定条形码类型，可使用 `DecodeType.AllSupportedTypes`，随后再过滤结果。

### 步骤 2：遍历所有检测到的条形码

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**为何重要** – PDF417 宏图像可能包含多个段。`ReadBarCodes()` 方法返回一个集合，便于您逐段处理。

**边缘情况**：如果图像中不包含任何 PDF417 符号，集合为空，循环体将不会执行。建议在循环后添加检查，以提示用户。

### 步骤 3：访问扩展的 PDF417 宏元数据

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**为何重要** – `Extended.Pdf417` 属性公开 PDF417 规范定义的字段，如文件 ID、段 ID 和文件名。当您需要从多个条形码扫描中重建多页文档时，这些数据至关重要。

**专业提示**：在访问 `Pdf417` 之前，请始终确认 `barcodeResult.Extended` 不为 null。库会对不支持扩展数据的符号返回 null。

### 步骤 4：输出条形码文本和宏细节

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**为何重要** – 控制台输出让您立即看到解码文本和宏元数据，便于调试以及后续处理（例如将信息存入数据库）。

**预期输出**（假设示例图像仅包含一个宏段）：

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

如果图像包含三个段，循环将打印三块，每块的 `Segment ID` 不同。

### 步骤 5：处理错误并清理资源

`using` 语句会自动释放 `BarCodeReader`，但仍需捕获可能因文件缺失或不支持的格式导致的异常：

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**为何重要** – 稳健的应用程序不会因为文件缺失或图像损坏而崩溃。提供明确的错误信息有助于您或支持团队快速定位问题。

## 使用 Aspose.BarCode 解码 PDF417 条形码

本节自然出现的次要关键词 **how to decode pdf417 barcode**。解码 PDF417 条形码的模式与上文相同，只需在不需要宏信息时省略 `MacroPdf417` 标志：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**为何选择此变体** – 当条形码不携带宏信息时，使用 `DecodeType.Pdf417` 可降低处理开销并简化结果处理。

**常见问题**：*如果条形码被旋转怎么办？*  
Aspose.BarCode 会自动检测旋转并纠正，无需额外的图像预处理代码。

## 完整、可运行的示例

将下面的完整程序复制到新建的控制台项目（`dotnet new console`）中，并将 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替换为实际的图像路径。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

运行程序后，控制台将打印条形码类型、解码文本以及任何宏元数据。如果图像不包含 PDF417 宏，程序会优雅地提示您。

## 结论

现在，您已经掌握了使用 Aspose.BarCode **在 C# 中读取图像条形码**、**解码 PDF417 条形码**，以及提取宏‑PDF417 扩展字段的方法。该方案涵盖了初始化、遍历、元数据访问、错误处理以及纯 PDF417 解码的变体。

接下来您可以：

* 将提取的数据存入 SQL 数据库以便后续检索。  
* 合并多个段以重建原始文档。  
* 探索 Aspose.BarCode 支持的其他符号类型，...

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步运用 API 功能并探索替代实现方案。每篇资源均提供完整可运行的代码示例和逐步说明。

- [如何在 C# 中读取 PDF417 – 完整条形码示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [如何在 C# 中读取 PDF417 – 完整条形码读取器示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何使用 Aspose 在 C# 中生成 PDF417 条形码图像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}