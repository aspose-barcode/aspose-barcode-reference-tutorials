---
category: general
date: 2026-08-03
description: 在 C# 中快速创建 PDF417 条码。了解如何生成 PDF417 条码以及如何使用 Aspose.Barcode 将条码图像保存为 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: zh
lastmod: 2026-08-03
og_description: 使用 Aspose.Barcode 在 C# 中创建 PDF417 条码。请按照本指南生成 PDF417 条码并高效保存条码图像。
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: 在 C# 中创建 PDF417 条码 – 完整编码教程
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: 在 C# 中创建 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 PDF417 条形码 – 步骤指南

如果您需要在 .NET 应用程序中**创建 PDF417 条形码**，本指南将准确展示如何生成 PDF417 条形码以及如何保存条形码图像。您最终会得到一个可用于报表、票据或移动扫描应用的 PNG 文件。

本教程涵盖从项目设置到最终 PNG 文件的全部过程。无需查阅外部文档，只需按照步骤操作并运行代码即可。

## 您需要的条件

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7+）
* Visual Studio 2022 或任何支持 C# 的 IDE
* Internet 访问以安装 **Aspose.Barcode for .NET** NuGet 包

这些前置条件可确保代码在无需额外配置的情况下成功编译。

## 创建 PDF417 条形码 – 项目设置

1. 打开命令提示符并创建一个新的控制台项目：

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. 添加 Aspose.Barcode 库：

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. 打开生成的 `Program.cs` 文件。文件顶部的 `using` 语句为您提供对条形码类的访问：

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

项目现在已准备好**创建 PDF417 条形码**。

## 使用 Aspose.Barcode 生成 PDF417 条形码

条形码创建的核心位于 `BarcodeGenerator` 类中。您需要指定符号类型（`EncodeTypes.Pdf417`）以及要编码的数据。

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### 为什么这很重要

* **EncodeTypes.Pdf417** 告诉库使用 PDF417 标准，该标准支持大容量数据和错误纠正。
* 提供 Unicode 字符可证明生成器能够在无需额外配置的情况下处理非 ASCII 输入。

## 如何配置条形码外观

您可以控制每个模块的大小、列数以及条形码是否使用紧凑（截断）模式。这些设置会影响可读性和文件大小。

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### 实用技巧

如果水平空间受限，需要更高的条形码，可增大 `Columns`。将 `Truncate` 设置为 `true` 可通过去除安静区来降低整体高度，这在移动设备屏幕上尤为适用。

## 如何将条形码图像保存为 PNG

在配置好生成器后，使用 `Save` 方法并提供文件路径和所需的图像格式。该方法会直接将图像写入磁盘。

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### 预期结果

运行程序后会在项目文件夹中生成 `CompactPdf417.png`。打开该文件即可看到一个紧凑的 PDF417 条形码，编码的字符串为 *Åspóse.Barcóde©*。该图像可嵌入 HTML、PDF 报告或打印在标签上。

## 完整源代码

下面是完整的可运行程序。将其复制到 `Program.cs` 中并执行 `dotnet run`。

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 验证输出

程序执行完毕后，您可以使用以下命令快速检查文件是否存在：

```bash
dotnet run && ls -l CompactPdf417.png
```

如果文件出现，则**创建 PDF417 条形码**的过程已成功。

## 常见变体和边缘情况

| 情形 | 调整 |
|-----------|------------|
| **Longer data string** | Increase `Columns` or set `Rows` to accommodate more codewords. |
| **Different image format** | Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`. |
| **Higher resolution** | Set `generator.Parameters.ImageResolution` before `Save`. |
| **Background color** | Use `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;` |
| **Exception handling** | Wrap `generator.Save` in a `try/catch` block to capture I/O errors. |

这些变体可帮助您根据特定设备或品牌需求定制条形码。

## 结论

您现在已经掌握了如何在 C# 中使用 Aspose.Barcode **创建 PDF417 条形码**、配置其外观，并将条形码图像 **保存为 PNG 文件**。完整示例展示了从项目设置到验证的每一步，使您能够将条形码生成集成到任何 .NET 解决方案中。

接下来，您可以进一步探索以下相关主题，如**如何生成 QR 码**、**在 PDF 文档中嵌入条形码**或**自定义条形码颜色**。这些内容均基于相同的生成器 API，帮助您以最小的工作量扩展应用的扫描能力。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在自己的项目中进一步掌握 API 功能并探索替代实现方式。

- [如何使用 Aspose.BarCode 创建条形码 – 紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码（ECC 200）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成自定义宽高比的 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}