---
category: general
date: 2026-08-12
description: 使用 BarCodeGenerator 在 C# 中创建条形码图像。了解如何生成 DataBar、控制条形码图像尺寸，以及高效创建多个条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: zh
lastmod: 2026-08-12
og_description: 使用 BarCodeGenerator 在 C# 中创建条形码图像。本教程逐步演示如何生成 DataBar 条码、调整条码图像尺寸以及生成多个条码。
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: 在 C# 中创建条形码图像 – 完整的 BarCodeGenerator 指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: 使用 BarCodeGenerator 在 C# 中创建条形码图像
url: /zh/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 BarCodeGenerator 在 C# 中创建条形码图像

如果您需要在 .NET 应用程序中**创建条形码图像**，本指南将向您展示如何使用 `BarCodeGenerator` 类完成此操作。无论您是在构建零售 POS 系统还是库存跟踪工具，您都将学习生成 DataBar 符号、控制条形码图像大小，以及一次性生成多个条形码。

您还将了解 **barcode generator c#** API 如何让您微调尺寸、切换输出格式，并处理诸如无效数据字符串等边缘情况。教程结束时，您能够自信地**创建多个条形码**，而无需编写重复代码。

## 前提条件

在开始之前，请确保您已具备：

- 已安装 .NET 6.0 或更高版本  
- 开发环境（Visual Studio、Rider 或 VS Code）  
- Aspose.BarCode for .NET NuGet 包（或任何提供 `BarCodeGenerator` 的兼容库）  

您可以使用以下方式添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 本教程涵盖的内容

1. 为 DataBar Omni‑directional 编码设置 **barcode generator c#** 实例。  
2. 通过更改 X‑dimension 和条形高度来调整 **barcode image size**。  
3. 使用循环**创建多个条形码**，高度各不相同。  
4. 将图像保存为 PNG 文件并验证输出。  

所有代码片段均为完整可直接复制粘贴到新控制台项目中的示例。

![Create barcode image example](barcode-example.png){alt="创建条形码图像示例"}

## 第 1 步：初始化生成器 – 条形码图像基础

第一步是使用所需的符号实例化 `BarCodeGenerator`。对于 DataBar Omni‑directional 符号，使用 `EncodeTypes.DatabarOmniDirectional`。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**为什么这很重要：** 实例化生成器会定义编码规则和数据负载。如果省略正确的 `EncodeTypes` 值，库将生成不受支持的条形码或抛出异常。

## 第 2 步：配置 X‑dimension 和条形高度 – 控制条形码图像大小

条形码的视觉尺寸由两个参数决定：

| 参数 | 控制内容 | 常见范围 |
|-----------|------------------|---------------|
| `x_dimension.pixels` | 最小模块（“点”）的宽度 | 1 – 4 px |
| `bar_height.pixels`  | 垂直条的高度 | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**专业提示：** 较小的 X‑dimension 能产生更高分辨率的图像，但在低质量打印机上可能更难扫描。请根据目标扫描设备调整该值。

## 第 3 步：保存第一张条形码 – 为 30 px 高度创建条形码图像

现在可以生成图像并写入磁盘。`Save` 方法接受文件路径和图像格式枚举。

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**预期结果：** 在 `C:\Barcodes` 中出现名为 `Databar30.png` 的 PNG 文件。打开文件后可看到 DataBar Omni‑directional 符号，图案清晰、对比度高。

## 第 4 步：更改高度并生成额外图像 – 创建多个条形码

要**创建多个条形码**并使用不同尺寸，只需修改 `BarHeight` 属性后再次调用 `Save`。这样可以避免重新实例化生成器，从而节省内存和 CPU 时间。

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**为何可行：** `BarCodeGenerator` 对象保存所有配置状态。更改单个属性会更新渲染引擎，以便在下次 `Save` 调用时生成新的图像，从而高效**创建多个条形码**。

## 第 5 步：进阶 – 如何使用自定义数据生成 DataBar

上面的示例使用了静态 GS1 负载。在实际场景中，您通常需要嵌入可变的产品标识符。库接受任何符合 DataBar 规范的字符串。

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**关键点：** 设置 `generator.CodeText` 会在不重新创建对象的情况下更新编码数据。这是处理大数据集时推荐的**how to generate databar**模式。

## 第 6 步：验证与排查 – 确保条形码图像尺寸正确

生成图像后，您可能希望通过代码程序化确认尺寸是否符合预期。`System.Drawing` 中的 `Image` 类可以读取文件并报告其大小。

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

如果高度未反映您设置的值，请检查：

- **X‑dimension**：过小的数值可能导致渲染器对高度进行四舍五入。  
- **图像格式**：某些格式（如 JPEG）在保存时会进行压缩，可能改变像素尺寸。PNG 能保留精确尺寸。

## 第 7 步：条形码图像大小与性能的最佳实践

| 建议 | 原因 |
|----------------|--------|
| 将 `x_dimension.pixels` 保持在 2 – 3 px 之间，以适配大多数扫描仪。 | 在可读性和文件大小之间取得平衡。 |
| 打印时使用 PNG 进行无损输出。 | 确保尺寸精确且边缘锐利。 |
| 生成大量条形码时复用同一个 `BarCodeGenerator` 实例。 | 减少对象分配开销。 |
| 在将字符串赋给 `CodeText` 前，先依据 GS1 标准进行验证。 | 防止运行时异常和无效扫描。 |
| 将生成的图像存放在专用文件夹，并使用清晰的命名约定（例如 `Databar_{GTIN}.png`）。 | 简化后续处理和审计追踪。 |

## 完整工作示例

下面是完整的程序示例，涵盖从初始化到验证的所有步骤。将代码复制到新建的控制台项目中并运行。



## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每个资源均提供完整的可运行代码示例和逐步解释。

- [生成条形码图像 – GS1 优惠券 UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [创建 DotCode 条形码图像 – 行与列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何使用 Aspose.BarCode for .NET 为 ITF-14 创建条形码安静区](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}