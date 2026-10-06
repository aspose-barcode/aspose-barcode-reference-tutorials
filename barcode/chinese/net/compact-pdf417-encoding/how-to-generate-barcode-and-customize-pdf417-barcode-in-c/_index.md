---
category: general
date: 2026-09-19
description: 如何在 C# 中生成条形码的分步指南。学习自定义 PDF417 条形码设置并创建 C# 开发者可立即使用的条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: zh
lastmod: 2026-09-19
og_description: 如何在 C# 中生成条形码并提供详细步骤。自定义 PDF417 条形码参数，创建可在今天的 C# 项目中使用的条形码图像。
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: 如何在 C# 中生成条形码并自定义 PDF417 条码
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: 如何在 C# 中生成条形码并自定义 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成条形码并自定义 PDF417 条形码

如果您需要在 .NET 应用程序中**how to generate barcode**，本教程为您提供一个完整、可直接运行的解决方案。您将学习如何自定义 PDF417 条形码的尺寸、选择列数，最后**create barcode image C#**项目可以直接嵌入的条形码图像。

生成条形码并不需要复杂的构建流水线。完成本指南后，您将拥有一个包含 MicroPDF417 条形码的 PNG 文件，尺寸和分辨率完全符合您的需求。

## 先决条件

您在开始之前应已安装以下内容：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.6+）
* Visual Studio 2022（或您喜欢的任何 C# 编辑器）
* Aspose.BarCode for .NET NuGet 包 – 使用以下命令安装  
  `dotnet add package Aspose.BarCode`

无需其他外部工具。

## 步骤 1：设置项目并导入命名空间

创建一个新的控制台项目并添加 Aspose.BarCode 引用。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

打开 `Program.cs` 并添加所需的 `using` 指令：

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

这些命名空间公开了让您**how to generate barcode**并控制 PDF417 特定选项的类。

## 步骤 2：使用所需文本初始化 MicroPDF417 生成器

第一行创建了一个针对 MicroPDF417 符号的 `BarcodeGenerator` 实例。构造函数接受编码类型和您想要编码的数据字符串。

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**为什么这很重要：**MicroPDF417 是完整 PDF417 标准的紧凑变体，适用于小标签或移动屏幕。使用正确的 `EncodeTypes` 初始化生成器可确保库使用正确的编码算法。

## 步骤 3：自定义 X 维度（模块宽度）以获得更高分辨率

X 维度控制单个条形码模块（最小的黑条或白条）的宽度。将其设置为较低的像素值可产生更高分辨率的图像。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么这很重要：**较大的 X 维度使低分辨率扫描仪更容易读取条形码，而较小的值则在有限空间内容纳更多数据。请根据扫描环境调整此值。

## 步骤 4：定义列数以控制条形码大小

MicroPDF417 支持 1‑4 列。列数越多，条形码越短且更宽；列数越少，条形码越高且更窄。

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**为什么这很重要：**选择合适的列数可让您在不进行手动缩放的情况下将条形码放入特定的 UI 元素或打印标签中。

## 步骤 5：将条形码保存为 PNG 图像

最后，将生成的条形码写入磁盘。PNG 保持无损质量，这对清晰扫描至关重要。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

如果目标目录不存在，`Save` 方法会抛出 `ArgumentException`。您可以使用简单的检查来防止此情况：

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### 完整源代码

将各部分组合在一起，以下是完整的可运行程序：

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

运行此程序会生成名为 **MicroPdf417.png** 的文件，外观如下图所示（为简洁起见未显示图像）。条形码编码了文本 *Sample*，并遵循您定义的 X 维度和列设置。

## 自定义其他 PDF417 选项

虽然本指南侧重于影响尺寸的**customize pdf417 barcode**参数，Aspose.BarCode 还提供许多您可能需要的额外设置：

| 属性 | 用途 | 典型值 |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | 控制行数（高度） | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | 设置错误纠正级别（数值越高容错越强） | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | 生成截断的条形码（无停止图案） | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | 选择数字、文本或字节压缩模式 | `CompactionModes.Numeric` 等 |

**专业提示：**当您需要条形码适配固定宽度时，先增大 `Columns` 并减小 `XDimension`。如果扫描仪报告缺失符号，请提高 `ErrorLevel` 以增强冗余度。

## 处理边缘情况

* **文本过长导致 MicroPDF417 超限：**Micro 变体支持最多 1 KB 数据。如果您的字符串超出此限制，请通过将 `EncodeTypes.MicroPdf417` 改为 `EncodeTypes.Pdf417` 切换到完整的 `Pdf417` 符号。
* **不支持的图像格式：**`BarCodeImageFormat` 还支持 `Jpeg`、`Bmp` 和 `Gif`。请选择与下游处理管道匹配的格式。
* **跨平台路径：**在面向 Linux 或 macOS 时，请使用 `Path.Combine` 而不是硬编码的反斜杠。

## 验证条形码

您可以使用任何标准条形码扫描应用（移动端或桌面端）验证生成的图像。扫描器应返回原始文本 **Sample**。如果验证失败：

1. 检查 X 维度是否设置低于 1 像素（某些扫描仪无法解析亚像素模块）。
2. 确保输出文件未损坏——重新运行程序并比较文件大小。
3. 提高 `ErrorLevel` 以提升容错能力。

## 结论

现在您已经了解如何使用 Aspose.BarCode 在 C# 中**how to generate barcode**，以及如何**customize pdf417 barcode**尺寸和列数，并且能够**create barcode image C#**项目直接嵌入。完整示例展示了从项目设置到最终 PNG 输出的实用工作流。

接下来，您可以通过更换 `EncodeTypes` 枚举值来探索 QR、Code128 或 DataMatrix 等其他符号。调整 `Resolution` 或 `Margin` 等附加参数，可为您的特定应用对每个条形码进行精细调校。

祝编码愉快，让您的条形码为下一个自动化项目赋能！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [如何使用 Aspose 在 C# 中生成 PDF417 条形码图像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何使用 Aspose 创建 PDF417 条形码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [如何在 C# 中保存条形码 – 生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}