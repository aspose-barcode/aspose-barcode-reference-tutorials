---
category: general
date: 2026-10-14
description: 在 C# 中创建一个控制台条形码扫描器，能够读取 PDF417 条码，处理 macro PDF417，并从单张图像中解码多个条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: 在 C# 中创建一个控制台条形码扫描器，以快速读取图像中的 PDF417 和 macro PDF417 条码。本逐步指南展示了如何在一张图片中解码多个条码。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: 在 C# 中创建控制台条形码扫描器 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: 在 C# 中创建控制台条形码扫描器 – 读取 PDF417 条码示例
url: /zh/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建控制台条码扫描器 – 读取 PDF417 条码示例

`BarCodeReader` 是 Aspose.BarCode 的核心类，用于从图像中解码条码并返回详细的元数据。如果您需要从图像中读取 PDF417 条码数据，本指南将展示如何在 C# 中使用 **BarCodeReader** 类。您将学习一个 **创建控制台条码扫描器** 示例，该示例还支持宏 PDF417，并且可以在单个图像中读取多个条码。

处理条码通常意味着要应对不同的图像来源、变化的光照条件，有时还会遇到诸如宏 PDF417 段之类的复合数据。本教程涵盖了解码 PDF417 条码、提取其扩展字段以及处理同一图片中多个条码所需的全部内容。完成后，您将拥有一个可运行的控制台程序，能够从图像文件读取条码并将详细信息打印到控制台。

## 快速答案
- **示例的作用是什么？** 它创建了一个控制台条码扫描器，从图片中读取 PDF417 和宏 PDF417 条码，并打印所有解码字段。  
- **需要哪个库？** Aspose.BarCode for .NET（NuGet）。  
- **能一次读取多个条码吗？** 可以——读取器会遍历图像中发现的每个条码。  
- **需要互联网连接吗？** 不需要，库完全离线工作。  
- **支持哪个 .NET 版本？** .NET 6.0 或更高。

## 您需要的条件

在开始之前，请确保您拥有：

* .NET 6.0 SDK 或更高版本已安装  
* 最近版本的 **Aspose.BarCode for .NET** NuGet 包（或任何提供 `BarCodeReader` 和 `DecodeType.MacroPdf417` 的兼容库）  
* 包含 PDF417 或宏 PDF417 条码的图像文件（示例使用 `ExtPDF417Meta.png`）  
* 如 Visual Studio 2022 等代码编辑器或 IDE  

无需额外的服务或外部 API。

## 为条码读取设置项目

1. **创建新的控制台项目**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **添加条码库**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **复制条码图像**  

   将 `ExtPDF417Meta.png`（或任何包含 PDF417 条码的图像）放入项目文件夹中。  
   在本教程中，我们假设文件位于 `YOUR_DIRECTORY/ExtPDF417Meta.png`。

项目现在已准备好编译并运行条码读取示例。

## 如何在 C# 中创建控制台条码扫描器？

`BarCodeReader` 是 Aspose.BarCode 提供的类，用于从图像中读取条码并返回其解码数据。  
使用 `BarCodeReader` 加载图像，将解码类型设置为 `MacroPdf417`，并遍历结果——这就是创建控制台条码扫描器所需的全部。读取器借助 `using` 语句自动释放本机资源，无需手动管理内存。此方法适用于 .NET 支持的任何图像格式，如 PNG、JPEG 或 BMP。

### 步骤详解

解决方案的核心是一个 `using` 块，它创建 `BarCodeReader` 实例，指定 `DecodeType.MacroPdf417`，并遍历每个检测到的条码。以下代码是一个完整的、独立的程序，您可以将其粘贴到 `Program.cs` 中。

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

**为什么这样有效**：  

* `DecodeType.MacroPdf417` 告诉读取器查找 PDF417 的宏扩展，该扩展携带额外的元数据，如文件 ID、段计数和时间戳。  
* `using` 语句确保非托管资源（文件句柄、本机解码缓冲区）及时释放。  
* `foreach` 循环自动处理图像中包含的 **所有** 条码，满足 *读取多个条码* 的需求。  

运行程序 (`dotnet run`) 时，您应该会看到类似以下的输出：

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

如果图像包含多个 PDF417 条码，循环会为每个条码打印一个单独的块，从而演示如何从单张图片 **读取多个条码**。

