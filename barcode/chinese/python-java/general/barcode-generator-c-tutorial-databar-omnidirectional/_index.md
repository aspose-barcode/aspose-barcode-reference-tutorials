---
category: general
date: 2026-11-14
description: 条形码生成器 C# 教程，展示如何创建 DataBar 全向条码，设置 X 维度，并以像素为单位调整条码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: zh
lastmod: 2026-11-14
og_description: 条形码生成器 C# 教程逐步解释如何生成 DataBar 全向条码、以像素定义 XDimension，并更改 PNG 输出的条码高度。
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 条形码生成器 C# 教程 – 创建 DataBar 条码
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 条形码生成器 C# 教程：DataBar 全向
url: /zh/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

如果您在寻找 **barcode generator C# tutorial**，恭喜您来对地方了。本指南将手把手教您创建 DataBar Omnidirectional 条码、以像素设置 XDimension，并调整条码高度以生成 PNG 图像。

您将看到一个完整、可运行的示例，涵盖从初始化生成器到使用不同条码高度保存多个图像的全部过程。无需查阅外部文档——只需复制代码、运行，即可得到两个可直接使用的条码文件。

## Prerequisites

在开始之前，请确保您已经：

* 安装了 .NET 6.0 或更高版本  
* 引用了提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的条码库（例如 Aspose.BarCode for .NET）  
* 对 C# 语法以及 Visual Studio 或您喜欢的 IDE 有基本了解  

> **Pro tip:** 如果您使用 Aspose.BarCode，请在项目中添加 NuGet 包 `Aspose.BarCode`。

## Barcode generator C# tutorial – step 1: create the generator

第一步是实例化一个 `BarcodeGenerator`，使用 `DatabarOmniDirectional` 编码类型并传入要编码的数据。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` 告诉库生成一种可以从任意方向读取的条码，这在零售包装和物流场景中非常理想。

## Set XDimension pixels for the barcode

X‑dimension 定义了条码中最小模块（即“像素”）的宽度。以像素为单位设置可以让您精确控制条码的视觉密度。

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* 将值设为 `2` 像素可产生足够清晰的条码，适用于大多数扫描仪，同时保持图像文件体积适中。

## Adjust bar height and save images

条码高度决定条纹的垂直长度。通过修改 `BarHeight.Pixels` 属性并再次调用 `Save`，您可以生成不同高度的多张图像。

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` 枚举值确保输出为无损 PNG 文件，这是条码图形的推荐格式，因为它能够保留精确的尺寸信息。

## Change bar height to create multiple images

在实际项目中，您常常需要同一条码的不同尺寸——比如一个用于小标签，另一个用于大海报。只需更改条码高度并复用同一个生成器实例：

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* 若条码高度设置得过低（例如低于 10 px），部分扫描仪可能难以读取。请务必使用目标扫描硬件对生成的图像进行测试。

## Full source code

下面是完整的程序代码，您可以直接复制到新的控制台项目中。代码已包含所有必需的 `using` 指令，并演示了两种条码高度的变化。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

运行程序后，将 `YOUR_DIRECTORY` 替换为有效的文件夹路径，您将在该目录下看到两张 PNG 文件：

* `DatabarBarHeight30Pixels.png` – 条纹高度为 30 px  
* `DatabarBarHeight60Pixels.png` – 条纹高度为 60 px  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Common questions

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG is preferred for lossless quality. |
| **What if I need a different XDimension?** | Adjust `generator.Parameters.Barcode.XDimension.Pixels` to any integer. Larger values increase overall barcode width. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | It is, provided the printed size meets the scanner’s minimum module size (usually 0.33 mm). The pixel‑based XDimension helps you meet that requirement. |
| **How do I embed the barcode in a PDF?** | After saving the PNG, use a PDF library (e.g., iTextSharp) to insert the image into a PDF page. |

## Conclusion

本 **barcode generator C# tutorial** 向您展示了如何创建 DataBar Omnidirectional 条码、以像素设置 XDimension，并生成不同条码高度的 PNG 文件。现在您拥有一段可复用的代码片段，可在任何需要条码生成的 C# 项目中进行适配。

### What’s next?

* 探索其他 `EncodeTypes`，如 `Code128` 或 `QR`，以扩展您的条码库。  
* 将生成的 PNG 与 PDF 生成库结合，制作可打印的发票。  
* 尝试使用 `generator.Parameters.Barcode.Color` 为条码添加自定义颜色，同时确保符合扫描仪规范。

欢迎修改示例、尝试更多条码高度或切换输出格式。祝编码愉快！

## What Should You Learn Next?

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步运用这些技巧。每篇资源均提供完整可运行的代码示例，并配有逐步解释，助您掌握更多 API 功能并探索替代实现方案。

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}