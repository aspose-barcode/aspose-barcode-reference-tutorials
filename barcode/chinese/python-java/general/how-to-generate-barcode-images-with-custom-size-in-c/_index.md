---
category: general
date: 2026-08-22
description: 如何使用 Aspose.BarCode 快速生成条形码，并了解在导出为 PNG 格式的条形码图像时如何更改条形码尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: zh
lastmod: 2026-08-22
og_description: 如何在 C# 中生成条形码，并在导出为 PNG 图像之前轻松更改条形码尺寸。请阅读完整指南。
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: 如何在 C# 中生成自定义尺寸的条形码图像
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中生成自定义尺寸的条形码图像
url: /zh/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成自定义尺寸的条形码图片

如果您需要 **生成条形码** 用于邮政自动化、库存跟踪或活动票务，本指南将为您展示一个完整、可直接运行的 C# 解决方案。您还将学习 **如何更改条形码尺寸** 并 **导出 PNG 格式的条形码图片**，无需离开 IDE。

我们将使用 Aspose.BarCode 库，因为它支持 OneCode 符号、可以像素级别控制尺寸，并且只需一次方法调用即可完成图像导出。教程结束时，您将拥有四个 PNG 文件——每个文件对应一个不同位数的 OneCode 条形码。

## 前置条件

- .NET 6.0 或更高（代码同样适用于 .NET Framework 4.6+）
- Visual Studio 2022（或您喜欢的任何 C# 编辑器）
- 对 **Aspose.BarCode** 的 NuGet 引用（`Install-Package Aspose.BarCode`）
- 基本的 C# 语法了解

> **专业提示：** 如果您在评估该库，Aspose 提供包含全部条形码功能的免费 30 天试用。

## 第一步：创建最小化的控制台项目

创建一个新的控制台应用并添加 Aspose.BarCode 包：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

生成的 `Program.cs` 将包含完整的条形码生成逻辑。

## 第二步：生成条形码 – 创建可复用方法

下面是一个自包含的方法，接收数据字符串、目标文件名以及可选的尺寸参数。该方法演示了 **生成条形码** 的核心模式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### 为什么这个方法很重要

- **封装性：** 所有与尺寸相关的设置集中在一个位置，调用时只需传入不同的尺寸即可。
- **可复用性：** 同一方法可用于任意 OneCode 字符串长度，这一点很关键，因为 OneCode 只接受 20‑31 位数字。
- **清晰度：** 带有表情符号的注释引导读者了解三个逻辑阶段——初始化、尺寸更改和导出。

## 第三步：根据不同需求更改条形码尺寸

有时扫描仪需要更高的条形码，或打印布局要求更窄的模块。`XDimension.Pixels` 属性控制单个条形码模块的宽度，而 `BarHeight.Pixels` 设置整体高度。

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**更改尺寸时的关键要点：**

- **最小 X 维度：** 技术上允许 1 像素，但大多数扫描仪至少需要 2 像素才能可靠读取。
- **最大高度：** 没有硬性上限，但过高的条形码可能超出标准标签的可打印区域。
- **宽高比：** 保持高度与模块宽度的比例平衡（≈12‑15 × 模块宽度），以避免失真。

## 第四步：以其他格式导出条形码图像（可选）

`Save` 方法接受多种 `BarCodeImageFormat` 值：`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`。如果需要无损矢量格式，也可以导出为 `Svg`。

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

导出为 PNG 是最常见的选择，因为它能保持清晰的边缘，并被网页浏览器和打印流水线广泛支持。

## 预期输出

运行程序后，项目文件夹中会生成四个 PNG 文件：

- `PostalOneCodeBarcode20Digits.png` – 20 位 OneCode 条形码
- `PostalOneCodeBarcode25Digits.png` – 25 位 OneCode 条形码
- `PostalOneCodeBarcode29Digits.png` – 29 位 OneCode 条形码
- `PostalOneCodeBarcode31Digits.png` – 31 位 OneCode 条形码

每张图片的效果类似下方占位图（实际图形取决于您提供的数字数据）。

![如何生成条形码示例](https://example.com/placeholder.png "如何生成条形码示例")

*图片的 alt 文本包含主要关键词，以提升可访问性和 SEO 效果。*

## 常见问题与边缘情况

| 问题 | 答案 |
|----------|--------|
| **如果数据字符串少于 20 位怎么办？** | OneCode 最少需要 20 位。请在前面补零，或使用其他符号（例如 Code128）。 |
| **可以在多线程环境中生成条形码吗？** | 可以。`BarcodeGenerator` 不是线程安全的，请为每个线程实例化独立的生成器。 |
| **如何设置背景颜色？** | 在调用 `Save` 之前使用 `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;`。 |
| **有没有办法直接将图像嵌入 HTML 页面？** | 将图像保存到 `MemoryStream`，转换为 Base64，然后使用 `<img src="data:image/png;base64,..." />` 嵌入。 |

## 结论

现在您已经掌握了使用 Aspose.BarCode 在 C# 中 **生成条形码** 图片的技巧，了解了通过调整 X 维度和条码高度 **更改条形码尺寸** 的方法，并会使用 **导出条形码图像** 为 PNG（或其他）格式。可复用的 `GenerateOneCode` 方法让您只需一行代码即可生成任意 20‑31 位的 OneCode 条形码。

接下来您可以：

- 尝试其他符号（`EncodeTypes.Code128`、`EncodeTypes.QR`）。
- 将生成器集成到返回条形码图像的 Web API 中。
- 将 PNG 输出与 PDF 库结合，在运单上嵌入条形码。

祝编码愉快，欢迎在评论区分享您的实现方式！

## 接下来您可以学习什么？

以下教程涵盖与本指南技术紧密相关的主题，提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并探索项目中的替代实现方案。

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码 – 步骤指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成自定义宽高比的 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何为一维 Databar 条形码生成并调整高度 – Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}