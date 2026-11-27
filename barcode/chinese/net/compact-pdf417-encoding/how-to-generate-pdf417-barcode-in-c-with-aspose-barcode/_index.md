---
category: general
date: 2026-11-27
description: 学习如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条码。调整尺寸、设置列数，并在几行代码内将其保存为 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: zh
lastmod: 2026-11-27
og_description: 在 C# 中即时生成 PDF417 条码。本教程展示如何配置尺寸、列数，并将结果保存为 PNG 图像。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: 在 C# 中生成 PDF417 条形码 – 使用 Aspose.BarCode 的快速指南
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
title: 如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 生成 PDF417 条码

如果您需要在 .NET 应用程序中**生成 PDF417 条码**，本指南将为您展示一个简洁的端到端解决方案。您将看到如何创建条码、微调其尺寸，并将结果写入 PNG 文件——全部使用 Aspose.BarCode 库。

在需要对大量数据进行编码以便在移动设备、登机牌或库存标签上扫描时，生成 PDF417 条码是常见的需求。完成本教程后，您将拥有一个可直接运行的控制台程序，能够生成高质量的 PNG 图像。

## 前提条件

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本已安装  
* 最新版本的 **Aspose.BarCode for .NET**（NuGet 包 `Aspose.BarCode`）  
* IDE 或编辑器（Visual Studio、VS Code、Rider 等）  

由于 Aspose.BarCode 是跨平台的，代码可在 Windows、Linux 和 macOS 上运行。

## 第 1 步：创建新的控制台项目

打开终端并运行：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

此命令会创建一个名为 **Pdf417Demo** 的最小 C# 项目，并添加 `Aspose.BarCode` 依赖。

## 第 2 步：编写条码生成代码

打开 **Program.cs**，将其内容替换为以下代码：

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

### 为什么每行代码都很重要

* **BarcodeGenerator** – 创建条码图像的核心类。传入 `EncodeTypes.Pdf417` 即可选择 PDF417 编码方式。  
* **XDimension.Pixels** – 决定最小条宽。数值越小图像越小，数值越大在低分辨率扫描仪上可提升可读性。  
* **Pdf417.Columns** – 控制数据列数。列数更多会生成更短但更高的条码，列数更少则条码更宽。  
* **ErrorCorrectionLevel** – 较高的纠错级别会添加冗余数据，使条码在受损时仍可读取，但会增大尺寸。  
* **Save(..., BarCodeImageFormat.Png)** – 将图像以 PNG 格式写入磁盘，PNG 为无损格式，适合后续处理或嵌入文档。

## 第 3 步：构建并运行程序

在终端中执行：

```bash
dotnet run
```

您应该会看到：

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

项目文件夹中会出现名为 **Pdf417Basic.png** 的文件。打开后可看到清晰的 PDF417 条码，编码的文本为 *“Sample text for PDF417 barcode”*。

![已保存为 PNG 文件的生成的 PDF417 条码](pdf417-barcode-example.png "PNG 格式的生成 PDF417 条码")

*图片说明：已生成并保存为 PNG 文件的 PDF417 条码截图，展示本教程的生成结果。*

## 第 4 步：常见变体和边缘情况

### 更改编码数据

将 `BarcodeGenerator` 的第二个参数替换为任意 UTF‑8 字符串，例如：

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

生成器会自动将数据分布到行和列中。

### 在不失真的情况下调整图像尺寸

如果需要更大的打印图像，可增大 `XDimension.Pixels`：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### 处理超长输入

PDF417 最多可编码 1 850 个字符。对于极长的字符串，您可能需要增加列数：

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

如果内容超过最大容量，Aspose.BarCode 会抛出 `ArgumentException`。请将生成代码放在 try‑catch 块中，以提供友好的错误提示。

### 以其他格式保存

Aspose.BarCode 支持 BMP、JPEG、TIFF 和 SVG。可以这样更改保存格式：

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## 第 5 步：验证条码

您可以使用任何 PDF417 读取器应用（例如支持条码扫描的智能手机相机应用）扫描条码，以确认其有效性。解码后的文本应与您传入生成器的字符串一致。

如果扫描失败：

* 确保图像未被压缩（使用 PNG 或无损 SVG）。  
* 验证 `ErrorCorrectionLevel` 是否足够高，以适应目标环境。  
* 检查条码尺寸是否符合扫描仪的分辨率要求。

## 结论

现在您已经掌握了如何在 C# 中使用 Aspose.BarCode **生成 PDF417 条码**、自定义尺寸、设置列数，并将结果导出为 PNG 图像。这种方法适用于从移动票务到库存管理的各种场景。

接下来，您可以进一步探索：

* 使用 `BarCodeReader` **读取** PDF417 条码。  
* 生成其他符号，如 QR Code 或 DataMatrix。  
* 将 PNG 嵌入 PDF、报告或网页中。  

欢迎尝试不同的纠错级别、图像格式和数据负载，以满足项目需求。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每篇资源均提供完整的可运行代码示例和逐步说明。

- [如何在 C# 中使用 Aspose.BarCode BarcodeGenerator 生成 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [如何生成 PDF417 条码并将其渲染为 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [如何在 C# 中生成 PDF417 条码并设置条码尺寸](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}