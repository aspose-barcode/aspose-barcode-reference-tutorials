---
category: general
date: 2026-10-21
description: 学习如何在 C# 中生成条形码图像，以及如何使用 Aspose.BarCode 将条形码文件导出为 PNG，以实现快速、可靠的结果。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: zh
lastmod: 2026-10-21
og_description: 如何在 C# 中生成条形码图像以及如何将条形码文件导出为 PNG。请按照本完整教程使用 Aspose.BarCode 创建 Planet
  和 RM4SCC 条形码。
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: 如何在 C# 中生成条形码图像并导出——一步步指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中生成条形码图像并导出
url: /zh/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成条形码图像并导出它们

如果您需要在 .NET 应用程序中 **生成条形码** 图像，本指南将向您展示创建 Planet 和 RM4SCC 条形码以及随后 **导出条形码** 为 PNG 文件的完整步骤。您将获得可直接运行的代码示例、每个设置的说明以及常见陷阱的提示。

本教程涵盖：

* 添加 Aspose.BarCode NuGet 包
* 配置模块宽度和可选的条码高度
* 将生成的条码保存到磁盘
* 验证输出文件

> **先决条件** – .NET 6+ SDK、Visual Studio 2022（或任意 IDE），以及用于下载 Aspose.BarCode 包的网络连接。

## 您将完成的内容

阅读完本文后，您将能够：

* 生成带自动条码高度的 **Planet** 条码。
* 生成带自动条码高度的 **RM4SCC** 条码。
* 覆盖默认高度，生成 100 像素高的条码。
* 将每个条码导出为 PNG 文件并保存到您指定的文件夹。

## 第 1 步：安装 Aspose.BarCode

在项目文件夹中打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该包提供 `BarcodeGenerator` 类和在后续代码中使用的 `EncodeTypes` 枚举。

## 第 2 步：设置输出文件夹

创建一个用于存放 PNG 文件的文件夹。该文件夹可以是绝对路径，也可以是相对于项目根目录的相对路径。

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **提示：** 使用 `Path.Combine` 可以避免硬编码路径分隔符，并在 Windows、macOS 和 Linux 上均能正常工作。

## 第 3 步：生成带自动条码高度的条码

当您未指定条码高度时，Aspose.BarCode 会自动选择适合编码数据的尺寸。以下代码使用 4 像素的模块宽度创建两个条码——Planet 和 RM4SCC。

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**为什么这样有效：**  
* `EncodeTypes.Planet` 和 `EncodeTypes.RM4SCC` 告诉生成器使用哪种符号集。  
* `XDimension.Pixels` 定义单个条码模块的宽度；4 px 的数值可产生清晰、可扫描的图像。  
* 由于未设置 `BarHeight`，库会自动计算最佳高度。

## 第 4 步：生成固定 100 像素条码高度的条码

如果您的设计需要特定的条码高度，可以覆盖自动计算：

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**为什么可能需要固定高度：**  
运输标签的设计规范通常要求精确的条码尺寸，以确保与条码扫描仪的兼容性。设置 `BarHeight.Pixels` 可保证所有生成图像的统一性。

## 第 5 步：验证导出的文件

程序运行后，`Barcodes` 文件夹中将包含四个 PNG 文件：

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

使用图像查看器打开任意文件，或将其嵌入 PDF 中以确认渲染正确。如果扫描仪无法读取条码，请增大 `XDimension.Pixels` 的数值或再次检查输入字符串的长度。

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

您应该会看到类似以下的输出：

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## 常见问题与边缘情况

| 问题 | 答案 |
|----------|--------|
| **我可以导出除 PNG 之外的其他格式吗？** | 可以。将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp`、`Gif` 或 `Tiff`。 |
| **如果我的数据包含符号集不支持的字符怎么办？** | 生成器会抛出 `ArgumentException`。请先验证输入，或切换到支持该字符集的符号集。 |
| **如何更改前景色/背景色？** | 在调用 `Save` 之前设置 `Parameters.Barcode.ForeColor` 和 `Parameters.Barcode.BackColor`。 |
| **有没有办法在内存中生成条码而不是保存到磁盘？** | 调用 `GenerateBarCodeImage()` 可获得 `System.Drawing.Image` 对象，然后可以自行处理或流式传输。 |

## 专业技巧：批量处理

当需要创建大量条码（例如用于邮件列表）时，可将生成逻辑包装在 `foreach` 循环中：

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

该模式可扩展至数千个条码，同时保持代码简洁。

## 结论

现在您已经掌握了使用 Aspose.BarCode 在 C# 中 **生成条形码** 图像以及 **导出条形码** 为 PNG 的方法。完整示例展示了 Planet 和 RM4SCC 符号集的自动高度和固定高度两种生成方式，为任何条码相关项目奠定了坚实基础。

**后续步骤**

* 探索其他符号集，如 Code128、QR 或 DataMatrix。  
* 试验颜色自定义（`ForeColor`、`BackColor`）。  
* 使用 PDF 库将生成的 PNG 集成到发票或运输标签的 PDF 中。  

祝编码愉快，让您的条码顺畅扫描！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在自己的项目中进一步掌握 API 功能并探索替代实现方案。每篇资源都提供完整的可运行代码示例和逐步说明。

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [在 C# 中创建 GS1 条码图像 – 快速生成条码的指南](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [在 C# 中使用 Aspose.BarCode 生成条码图像](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}