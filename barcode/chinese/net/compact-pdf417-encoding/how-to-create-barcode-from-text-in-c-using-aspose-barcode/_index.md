---
category: general
date: 2026-10-28
description: 使用 Aspose.BarCode 在 C# 中从文本创建条形码。学习生成 PDF417 条形码图像、设置列数、调整 X 维度以及启用紧凑模式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: zh
lastmod: 2026-10-28
og_description: 使用 Aspose.BarCode 在 C# 中从文本创建条形码。本教程展示如何生成 PDF417 条形码图像，定制尺寸、列数和紧凑模式。
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: 在 C# 中从文本创建条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: 如何使用 Aspose.BarCode 在 C# 中从文本创建条形码
url: /zh/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 从文本创建条形码

如果您需要在 .NET 应用程序中 **从文本创建条形码**，本指南提供了一个可直接运行的解决方案。您将看到如何 **生成 PDF417 条形码** 图像、控制模块宽度、列数，并在不离开 IDE 的情况下启用紧凑模式。

本教程涵盖了生成 **barcode C#** 代码所需的全部内容，从库安装到保存最终的 PNG 文件。完成后，您可以在报表、票据或库存标签中嵌入高密度的 PDF417 条形码。

## 前置条件

开始之前，请确保您具备以下条件：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的编辑器）  
* 可访问互联网以下载 Aspose.BarCode for .NET NuGet 包  

这些条件足以在 Windows、Linux 或 macOS 上编译并运行示例。

## 第一步：安装 Aspose.BarCode NuGet 包

提供条形码生成功能的库是 **Aspose.BarCode for .NET**。使用 .NET CLI 安装：

```bash
dotnet add package Aspose.BarCode
```

该包会添加 `Aspose.BarCode` 命名空间，其中包含本教程中使用的 `BarcodeGenerator` 类。

## 第二步：创建控制台项目并添加代码

新建一个控制台项目，并用以下代码替换生成的 `Program.cs`。该程序演示了如何 **从文本创建条形码** 并将其保存为 **PDF417 条形码图像**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### 每行代码的意义

* **`EncodeTypes.Pdf417`** 选择 PDF417 符号集，适用于在二维格式中编码大量数据。  
* **`XDimension.Pixels = 2`** 减小模块宽度，使条形码更密集，更适合空间受限的场景。  
* **`Pdf417.Columns = 3`** 控制垂直数据列数；列数较少会得到更高但更窄的条形码。  
* **`Pdf417.Truncate = true`** 启用紧凑模式，裁剪右侧未使用的列。这是将普通 PDF417 转换为 **紧凑 PDF417 条形码图像** 的关键设置。  

## 第三步：构建并运行项目

在项目目录下执行以下命令：

```bash
dotnet build
dotnet run
```

程序执行完毕后，您会在控制台看到确认文件位置的消息。使用任意图像查看器打开 `CompactPdf417.png`，即可验证结果。

**预期输出** – 一个高对比度的 PNG，显示紧凑的 PDF417 条形码，编码字符串为 `Åspóse.Barcóde©`。使用标准条形码阅读器扫描该图像会返回原始文本，证明 **generate pdf417 barcode** 成功。

## 第四步：为不同场景自定义条形码

虽然示例使用了固定的列数和 X‑dimension，您仍可根据需求调整生成器：

| 场景 | 调整方式 |
|----------|------------|
| 更大的数据负载 | 增加 `Pdf417.Columns` 或手动设置 `Pdf417.Rows` |
| 更高的扫描可靠性 | 将 `XDimension.Pixels` 提升至 3 或 4 |
| 不同的图像格式 | 将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Bmp` |
| 透明背景 | 设置 `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

这些选项帮助您 **generate barcode C#**，以适配移动应用、桌面报表或 Web 服务等不同部署场景。

## 第五步：处理边缘情况和最佳实践

* **Unicode 支持** – 生成器会自动编码 Unicode 字符，但如果从文件读取，请确保源字符串为 UTF‑8 编码。  
* **大文本** – PDF417 最多可编码 1,850 个字母数字字符。超出此限制时，库会抛出异常；请将数据拆分为多个条形码或改用容量更大的符号集。  
* **错误处理** – 将生成代码放在 `try/catch` 块中，捕获 `BarCodeException` 并提供友好的错误信息。  
* **性能** – 在循环中生成大量条形码时，复用同一个 `BarcodeGenerator` 实例并仅在迭代间更新 `CodeText`，可提升效率。

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## 完整源码列表

以下是完整的、可直接复制到 `Program.cs` 的程序。无需其他文件。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

运行此程序会生成下图所示的 **pdf417 条形码图像**。

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="使用 C# 从文本创建的紧凑 PDF417 条形码"}

*图片说明：该 PNG 文件显示一个紧凑的 PDF417 条形码，编码字符串为 “Åspóse.Barcóde©”。*  

## 结论

现在您已经掌握了如何在 C# 中 **从文本创建条形码**，并生成带有自定义尺寸和紧凑模式的 **PDF417 条形码图像**。示例演示了实现 **generate barcode C#** 的关键步骤、Unicode 数据处理以及针对不同部署场景的视觉参数调整。

接下来，您可以进一步探索 **generate QR code in C#**、**add barcode to PDF documents** 或 **embed barcodes in ASP.NET Core APIs** 等相关主题。它们都基于本指南中介绍的 `BarcodeGenerator` 基础。

祝编码愉快，尽情将条形码集成到您的 .NET 解决方案中！


## 接下来您应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，每篇资源都提供完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方式。

- [Generate PDF417 Barcode in C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [How to generate PDF417 barcode with Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}