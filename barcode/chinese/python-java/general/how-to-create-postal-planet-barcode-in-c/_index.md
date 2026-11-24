---
category: general
date: 2026-11-23
description: 使用 Aspose.BarCode 在 C# 中创建邮政 Planet 条码。了解如何生成 Planet 条码、设置 X 维度以及保存实心或空白条。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: zh
lastmod: 2026-11-23
og_description: 在 C# 中创建邮政 Planet 条码，并学习如何使用 Aspose.BarCode 生成 Planet 条码。请参考完整示例，以生成实心和空心条。
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: 如何在 C# 中创建邮政星球条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中创建邮政星球条码
url: /zh/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建邮政 Planet 条形码

如果您需要在 .NET 应用程序中 **创建邮政 Planet 条形码**，本指南将向您展示如何使用 Aspose.BarCode 库 **生成 Planet 条形码**。您将看到如何配置 X 维度、在实心条和空心条之间切换，以及将图像保存为 PNG 格式。

生成 Planet 条形码是邮政服务常见的需求，因为它们需要高密度、机器可读的符号。完成本教程后，您将拥有两个 PNG 文件——一个实心条版本，一个空心条版本——可直接集成到任何邮件工作流中。

## 前置条件

在开始之前，请确保您已经：

* 安装了 .NET 6.0 SDK 或更高版本。
* 配置好用于 .NET 开发的 Visual Studio 2022（或任意 C# 编辑器）。
* 拥有 **Aspose.BarCode for .NET** 的有效 NuGet 许可证。使用以下命令安装包：

```bash
dotnet add package Aspose.BarCode
```

无需额外的外部服务；该库在本地完成所有编码工作。

## 第一步 – 创建邮政 Planet 条形码

首先实例化一个用于 **Planet** 符号的 `BarcodeGenerator`，并提供要编码的数据。根据邮政规范，数据字符串必须是数字且最长 12 位。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

创建生成器会分配渲染所需的所有内部结构。`EncodeTypes.Planet` 枚举值选择了邮政格式的正确编码算法。

## 第二步 – 设置 X 维度以获得更佳可视性

X 维度定义了单个模块（最小条形单元）的宽度。4 像素的值能够在不放大整体图像的前提下提供清晰的视觉表现。

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

在低分辨率介质上打印条形码时，调整 X 维度尤为重要。同一设置将在空心条版本中复用，以保持两张图像的一致性。

## 第三步 – 保存实心条条形码

默认情况下，生成器渲染 **实心条**（黑色实心模块）。保存图像只需一次方法调用，即可将 PNG 文件写入磁盘。

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

将 `YOUR_DIRECTORY` 替换为您希望输出文件的实际路径。`BarCodeImageFormat.Png` 枚举保证了无损压缩，适合后续处理。

## 第四步 – 为空心条创建另一个 Planet 条形码生成器

要生成使用 **空心条**（黑色背景上的白色模块）的版本，需要第二个 `BarcodeGenerator` 实例。复用相同的数据字符串可确保两张图像对应相同的邮政编码。

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

单独的生成器可以隔离 `FilledBars` 属性，使您能够在不影响第一张图像的情况下切换视觉样式。

## 第五步 – 配置生成器以渲染空心条

`FilledBars` 标志用于切换渲染模式。将其设为 `false` 表示库在绘制条形时使用空心（透明）条，而保持背景为实心。

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

保持与实心版本相同的 X 维度可确保两张 PNG 文件尺寸一致，简化打印模板中的布局计算。

## 第六步 – 保存渲染空心条的条形码

最后，将空心条图像写入磁盘。仍使用 PNG 格式，但您可以通过更改 `BarCodeImageFormat` 的值切换为 JPEG 或 BMP。

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

此时您将拥有两个文件：

* `PostalPlanetFilledBars.png` – 实心黑色条。
* `PostalPlanetEmptyBars.png` – 黑色背景上的空心条。

两者均符合 Planet 符号的邮政规范。

## 完整源代码

将所有步骤组合在一起即可得到一个紧凑的控制台应用程序，直接运行即可。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

编译并运行程序：

```bash
dotnet run
```

控制台会打印 *Barcodes generated successfully.*，并在项目文件夹中生成两张 PNG 文件。

## 预期输出

下面是实心条图像的可视化示例。空心条对应图像在外观上相同，只是条形为透明。

![已创建的邮政 Planet 条形码（实心条）示例](postal-planet-filled.png)

*图片替代文字:* **已创建的邮政 Planet 条形码（实心条）示例**（包含主要关键词）。

默认情况下，两张图像的尺寸为 150 × 150 像素，但您可以通过 `ImageWidth` 和 `ImageHeight` 参数控制整体大小，以满足不同分辨率的需求。

## 可选变体

### 更改图像格式

如果下游系统更倾向于 JPEG，可将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`。JPEG 会引入压缩伪影，仅在文件大小是关键约束时使用。

### 缩放条形码

通过调整 `Resolution` 属性，可在保持模块宽度不变的前提下放大条形码：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

更高的 DPI 值可提升激光打印机的打印质量。

### 使用自定义背景颜色

可以使用以下代码设置背景颜色：

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

此功能适用于视觉测试，但在生产邮政标签中应避免使用非白色背景。

## 常见问题

**这能在 .NET Core 上运行吗？**  
可以。Aspose.BarCode 库面向 .NET Standard 2.0，兼容 .NET 5、.NET 6 和 .NET Core 3.1。

**如果数据字符串包含非数字字符会怎样？**  
Planet 条形码仅接受数字输入。提供字母或符号会触发 `BarcodeException`。请在创建生成器前对输入进行验证。

**我能在内存中生成条形码而不写入磁盘吗？**  
可以使用 `GenerateBarCodeImage` 方法获取 `System.Drawing.Image` 对象，然后直接将其流式传输到响应或数据库中。

## 结论

现在您已经掌握了如何在 C# 中 **创建邮政 Planet 条形码**，并了解了如何使用实心条和空心条两种样式 **生成 Planet 条形码**。本教程覆盖了完整工作流——从初始化生成器、配置 X 维度、切换 `FilledBars` 标志，到保存 PNG 文件。您可以尝试不同的图像格式、DPI 设置和背景颜色，以适配特定的邮件系统。

下一步，您可以使用相同的 Aspose.BarCode API 探索其他邮政符号，如 **POSTNET** 或 **Intelligent Mail**。将 `EncodeTypes.Postnet` 等参数按本示例方式调整，即可在同一代码库中构建完整的条形码生成套件。

## 接下来您可以学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}