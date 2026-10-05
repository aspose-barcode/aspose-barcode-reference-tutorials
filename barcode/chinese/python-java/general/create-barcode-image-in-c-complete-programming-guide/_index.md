---
category: general
date: 2026-08-09
description: 使用本分步指南在 C# 中创建条形码图像。学习如何生成条形码、调整条形码高度像素，并高效地创建多个条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: zh
lastmod: 2026-08-09
og_description: 快速在 C# 中创建条形码图像。请按照本教程学习如何生成条形码、设置条形码高度像素以及生成多个条形码。
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: 在 C# 中创建条形码图像 – 开发者完整指南
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 在 C# 中创建条形码图像——完整编程指南
url: /zh/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建条形码图像 – 完整编程指南

如果您需要在 .NET 应用程序中**创建条形码图像**，本指南将向您展示如何使用 Aspose.BarCode 库**生成条形码**。您将了解如何控制**条形码高度像素**、保存图像以及在不重复代码的情况下**生成多个条形码**。

本教程涵盖了从安装包到自定义尺寸的全部内容，您可以直接复制粘贴一个可直接运行的示例到您的项目中。

## 前提条件

* .NET 6.0 SDK 或更高版本已安装  
* Visual Studio 2022（或任何 C# IDE）  
* NuGet 包 `Aspose.BarCode` – 使用以下方式安装  

```bash
dotnet add package Aspose.BarCode
```

无需其他依赖项。

## 使用 BarcodeGenerator C# 生成条形码图像

用于创建条形码图像的核心类是 `BarcodeGenerator`。它封装了编码类型、数据字符串以及所有渲染参数。

### 步骤 1：定义输出文件夹

选择一个用于存放生成的 PNG 文件的文件夹。使用绝对路径可以避免权限问题。

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **为什么？** 以编程方式创建文件夹可确保即使在全新机器上，后续的 `Save` 调用也能成功。

### 步骤 2：实例化条形码生成器

对于 DataBar Omnidirectional 条形码，传入 `EncodeTypes.DatabarOmniDirectional` 和 GS1‑128 数据字符串。

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **注意：** `BarcodeGenerator` 对象是可复用的；您可以在保存之间更改其参数，以**从相同数据创建多个条形码**。

### 步骤 3：设置通用条形码参数

最常见的视觉调节是 X‑dimension（模块宽度）和条码高度。两者均以像素为单位。

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **为什么要设置 X‑dimension？** 较小的 X‑dimension 能产生更高的分辨率，这在图像需要打印或在高 DPI 屏幕上显示时尤为重要。

### 步骤 4：保存第一张条形码图像

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

文件 `DatabarBarHeight30Pixels.png` 现在包含一个高度为 30 像素的 DataBar Omnidirectional 条形码。

### 步骤 5：调整条形码高度像素

更改高度不需要新的 `BarcodeGenerator` 实例，只需修改参数即可。

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### 步骤 6：保存第二张条形码图像

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

现在您拥有两个 PNG 文件，具有不同的**条形码高度像素**，演示了创建**条形码图像**变体是多么简单。

## 动态设置条形码高度像素

通常您需要一系列高度匹配 UI 元素或打印标签的条形码。下面的辅助方法抽象了高度的更改：

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

现在您可以调用 `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` 在一行代码中**创建高度为 45 像素的条形码图像**。

## 在循环中创建多个条形码

当您拥有一组产品标识符时，`foreach` 循环可以消除重复代码。此示例展示了如何从 GTIN 数组**创建多个条形码**。

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

该循环生成三个 PNG 文件，每个文件都有不同的 **条形码高度像素** 值。由于 `SaveBarcodeWithHeight` 辅助方法封装了高度的更改，主循环保持简洁且专注于数据。

### 预期输出

运行完整示例后，`Barcodes` 文件夹包含：

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

打开任意 PNG 文件，都能看到清晰的 DataBar Omnidirectional 条形码，可被标准移动应用扫描。

## 常见陷阱与专业提示

| 问题 | 为什么会发生 | 如何避免 |
|------|--------------|----------|
| **错误的 EncodeTypes** | 对 DataBar 使用 1D 类型会生成不可读的图像。 | 始终为 GS1‑128 负载选择 `EncodeTypes.DatabarOmniDirectional`（或其他 DataBar 变体）。 |
| **X‑dimension 不足** | 非常低的 X‑dimension 可能导致细条在低分辨率显示器上消失。 | 在屏幕显示时保持 `XDimension.Pixels` ≥ 2；打印时提高到 3‑4。 |
| **文件路径错误** | 相对路径可能解析到意外的目录。 | 使用 `Path.Combine` 和 `Environment.CurrentDirectory` 构建绝对路径。 |
| **覆盖图像** | 在循环中重复使用相同文件名会覆盖之前的结果。 | 在文件名中加入唯一标识符（例如 GTIN 或时间戳）。 |
| **缺少 NuGet 包** | 代码可以编译，但运行时抛出 `FileNotFoundException`。 | 确认已安装 `Aspose.BarCode` 并在项目中引用它。 |

## 完整工作示例

下面是完整的程序，您可以复制到控制台应用程序中。它包括所有步骤、辅助方法和错误处理。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

运行此程序

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [创建条形码自定义高度 – 一维条形码](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [创建条形码图像 C# – GS1 DataMatrix 示例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [创建 DotCode 条形码图像 – 行与列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}