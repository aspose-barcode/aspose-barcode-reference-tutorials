---
category: general
date: 2026-09-16
description: 了解如何设置宽度、如何创建空白条以及在使用 Aspose.BarCode 生成 Planet 条码时如何填充条。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: zh
lastmod: 2026-09-16
og_description: 如何在使用 Aspose.BarCode 生成 Planet 条码时设置宽度、制作空白条并填充条——完整的逐步指南。
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: 如何在 C# 中设置宽度并生成 Planet 条码
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中设置宽度并生成 Planet 条码
url: /zh/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中设置宽度并生成 Planet 条形码

如果您需要**设置宽度**来生成 Planet 条形码，本指南将展示完整的过程。您还将看到**如何生成空白条**、**如何填充条**，以及使用 Aspose.BarCode for .NET **生成 Planet 条形码**的具体步骤。

生成邮政风格的 Planet 条形码在构建邮件标签应用或邮政服务集成时非常常见。完成本教程后，您将拥有一个可直接运行的控制台程序，能够创建实心条图像和空白条图像，两者均使用相同的数据字符串。

## 前置条件

- .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7+）
- Visual Studio 2022 或任何兼容 C# 的 IDE
- Aspose.BarCode for .NET NuGet 包 (`Aspose.BarCode`)  
  安装方式：

```bash
dotnet add package Aspose.BarCode
```

无需额外配置；库内部已处理图像编码。

## 第一步：创建控制台项目并添加库

打开终端并运行：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

这将在项目中创建一个 `Program.cs` 文件，我们将在其中编写条形码逻辑。

## 第二步：编写代码 – 设置宽度并生成 Planet 条形码

打开 `Program.cs`，将其内容替换为以下完整示例：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### 为什么每一步都很重要

- **如何设置宽度**：`XDimension.Pixels` 属性直接影响每根条的物理尺寸。选择 2 到 6 像素之间的值可以在屏幕可读性和打印质量之间取得平衡。
- **如何生成空白条**：将 `FilledBars = false` 设置为只绘制条的轮廓。此样式适用于“浅色打印深色底”或希望保留纸张纹理的场景。
- **如何填充条**：默认的 `FilledBars = true` 会生成实心黑色条，这是大多数邮政扫描仪的标准。
- **生成 Planet 条形码**：使用 `EncodeTypes.Planet` 选择美国邮政服务（USPS）所需的特定编码。

## 第三步：构建并运行程序

在项目文件夹中执行：

```bash
dotnet run
```

您应该会看到类似以下的控制台输出：

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

项目目录中会出现两个 PNG 文件：

- `PostalPlanetFilledBars.png` – 实心黑色条（默认样式）
- `PostalPlanetEmptyBars.png` – 轮廓条（空白样式）

使用任意图像查看器打开它们，以验证条宽度符合 4 像素设置，并且空白版本显示未填充的条。

## 常见问题与边缘情况

| 问题 | 回答 |
|----------|--------|
| *我可以使用其他图像格式吗？* | 可以。根据需要将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Gif`。 |
| *如果条形码对我的标签来说太宽怎么办？* | 将 `XDimension.Pixels` 降低（例如设为 `2`）或增加标签打印机的模块宽度。 |
| *我需要手动设置 `Height` 吗？* | 库会根据编码自动计算高度。您可以通过 `Parameters.Barcode.BarHeight` 覆盖此值。 |
| *所有打印机都支持空白条样式吗？* | 大多数现代热敏打印机都能处理实心和空白两种样式，但如果使用旧设备，请进行测试打印以确认。 |
| *如何在条形码下方添加可读的文字说明？* | 使用 `Parameters.Caption` 启用并设置文字样式；将 `CaptionAbove` 设为 `false` 可将说明放在下方。 |

## 专业技巧

- **复用同一生成器**仅在所有参数保持完全一致时才可。保存后更改 `FilledBars` 不会影响已保存的图像，因此如示例中重新实例化可确保干净的起点。
- **批量生成**：将代码放入循环中，并在每次迭代时更改 `data`，即可为批量邮件创建一系列 Planet 条形码。
- **性能优化**：处理成千上万的条形码时，创建单个 `BarcodeGenerator` 实例，根据需要调整 `XDimension` 和 `FilledBars`，并重复使用该对象以减少内存分配。

## 结论

您现在已经掌握了 **如何设置宽度**、**如何生成空白条**、**如何填充条**，以及使用 Aspose.BarCode 在 C# 中 **生成 Planet 条形码** 的完整步骤。完整的可运行示例会生成实心条和空白条的 PNG 文件，随时可集成到任何邮件标签工作流中。

接下来，您可以探索诸如 **如何在同一标签上添加 QR 码**、**自定义条形码颜色** 或 **将条形码嵌入 PDF 文档** 等相关主题。这些内容都基于本指南中讲解的基础。祝编码愉快！

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中尝试不同实现方式。每篇资源都提供完整的可运行代码示例和逐步说明。

- [在 C# 中创建 Planet 条形码图像 – 如何生成邮政条形码](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [如何在 Java 中创建带空白条的 Code128 条形码](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [如何使用 Aspose.BarCode 在 Java 中生成条形码图像](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}