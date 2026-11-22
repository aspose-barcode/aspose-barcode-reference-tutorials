---
category: general
date: 2026-11-20
description: 使用 Aspose.BarCode 在 C# 中创建条形码图像。了解如何生成具有自定义布局的 PDF417 条码并将其保存为 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: zh
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中创建条形码图像。本指南展示如何生成 PDF417 条码、定制布局并导出为 PNG。
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: 使用 C# 创建 PDF417 条形码图像 – 完整教程
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: 如何在 C# 中使用 PDF417 创建条码图像 – 步骤指南
url: /zh/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 PDF417 创建条形码图像 – 步骤指南

如果您需要在 .NET 应用程序中 **create barcode image**，本指南将向您展示如何使用自定义布局 **generate PDF417 barcode** 并将其保存为 PNG 文件。您将看到完整可运行的代码，了解每个设置为何重要，并学习常见陷阱，以确保条形码在生产环境中可靠工作。

在本教程中，您将：

* 初始化 Aspose.BarCode 生成器用于 PDF417。
* 配置列数和行数以控制条形码的形状。
* 将结果导出为高质量 PNG 图像。
* 探索错误纠正和数据长度的可选设置。

唯一的前提是拥有最近的 .NET SDK（.NET 6 或更高）以及 **Aspose.BarCode for .NET** 的许可证或免费试用版。

---

## 前置条件和设置

在开始之前，请确保您具备以下条件：

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6 SDK 或更高版本 | 为 C# 控制台应用提供运行时。 |
| Visual Studio 2022（或 VS Code） | 提供带有 Aspose API IntelliSense 的 IDE。 |
| Aspose.BarCode for .NET NuGet 包 | 提供 `BarcodeGenerator`、`EncodeTypes` 和图像导出辅助工具。 |
| 对输出文件夹的写入权限 | 生成器将 PNG 文件写入磁盘。 |

您可以使用以下命令添加 NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

---

## 第 1 步：创建新的控制台项目

首先，搭建一个简单的控制台应用程序，以容纳条形码生成逻辑。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 为什么这段代码有效

* **`BarcodeGenerator`** 是所有条形码类型的入口。通过传入 `EncodeTypes.Pdf417`，您告诉库生成 PDF417 符号。
* **列和行** 是布局的主要杠杆。列数少会产生更高的条形码；列数多则更宽。根据图像显示的空间（例如标签打印机 vs. 网页）调整这些值。
* **错误纠正** 在条形码可能被弄脏或在低质量介质上打印时提升扫描可靠性。默认级别为 0；略微提升（2–4）是尺寸与鲁棒性之间的良好折中。
* **`Save`** 将图像以 PNG 格式写入磁盘，保留锐利的边缘，并在浏览器和移动设备上均可使用。

当您运行程序（`dotnet run`）时，它会在项目文件夹中创建 `CustomPdf417.png`。PNG 如下所示：

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Alt text:* **create barcode image** – PDF417 条码在 C# 中生成并保存为 PNG。

---

## 第 2 步：针对真实场景微调条形码

### 调整数据长度

PDF417 最多可编码 1,850 个字符。如果需要编码更长的字符串，请考虑将数据拆分为多个条形码或使用 **compact mode**：

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

紧凑模式会减少行数，但可能增加视觉密度，请使用您的扫描仪进行测试。

### 控制图像尺寸

默认图像尺寸是根据模块大小（条形码中最小的方块）计算的。您可以显式设置 DPI，或在生成后对图像进行缩放：

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

或者，保存后如果需要缩略图，可使用 System.Drawing 进行尺寸调整。

### 处理特殊字符

PDF417 支持完整的 ASCII 集。如果您的数据包含 Unicode 字符，请确保将字符串编码为 UTF‑8：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## 第 3 步：常见陷阱及规避方法

| Pitfall | Symptom | Fix |
|---------|---------|-----|
| 列数过多导致数据不匹配 | 条码被截断或抛出异常。 | 减少 `Columns`，或通过省略此设置让库自动调整大小。 |
| 噪声打印机上的低错误纠正 | 扫描仪间歇性读取失败。 | 将 `ErrorCorrectionLevel` 提高到至少 2。 |
| 保存到只读目录 | 运行时出现 `UnauthorizedAccessException`。 | 使用可写文件夹，例如 `Environment.CurrentDirectory` 或 `Path.GetTempPath()`。 |
| 使用过时的 Aspose.BarCode 版本 | 缺少 `CompactMode` 等属性。 | 将 NuGet 包更新到最新稳定版。 |

---

## 第 4 步：验证结果

要确认条形码生成正确，您可以：

1. 在任意图像查看器中打开 `CustomPdf417.png` —— 条码应清晰锐利，黑色模块在白色背景上分明。
2. 使用免费 PDF417 扫描应用（iOS 与 Android 均可）扫描图像。应用应显示 **“Sample data for PDF417 barcode”**。
3. （可选）在单元测试中使用 `System.Drawing.Bitmap` 加载图像，并断言 `(0,0)` 处的像素为黑色，以确认图像非空。

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

如果断言通过，您已成功 **create barcode image** 并以编程方式 **generate PDF417 barcode**。

---

## 结论

您现在了解如何在 C# 中通过 **create barcode image**，使用 **generating PDF417 barcode** 的自定义布局、调整错误纠正并导出为 PNG。完整示例演示了从初始化 `BarcodeGenerator` 到保存最终图像的每一步，您可以复制、粘贴并在自己的项目中运行。

接下来，您可以探索：

* **Embedding the PNG in a web API**，让客户端按需请求条形码（将 `generate pdf417` 作为服务）。
* **Batch generation**，针对大数据集循环处理字符串列表，并将每个 PNG 存入数据库。
* **Alternative output formats**（SVG、JPEG），只需更改 `BarCodeImageFormat`。

随意尝试列/行比例、错误纠正级别和图像分辨率，以满足扫描硬件或 UI 设计的精确需求。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，每个资源都提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}