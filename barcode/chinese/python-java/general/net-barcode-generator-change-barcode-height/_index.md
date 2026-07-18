---
category: general
date: 2026-07-18
description: 了解如何使用 .net 条码生成器生成条码图像，并轻松更改 GS1‑Databar 全向符号的条码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: zh
lastmod: 2026-07-18
og_description: .NET 条形码生成器让您快速创建条形码图像。本指南展示如何生成条形码、调整条码高度以及保存 PNG 文件。
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: 使用 .net 条码生成器更改条码高度
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET 条形码生成器 – 更改条形码高度
url: /zh/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – 更改条码高度

是否曾想过 **如何生成条码** 图像而不需要使用大量第三方工具？在 .NET 世界中，有一种出乎意料的简洁方式来实现，而关键就在于 **.net barcode generator**。只需几行 C# 代码，就能生成 GS1‑Databar Omni‑Directional 符号，调整条码高度，并将结果保存为 PNG 文件。

如果你正在构建库存系统、运单标签打印机，或任何需要可扫描代码的应用，本教程将在几分钟内帮助你从零实现可用的条码。我们将逐步讲解完整代码，说明每个设置为何重要，并展示如何 **更改条码高度** 而不破坏规范。

## 所需条件

- .NET 6.0 或更高版本（API 在 .NET Framework 4.7+ 上表现相同）
- 条码库的引用（例如 Aspose.BarCode for .NET —— 许多商业套件使用相同的类）
- 开发环境（Visual Studio、Rider，或带有 C# 扩展的 VS Code）
- 一个拥有写入权限的文件夹 —— 本教程会将 PNG 文件保存到该文件夹

仅此而已。除条码库本身外，无需额外的 NuGet 包。

## 使用 .net barcode generator 更改条码高度

下面是一个 **完整、可运行的控制台程序**。将其粘贴到新的 C# 项目中，调整输出文件夹路径，然后按 F5 运行。

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### 为什么每行代码都很重要

| 行 | 原因 |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | 实例化 **.net barcode generator**，并指定所需的符号类型和数据负载。`EncodeTypes.DatabarOmniDirectional` 枚举告诉库使用 GS1‑Databar Omni‑Directional 格式。 |
| `XDimension.Pixels = 2;` | X‑dimension 是最细条的宽度。设置为 *2 像素* 可在大多数显示器上生成清晰图像，同时保持文件体积小。 |
| `BarHeight.Pixels = 30;` | 这一步 **更改条码高度**，决定每根条的高度。30 像素的高度是小标签的良好默认值。 |
| `generator.Save(...);` | 将条码持久化为 PNG 文件。PNG 为无损格式，意味着扫描器看到的正是你生成的精确图案。 |
| `BarHeight.Pixels = 60;` | 此处再次 **更改条码高度**——这次设为 60 像素。调用第二次 `Save` 时，库会自动使用新尺寸重新渲染符号。 |
| `Console.WriteLine(...);` | 快速反馈，表明过程已完成且未抛出异常。 |

> **小技巧：** 如果需要更高分辨率的打印输出，可将 `BarCodeImageFormat.Png` 换成 `BarCodeImageFormat.Tiff` 并提升 `Resolution` 属性（例如 `generator.Parameters.ImageResolution = 300;`）。条码高度仍会被遵循，只是以更细的 DPI 渲染。

## 使用不同设置生成条码图像

上面的代码片段涵盖了基础，但实际场景常常需要额外的微调：

### 为大幅面打印调整 X‑dimension
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
增加 X‑dimension 会在不改变编码数据的前提下放大整个条码。打印大标签时非常实用。

### 切换输出格式
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG 可无限缩放，适合需要清晰矢量图的网页扫描器。

### 添加可读文本
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
启用 `CodeTextVisible` 会在条码下方附加原始数据，便于测试时进行人工核对。

## 常见陷阱——在 **更改条码高度** 时

1. **高度过小** —— 某些扫描器要求最小条码高度（通常为 10 mm 实际尺寸）。如果 `BarHeight.Pixels` 设置得太低，生成的图像在真实扫描器上可能无法读取。务必使用目标硬件进行测试。  
2. **X‑dimension 与高度不匹配** —— 极高的条码高度配合极小的 X‑dimension 会显得拉伸，可能导致解码错误。除非规范另有说明，否则建议保持大致 3:1 到 5:1 的比例。  
3. **忘记重置参数** —— 生成器在多次保存之间会保留状态。如果为一张图像更改了 `BarHeight`，随后在同一实例上生成另一张条码，之前的高度会被保留。要么重置属性，要么为每个不同的条码实例化新的 `BarcodeGenerator`。

## 完整端到端示例（含 NuGet 安装）

如果从零开始，请按以下步骤搭建项目：

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

将自动生成的 `Program.cs` 替换为前面展示的代码块，**记得将 `YOUR_DIRECTORY` 替换为类似 `Path.Combine(Environment.CurrentDirectory, "output")` 的路径**。然后：

```bash
dotnet run
```

你应该会在 `output` 文件夹中看到两个 PNG 文件：

- `DatabarBarHeight30Pixels.png` —— 紧凑的 30 像素高条码。  
- `DatabarBarHeight60Pixels.png` —— 更高的 60 像素版本。

两张图像看起来相似，但第二张的条更长，低分辨率扫描器更容易读取。

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator 输出显示不同的条码高度"}

## 小结与后续

我们已经介绍了如何使用 **.net barcode generator** **生成条码** 图像，微调 **更改条码高度** 属性，并以 PNG 格式保存结果。关键要点如下：

- 使用正确的 `EncodeTypes` 实例化生成器。  
- 通过 `XDimension` 与 `BarHeight` 控制视觉尺寸。  
- 每次更改后调用 `Save` 以生成新图像。  
- 如有需要，可调整分辨率、格式等。

## 接下来该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助你进一步掌握 API 功能并在项目中探索替代实现方式。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}