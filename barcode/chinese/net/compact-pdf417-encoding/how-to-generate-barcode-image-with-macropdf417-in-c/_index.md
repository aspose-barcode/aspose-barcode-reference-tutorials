---
category: general
date: 2026-11-23
description: 学习如何使用 Aspose.BarCode for .NET 在 C# 中生成带有 MacroPdf417 元数据的条形码图像。请遵循完整的分步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: zh
lastmod: 2026-11-23
og_description: 如何使用 Aspose.BarCode for .NET 生成条形码图像。本教程展示了 MacroPdf417 元数据配置和 C#
  条形码生成。
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: 如何在 C# 中使用 MacroPdf417 生成条形码图像
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: 如何在 C# 中使用 MacroPdf417 生成条形码图像
url: /zh/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 MacroPdf417 生成条形码图像

如果您需要在 .NET 应用程序中**生成条形码图像**，本指南将向您展示如何使用**Aspose.BarCode for .NET**实现。我们将一步步演示创建**MacroPdf417 条形码**、配置其元数据，并将结果保存为 PNG 文件。

本教程涵盖了从安装库到编写完整可运行的控制台程序的所有内容。结束时，您将拥有一个可直接使用的代码示例，能够生成高质量的条形码图像，并且您将了解如何**设置条形码元数据**、选择**条形码图像格式**以及排查常见问题。无需任何 Aspose 经验——只需具备基本的 C# 知识即可。

## 安装 Aspose.BarCode for .NET

在您能够**生成条形码图像**之前，需要先获取 Aspose.BarCode 的 NuGet 包。

1. 在 Visual Studio 中打开终端或“程序包管理器控制台”。  
2. 运行以下命令：

```bash
dotnet add package Aspose.BarCode
```

该包会添加 `Aspose.BarCode.Generation` 命名空间，其中包含用于**C# 条形码生成**的 `BarcodeGenerator` 类。

> **专业提示：** 使用最新的稳定版本（截至 2026 年 11 月，当前版本为 24.11），以获取最新功能和错误修复。

## 创建 BarcodeGenerator 实例

第一段代码创建了一个针对**MacroPdf417 条形码**类型配置的 `BarcodeGenerator`，并提供了要编码的数据字符串。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

`using` 代码块确保生成器能够正确释放，释放任何非托管资源。

## 配置基本外观

可读的条形码始于合理的尺寸设置。这里我们设置每个模块的像素宽度（`XDimension`）以及 PDF417 矩阵的列数。

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*为什么使用这些数值？*  
- **XDimension** 控制每根条的粗细；2 像素在屏幕显示和大多数打印机上表现良好。  
- **Columns** 影响整体宽度；较少的列数可以保持条形码紧凑，同时保留纠错能力。

## 设置条形码元数据（MacroPdf417 特有）

MacroPdf417 允许您直接在条形码中嵌入文件级信息。这正是您**设置条形码元数据**（如文件 ID、段 ID 和时间戳）的地方。

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 每个属性的含义

| 属性 | 用途 |
|----------|---------|
| **MacroPdf417FileID** | 条形码所属逻辑文件的唯一标识符。 |
| **MacroPdf417SegmentID** | 当前段的索引（从 0 开始）。 |
| **MacroPdf417SegmentsCount** | 组成整个文件的段总数。 |
| **MacroPdf417FileName** | 源文件的可读名称。 |
| **MacroPdf417Checksum** | 用于数据完整性验证的可选 CCITT‑16 校验和。 |
| **MacroPdf417FileSize** | 原始文件的预期大小（字节）。 |
| **MacroPdf417TimeStamp** | 条形码生成的日期和时间——有助于版本跟踪。 |
| **MacroPdf417Addressee / Sender** | 可保存路由信息的自定义字符串。 |
| **MacroPdf417Terminator** | 指示此段是否为最后一段（`Set`）或非最后段（`Unset`）。 |

> **边缘情况：** 如果您计划将大型文档拆分为多个段，请在所有生成的条形码中保持 `SegmentsCount` 一致。计数不匹配会导致解码失败。

## 选择条形码图像格式并保存

Aspose 支持多种**条形码图像格式**（PNG、JPEG、BMP、TIFF 等）。PNG 为无损格式，适用于大多数网页和打印场景。

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

将 `YOUR_DIRECTORY` 替换为应用程序具有写入权限的绝对或相对文件夹路径。

程序运行时，您应在控制台看到确认文件位置的消息。使用任意图像查看器打开 PNG 文件，您将看到清晰的**MacroPdf417 条形码**，其中已编码您提供的文本以及定义的元数据。

### 预期输出

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

图像文件大小大约为 30‑40 KB，具体取决于所选的 `XDimension` 和列数。

## 验证条形码并排除故障

1. **目视检查** – 条形码应显示一系列堆叠的列，并在其周围有安静区（白色边距）。  
2. **解码测试** – 使用条形码扫描应用或 Aspose.BarCode 的 `BarCodeReader` 类读取图像，确认所有元数据字段均已正确嵌入。  



## 接下来应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您在此基础上进一步掌握 API 功能并探索在项目中实现的替代方案。每个资源都包含完整的可运行代码示例和逐步说明。

- [使用 Aspose.BarCode 在 C# 中生成 PDF417 条形码图像 – 步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [使用 Aspose.BarCode for .NET 生成带自定义文本的条形码](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [使用 C# 和 Aspose.BarCode 从图像读取条形码 – 步骤指南](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}