## 如何从图像中读取多个条码？

使用单个 `BarCodeReader` 实例，并将 `DecodeType` 标志设置为包含所有想要检测的格式。通过使用位或运算符组合标志，您可以让库一次性查找 PDF417、QR、Code‑128 等多种符号。这消除了对多个读取器的需求并降低了处理时间。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

`DecodeType` 是位掩码，因此您可以组合任意数量的支持格式。Aspose.BarCode 支持 **30+ 条码符号**，包括 QR、DataMatrix、Code‑128 和 UPC‑A，使单个扫描器能够处理诸如产品标签、票据验证和身份验证等多种使用场景。

## 什么是宏 PDF417，如何安全访问其字段？

宏 PDF417 是 PDF417 符号的扩展，允许将大型数据集拆分到多个条码符号中。  
宏 PDF417 添加了一套丰富的扩展属性。然而，并非每个条码都包含所有字段。访问缺失的属性可能会抛出 `NullReferenceException`。最安全的做法是在打印之前验证每个属性，以确保即使宏数据缺失，应用程序也能保持稳定。

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*为什么这很重要*：在实际部署中，您可能会收到缺少宏数据的普通 PDF417 条码。防御性检查可确保您的应用程序在没有崩溃的情况下继续运行。

## 常见陷阱与最佳实践

| 问题 | 原因 | 推荐解决方案 |
|-------|----------------|-----------------|
| 图像路径不正确 | `BarCodeReader` 在任何解码发生之前抛出文件未找到异常 | 使用 `Path.Combine` 并通过 `File.Exists` 验证文件是否存在 |
| 低分辨率图像 | 解码器无法定位条码边缘，导致检测为零 | 提供至少 300 dpi 的分辨率以获得可靠结果 |
| 条码旋转 > 45° | 许多库假设条码是正立的 | 如果图像可能被旋转，启用 `reader.RecognitionOptions.RotateImage = true` |
| 缺少宏字段 | 尝试读取空属性会导致崩溃 | 在访问宏属性之前始终检查是否为 `null` |
| 大批量处理 | 为每个文件重新创建读取器会增加开销 | 在处理大量图像时，使用单个 `BarCodeReader` 实例并切换不同的流 |

## 为什么在控制台条码扫描器中使用 Aspose.BarCode？

Aspose.BarCode 能解码 **30+ 条码类型**，并且在不将整个文件加载到内存的情况下处理高达 **200 MP** 的图像，在典型的 3.2 GHz CPU 上实现 **每秒 150 帧** 的吞吐量。这些量化的能力使其成为延迟和准确性至关重要的高容量本地扫描解决方案的可靠选择。

## 接下来您应该学习什么？

以下教程涵盖了与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方法。

- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条码](/barcode/english/net/datamatrix-barcode-reading/)
- [读取 DataMatrix 条码 C# – 自动生成 DataMatrix 模式](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [从图像读取条码 – 使用 Aspose.BarCode 掌握 Java 中的条码区域提取](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## 常见问题

**问：我可以在生产环境中使用此扫描器吗？**  
答：可以。购买商业版 Aspose.BarCode 许可证以去除评估水印并获得完整支持。

**问：该库在 Linux 和 macOS 上能工作吗？**  
答：当然可以。Aspose.BarCode for .NET 是跨平台的，可在 Windows、Linux 和 macOS 上的 .NET 6+ 环境运行。

**问：如何处理非常大的图像而不耗尽内存？**  
答：使用 `LoadOptions` 构造函数启用流式模式，图像将分块处理，而不是一次性全部加载到内存中。

**问：能解码加密或受密码保护的图像吗？**  
答：读取器可以处理使用标准 PNG/JPEG 密码方案加密的图像；只需通过 `reader.ImagePassword` 提供密码即可。

**问：如果我的条码部分受损怎么办？**  
答：启用错误纠正选项，例如 `reader.RecognitionOptions.CorrectErrors = true`，以提升对损坏或噪声的容错能力。

---

**最后更新：** 2026-10-14  
**测试版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何在 C 中读取 Pdf417 完整条码读取示例](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [读取多个条码 C 完整指南（使用 Pdf417）](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [使用 C 条码读取器示例从图像解码条码](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}