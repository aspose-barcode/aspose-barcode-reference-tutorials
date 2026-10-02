---
category: general
date: 2026-09-10
description: 在 C# 中快速生成 PDF417 条码。了解如何使用 Aspose.BarCode 仅用几行代码生成 PDF417 并更改条码尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: zh
lastmod: 2026-09-10
og_description: 在 C# 中即时生成 PDF417 条码。本教程展示了如何使用 Aspose.BarCode 生成 PDF417 以及如何更改条码尺寸。
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: 在 C# 中生成 PDF417 条码 – 完整编程指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中生成 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中生成 PDF417 条码 – 步骤指南

如果您需要在 .NET 应用程序中**生成 PDF417 条码**，本指南将准确展示如何操作。您将看到一个简洁、可直接运行的示例，它创建 PDF417 条码、让您控制其尺寸，并将结果保存为 PNG 图像。

生成 PDF417 条码是库存系统、登机牌和文档追踪等场景的常见需求。在本教程中，我们还会介绍**如何更改条码尺寸**，以便代码能够适应不同的打印或屏幕显示需求。

## 前置条件

在开始之前，请确保您拥有：

* .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.6+）
* Visual Studio 2022 或任意 C# IDE
* **Aspose.BarCode for .NET** NuGet 包  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 对 C# 控制台应用有基本了解

## 项目设置

1. 创建一个新的控制台项目：

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. 添加 Aspose.BarCode 引用（见前置条件）。

3. 打开 `Program.cs`，将其内容替换为下面的完整示例。

## 步骤 1：生成 PDF417 条码

第一步是创建一个针对 **PDF417** 符号的 `BarcodeGenerator` 实例。该对象是所有条码操作的入口。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*为什么这很重要* – `EncodeTypes.Pdf417` 枚举值告诉 Aspose.BarCode 使用 PDF417 标准，第二个参数提供要编码的数据。生成器现在持有一个完整的条码对象，您可以在保存之前对其进行自定义。

## 步骤 2：如何更改条码尺寸（模块大小）

PDF417 条码由小方形模块组成。调整模块大小即可在不改变编码数据的前提下改变图像的整体尺寸。

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*为什么这很重要* – 更大的 `XDimension` 会生成更大的条码，适合高分辨率打印；较小的值更适合屏幕显示。默认通常是 1 px，在现代显示器上可能显得过于紧凑。

## 步骤 3：配置布局 – 列数和行数

PDF417 允许您定义列数和行数，这会影响条码的形状以及错误纠正能力。

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*为什么这很重要* – 增加列数会使条码更宽，增加行数会使条码更高。根据 UI 或标签的可用空间调整这些值。

## 步骤 4：保存条码图像

最后，将条码写入文件。这里使用 PNG，因为它能够保持清晰的边缘并支持透明度。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

运行程序后会在项目的输出文件夹中生成 `LayoutPdf417.png`。图像效果如下：

![生成 PDF417 条码示例，显示 4 列和 9 行](https://example.com/images/pdf417-sample.png){#barcode-image alt="生成 PDF417 条码示例，显示 4 列和 9 行"}

*提示*：如果需要其他图像格式（JPEG、BMP、TIFF），请将 `BarCodeImageFormat.Png` 替换为相应的枚举值。

## 如何生成 PDF417 – 替代数据来源

上面的代码使用了硬编码字符串 `"Layout test"`。在实际项目中，您通常会从数据库、文件或用户输入中获取数据。

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

其余步骤（尺寸、布局、保存）保持不变。这演示了**如何从动态来源生成 PDF417**，而无需额外的复杂操作。

## 常见问题及规避方法

| 问题 | 产生原因 | 解决方案 |
|------|----------|----------|
| 条码显示模糊 | `XDimension` 对输出分辨率设置过低 | 增大 `XDimension.Pixels`，或保存为矢量格式如 SVG（`BarCodeImageFormat.Svg`） |
| 文本无法适配所选布局 | 选定的行/列容纳的字符过多 | 减少行/列数量，或将数据拆分为多个条码 |
| 未生成图像文件 | 输出文件夹不存在或缺少写入权限 | 确认目录已创建（`Directory.CreateDirectory`），并以适当权限运行应用 |

## 验证条码

生成图像后，您可以使用任何 PDF417 扫描应用（手机上有免费扫描器）或内置的 Aspose.BarCode 读取器进行验证：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

如果输出与原始文本一致，**生成 PDF417 条码**的过程即告成功。

## 完整、可运行的示例

下面是完整的程序代码，可直接复制粘贴到 `Program.cs` 中。它包含所有 using 指令、错误处理以及注释。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

运行该程序后会输出：

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

现在您拥有一个**完整、独立的解决方案**，可以生成 PDF417 条码并控制其尺寸。

## 结论

在本教程中，您学习了如何使用 Aspose.BarCode 在 C# 中**生成 PDF417 条码**，以及如何通过调整 X‑dimension 来**更改条码尺寸**，并掌握了列数和行数的布局配置。您还看到如何以编程方式验证结果以及如何将代码适配为动态数据来源。

接下来，您可以进一步探索：

* **如何生成 PDF417** 并调节错误纠正级别 (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* 导出为**矢量格式**（SVG、EPS），实现无限缩放
* 使用 **Aspose.PDF** 将条码嵌入 PDF 文档

尝试不同的模块大小和布局选项，以满足您特定的 UI 或打印需求。祝编码愉快！

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在实际项目中进一步掌握 API 功能并探索替代实现方式。每篇资源都提供完整可运行的代码示例和逐步解释。

- [如何使用 Aspose 生成 PDF417 条码 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [调整条码尺寸 – C# 生成 PDF417 条码指南](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [如何在 C# 中保存条码 – 生成 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}