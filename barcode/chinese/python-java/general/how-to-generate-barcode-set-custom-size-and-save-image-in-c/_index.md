---
category: general
date: 2026-09-13
description: 学习如何在 C# 中生成条形码、自定义条形码尺寸，并使用 Aspose.BarCode 将条形码图像保存为 PNG。完整的分步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: zh
lastmod: 2026-09-13
og_description: 如何在 C# 中生成自定义尺寸的条形码并将条形码图像保存为 PNG。请参阅 Aspose.BarCode 的完整指南。
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: 如何在 C# 中生成条码、设置自定义尺寸并保存图像
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中生成自定义尺寸的条形码并保存图像
url: /zh/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成自定义尺寸的条形码并保存图像

如果您需要在 .NET 应用程序中**生成条形码**，本教程为您提供完整的解决方案。您将看到如何使用几行 C# 代码调整**自定义条码尺寸**并**保存条形码图像**文件。

生成条形码是库存系统、运输标签和销售点应用程序的常见需求。阅读完本指南后，您将拥有一个可运行的程序，它会创建两个 DataBar‑Stacked‑Omnidirectional 条码，每个条码具有不同的纵横比，并将它们写入磁盘上的 PNG 文件。

**Prerequisites**

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
- Visual Studio 2022 或任意 C# IDE
- Aspose.BarCode for .NET（免费试用版或已授权的 NuGet 包）

---

## 如何使用 Aspose.BarCode 生成条形码

Aspose.BarCode 库抽象了条码标准的底层细节，让您专注于要编码的数据和所需的视觉外观。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 为什么每一行都很重要

| Step | Explanation |
|------|-------------|
| **1️⃣ 创建生成器** | `EncodeTypes.DatabarStackedOmniDirectional` 枚举告诉 Aspose 使用哪种条码符号。字符串 `"(01)12345678901231"` 符合 GS1‑128 数据格式，其中 `(01)` 是 GTIN 的应用标识符。 |
| **2️⃣ 设置 X‑dimension** | `XDimension.Pixels` 定义单个条码模块（最小条）的宽度。更改此值是实现**自定义条码尺寸**的主要方式，而无需更改编码数据。 |
| **3️⃣ 设置纵横比并保存** | `DataBar.AspectRatio` 控制 DataBar 符号的高宽比。纵横比为 15 时生成相对短而宽的条码，30 时则更高。`Save` 将可视化表示写入 PNG 文件，满足**保存条形码图像**的需求。 |
| **4️⃣ 更改纵横比并再次保存** | 复用同一个生成器实例可以在保持数据不变的情况下，生成具有不同视觉特性的多张图像。 |

---

## 超越 X‑dimension 的自定义条码尺寸调整

虽然 `XDimension.Pixels` 设置模块宽度，您还可以通过组合以下两个属性进一步微调条码的整体尺寸：

1. **`BarHeight`** – 以像素为单位的显式高度。  
2. **`BarWidth`** – 以像素为单位的显式宽度（会覆盖 X‑dimension）。

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** 打印条码时，请始终在最终打印尺寸下测试生成的图像。2 px 的模块宽度适合屏幕显示，但打印标签通常需要至少 4 px 才能保持可扫描性。

---

## 为保存条形码图像选择合适的图像格式

Aspose.BarCode 支持 PNG、JPEG、BMP、GIF 和 TIFF。PNG 为无损格式，能够保留清晰的边缘，是大多数应用的最安全选择。如果需要更小的网页文件，质量设为 90 的 JPEG 也可使用，但需注意压缩伪影可能影响扫描可靠性。

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## 完整、可运行的示例

下面是一个独立的控制台应用程序示例，您可以复制、粘贴并直接运行。它演示了**生成条形码**、修改**自定义条码尺寸**以及在两种不同格式下**保存条形码图像**的过程。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Expected output on the console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

四个图像文件将会出现在程序所在目录中。

## 接下来应该学习什么？

以下教程涵盖了与本指南技术密切相关的主题，帮助您在已有技巧的基础上进一步深入。每篇资源都提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose 生成 PDF417 条码 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义纵横比的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}