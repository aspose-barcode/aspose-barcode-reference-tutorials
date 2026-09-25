---
category: general
date: 2026-08-22
description: 如何在 C# 中读取 PDF417 条码的分步指南，包括如何从图像中读取多个条码并提取 MacroPdf417 详细信息。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: zh
lastmod: 2026-08-22
og_description: 如何在 C# 中快速读取 PDF417 条码。本教程展示了如何从图像中读取多个条码并获取 MacroPdf417 扩展信息。
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: 如何在 C# 中读取 PDF417 条码 – 完整编程演练
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中读取 PDF417 条形码 – 完整指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 条形码 – 完整指南

如果您需要在 .NET 应用程序中 **how to read PDF417** 条码，本教程提供了一个可直接运行的解决方案。您将学习如何从单个图像读取多个条码，提取完整的 MacroPdf417 数据集，并在控制台中显示。该方法使用 Aspose.BarCode for .NET 库，仅需几行代码。

从图像读取条码是库存系统、票据验证和文档管理中的常见任务。通过本指南，您将能够解码任何 PDF417 或 MacroPdf417 条码，在一张图片中处理多个代码，并了解 MacroPdf417 提供的扩展字段。

## Prerequisites

- .NET 6.0 SDK 或更高版本（代码同样可以在 .NET Framework 4.7+ 上编译）
- Visual Studio 2022 或您喜欢的任何 C# 编辑器
- Aspose.BarCode for .NET NuGet 包（`Install-Package Aspose.BarCode`）
- 包含 MacroPdf417 条码的示例图像（例如 `MacroPdf417.png`）

无需额外配置；库内部已处理图像加载和解码。

## 如何在 C# 中从图像读取 PDF417 条码

解决方案的核心是 `BarCodeReader` 类。它打开图像，检测指定类型的所有条码，并返回 `BarCodeResult` 对象的集合。下面的代码展示了一个完整的控制台程序。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 为什么每行代码都很重要

| 步骤 | 目的 |
|------|------|
| **1️⃣ Initialize** | 创建一个绑定到图像文件的 `BarCodeReader`，并将检测限制在 MacroPdf417 符号上，从而加快处理速度。 |
| **2️⃣ Iterate** | `ReadBarCodes()` 返回 **所有** 与请求类型匹配的条码，使您能够 **read multiple barcodes** 而无需额外循环。 |
| **3️⃣ Basic output** | 显示通用的 `CodeTypeName` 和可读的 `CodeText`。这对于日志记录或快速验证非常有用。 |
| **4️⃣ Extended data** | MacroPdf417 包含额外的元数据（文件 ID、段计数、时间戳等）。`Extended.Pdf417` 对象直接公开每个字段，便于存储或验证完整的数据包。 |

将程序运行在有效的 MacroPdf417 图像上会产生类似以下的控制台输出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

输出确认库成功读取了条码，提取了文本，并提供了每个 MacroPdf417 字段。

## 从单张图像读取多个条码

许多实际场景会在同一标签上放置多个 PDF417 符号——比如包含承运人代码、跟踪号码和海关申报的装运清单。上面的代码块已经 **read multiple barcodes**，因为 `ReadBarCodes()` 返回所有匹配项的可枚举集合。无需额外配置；只需像示例中那样遍历结果即可。

如果希望将读取器限制为标准 PDF417（非宏）同时仍处理多个代码，只需将 `DecodeType.MacroPdf417` 替换为 `DecodeType.Pdf417`。其余逻辑保持不变。

## 理解 MacroPdf417 扩展数据

MacroPdf417 是常规 PDF417 规范的扩展。它将大负载拆分为多个段，并添加一个小标题来描述整个文件。最相关的字段包括：

- **MacroPdf417FileID** – 所有同一文件段共享的唯一标识符。
- **MacroPdf417SegmentID** – 当前段的序号。
- **MacroPdf417SegmentsCount** – 预期的总段数。
- **MacroPdf417FileName** – 随条码传输的可选文件名。
- **MacroPdf417Checksum** – 整个文件的错误检查值。
- **MacroPdf417FileSize** – 原始二进制负载的大小。
- **MacroPdf417TimeStamp** – 条码生成时的 ISO‑8601 时间戳。
- **MacroPdf417Addressee / Sender** – 用于路由的可选文本字段。
- **MacroPdf417Terminator** – 指示该段是否为最后一段。

当收到所有段后，您可以通过 `MacroPdf417SegmentID` 对段进行排序，并将 `CodeText` 值拼接起来，以重建原始文件。只要拥有这些字段，实现逻辑相当直接。

## 常见陷阱与专业技巧

- **图像质量很重要** – 低分辨率或高度压缩的 PNG/JPEG 文件可能导致检测遗漏。打印条码时请使用至少 300 dpi 的分辨率。
- **混合符号** – 如果图像同时包含 MacroPdf417 和普通 PDF417，可实例化两个读取器（分别对应各自的 `DecodeType`），或使用 `DecodeType.AllSupported` 并通过 `result.CodeTypeName` 过滤结果。
- **内存使用** – `using` 语句会及时释放 `BarCodeReader`，防止大型图像缓冲区长时间占用内存。
- **线程安全** – `BarCodeReader` 不是线程安全的。如果并行解码图像，请为每个线程创建单独实例。
- **错误处理** – 将 `ReadBarCodes()` 调用包装在 try/catch 块中，以捕获 `BarCodeException`，处理损坏的图像。

## 完整工作示例回顾

下面是完整的程序代码，您可以复制到新的控制台项目中。它包含所有 `using` 指令、图像路径常量以及释放模式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

使用 `dotnet build` 编译，使用 `dotnet run` 运行。控制台会打印每个条码的基本数据以及完整的 MacroPdf417 负载。

## 下一步

- **Reconstruct multipart files** – collect all segments, sort by `MacroPdf417SegmentID`, and concatenate `CodeText` to


## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方案。每个资源都提供完整的可运行代码示例和逐步解释。

- [如何生成 PDF417 条码 – 紧凑 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何在 Java 中读取带有土耳其字符的 PDF417 条码](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [如何在 Java 中使用 Aspose 读取 PDF417 条码（中文）](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}