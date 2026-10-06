---
category: general
date: 2026-10-05
description: C# 条形码生成器示例，展示如何生成 Planet 条形码并创建条形码图像。请按照此分步指南操作。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: zh
lastmod: 2026-10-05
og_description: C# 条形码生成器示例一步步教你如何生成 Planet 条形码并创建条形码图像。获取完整、可运行的解决方案。
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: C# 条形码生成示例 – 快速生成 Planet 条码
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Planet 符号库构建条码生成器示例
url: /zh/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 条形码生成示例 – 生成 Planet 条形码并创建条形码图像

如果您需要一个 **barcode generator example**（条形码生成示例）在 C# 中，本指南将准确展示如何仅用几行代码生成 Planet 条形码并创建条形码图像（c#）。您将看到一个完整、可直接运行的解决方案，您可以将其放入任何 .NET 项目中。

Planet 条形码被邮政服务用于编码路由信息。通过本教程，您将了解为何库会自动确定条形码高度、如何控制 X 维度以及如何将结果保存为 PNG 文件。无需外部工具——只需 Aspose.BarCode for .NET 包和 .NET 开发环境。

## 先决条件

* .NET 6.0 SDK 或更高版本已安装  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 包 (`Aspose.BarCode`)  

您可以通过命令行安装该包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：初始化用于 Planet 编码的条形码生成器

在任何 **barcode generator example** 中的第一步是创建一个 `BarcodeGenerator` 实例并指定编码类型。对于 Planet 条形码，您使用 `EncodeTypes.Planet` 并传入要编码的数据字符串。

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**为什么重要：** `EncodeTypes.Planet` 枚举告诉库使用 Planet 符号系统，该系统具有邮政标准要求的固定模块模式。提供数据（本例中的 `"123456"`）可确保条形码包含正确的数字路由代码。

## 步骤 2：配置 X 维度（模块宽度），单位为像素

X 维度控制每个独立模块（最小条）的宽度。调整它会改变条形码的整体尺寸，而不会影响可读性。

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**为什么重要：** 更大的 X 维度会生成更大的条形码，这在打印大信封时很有用。库会自动缩放高度，以保持 Planet 条形码的正确宽高比。

## 步骤 3：将条形码图像保存到磁盘

最后，您保存生成的图像。库会确定最佳高度，因此您只需指定输出路径和格式。

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**为什么重要：** 保存为 PNG 可保留条形码的清晰边缘，这对可靠扫描至关重要。如果需要其他输出格式，`Save` 方法还支持 JPEG、BMP、TIFF 等。

### 预期输出

运行代码后，您将在 `C:\Barcodes` 中找到名为 **PlanetAutoHeight.png** 的文件。该图像将类似于下方示例（alt 文本：*barcode generator example showing a Planet barcode*）。

![C# 示例生成的 Planet 条形码](/images/planet-barcode-example.png){alt="barcode generator example showing a Planet barcode"}

## 步骤 4：可选 – 自定义前景色和背景色

如果您的应用程序需要不同的视觉样式，您可以在保存之前更改条形码的颜色。

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**提示：** 始终使用真实扫描仪测试自定义条形码，以确认颜色更改不会影响可读性。

## 步骤 5：错误处理与验证

如果数据不符合 Planet 符号系统要求（例如，包含非数字字符），Aspose.BarCode 库会抛出 `ArgumentException`。请将生成代码包装在 try‑catch 块中，以提供明确的反馈。

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**为什么重要：** Planet 条形码仅接受特定长度的数字数据。适当的验证可防止运行时错误，并在集成测试期间节省时间。

## 完整、可运行的示例

将所有步骤组合在一起，可得到一个可自行复制、粘贴并运行的独立程序。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

编译并运行程序：

```bash
dotnet run
```

您应该会在控制台看到确认文件位置的消息，PNG 文件将包含生成的 Planet 条形码。

## 常见变体和边缘情况

| 变体 | 实现方法 | 使用场景 |
|-----------|------------------|------------|
| **不同的数据长度** | 将 `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` 中的第二个参数更改为所需值 | 需要更长路由号码的邮政服务 |
| **更高分辨率** | 在 `Save` 之前设置 `generator.Parameters.ImageResolution = 300;` | 在高 DPI 打印机上打印 |
| **不同的图像格式** | 使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Tiff` | 当 PNG 不适合您的工作流时 |
| **动态文件名** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | 批量处理多个条形码 |

## 强化技巧：构建稳健的条形码生成示例

* **重用生成器实例** 在使用相同设置创建大量条形码时；只需更改 `EncodeTypes` 或数据字符串即可提升性能。  
* **验证输入** 在传递给 `BarcodeGenerator` 之前。使用类似 `^\d{6,9}$` 的简单正则表达式可确保数据符合 Planet 要求。  
* **释放资源** 如果在长期运行的服务中生成成千上万的图像。`BarcodeGenerator` 实现了 `IDisposable`，因此在适当情况下请使用 `using` 块进行包装。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## 结论

本 **barcode generator example** 演示了如何使用 Aspose.BarCode for .NET **生成 Planet 条形码** 并 **创建条形码图像（c#）**。您学习了如何初始化生成器、设置 X 维度、可选地自定义颜色、处理验证错误以及将结果保存为 PNG 文件。提供的完整源代码使您能够立即将 Planet 条形码生成集成到任何 C# 应用程序中。

接下来，您可以探索其他符号系统，如 QR、Code128 或 DataMatrix——它们都遵循相同的模式：创建 `BarcodeGenerator`、配置参数并调用 `Save`。相同的原理适用于所有情况，使您能够轻松在各种业务场景中扩展条形码生成能力。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [创建 Planet 条形码图像 – 步骤指南](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [条形码生成器 C# – 创建 Planet 条形码和 RM4SCC 示例](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [使用条形码生成器示例创建 C# 条形码图像](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}