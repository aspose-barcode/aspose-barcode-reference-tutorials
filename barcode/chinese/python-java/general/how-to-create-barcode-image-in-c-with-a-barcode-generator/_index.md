---
category: general
date: 2026-10-02
description: 使用条形码生成器在 C# 中创建条形码图像，控制条形码像素大小并调整条形码高度，以实现自定义条形码尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: zh
lastmod: 2026-10-02
og_description: 使用条码生成器在 C# 中创建条码图像。了解如何设置条码像素大小、调整条码高度以及定义自定义条码尺寸。
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: 在 C# 中创建条形码图像 – 条形码生成器及自定义尺寸指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 如何使用条码生成器在 C# 中创建条码图像
url: /zh/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用条码生成器创建条码图像

如果您需要 **创建条码图像** 文件并以编程方式生成，本指南提供了一个完整、可直接运行的 C# 示例。通过使用条码生成器，您可以控制 **条码像素大小**、**调整条码高度**，并在不离开 IDE 的情况下定义 **自定义条码尺寸**。

您将学习如何生成两个 PNG 文件——一个条码高度为 30 px，另一个为 60 px——同时保持模块宽度不变。此步骤适用于库支持的任何条码类型，您可以将其迁移到 QR 码、Code 128 或其他符号。

## 所需环境

- .NET 6.0 或更高（代码同样可以在 .NET Framework 4.8 下编译）
- 条码库引用（例如 Aspose.BarCode for .NET 或任何兼容的 `BarcodeGenerator` 类）
- 基础的 C# 知识
- 对将保存 PNG 文件的文件夹拥有写入权限

## 第一步：初始化条码生成器以 **创建条码图像**

首先，导入所需的命名空间并实例化 `BarcodeGenerator`。构造函数接受条码类型（`EncodeTypes.DatabarOmniDirectional`）和要编码的数据字符串。

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

创建生成器是任何 **barcode generator c#** 工作流的基础。它会分配内部绘图画布并准备好渲染数据。

## 第二步：定义 **条码像素大小** 和初始条码高度

最终图像的视觉质量取决于两个参数：

| 参数 | 含义 |
|-----------|---------|
| `XDimension.Pixels` | 单个模块（最小的黑/白单元）的宽度。 |
| `BarHeight.Pixels` | 当前图像的条码高度。 |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

在保持 **条码像素大小** 不变的同时更改高度，可让您创建符合品牌指南或扫描要求的 **自定义条码尺寸**。

## 第三步：保存第一张 PNG 文件（30 px 高度）

现在将图像写入磁盘。`Save` 方法接受文件路径和所需的图像格式。

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

生成的文件是一张 **条码图像**，条码高度为 30 px，模块宽度为 2 px，适合紧凑标签。

## 第四步：为更大版本 **调整条码高度**

要生成尺寸不同的第二张图像，只需更改 `BarHeight.Pixels` 属性即可。这演示了在不重新创建生成器的情况下 **adjust barcode height** 的简便性。

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

在保持 **条码像素大小** 的前提下更改高度，可确保条码保持清晰，整体宽高比保持一致。

## 第五步：保存第二张 PNG 文件（60 px 高度）

最后，持久化更大的版本。

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

现在您已经拥有两种 **custom barcode dimensions**，并排保存：

- `DatabarBarHeight30Pixels.png` – 30 px 条码高度
- `DatabarBarHeight60Pixels.png` – 60 px 条码高度

两张图像共享相同的 **barcode pixel size**（2 px），确保不同尺寸之间的视觉一致性。

## 为什么这些设置很重要

- **条码像素大小**（`XDimension`）影响扫描器的可读性。2 px 的宽度是常见默认值，兼顾文件大小和扫描可靠性。
- **条码高度** 决定标签上条码的视觉高度。部分零售扫描器要求最小高度；另一些则允许更高的条码以提升美观。
- 在仅调节 `BarHeight` 的情况下保持生成器实例存活，可减少内存分配并加快批量处理速度。

## 边缘情况与最佳实践提示

| 场景 | 推荐做法 |
|-----------|----------------------|
| **不同图像格式**（JPEG、BMP） | 在 `Save` 调用中更改为 `BarCodeImageFormat.Jpeg` 或 `.Bmp`。JPEG 文件更小，但可能产生压缩伪影。 |
| **高分辨率输出**（例如 300 DPI） | 按比例增加 `XDimension.Pixels`（如 4 px），并相应调整 `BarHeight.Pixels` 以保持相同的实际尺寸。 |
| **动态数据字符串** | 将生成器创建封装在接受数据字符串为参数的方法中，然后复用同一 `barcode` 实例进行多次保存。 |
| **线程安全的批量生成** | 为每个线程实例化单独的 `BarcodeGenerator`，或使用线程本地池以避免竞争条件。 |
| **文件系统权限错误** | 确认 `outputFolder` 已存在且进程拥有写入权限；优雅地捕获 `IOException`。 |

## 完整源码列表

下面是完整的、可直接复制、粘贴并运行的程序。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### 预期输出

运行程序后，`YOUR_DIRECTORY` 文件夹中会出现两张 PNG 文件：

- **DatabarBarHeight30Pixels.png** – 适用于小标签的紧凑条码。
- **DatabarBarHeight60Pixels.png** – 适用于高可视性场景的更大版本。

两文件均可在任意图像查看器中打开、打印或嵌入 PDF。

## 结论

现在您已经掌握了如何在 C# 中使用 **barcode generator c#** **创建条码图像** 文件，控制 **barcode pixel size**、**adjust barcode height**，并生成满足特定扫描或品牌需求的 **custom barcode dimensions**。该示例展示了一个简洁、可重复的模式，能够扩展到批量处理或不同符号类型。

### 接下来可以探索的内容

- 将 `EncodeTypes.DatabarOmniDirectional` 替换为其他类型，如 `EncodeTypes.Code128` 或 `EncodeTypes.QR`。
- 通过 `barcode.Parameters.Barcode.ForeColor` 与 `BackColor` 设置前景/背景颜色。
- 生成 SVG 或 PDF 输出以实现矢量打印。
- 使用 `Graphics` 将多个条码合并为单张图像，以创建复合标签。

欢迎随意实验这些参数，并将此模式集成到您的库存、票务或任何需要程序化条码生成的系统中。祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并探索在项目中的替代实现方式。

- [How to create barcode image in C# with adjustable height](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}