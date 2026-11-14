---
category: general
date: 2026-11-14
description: 学习如何使用 Aspose.BarCode 在 C# 中创建条形码图像。本分步指南涵盖条形码生成器 C# 设置、GS1 格式化以及 PNG
  导出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: zh
lastmod: 2026-11-14
og_description: 快速在 C# 中创建条形码图像。遵循本指南学习如何生成条形码、使用 C# 条形码生成器，并导出 GS1 MicroPDF417 PNG。
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: 在 C# 中创建条形码图像 – GS1 MicroPDF417 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中使用 GS1 MicroPDF417 创建条形码图像
url: /zh/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 GS1 MicroPDF417 创建条形码图像

如果您需要在 C# 中 **创建条形码图像**，本指南为您提供一个完整、可直接运行的解决方案。您将了解 **如何生成符合 GS1 标准的条形码** 数据，配置生成器，并导出高质量的 PNG 文件。

本教程涵盖了从安装所需库到处理常见数据格式陷阱的全部内容。完成后，您只需几行代码即可生成 **来自数据的条形码图像**，并且会了解每个设置的意义。

## 前置条件

* 已安装 .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）。
* 使用 Visual Studio 2022 或 Visual Studio Code 等 IDE。
* **Aspose.BarCode for .NET** NuGet 包。使用以下方式安装：

```bash
dotnet add package Aspose.BarCode
```

* 对 C# 语法和 GS1 应用标识符（AI）格式有基本了解。

> **专业提示：** 请保持库版本为最新；最新版本增加了对新条形码符号的支持并提升了性能。

## 使用 BarcodeGenerator 创建条形码图像

本节包含核心实现。代码创建一个 **barcode generator c#** 实例，配置可读性的 X‑dimension，并将结果保存为 PNG 文件。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### 为什么每行代码都很重要

* **EncodeTypes.MicroPdf417** 告诉库使用 GS1 MicroPDF417 符号，该符号紧凑且适合移动扫描。
* **data string** 必须以 GS1 AI `(01)`（全球贸易项目编号，GTIN）开头，随后是 `(21)`（序列号）。如果格式不正确，生成器会抛出异常。
* **XDimension.Pixels** 控制最小条的宽度。较大的数值可提升低分辨率显示屏上的可读性，较小的数值则可减小图像尺寸。
* **BarCodeImageFormat.Png** 生成无损图像，保留可靠扫描所需的锐利边缘。

运行程序后，会在桌面生成 `GS1MicroPdf417.png`。打开文件可看到密集的黑底白字条形码，编码了 GTIN `12345678901234` 和序列号 `ABC123`。

## 如何使用 GS1 MicroPDF417 生成条形码

如果您对 GS1 格式还不熟悉，以下是基本规则：

| GS1 AI | 含义                     | 示例               |
|--------|--------------------------|--------------------|
| (01)   | Global Trade Item Number | 12345678901234 |
| (21)   | Serial number (optional) | ABC123 |

当您将 AI 与其对应的值拼接时，需要将每个 AI 用括号括起，并紧随其后放置数值。得到的字符串可直接传递给 **barcode generator c#**，无需额外编码。

### 常见陷阱

* **缺少括号** – 生成器会将字符串视为原始数据，且不会执行 GS1 校验。
* **超出长度限制** – MicroPDF417 最多支持 155 个字符。请去除不必要的空白。
* **无效字符** – GTIN 只能使用数字字符；序列号可以包含大写字母和数字。

## 根据数据自定义条形码图像

除了基本的 X‑dimension，Aspose.BarCode 还提供许多视觉调节。以下是根据项目需求可能进行的几项调整。

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

每个设置都是可选的；默认值已经能够生成干净、可扫描的 **barcode image**。仅在确认扫描仪仍能读取代码后，才尝试更改颜色和分辨率。

## 将条形码保存为其他格式

虽然 PNG 是网页和移动端最常用的格式，但您可能需要 JPEG、BMP 或 SVG。`Save` 方法接受任意 `BarCodeImageFormat` 值。

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG 可以减小文件大小，但会产生压缩伪影，可能影响可读性。
* SVG 保持矢量质量，适用于响应式网页设计。

## 验证生成的条形码

快速确认 **create barcode image** 步骤是否成功的方法是使用支持 GS1 MicroPDF417 的移动扫描应用。扫描保存的 PNG，应用应显示：

```
GTIN: 12345678901234
Serial: ABC123
```

如果扫描器报错，请再次检查 AI 格式以及 X‑dimension 的取值。

## 完整示例 – 独立的控制台程序

下面是一个完整的程序，您可以复制、粘贴并直接运行（除 NuGet 安装步骤外无需修改）。

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

运行程序后，控制台会打印完整的文件路径，PNG 文件会出现在桌面。此示例演示了 **how to generate barcode** 数据、定制外观，并在单一完整的工作流中导出 **barcode image from data**。

## 常见问题

| 问题 | 回答 |
|------|------|
| *我可以生成其他 GS1 符号吗？* | 可以。将 `EncodeTypes.MicroPdf417` 替换为 `EncodeTypes.Pdf417`、`EncodeTypes.DataMatrix` 等，并相应地调整数据字符串。 |
| *如果我的数据超出 MicroPDF417 的容量怎么办？* | 切换到常规的 PDF417 符号，它支持更长的负载。 |
| *我需要为 Aspose.BarCode 购买许可证吗？* | 免费评估许可证可用于开发。生产环境请购买许可证以去除评估水印。 |
| *PNG 适合用于标签打印吗？* | 将 `ImageResolution` 提高到 300 dpi 或更高，并考虑保存为 TIFF 以用于工业打印机。 |

## 结论

现在，您已经了解如何使用 **barcode generator c#** 方法在 C# 中 **create barcode image**，为 **create gs1 barcode** 场景格式化数据，并将结果导出为 PNG 或其他图像类型。完整示例展示了从数据准备到视觉自定义的每一步，使您能够在任何 .NET 应用程序中集成条形码创建功能。

接下来，您可以探索相关主题，例如针对二维码的 **barcode image from data**、将多个条形码添加到单个 PDF，或为库存系统实现批量自动生成。尝试不同的 X‑dimension 值和图像格式，以找到适合您特定扫描环境的最佳方案。

祝编码愉快，让您的应用程序开始 **creating barcode images**，在真实环境中可靠运行！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方式。

- [如何在 C# 中使用 Aspose.Barcode 创建条形码图像](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [如何在 C# 中使用 Aspose.BarCode 创建邮政条形码图像](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [如何在 C# 中创建 PDF417 条形码图像 – 完整指南](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}