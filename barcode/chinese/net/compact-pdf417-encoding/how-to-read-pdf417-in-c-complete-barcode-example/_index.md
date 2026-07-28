---
category: general
date: 2026-07-27
description: 如何在 C# 中快速读取 PDF417 条码。学习读取多个条码、解码图像，并在完整的 C# 条码示例中获取 Macro PDF417 元数据。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: zh
lastmod: 2026-07-27
og_description: 使用本分步指南在 C# 中读取 PDF417 条码。解码图像、处理多个条码，并在可直接运行的示例中提取 Macro PDF417 元数据。
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: 如何在 C# 中读取 PDF417 – 完整条码示例
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: 如何在 C# 中读取 PDF417 – 完整条码示例
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 – 完整条码示例

有没有想过在 C# 应用程序中 **如何读取 PDF417** 条码而不抓狂？你并不是唯一的遇到这种情况的人。无论你是在构建物流扫描器、票据验证器，还是仅仅需要从 PDF417 编码的身份证中提取数据，这个过程起初可能会显得有些神秘。  

在本教程中，我们将演示一个 **c# barcode example**，它读取 PDF417 图像，若存在则处理 **read multiple barcodes**，并提取所有可能需要的实用 Macro PDF417 元数据。

## 您将构建的内容

通过本指南的学习，你将拥有一个小型控制台程序，它能够：

1. 从磁盘加载条码图像。  
2. 解码 **PDF417**（包括 Macro PDF417）条码。  
3. 打印基本信息，如代码类型和文本。  
4. 输出完整的 Macro PDF417 字段集（文件 ID、段 ID、校验和等）。  

无需外部服务，仅使用一个 NuGet 包和几行 C# 代码。

## 前置条件 – 开始前需要的东西

- **.NET 6.0** 或更高（代码同样适用于 .NET Framework 4.6+）。  
- 最近版本的 **Aspose.BarCode for .NET** 库 – 通过 NuGet 安装 (`Install-Package Aspose.BarCode`)。  
- 包含 PDF417 条码的图像文件（演示使用 `ExtPDF417Meta.png`）。  
- 对 C# 控制台应用有基本了解（如果你已经写过 “Hello World”，就可以了）。

> **专业提示：** 如果没有现成的 PDF417 示例，可在 Aspose 演示站点生成，或使用能够创建 PDF417 标签的手机应用。

## 步骤 1：设置项目并安装库

首先，创建一个新的控制台项目：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

这将引入我们需要的 **c# barcode example** 依赖。打开 `Program.cs`，将默认代码替换为下面的骨架代码：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## 步骤 2：为 PDF417 初始化条码读取器

解决方案的核心是 `BarCodeReader` 类。我们告诉它要扫描的文件以及关注的条码类型——在本例中是 `DecodeType.Pdf417` 或宏变体 `DecodeType.MacroPdf417`。使用宏类型可确保捕获扩展字段。

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

为什么使用 `MacroPdf417` 而不是普通的 `Pdf417`？Macro PDF417 包含额外的元数据（文件 ID、段计数、时间戳等），许多实际应用都依赖这些信息——比如跨多页的运输清单。

## 步骤 3：读取图像中找到的所有条码

单张图像可能包含 **read multiple barcodes**——例如在 PDF417 旁边还有 QR 码。`ReadBarCodes()` 方法返回一个 `IEnumerable<BarCodeResult>`，我们可以遍历它。

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

如果图像仅包含一个 PDF417，循环仍会执行一次，使代码在将来需要从同一次扫描 **read multiple barcodes** 时保持灵活。

## 步骤 4：显示基本条码信息

在深入宏字段之前，显示条码类型和解码文本会很有帮助。这可以让你确认读取器确实识别出了 PDF417，而不是其他符号。

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` 将返回 *MacroPdf417*（如果未设置宏标志则为 *Pdf417*），而 `CodeText` 包含条码中编码的原始数据。

## 步骤 5：提取 Macro PDF417 元数据

`Extended` 属性让你深入了解 PDF417 特有的结构。下面打印的每个字段都直接对应 PDF417 宏规范。

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Each line pulls a different piece of the macro payload:

- **FileID** – 整个文档集的唯一标识符。  
- **SegmentID** – 多段文件的当前段。  
- **SegmentsCount** – 预期的总段数。  
- **FileName, Checksum, FileSize** – 用于验证传输文件完整性。  
- **TimeStamp, Addressee, Sender** – 许多物流系统嵌入的可选字段。  

如果源条码中缺少这些字段，库会返回 `null` 或 `0`，你可以根据需要进行处理。

## 步骤 6：运行完整示例

将所有内容整合在一起，下面是完整的、可直接运行的程序：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 预期输出

当你对有效的 `ExtPDF417Meta.png` 运行程序时，应该会看到类似如下的输出：

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

如果图像包含多个条码，

## 接下来你应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本示例演示的技术。每个资源都包含完整的可运行代码示例和逐步说明，帮助你掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何生成 PDF417 条码 – 紧凑 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何创建条码 – 使用 Aspose.BarCode 的紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条码](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}