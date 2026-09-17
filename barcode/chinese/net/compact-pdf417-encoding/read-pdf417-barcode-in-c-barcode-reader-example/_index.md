---
category: general
date: 2026-08-03
description: 使用 C# BarCodeReader 从图像读取 PDF417 条码 – 一个完整的条码读取示例，还展示了如何读取多个条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: zh
lastmod: 2026-08-03
og_description: 使用 C# BarCodeReader 示例快速读取 PDF417 条码。按照本分步指南解码宏 PDF417 并从图像中读取多个条码。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: 在 C# 中读取 PDF417 条码 – 完整的条码读取示例
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: 在 C# 中读取 PDF417 条码 – 条码读取示例
url: /zh/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中读取 PDF417 条码 – 条码读取示例

如果您需要从图像中读取 PDF417 条码数据，本指南将展示如何使用 C# 中的 **BarCodeReader** 类来实现。您将学习一个条码读取示例，该示例还能处理宏 PDF417，并且可以在单张图像中读取多个条码。

处理条码通常意味着要应对不同的图像来源、变化的光照条件，有时还会遇到诸如宏 PDF417 片段之类的复合数据。本教程涵盖了解码 PDF417 条码、提取其扩展字段以及从同一图片中处理多个条码所需的全部内容。完成后，您将拥有一个可运行的控制台程序，能够从图像文件读取条码并将详细信息打印到控制台。

## 您需要的准备

在开始之前，请确保您已具备：

* 已安装 .NET 6.0 SDK 或更高版本  
* 最近版本的 **Aspose.BarCode for .NET** NuGet 包（或任何提供 `BarCodeReader` 和 `DecodeType.MacroPdf417` 的兼容库）  
* 包含 PDF417 或宏 PDF417 条码的图像文件（示例使用 `ExtPDF417Meta.png`）  
* Visual Studio 2022 等代码编辑器或 IDE  

无需额外的服务或外部 API。

## 设置条码读取项目

1. **创建一个新的控制台项目**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **添加条码库**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **复制条码图像**  

   将 `ExtPDF417Meta.png`（或任何包含 PDF417 条码的图像）放入项目文件夹。  
   本教程默认文件位于 `YOUR_DIRECTORY/ExtPDF417Meta.png`。

项目现在已准备好编译并运行条码读取示例。

## 使用 BarCodeReader 读取 PDF417 条码

解决方案的核心是一个 `using` 块，它创建 `BarCodeReader` 实例，指定 `DecodeType.MacroPdf417`，并遍历每个检测到的条码。以下代码是一个完整的、独立的程序，您可以直接粘贴到 `Program.cs` 中。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**工作原理**：  

* `DecodeType.MacroPdf417` 告诉读取器查找 PDF417 的宏扩展，该扩展携带文件 ID、段计数、时间戳等额外元数据。  
* `using` 语句确保非托管资源（文件句柄、原生解码缓冲区）能够及时释放。  
* `foreach` 循环自动处理图像中 **所有** 条码，满足 *读取多个条码* 的需求。  

运行程序（`dotnet run`）后，您应看到类似以下的输出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

如果图像中包含多个 PDF417 条码，循环会为每个条码打印一个独立的块，从而演示如何 **从单张图片读取多个条码**。

## 从图像中读取多个条码

同一个 `BarCodeReader` 实例可以一次解码多种条码类型。若要将范围从仅宏 PDF417 扩展到任意 PDF417（甚至 QR、Code128 等），只需调整 `DecodeType` 标志：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* 是位掩码，您可以组合任意数量的受支持格式。这种灵活性使得代码片段成为一个 **条码读取示例**，能够适用于扫描商品标签、票据或身份证等各种使用场景。

## 安全访问宏 PDF417 字段

宏 PDF417 添加了一组丰富的扩展属性。但并非每个条码都包含所有字段。访问不存在的属性会抛出 `NullReferenceException`。最安全的做法是在打印之前先验证每个属性是否为 null：

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*为何重要*：在实际部署中，您可能会收到不包含宏数据的普通 PDF417 条码。防御性检查可确保应用程序在缺少字段时仍能正常运行，而不会崩溃。

## 常见陷阱与最佳实践

| 问题 | 产生原因 | 推荐解决方案 |
|------|----------|--------------|
| 图像路径不正确 | `BarCodeReader` 在解码前会抛出文件未找到异常 | 使用 `Path.Combine` 并通过 `File.Exists` 验证文件是否存在 |
| 低分辨率图像 | 解码器无法定位条码边缘，导致检测为零 | 提供至少 300 dpi 的最小分辨率以获得可靠结果 |
| 条码旋转 > 45° | 许多库默认假设条码是正向的 | 如有需要，启用 `reader.RecognitionOptions.RotateImage = true` |

## 接下来应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步深入。每篇资源都提供完整的可运行代码示例，并配有逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}