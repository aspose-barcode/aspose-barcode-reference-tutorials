---
category: general
date: 2026-10-18
description: 学习如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码。本教程涵盖基本、紧凑、宏和微型 PDF417 的生成，并提供完整代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: zh
lastmod: 2026-10-18
og_description: 使用 Aspose.BarCode 在 C# 中创建 PDF417 条码。按照本指南一步步生成基本、紧凑、宏和微型 PDF417 条码。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: 在 C# 中创建 PDF417 条码 – 完整的 Aspose.BarCode 教程
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: 使用 Aspose.BarCode 在 C# 中创建 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码 – 步骤指南

如果您需要在 .NET 应用程序中 **创建 PDF417 条形码**，本教程将带您完整了解整个过程。您将看到如何生成基础条形码、启用紧凑模式、添加宏元数据以及生成微型变体——全部配有清晰的说明和可运行的代码。

在物流、票务和文档管理等领域，生成 PDF417 条形码非常常见。阅读完本指南后，您将能够在任何 C# 项目中集成条形码创建，而无需外部工具。

## 前提条件

* .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
* Visual Studio 2022 或任意 C# IDE
* **Aspose.BarCode for .NET** NuGet 包  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 对用于保存生成的 PNG 文件的文件夹具有写入权限

无需额外配置；库会处理所有底层编码细节。

## 步骤 1：创建基础 PDF417 条形码

第一步是创建一个具有自定义尺寸和列数的普通 PDF417 条形码。

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**这些设置为何重要**

* `XDimension.Pixels` 控制每个条形码元素的物理尺寸。值为 2 时，可在大多数屏幕和打印机上生成清晰的图像。
* `Pdf417.Columns` 决定条形码包含多少数据列。列数少可减小宽度，列数多则提升数据容量。

运行代码后会生成 `Pdf417Basic.png`，其外观类似典型的 PDF417 符号，具有三列数据以及右侧完整的元数据列。

## 步骤 2：启用紧凑（截断）模式

紧凑模式会去除右侧的元数据列，使条形码更窄。当空间受限且数据可以从剩余行重建时，这非常有用。

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**为何截断？**  
当 `Truncate` 为 `true` 时，生成器会省略存放纠错和文件级元数据的可选右侧列。生成的条形码占用的列更少，仍可被大多数 PDF417 读取器扫描。

## 步骤 3：创建带文件级元数据的宏 PDF417 条形码

宏 PDF417 在标准格式上加入段标识符，使得大型文档可以拆分为多个条形码。这对于编码长字符串或多页文件非常方便。

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**宏字段说明**

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | 整个文件的唯一标识符；所有段共享此值。 |
| `MacroPdf417SegmentID` | 当前段的索引（从 1 开始）。 |
| `MacroPdf417SegmentsCount` | 组成完整数据集的段总数。 |

支持宏 PDF417 的扫描器可以通过读取所有段并利用这些标识符来重新组装原始数据。

## 步骤 4：为短数据创建微型 PDF417 条形码

微型 PDF417 是为小容量（最多 90 字符）设计的紧凑版本。它将列范围限制在 1‑4，适用于小标签或显示面积受限的设备。

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**何时使用微型 PDF417**  
当数据负载较短且需要尽可能小的条形码时使用此变体。它非常适合库存标签、门禁卡或任何对屏幕空间要求极高的场景。

## 完整可运行示例

下面是一个独立的控制台应用程序，可一次性生成四种条形码。将代码复制到新的 C# 项目中，将 `YOUR_DIRECTORY` 替换为已有的文件夹路径，然后运行。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**预期输出**

运行程序后会在指定文件夹中生成四个 PNG 文件：

* `Pdf417Basic.png` – 标准条形码，包含三列
* `CompactPdf417.png` – 相同数据，截断右侧列
* `MacroPdf417.png` – 包含段元数据的宏条形码
* `MicroPdf417.png` – 用于短字符串的紧凑微型条形码

使用图像查看器打开任意图片，即可看到独特的 PDF417 图案。使用移动条形码阅读器（例如 ZXing、Scandit）扫描它们会返回原始文本字符串。

## 常见问题与技巧

* **条形码如果看起来模糊怎么办？**  
  将 `XDimension.Pixels` 提升至 3 或 4。更大的模块尺寸会生成更高分辨率的图像，但文件体积会增大。

* **可以输出 SVG 而不是 PNG 吗？**  
  可以。在 `Save` 调用中将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Svg`。

* **需要手动设置纠错级别吗？**  
  Aspose.BarCode 会自动选择最佳级别。对于特定场景，您可以调整 `Pdf417.ErrorCorrectionLevel`。

* **如何将条形码嵌入 PDF 文档？**  
  使用 `Aspose.Pdf` 将生成的 PNG 或 SVG 作为图像元素添加到 PDF 页面上。

* **库是否线程安全？**  
  每个 `BarcodeGenerator` 实例都是独立的；您可以在多个线程上创建生成器而无需共享状态。

## 结论

现在，您已经了解如何使用 Aspose.BarCode 在 C# 中 **创建 PDF417 条形码**，涵盖基础、紧凑、宏和微型四种变体。

## 接下来您应该学习什么？

以下教程涉及与本指南密切相关的主题，基于本教程演示的技术。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中创建 pdf417 条形码 – 步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中使用紧凑模式创建 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [如何在 C# 中使用 Aspose.BarCode 创建宏 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}