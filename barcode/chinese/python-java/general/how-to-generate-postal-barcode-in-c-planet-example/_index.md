---
category: general
date: 2026-10-28
description: 使用 Planet 格式在 C# 中生成邮政条形码。此 Planet 条形码示例展示了如何设置条形码宽度以及保存实条和空条。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: zh
lastmod: 2026-10-28
og_description: 使用 C# 生成邮政条码，提供完整的 Planet 条码示例。学习设置条码宽度、生成实心条以及创建空条图像。
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: 使用 C# 生成邮政条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中生成邮政条形码 – 行星示例
url: /zh/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成邮政条码 – Planet 示例

如果您需要在 C# 中生成邮政条码，本指南将带您完成完整的解决方案。您将看到一个实用的 Planet 条码示例，它可以对数字字符串进行编码、设置条码宽度，并保存实心和空心条的图像。

创建邮政条码并不需要复杂的构建流水线。完成本教程后，您可以将条码生成集成到任何 .NET 应用程序中，自定义 X 维度，并选择条码是实心还是空心。

## 前置条件

* 已安装 .NET 6.0 SDK 或更高版本  
* C# 开发环境（Visual Studio、VS Code 或 Rider）  
* **Aspose.BarCode for .NET** NuGet 包（版本 23.10 或更高）  

您可以使用以下命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

下面的代码片段假设您已在文件顶部添加了 `using Aspose.BarCode.Generation;`。

## 使用 Planet 符号生成邮政条码

第一步是创建一个使用 Planet 符号的 `BarcodeGenerator` 实例。Planet 是一种被多个国家邮政服务使用的邮政条码格式。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**为什么这很重要：**  
`EncodeTypes.Planet` 告诉库使用 Planet 条码标准，该标准将数字数据编码为一系列条和空。构造函数接收您想要编码的数据字符串（本例中为 `"123456"`）。

运行程序后会在可执行文件的工作目录中生成两个 PNG 文件：

* **PostalPlanetFilledBars.png** – 条形以实心黑色矩形呈现。  
* **PostalPlanetEmptyBars.png** – 条形以白色矩形加黑色轮廓呈现，适用于在深色背景上打印。

## 设置条码宽度（X 维度），单位为像素

条码的视觉尺寸由 X 维度控制，它定义单根条的宽度。调整该值可确保条码在预期的打印分辨率下能够正确扫描。

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**为什么需要设置它：**  
较大的 X 维度使条码在低分辨率扫描仪上更易扫描，而较小的数值则可在高密度打印时减小整体图像尺寸。默认宽度为 2 像素；4 像素是大多数桌面打印机的常用折中。

您可以尝试不同的数值：

| 像素 | 典型使用场景 |
|------|--------------|
| 2    | 高密度标签 |
| 4    | 标准办公打印 |
| 6‑8  | 大幅标识 |

**提示：** 更改 X 维度后，请始终使用目标扫描仪测试生成的条码。

## Planet 条码示例 – 实心与空心条

Planet 条码可以使用实心（filled）条或轮廓（empty）条进行渲染。`FilledBars` 属性用于切换此行为。

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**为什么可能选择空心条：**  
空心条在深色包装上提升对比度，因为每根条的白色内部在深色背景下更为突出。实心条是默认设置，适用于浅色介质。

**预期输出：**  

*两张图像显示相同的编码数据（`123456`）。* 唯一的视觉差异在于条的样式。以下是您将看到的文字描述：

* **实心条图像：** 白色背景上的实心黑色垂直条。  
* **空心条图像：** 形成相同图案的黑色轮廓，内部为白色。

您可以使用任意图像查看器打开 PNG 文件，以验证图案符合 Planet 规范。

## 自定义其他条码属性（可选）

虽然上述核心步骤已覆盖大多数场景，但您可能希望微调其他设置：

| 属性 | 描述 | 常见取值 |
|------|------|----------|
| `Barcode.Color` | 条的前景颜色 | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | 背景填充颜色 | `System.Drawing.Color.White` |
| `Barcode.CodeText` | 条码下方显示的可读文本 | 与编码数据相同或自定义标签 |
| `Barcode.ImageFormat` | 输出格式（PNG、JPEG、BMP 等） | `BarCodeImageFormat.Png` |

设置自定义前景颜色的示例：

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

这些可选的微调有助于匹配企业品牌或满足特定的打印需求。

## 常见陷阱及避免方法

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 条码无法读取 | X 维度对打印机 DPI 来说太小 | 将 `XDimension.Pixels` 增加到 4 或更高 |
| 图像文件损坏 | 目标文件夹缺少写入权限 | 使用绝对路径或确保目录存在 |
| 使用了错误的符号 | 传入 `EncodeTypes.Code128` 而非 `EncodeTypes.Planet` | 验证 `EncodeTypes` 参数与邮政格式匹配 |

**专业提示：** 在投入生产前，请始终生成测试条码并使用目标硬件进行扫描。

## 完整、可运行的示例

下面是一个独立的控制台应用程序，包含了所有讨论的步骤。将代码复制到新的 .NET 控制台项目中并运行，即可在输出文件夹中看到两个 PNG 文件。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**验证步骤：**  

1. 构建项目（`dotnet build`）。  
2. 运行可执行文件（`dotnet run`）。  
3. 在 `bin/Debug/net6.0` 文件夹中找到 `PostalPlanetFilledBars.png` 和 `PostalPlanetEmptyBars.png`。  
4. 打开每张图像；您应该看到一系列代表数字字符串的垂直条。

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何创建带实心和空心条的 Planet 条码](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [如何在 C# 中设置宽度并生成 Planet 条码](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [在 C# 中创建邮政条码 – 完整生成器示例](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}