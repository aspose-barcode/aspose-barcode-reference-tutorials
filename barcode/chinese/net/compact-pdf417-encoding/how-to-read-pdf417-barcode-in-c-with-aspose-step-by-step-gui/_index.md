---
category: general
date: 2026-10-24
description: 学习如何使用 Aspose.BarCode 在 C# 中读取 PDF417 条码。本教程涵盖读取条码图像、提取 Macro PDF417
  字段以及处理常见场景。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: zh
lastmod: 2026-10-24
og_description: 如何在 C# 中使用 Aspose.BarCode 读取 PDF417 条码。请遵循本完整教程解码图像、获取 Macro PDF417
  元数据，并避免常见陷阱。
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: 使用 Aspose 在 C# 中读取 PDF417 条形码 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: 使用 Aspose 在 C# 中读取 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose 读取 PDF417 条码 – 步骤指南

如果您需要在 .NET 应用程序中 **读取 PDF417 条码**，本指南将向您展示如何使用 Aspose.BarCode 库在 C# 中读取 PDF417 条码。无论是处理扫描文档、移动端捕获，还是批量导入的图像，下面的代码都能解码条码并提取您可能需要的所有 Macro PDF417 属性。

在 C# 中读取条码图像可能会让人望而生畏，尤其是当条码包含扩展元数据时。本教程通过提供完整可运行的示例、解释每一行代码，并覆盖缺失宏段或图像损坏等边缘情况，消除您的猜测。完成后，您将能够自信地将 PDF417 解码集成到任何 C# 项目中。

## 前置条件

开始之前，请确保您拥有：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* **Aspose.BarCode for .NET** 的许可证或免费评估版 – 您可以从 Aspose 官网获取临时密钥  
* 包含 Macro PDF417 条码的图像文件（例如 `ExtPDF417Meta.png`）

> **专业提示：** 如果您只想尝试，Aspose 提供 30 天试用，包含完整的条码读取功能。

## 第一步：安装 Aspose.BarCode NuGet 包

在终端中打开项目文件夹并运行：

```bash
dotnet add package Aspose.BarCode
```

该包会添加 `Aspose.BarCode.ReadRecognition` 命名空间，其中包含用于解码图像的 `BarCodeReader` 类。

## 第二步：为 PDF417 图像创建 BarCodeReader

`BarCodeReader` 构造函数接受两个参数：图像文件的路径以及您想要的 `DecodeType`。指定 `DecodeType.MacroPdf417` 可让 Aspose 查找 Macro PDF417 符号并自动填充扩展属性。

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### 为什么使用 `DecodeType.MacroPdf417`？

* **Macro PDF417** 保存了额外字段（文件 ID、段计数、时间戳等），这些在标准 PDF417 中不存在。  
* 只有在请求宏类型时，`BarCodeResult` 的 `Extended` 属性才会被填充，从而省去单独的解析步骤。

## 第三步：遍历所有检测到的条码

一张图像可能包含多个 PDF417 符号（例如文档被拆分到多页时）。`ReadBarCodes()` 方法返回 `IEnumerable<BarCodeResult>`，您可以对其进行循环。

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

如果图像中不包含任何条码，循环根本不会执行，程序会优雅地退出。这种行为使代码在批处理时更加安全，因为有些文件可能没有条码。

## 第四步：输出 Macro PDF417 扩展属性

`Extended.Pdf417` 属性聚合了所有宏特定字段。每个字段都直接映射到 PDF417 规范，您可以将它们存入数据库、记录日志，或用于进一步校验。

```csharp
        // Macro PDF417 extended properties
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
    }
}
```

### 各属性含义

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | 整个多段文档的唯一标识符。 |
| **MacroPdf417SegmentID** | 当前段的索引（从 0 开始）。 |
| **MacroPdf417SegmentsCount** | 属于该文件的段总数。 |
| **MacroPdf417FileName** | 条码中嵌入的可选文件名。 |
| **MacroPdf417Checksum** | 宏数据块的 CRC‑16 校验和。 |
| **MacroPdf417FileSize** | 原始文件大小（字节）。 |
| **MacroPdf417TimeStamp** | 生成宏条码的时间戳。 |
| **MacroPdf417Addressee** | 文档的预期收件人。 |
| **MacroPdf417Sender** | 文档的发送方。 |
| **MacroPdf417Terminator** | 表示宏序列结束的终止标志。 |

在您需要重建被拆分为多个 PDF417 符号的大型 PDF 或图像时，这些字段尤为有用。

## 第五步：处理常见边缘情况

### 缺失宏字段

有时生成的 PDF417 条码未包含可选宏字段。访问缺失属性会返回 `null` 或 `0`。如果您计划存储这些值，请做好防护：

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### 图像损坏或质量低下

如果图像模糊，可以通过启用 `BarCodeReader` 的质量选项来提升检测率：

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

这些设置是可选的，但在扫描文档时可以显著提高成功率。

### 单张图像中包含多种条码格式

如果您怀疑图像中可能存在其他条码类型，请使用 `DecodeType.AllSupported` 并过滤结果：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## 完整可运行示例

将以下程序复制到新的控制台项目（`dotnet new console`）中并运行。将 `imagePath` 变量替换为您自己的 Macro PDF417 图像所在位置。

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**预期输出**（数值会根据您的图像而不同）：

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

如果图像不包含 Macro PDF417 符号，程序将不输出任何内容并静默退出——这对于处理大量文件的批处理任务非常合适。

## 常见问题

**Q: 可以使用相同的代码读取标准 PDF417（非宏）吗？**  
A: 可以。将 `DecodeType.MacroPdf417` 改为 `DecodeType.Pdf417`。`Extended` 属性将为空，但 `CodeText` 和 `CodeTypeName` 仍然可用。

**Q: Aspose.BarCode 是否支持从流而非文件路径读取？**  
A: 完全支持。使用 `new BarCodeReader(Stream, DecodeType)` 重载，并传入 `FileStream` 或 `MemoryStream`。当图像来自 Web API 时非常有用。

**Q: 如何验证校验和？**  
A: `MacroPdf417Checksum` 字段包含原始 CRC‑16 值。您可以在重建的文件上重新计算校验和并与该值比较，以确保数据完整性。

## 后续步骤与相关主题

* **写入 PDF417 条码** – 探索 `BarCodeGenerator` 以创建用于测试的宏条码。  
* **合并多个段** – 读取完所有段后，按 `MacroPdf417SegmentID` 排序并连接 `CodeText`，即可重建原始负载。  
* **性能调优** – 在高吞吐场景下，复用单个 `BarCodeReader` 实例以处理多张图像，并

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}