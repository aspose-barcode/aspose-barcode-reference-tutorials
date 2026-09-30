---
category: general
date: 2026-08-22
description: 学习如何在 C# 中创建微型 PDF417 条码并生成条码 PNG 图像。包括设置条码尺寸和保存文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: zh
lastmod: 2026-08-22
og_description: 在 C# 中创建微型 PDF417 条码并导出为 PNG。按照本指南设置条码尺寸，快速生成条码图像。
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: 在 C# 中创建微型 PDF417 条码 – 完整编码教程
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: 如何在 C# 中创建微型 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建微型 PDF417 条码 – 步骤指南

如果您需要为票务系统、库存标签或移动扫描 **创建微型 PDF417 条码**，本教程将为您详细演示。您将看到完整的 C# 程序生成条码 PNG，学习如何设置条码尺寸，并了解每个配置选项。

阅读完本指南后，您将能够生成高分辨率的条码图像，自定义 X 维度，选择列数，并将结果保存为 PNG 文件——只需几行代码。

## 您需要的条件

- .NET 6.0 SDK 或更高版本（代码兼容 .NET Core 和 .NET Framework）
- Visual Studio 2022 或任何支持 C# 的 IDE
- **Aspose.BarCode for .NET** NuGet 包（或任何支持 `EncodeTypes.MicroPdf417` 的库）
- 对 C# 语法的基本了解

> **专业提示：** Aspose.BarCode 的免费社区版已足以用于开发和测试。生产环境请获取许可证以去除评估水印。

## 第一步：安装条码库

在项目文件夹中打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

此操作会添加 `Aspose.BarCode` 程序集，提供用于 **创建条码图像 C#** 应用的 `BarcodeGenerator` 类。

## 第二步：初始化生成器 – 创建微型 PDF417 条码

第一行可执行代码会创建一个针对 Micro PDF417 符号的 `BarcodeGenerator` 实例，并提供要编码的数据。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*为何重要*：`EncodeTypes.MicroPdf417` 枚举指示库使用 PDF417 的紧凑版本，非常适合小标签和移动屏幕。

## 第三步：如何在 C# 中设置条码尺寸

微调模块宽度（X 维度）可控制条码的视觉密度。较小的数值会产生更清晰的图像，而较大的数值则使条码在远距离下更易于扫描。

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **为何需要设置尺寸**：如果不调整 X 维度，默认值在高 DPI 渲染时可能导致条码模糊。将其设为 2 像素是大多数基于屏幕的扫描的良好平衡。

## 第四步：选择列数 – 控制条码宽度

Micro PDF417 支持 1 到 4 列。列数越多，数据在水平方向上压缩越多，从而减小整体图像宽度。

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*边缘情况*：如果请求 5 列，库会抛出 `ArgumentOutOfRangeException`。请始终保持在文档规定的范围内。

## 第五步：如何生成条码 PNG – 保存图像

现在您可以将生成的条码导出为 PNG 文件。PNG 保持无损质量，这对可靠扫描至关重要。

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

运行程序后，您会在控制台看到确认文件位置的消息。生成的 `MicroPdf417.png` 如下所示：

![显示使用 C# 创建的生成的微型 PDF417 条码的截图](micro-pdf417-example.png "生成的微型 PDF417 条码")

*图片替代文字*：**使用 C# 生成的微型 PDF417 条码** – 展示了应用尺寸和列设置后的最终输出。

## 第六步：运行并验证输出

1. 构建项目：`dotnet build`。
2. 执行：`dotnet run`。
3. 在桌面上打开 `MicroPdf417.png` 并使用移动条码扫描应用进行扫描。

您应该看到解码后的文本 **“Sample text”**。如果扫描器报错，请再次检查 X 维度和列数——极端值可能导致条码对某些设备过于密集。

## 常见变体和故障排除

| 情况 | 调整 |
|-----------|------------|
| **需要更大的条码以适配低分辨率打印机** | 将 `XDimension.Pixels` 增加到 3 或 4。 |
| **希望在不改变宽度的情况下获得更高的条码** | 设置 `generator.Parameters.Barcode.Pdf417.Rows`（行范围 3‑90）。 |
| **在循环中生成多个条码** | 重复使用同一个 `BarcodeGenerator` 实例，并在每次 `Save` 前仅更改 `CodeText`。 |
| **保存为 JPEG 而非 PNG** | 将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`。 |
| **在 .NET Framework 4.7 上运行** | 相同代码可工作；只需引用相应的 `Aspose.BarCode.dll`。 |

## 完整源码列表（可运行）

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**预期输出** – 一个 200 × 100 像素的 PNG 文件，包含清晰的 Micro PDF417 条码，解码后为 “Sample text”。

## 结论

您现在已经了解如何在 C# 中 **创建微型 PDF417 条码**、**设置条码尺寸**，以及 **生成条码 PNG** 图像。完整示例演示了从库安装到保存最终文件的每一步，帮助您将条码生成直接嵌入自己的应用程序中。

接下来，您可以探索相关主题，例如 **使用 Aspose.BarCode 创建 QR 码**、**自定义颜色**，或 **在 PDF 文档中嵌入条码**。这些都基于本文中介绍的相同 `BarcodeGenerator` 基础。

欢迎尝试不同的数据字符串、列数和 X 维度值，以适配您的特定扫描环境。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本教程演示的技术。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose.BarCode 创建条码 – 紧凑型 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何生成 PDF417 条码 – 紧凑型 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何使用 Aspose.BarCode for .NET 创建 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}