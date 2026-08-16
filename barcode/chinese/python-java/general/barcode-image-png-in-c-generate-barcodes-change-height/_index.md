---
category: general
date: 2026-08-15
description: 在 C# 中生成 PNG 条形码图像——学习如何生成邮政条形码、创建 Planet 条形码，并使用简易生成器更改条形码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: zh
lastmod: 2026-08-15
og_description: C# 教程中的条形码 PNG 图像展示了如何生成邮政条形码、创建 Planet 条形码以及使用 BarcodeGenerator API
  更改条形码高度。
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: C# 中的条形码 PNG 图像 – 生成和调整条形码
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: 在 C# 中生成条形码 PNG 图像，修改高度
url: /zh/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 中的条形码 PNG 图像 – 生成条形码，修改高度

如果您需要在 C# 中生成 **barcode image PNG**，本指南将带您完整了解整个过程。您将学习如何生成邮政条形码、创建 Planet 条形码，以及在不离开 IDE 的情况下修改条形码高度。

生成可靠的 PNG 条形码是运输标签、库存系统和自动邮件解决方案的常见需求。完成本教程后，您将拥有一个可复用的代码片段，能够为 Planet 和 RM4SCC 两种格式生成高质量的 PNG 文件，并且了解如何调整条形码高度以符合邮政规范。

## 您需要的条件

- .NET 6+ 或 .NET Framework 4.7.2（BarcodeGenerator API 可在任何近期的 .NET 运行时上工作）  
- 对 **Aspose.BarCode for .NET** NuGet 包的引用（或任何提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的兼容库）  
- 对 C# 语法和文件 I/O 的基本了解  

无需额外工具；代码可在 Visual Studio、Rider 或 `dotnet` CLI 中运行。

## Barcode image PNG – 基本生成

第一步是使用默认尺寸创建 **barcode image PNG**。这将建立一个基线文件，您可以在之后进行自定义。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**为什么这样有效：**  
- `EncodeTypes.Planet` 告诉生成器使用 Planet 符号，这在许多邮政服务中是必需的。  
- `XDimension.Pixels` 控制最小条的宽度；4 px 的值在典型标签尺寸下可生成可读的条形码。  
- `Save` 方法将 **barcode image PNG** 文件写入磁盘，保留所有向量信息为光栅像素。

## 更改条形码高度 – 定制视觉重量

邮政指南通常要求特定的条码高度。下面的代码片段演示如何为相同的 Planet 条形码设置自定义的 100 像素高度。

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**为什么要更改高度：**  
更高的条码在低分辨率打印机上可提升扫描可靠性，而更短的条码则节省标签空间。`BarHeight.Pixels` 属性允许您微调此属性而不影响 X 维度。

## 生成邮政条形码 – 创建 RM4SCC 示例

RM4SCC 格式是英国使用的另一种常见邮政条形码。生成步骤与 Planet 示例相同，进一步强化了 **barcode generator c#** 模式。

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## 更改条形码高度 – RM4SCC 变体

与 Planet 条形码一样，您可以调整 RM4SCC 的条码高度。下面的代码将高度设置为 100 px，为相同的数据字符串生成第二个 **barcode image PNG**。

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## 完整、可运行的示例

将所有步骤组合在一起，可得到一个单独的、独立的程序，生成四个 PNG 文件：

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [创建条形码自定义高度 – 一维条形码](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [创建条形码 PNG – DataMatrix 长宽比 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [创建条形码图像 C# – GS1 DataMatrix 示例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}