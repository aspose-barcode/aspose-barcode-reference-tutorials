---
category: general
date: 2026-10-05
description: 在 C# 中创建条形码 PNG，并学习如何为堆叠式 DataBar 全向条码设置宽高比为 15。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: zh
lastmod: 2026-10-05
og_description: 在 C# 中创建条形码 PNG，并在几步内了解如何为堆叠式 DataBar 全向条码设置宽高比 15。
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: 在 C# 中创建条形码 PNG – 设置宽高比为 15 的教程
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中创建具有自定义宽高比的条形码 PNG
url: /zh/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建具有自定义宽高比的条形码 PNG

如果您需要在 C# 中 **创建条形码 PNG**，本指南将向您展示如何为堆叠式 DataBar 全向条码设置 **宽高比** 15。我们将逐步演示每个 API 调用，解释宽高比为何重要，并提供一个完整、可运行的示例，您可以直接放入任何 .NET 项目中。

生成条形码图像是库存系统、运输标签和零售 POS（销售点）应用的常见需求。完成本教程后，您将拥有符合业务合作伙伴精确视觉规格的 PNG 文件。无需外部工具，无需手动图像编辑——只需代码。

## 前提条件

在开始之前，请确保您具备：

* .NET 6.0 或更高版本（示例使用 .NET 6，但在 .NET 5+ 上同样适用）
* Visual Studio 2022（或任何支持 .NET 的 IDE）
* **Aspose.BarCode for .NET** NuGet 包  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 对要保存 PNG 文件的文件夹拥有写入权限

这些要求非常低；相同代码可在 .NET Core、.NET Framework 或控制台应用中运行。

## 使用 Aspose.BarCode 创建条形码 PNG

第一步是使用正确的条码类型实例化 `BarcodeGenerator` 类。本例使用 `EncodeTypes.DatabarStackedOmniDirectional`，它会生成可从任意方向读取的堆叠式 DataBar。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*为什么重要：* 构造函数接受两个参数——**条码符号系统**和**数据字符串**。DataBar 格式要求使用 GS1 应用标识符，这也是示例数据以 `(01)` 开头的原因。

## 如何为堆叠式 DataBar 设置宽高比

DataBar 的视觉宽度由 **宽高比** 属性控制。更高的比例会使条形更宽，从而提升低分辨率打印机上的扫描可靠性。

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` 定义单个模块（最小条或空格）的大小。将其保持在 2 px 可得到清晰、高密度的图像，适用于大多数标签打印机。

## 设置宽高比 15 – 代码演练

现在我们应用 **设置宽高比 15** 的需求。这是本教程的核心，展示了您需要的确切 API 调用。

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*为什么是 15？* 堆叠式 DataBar 的默认宽高比为 12。将其提升至 15 会使每条条形的宽度增加约 25 %，这通常符合物流供应商要求更宽条码以加快扫描的规格。

## 将条形码保存为 PNG

在配置好生成器后，最后一步是将图像写入磁盘。`Save` 方法接受文件路径和图像格式枚举。

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG 格式保持无损质量，确保条码在任何显示器或打印机上都能如设计般准确呈现。

## 完整示例及预期输出

下面是可以直接复制到控制台应用 `Main` 方法中的完整程序。它包含了上述所有步骤，并附带一条简短的验证信息。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**预期输出**

运行程序后会生成名为 `DatabarAspectRatio15.png` 的文件，里面包含清晰、宽度加大的堆叠式 DataBar 条码。打开 PNG 时，您应看到水平拉伸的条码，但仍符合 GS1 DataBar 规范。

![宽高比为 15 的条形码 PNG](barcode-aspect15.png)

*图片替代文字：* **创建显示宽高比为 15 的堆叠式 DataBar 条码的 PNG**

### 提示与常见陷阱

| 情况 | 建议 |
|-----------|----------------|
| **图像模糊** | 将 `XDimension.Pixels` 提升至 3 px 或更高，但保持整体图像尺寸低于 500 px，以免文件过大。 |
| **扫描仪无法读取代码** | 确认数据字符串遵循 GS1 格式（以 `(01)` 为前缀）。同时确保打印机分辨率至少为 300 dpi。 |
| **需要其他文件格式** | 将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Gif`——API 支持所有主流栅格格式。 |
| **在 Web 应用中运行** | 使用 `generator.Save(Stream, BarCodeImageFormat.Png)` 直接写入 HTTP 响应，无需触及文件系统。 |

### 扩展示例

* **在同一图像中生成多个条码：** 创建额外的 `BarcodeGenerator` 实例，并使用 `Graphics` 将它们绘制到同一 `Bitmap` 上。  
* **添加可读文本：** 设置 `generator.Parameters.Caption.Visible = true` 并通过 `generator.Parameters.Caption.Font` 自定义字体。  
* **动态宽高比：** 从配置文件或数据库读取比例值，以在运行时生成不同宽度的条码。

## 结论

在本教程中，您学习了如何在 C# 中 **创建条形码 PNG**，并为堆叠式 DataBar 全向条码精确 **设置宽高比** 15。完整、可运行的代码演示了所有必需的 API 调用，解释了每个设置的意义，并提供了实际部署的实用技巧。

接下来，您可以探索 **如何为其他条码类型（如 QR Code 或 Code 128）设置宽高比**，或将生成器集成到 ASP .NET Core 服务中，以按需返回条码图像。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您进一步掌握 API 功能并在项目中尝试不同实现方式。每篇资源都提供完整的可运行代码示例和逐步解释。

- [如何使用 C# 和 Aspose.Barcode 创建 databar PNG 图像](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [如何在 C# 中使用 Aspose.Barcode 创建堆叠式 databar 条码](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [在 .NET 中自定义堆叠式全向 DataBar 的宽高比](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}