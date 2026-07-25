---
category: general
date: 2026-07-24
description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 条码。了解如何在几分钟内使用紧凑模式创建 PDF417 条码（C#）。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: zh
lastmod: 2026-07-24
og_description: 使用 Aspose.BarCode 在 C# 中快速生成 PDF417 条码。本教程展示如何在紧凑模式下创建 PDF417 条码，涵盖设置、代码和验证。
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: 在 C# 中生成 PDF417 条码 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 在 C# 中生成 PDF417 条码 – 创建 PDF417 条码 C#
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中生成 PDF417 条形码 – 完整编程演练

是否曾想过如何在 C# 应用程序中**生成 PDF417 条形码**，而无需在无尽的论坛帖子中苦苦搜索？你并不是唯一有此困惑的人。无论是构建票务系统、制作安全身份证，还是仅仅需要一种快速将数据嵌入可打印格式的方式，掌握 PDF417 格式都能为你节省数小时的试错时间。

在本指南中，我们将逐步演示一个**完整、可直接运行的示例**，展示如何使用流行的 Aspose.BarCode 库**在 C# 中创建 PDF417 条形码**。我们将覆盖从安装 NuGet 包到微调紧凑模式的全部内容，让你可以复制粘贴代码并立即看到结果。

## 您将学习的内容

- 如何在 .NET 项目中设置 Aspose.BarCode 库。  
- 生成带有自定义文本、模块大小和列数的 **PDF417 条形码** 所需的精确 C# 语句。  
- 为什么切换 *Compact*（Truncate）选项对密集数据很重要。  
- 如何将条形码保存为 PNG 并验证输出。  

不需要任何条形码经验；只需对 C# 和 Visual Studio（或任何你喜欢的 IDE）有基本了解。完成后，你将拥有一个可复用的方法，能够直接嵌入任何需要 PDF417 图像的项目中。

## 前置条件

| 要求 | 原因 |
|-------------|----------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode 支持两者；更新的运行时提供更好的性能。 |
| Visual Studio 2022 (or VS Code with C# extensions) | 提供 IntelliSense 并便于调试。 |
| Internet connection (for the first NuGet restore) | 库从 NuGet.org 拉取。 |
| Basic C# knowledge | 需要了解类结构和方法调用。 |

如果你已经具备这些条件，太好了——让我们开始吧。

## 安装 Aspose.BarCode NuGet 包

在终端中打开你的项目文件夹并运行：

```bash
dotnet add package Aspose.BarCode
```

或者，在 Visual Studio 中，右键单击 **Dependencies → Manage NuGet Packages**，搜索 *Aspose.BarCode*，然后点击 **Install**。此操作会一次性引入我们将使用的所有类型，包括 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat`。

> **专业提示：** 安装后，清理并重新生成解决方案，以确保程序集被正确引用。

## 生成 PDF417 条形码 – 设置和依赖

首先，我们需要一个 `using` 块，将相关命名空间引入作用域。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

这些命名空间让我们能够访问生成器类和条形码类型的枚举。没有任何复杂操作——仅三行代码，即可开始创建条形码。

## 创建 PDF417 条形码 C# – 步骤实现

下面是一个**独立的控制台程序**，它使用字符串 `"Åspóse.Barcóde©"` 创建一个紧凑的 PDF417 条形码，并将其保存为 `CompactPdf417.png`。你可以随意替换为任何需要的文本；生成器会开箱即支持 Unicode 字符。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 为什么每一步都很重要

1. **数据定义** – PDF417 最多可存储约 1850 个字符，但我们在演示中保持简短。Unicode 支持意味着这些带重音的字符不会导致错误。  
2. **生成器构造** – `EncodeTypes.Pdf417` 枚举值告诉 Aspose 使用哪种符号；如果改为 `EncodeTypes.QR`，则会生成 QR 码。  
3. **X 维度** – 该参数控制每个模块（构成条形码的微小方块）的宽度。`2` 像素的值可生成在 300 dpi 打印时仍清晰可读的图像。  
4. **PDF417 选项** – `Columns` 影响条形码的宽高比；列数更少会使图像更高，这在收据等场景中很有用。`Truncate`（亦称 *紧凑模式*）去除起止模式的填充，在不牺牲数据完整性的前提下降低文件大小。  
5. **输出路径** – 使用 `Environment.CurrentDirectory` 可确保图像保存于可执行文件所在目录，便于开发期间定位。  
6. **保存** – `BarCodeImageFormat.Png` 提供无损质量，适合后续处理或嵌入 PDF 中。  

运行程序（`dotnet run` 或在 Visual Studio 中按 **F5**）。几秒后，你应看到控制台消息确认文件位置，PNG 文件将出现在项目文件夹中。

![Generate PDF417 barcode example](generated-pdf417.png)

*图片替代文字：生成 PDF417 条形码示例 – 使用 C# 创建的紧凑 PDF417 条形码的 PNG 图像。*

## 配置紧凑模式 – C# 条形码生成器 PDF417 选项

如果需要更大的条形码（例如远距离扫描），可以调整 `Columns` 和 `Rows` 属性。下面是一个快速代码片段，演示不同的配置方式：

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **常见问题：** *禁用 Truncate 会破坏现有扫描仪吗？*  
> 通常不会。大多数现代扫描仪都能识别全尺寸和紧凑模式的 PDF417。不过，如果你的目标是旧版硬件，建议将 `Truncate` 保持为 `false`。

## 保存并验证 – 如何生成 PDF417 条形码输出

保存后，你可以使用任意图像查看器打开 PNG。为了再次确认条形码编码了预期的数据，可使用 Aspose 的 `BarCodeReader`：



## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，帮助你在此基础上进一步学习。每个资源都提供完整的可运行代码示例和逐步解释，助你掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何使用 Aspose.BarCode 创建条形码 – 紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义宽高比的 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Java 条形码库 – 使用 Aspose 将条形码添加到 PDF](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}