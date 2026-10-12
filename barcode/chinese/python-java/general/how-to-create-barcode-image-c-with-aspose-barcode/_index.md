---
category: general
date: 2026-10-12
description: 使用 Aspose.BarCode 在几分钟内创建 C# 条形码图像。此逐步条形码生成器示例 C# 演示如何设置宽高比并保存 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: zh
lastmod: 2026-10-12
og_description: 使用 C# 即时生成条形码图像。遵循此 C# 条形码生成器示例，生成具有自定义宽高比的高质量 PNG 条形码。
og_image_alt: Sample barcode image created with C# using Aspose.BarCode
og_title: C# 创建条形码图像 – Aspose.BarCode 快速指南
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  headline: How to create barcode image c# with Aspose.BarCode
  type: TechArticle
- description: Create barcode image c# using Aspose.BarCode in minutes. This step‑by‑step
    barcode generator example c# shows how to set aspect ratios and save PNG files.
  name: How to create barcode image c# with Aspose.BarCode
  steps:
  - name: – Initialise the barcode generator
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: – Set the module (X‑dimension) size
    text: '```csharp // Adjust visual parameters – set the module size (X‑dimension)
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: – Save the first image with aspect ratio 15
    text: '```csharp // Set the first aspect ratio (15) and save the image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 15; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
      ```'
  - name: – Change the aspect ratio to 30 and save a second image
    text: '```csharp // Change the aspect ratio to 30 and save the second image. barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio
      = 30; barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
      ```'
  - name: Expected output
    text: 'Running the program creates two PNG files:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 如何使用 Aspose.BarCode 在 C# 中创建条形码图像
url: /zh/python-java/general/how-to-create-barcode-image-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中创建条形码图像

如果您需要快速 **创建条形码图像 C#**，本指南将带您完成一个完整且可运行的示例。无论您是在构建运输标签系统还是库存扫描器，下面的步骤都精确演示了如何配置 DataBar Stacked Omnidirectional 条码、调整其视觉参数，并将结果保存为 PNG 文件。

您还将看到一个 **barcode generator example c#**，演示如何即时更改宽高比，从而在不重写代码的情况下生成多种变体。无需外部文档——只需复制、粘贴并运行。

## 您需要的准备

* .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
* Aspose.BarCode for .NET 的 **NuGet** 包  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 一个用于写入生成的 PNG 文件的文件夹（在代码中将 `YOUR_DIRECTORY` 替换为实际路径）

这些前提条件可确保 **barcode generator example c#** 能在任何现代的 Windows、Linux 或 macOS 开发机器上运行。

## 使用 Aspose.BarCode 在 C# 中创建条形码图像

该过程包括四个简短步骤：实例化生成器、设置模块尺寸、配置宽高比，最后保存图像。每一步都会解释其 *原因*，而不仅仅是 *如何* 编写代码。

### 步骤 1 – 初始化条码生成器

```csharp
using Aspose.BarCode.Generation;

// Create a DataBar Stacked Omnidirectional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

**为什么重要：** `BarcodeGenerator` 构造函数接受两个参数：条码符号类型（`EncodeTypes.DatabarStackedOmniDirectional`）和原始数据字符串。`(01)` 前缀告诉扫描仪，随后 14 位数字代表 GTIN‑14 标识符，这在零售和物流中是常见需求。

### 步骤 2 – 设置模块（X 维度）大小

```csharp
// Adjust visual parameters – set the module size (X‑dimension) in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么重要：** X 维度决定最小条（即“模块”）的宽度。`2` 像素的值可生成清晰的高分辨率条码，即使放大后仍保持可读性。如果需要更大的条码用于海报，请按比例增大此值。

### 步骤 3 – 使用宽高比 15 保存第一张图像

```csharp
// Set the first aspect ratio (15) and save the image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**为什么重要：** DataBar 符号支持 *宽高比*，影响高宽比例。`15` 的宽高比是许多零售应用的默认值，可生成紧凑、近似方形的条码，易于贴在小标签上。

### 步骤 4 – 将宽高比改为 30 并保存第二张图像

