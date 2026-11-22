---
category: general
date: 2026-11-20
description: 学习如何使用 Aspose.BarCode 在 C# 中创建宏 PDF417 条形码。本指南涵盖元数据、参数以及图像保存。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: zh
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中创建宏 PDF417 条码。请参阅本完整教程，了解如何设置元数据、配置参数并导出 PNG。
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: 在 C# 中创建宏 PDF417 条码 – 逐步指南
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
title: 如何在 C# 中使用 Aspose.BarCode 创建宏 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 创建宏 PDF417 条形码

如果您需要在 .NET 应用程序中**创建宏 PDF417 条形码**，本教程将展示具体步骤。您将看到如何配置宏特定的元数据、调整视觉设置，并将结果保存为 PNG 文件。

在需要将大型数据集拆分到多个符号中，同时保留文件级标识符时，生成宏 PDF417 条形码非常有用。在下面的示例中，我们使用 Aspose.BarCode 库，它为所有 PDF417 功能提供了流畅的 API。

阅读完本指南后，您将拥有一个可直接运行的控制台程序，生成包含完整宏信息的条形码图像。

## 前提条件

* 已安装 .NET 6.0 SDK 或更高版本。
* Visual Studio 2022（或任何支持 C# 的 IDE）。
* **Aspose.BarCode for .NET** NuGet 包 (`Aspose.BarCode`)。

您可以使用以下命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：初始化宏 PDF417 条形码生成器

第一步是使用 `EncodeTypes.MacroPdf417` 枚举值实例化 `BarcodeGenerator`。这告诉库将条形码视为宏 PDF417 符号。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*为什么这很重要*：选择 `MacroPdf417` 会在 `Pdf417` 参数对象上启用所有宏相关属性。

## 步骤 2：设置基本视觉外观

可读的条形码始于合适的模块大小和列数。`XDimension.Pixels` 属性控制单个模块的宽度，而 `Pdf417.Columns` 定义每行包含多少数据列。

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

调整这些数值会影响扫描仪的可靠性和图像大小。

## 步骤 3：定义宏文件标识细节

宏 PDF417 需要文件标识符、段标识符以及总段数。这三个字段使扫描仪能够重新组装原始数据集。

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

这些 **宏 PDF417 参数** 是宏功能的核心。没有它们，扫描仪无法将符号关联起来。

## 步骤 4：添加可选宏元数据

除了必需的标识符外，宏格式还支持额外字段，如校验和、文件大小、时间戳、收件人、发送者以及终止标志。提供这些数据可提升错误检测并为下游系统提供上下文。

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

*专业提示*：如果您的工作流不需要某个字段，可以保持其默认值。库会在条形码中省略相应的数据元素。

## 步骤 5：保存条形码图像

在配置完所有参数后，调用 `Save` 导出条形码。示例将 PNG 文件存储在用户指定的目录中。

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

程序结束后，`ExtPDF417Meta.png` 包含一个宏 PDF417 条形码，编码文本 `"Åspóse.Barcóde©"` 以及所有宏元数据。

## 完整源代码

下面是完整的、独立的程序。将其复制到新的控制台项目中，并在安装 Aspose.BarCode NuGet 包后运行。

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

### 预期输出

运行程序会打印类似以下的确认行：

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

打开 PNG 文件会看到密集的高对比度条形码。使用兼容 PDF417 的扫描仪扫描后，会返回原始文本以及所有宏字段。

## 常见问题与边缘情况

### 如果需要超过 20 个段怎么办？

`MacroPdf417SegmentsCount` 属性可设置至 `255`。确保接收系统能够处理更大的段计数，并考虑将数据拆分为可管理数量的符号。

### 校验和如何影响扫描？

CCITT‑16 校验和 (`MacroPdf417Checksum`) 提供额外的错误检查层。如果扫描仪检测到不匹配，它将拒绝该条形码。如果您的工作流不需要校验和，可以省略它。

### 是否可以在没有 Aspose 的情况下生成 PDF417 宏条形码？

可以，其他库（例如 ZXing.Net、Dynamsoft）支持 PDF417，但宏特定字段通常缺失。Aspose.BarCode 提供了最完整的宏元数据实现。

### 保存时支持哪些图像格式？

`Save` 方法接受 `BarCodeImageFormat` 中定义的任何格式，如 `Png`、`Jpeg`、`Gif`、`Bmp` 和 `Tiff`。请选择与下游处理流水线匹配的格式。

## 结论

现在您已经了解如何在 C# 中使用 Aspose.BarCode **创建宏 PDF417 条形码**。本教程涵盖了生成器初始化、视觉设置、宏文件标识符、可选元数据以及图像导出。凭借此基础，您可以在库存系统、文档追踪或任何需要分段数据传输的场景中嵌入宏 PDF。

接下来的步骤包括尝试不同的 `XDimension` 值以获得更高分辨率、添加纠错级别调整，或将条形码集成到直接返回 PNG 流的 Web API 中。有关相关主题，请参阅 **barcode generator example**、**PDF417 macro parameters** 和 **macro PDF417 metadata** 处理的教程。

祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何在 C# 中使用宏 PDF417 选项创建 PDF417 条形码图像](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [C# 从图像读取条形码 – 完整指南（含宏 PDF417）](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [如何使用 Aspose 创建 PDF417 条形码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}