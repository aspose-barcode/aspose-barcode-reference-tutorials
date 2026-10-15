---
category: general
date: 2026-10-08
description: 学习如何使用 C# 条码生成器示例调整条码图像大小，仅用几行代码即可将条码高度从 30 像素改为 60 像素。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: zh
lastmod: 2026-10-08
og_description: 如何使用 C# 条码生成器示例快速调整条码大小。调整条码高度，保存 PNG 文件，避免常见陷阱。
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: 如何在 C# 中调整条形码大小 – 步骤式生成器示例
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: 如何在 C# 条形码生成器示例中调整条形码大小
url: /zh/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条形码生成器示例调整条形码大小

如果您需要在 .NET 项目中 **how to resize barcode**（调整条形码）图像，本指南提供完整的解决方案。您将看到一个简洁的 **barcode generator example C#**（条形码生成器示例 C#），它将条码高度从 30 px 改为 60 px，并将每个版本保存为 PNG 文件。

在收据、标签或产品页面上以不同的视觉比例显示相同数据时，通常需要调整条形码的大小。与其使用外部编辑器手动编辑光栅图像，不如通过编程方式调整条形码尺寸，从而保持数据完整性。

在本教程中，您将：

* 设置 DataBar Omni‑Directional 条形码生成器。
* 修改 X‑dimension（模块宽度）和条码高度参数。
* 保存两个不同高度的图像。
* 了解为何更改条码高度有效以及需要注意的边缘情况。

> **先决条件** – 您已具备 .NET 开发环境（Visual Studio 2022 或更高）以及提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的条形码库。代码适用于截至 2026 年 10 月的最新库版本。

## 条形码生成器示例 C# 的先决条件

在开始之前，请确保您拥有：

| 项目 | 原因 |
|------|--------|
| .NET 6.0 SDK 或更高版本 | 提供示例中使用的运行时和语言特性。 |
| 条形码库（如 Aspose.BarCode、Dynamsoft，或任何提供 `BarcodeGenerator` 的库） | 提供 `EncodeTypes.DatabarOmniDirectional` 枚举和图像导出方法。 |
| 可写入的文件夹（例如 `C:\Temp\Barcodes\`） | 示例会将 PNG 文件保存到该位置。 |
| 基础 C# 知识 | 本教程假设您熟悉类、属性和字符串插值。 |

如果尚未安装库，请通过 NuGet 安装：

```bash
dotnet add package Aspose.BarCode
```

将包名替换为您实际使用的名称；下面展示的 API 结构在大多数条形码 SDK 中都是通用的。

## How to resize barcode – step 1: create the generator

第一步是实例化一个 `BarcodeGenerator`，并指定所需的符号类型和数据负载。在本例中，我们生成一个 **DataBar Omni‑Directional** 条形码，编码一个 GTIN‑14 值。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**为什么重要**：`EncodeTypes.DatabarOmniDirectional` 枚举告诉库使用哪种条形码标准。数据字符串遵循 GS1 应用标识符 `(01)`，用于 14 位 GTIN，确保条码符合全球贸易标准。

## How to resize barcode – step 2: define the module width and initial bar height

条形码的视觉尺寸取决于两个参数：

* **X‑dimension** – 最小条（模块）的宽度，以像素或毫米为单位。
* **Bar height** – 条的垂直长度。

在保存之前设置这些值，可确保渲染的图像符合所需尺寸。

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**说明**：X‑dimension 为 2 px 可生成紧凑且仍能可靠扫描的条码。30 px 的高度是小标签的常见默认值。如果需要更密集或更稀疏的图案，可独立调整 X‑dimension 与高度。

## How to resize barcode – step 3: save the first image (30 px height)

现在将条码导出为 PNG 文件。`Save` 方法接受文件路径和图像格式枚举。

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**结果**：`DatabarBarHeight30Pixels.png` 包含一张高度为 30 px 的条码图像。您可以使用任意图像查看器打开文件以验证尺寸。

## How to resize barcode – step 4: change the bar height to 60 px

要创建更大的版本，只需修改 `BarHeight` 属性。生成器会复用相同的数据和 X‑dimension，条码的图案保持不变——仅视觉尺寸改变。

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**为何可行**：条码渲染引擎在需要时计算每根条的几何形状。在下一次 `Save` 调用前更新高度属性，会触发使用新尺寸的全新光栅化过程。

## How to resize barcode – step 5: save the second image (60 px height)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

现在您拥有两张 PNG 文件：一张小的（30 px），一张大的（60 px），可用于不同标签尺寸。

## Full source code for the barcode generator example C#

下面是完整、可直接运行的程序。将其复制到新的控制台项目中即可立即测试。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**控制台预期输出**：

```
Saved 30 px barcode.
Saved 60 px barcode.
```

运行后，打开这两张 PNG 文件即可看到视觉差异。两张条码均编码相同的 GTIN‑14 值，且无论高度如何都能同等扫描。

## Why adjusting bar height is safe for scanning

条码扫描器读取的是明暗模块的模式，而不是像素的绝对数量。只要 **X‑dimension** 保持在扫描器容差范围内（通常为 0.5 mm 到 2 mm），更改高度不会影响可读性。库会自动缩放模块，保留必要的安静区和对齐模式。

## Common pitfalls and how to avoid them

| 常见问题 | 解决办法 |
|---------|------------|
| **输出文件夹不存在** | 在保存前调用 `Directory.CreateDirectory(outputPath)`。 |
| **X‑dimension 设置不当导致扫描模糊** | 对大多数打印机保持 `XDimension.Pixels` 在 1 px 到 4 px 之间；并使用实物扫描仪进行测试。 |
| **对非常大的条码使用光栅格式** | 切换到 `BarCodeImageFormat.Svg`，实现无限可伸缩且无像素化。 |
| **忘记在第二次保存前重置 `BarHeight`** | 确保在再次调用 `Save` 之前先赋予新的高度值。 |

## Pro tip: generate multiple sizes in a loop

如果需要一系列高度（例如 30 px、45 px、60 px），使用简单的 `foreach` 循环即可避免代码重复：

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

该模式非常适合对产品目录进行批量处理。

## Edge cases: different image formats and DPI settings

* **SVG 输出** – 使用 `BarCodeImageFormat.Svg` 生成矢量文件，可在不损失质量的前提下任意缩放。  
* **高 DPI PNG** – 将 `generator.Parameters.Image.DpiX` 与 `DpiY` 设置为 300 或 600，以获得适合打印的图像；条码高度仍以像素计量，需要相应按比例增大。  
* **非标准符号** – 某些条码类型（如 QR Code）使用独立的 `Size` 属性而非 `BarHeight`。请查阅库文档获取对应信息。

## Testing the resized barcode

1. 在图像查看器中打开每个 PNG，验证像素尺寸（例如 150 × 30 px 与 150 × 60 px）。  
2. 按 100% 缩放打印图像。  
3. 使用手持条码扫描器或移动应用扫描。解码后的数据应与原始 GTIN‑14 完全一致。

## What Should You Learn Next?

以下教程涵盖与本指南密切相关的主题，帮助您进一步掌握 API 功能并探索在项目中的替代实现方式。

- [C# 条形码生成器示例 – 设置宽度和高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [使用 Aspose.BarCode 在 C# 中调整条形码大小 – 步骤指南](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [使用条形码生成器 C# 保存条码图像 – 步骤指南](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}