```csharp
// Change the aspect ratio to 30 and save the second image.
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

**为什么重要：** 将宽高比提升至 `30` 会使条码在垂直方向上拉伸，提升在低分辨率扫描仪或高于宽度的标签上的可读性。由于复用了同一个 `BarcodeGenerator` 实例，可避免为每种变体分配新对象——这是一种高效的批处理模式。

## 完整、可运行的示例

下面是完整的程序代码，您可以复制到控制台应用程序中。它包含必要的 `using` 指令、错误处理以及解释每行代码的注释。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // Initialise the generator with DataBar Stacked Omnidirectional symbology.
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.DatabarStackedOmniDirectional,
                    "(01)12345678901231");

                // Set the module (X‑dimension) size – 2 pixels gives a clear image.
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // -----------------------------------------------------------------
                // First image – aspect ratio 15 (default for most retail use cases)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 15;
                string path15 = "YOUR_DIRECTORY/DatabarAspectRatio15.png";
                generator.Save(path15, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 15 to {path15}");

                // -----------------------------------------------------------------
                // Second image – aspect ratio 30 (taller barcode for special scanners)
                // -----------------------------------------------------------------
                generator.Parameters.Barcode.DataBar.AspectRatio = 30;
                string path30 = "YOUR_DIRECTORY/DatabarAspectRatio30.png";
                generator.Save(path30, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved barcode with aspect ratio 30 to {path30}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error generating barcode: {ex.Message}");
            }
        }
    }
}
```

### 预期输出

运行程序后会生成两个 PNG 文件：

| 文件名 | 宽高比 | 典型用途 |
|-----------|--------------|-------------|
| `DatabarAspectRatio15.png` | 15 | 标准零售标签 |
| `DatabarAspectRatio30.png` | 30 | 高标签或低分辨率扫描仪 |

两张图像均包含清晰的 DataBar Stacked Omnidirectional 条码，编码的 GTIN‑14 值为 `12345678901231`。您可以使用任意图像查看器打开 PNG 文件以验证其视觉质量。

![使用 C# 和 Aspose.BarCode 创建的示例条码图像](https://example.com/placeholder.png){.align-center width=400 alt="使用 C# 和 Aspose.BarCode 创建的示例条码图像"}

*上述 alt 文本包含主要关键词，有助于搜索引擎和屏幕阅读器。*

## 其他注意事项和最佳实践提示

* **Supported formats** – `BarCodeImageFormat` 支持 PNG、JPEG、BMP、GIF 和 TIFF。PNG 为无损格式，是下游扫描的最安全选择。
* **Color customization** – 您可以通过 `generator.Parameters.Barcode.ForegroundColor` 和 `BackgroundColor` 更改前景/背景颜色。这在彩色介质打印时非常有用。
* **Batch generation** – 对于大型库存，可将保存逻辑包装在读取 CSV 文件中产品数据的 `foreach` 循环中。复用同一 `BarcodeGenerator` 实例可降低内存压力。
* **Error handling** – 完整示例中的 `try/catch` 块捕获诸如数据字符串无效或写入权限错误等问题，这在目标目录不存在时尤为常见。
* **Performance** – 在首次 `Save` 调用前设置 `XDimension.Pixels` 可确保渲染器在每次宽高比更改时仅计算一次位图大小。

## 结论

现在您已经了解如何使用 Aspose.BarCode **创建条形码图像 C#**，调整 X 维度、切换宽高比，并在单个可复用代码块中保存 PNG 文件。此 **barcode generator example c#** 覆盖了在为零售或物流应用生成 DataBar Stacked Omnidirectional 符号时最常见的变体。

## 接下来做什么？

* 探索其他符号如 `EncodeTypes.Code128` 或 `EncodeTypes.QR`，以拓宽您的解决方案。
* 尝试使用 `generator.Parameters.Barcode.ImageMargin` 为条码添加空白边距。
* 将生成的 PNG 与 Aspose.PDF 集成到 PDF 发票中，或直接嵌入到 HTML 报告中。

请随意根据您的具体工作流调整代码——无论是每个产品生成单张图像，还是批量导出数千条条码，此模式都能高效扩展。

---

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在已演示的技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方式。

- [如何使用 Aspose.Barcode 在 C# 中创建条码图像](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [C# 中的条码生成器示例 – 设置列、行并导出图像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [如何使用 Aspose.BarCode 在 C# 中创建邮政条码图像](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}