---
category: general
date: 2026-10-21
description: 在 C# 中快速生成 PDF417 条形码。了解如何使用自定义布局、列、行以及 PNG 输出生成 PDF417 条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: zh
lastmod: 2026-10-21
og_description: 在 C# 中生成 pdf417 条形码。请按照本教程学习如何使用自定义列、行以及 PNG 输出生成 pdf417 条形码。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: 在 C# 中生成 PDF417 条码 – 完整分步指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: 在 C# 中使用自定义列和行生成 PDF417 条码
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中生成 pdf417 条形码 – 完整编程指南

如果您需要在 .NET 应用程序中 **生成 pdf417 条形码**，本指南将向您展示如何仅用几行代码实现。您将看到一个实际示例，配置列数和行数，然后将结果保存为 PNG 图像。相同的方法适用于任何您想要编码的文本，因此您可以将其用于发票、票据或身份证等场景。

生成 **pdf417 条形码** 往往感觉与代码库的其他部分是分离的任务。通过本教程，您将了解布局参数为何重要，如何控制图像质量，以及哪些库调用是可靠 **生成 pdf417 条形码** 所必需的。

## 您需要的环境

* .NET 6.0 SDK 或更高版本已安装  
* 支持 C# 的 IDE（Visual Studio、VS Code、Rider 等）  
* **Aspose.BarCode for .NET** NuGet 包（或任何兼容的条形码库）  

您可以使用以下命令添加该库：

```bash
dotnet add package Aspose.BarCode
```

该库提供了在本教程中贯穿使用的 `BarcodeGenerator` 类。

## 步骤 1：创建条形码生成器实例

第一行代码创建了一个能够 **生成 pdf417 条形码** 的对象。您必须指定编码类型 (`EncodeTypes.Pdf417`) 和要编码的文本。

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*此步骤的重要性* – `BarcodeGenerator` 封装了条形码的所有设置。使用正确的 `EncodeTypes` 实例化它，可让引擎使用 PDF417 符号，而不是 QR、Code128 或其他格式。

## 步骤 2：配置 PDF417 布局

PDF417 允许您控制列数和行数，这直接影响条形码的尺寸和密度。调整这些数值是使用自定义布局 **生成 pdf417 条形码** 的核心。

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*为何可能需要更改这些数值* – 更多列会降低条形码的高度，而更多行会增加宽度。请选择适合目标扫描设备和可用打印区域的数值。

> **专业提示：** 如果省略行数，库会根据数据长度自动计算最佳行数。当您需要 UI 布局的固定图像尺寸时，显式设置行数会很有用。

## 步骤 3：选择图像格式并保存文件

在配置布局后，您可以将条形码渲染为图像。下面的示例将条形码保存为 PNG 文件，但您也可以选择 JPEG、BMP 或 TIFF。

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

代码运行后，`CustomLayout.png` 将包含与您提供的列/行设置相匹配的清晰 **pdf417 条形码**。

### 预期输出

打开 `CustomLayout.png` 可看到一个矩形条形码，包含四列数据和九行。使用任何 PDF417 读取器扫描该图像会返回原始文本 **“Sample Text”**。

![生成的 PDF417 条形码示例](generated-pdf417.png){: .center-image alt="生成的 pdf417 条形码已保存为 PNG 文件"}

## 步骤 4：完整、可运行的示例

下面是一个独立的控制台应用程序示例，将所有部分组合在一起。将代码复制到新的 `.csproj` 项目中并运行——无需其他文件。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

运行程序后会打印确认信息，并在 `output` 子文件夹下创建 PNG 文件。该图像可嵌入报告、打印在标签上，或发送到移动设备进行扫描。

## 常见变体和边缘情况

| 场景 | 需要更改的内容 | 重要原因 |
|----------|----------------|----------------|
| **编码长字符串** | 增加 `Rows` 或通过省略 `Rows` 赋值让库自动计算 | PDF417 可容纳最多 1,850 个字符；行数不足会导致截断 |
| **更高的视觉质量** | 将 `generator.Parameters.ImageResolution` 设置为 600 DPI | 适用于高分辨率打印机的打印 |
| **不同的图像格式** | 将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Tiff` | JPEG 可减小文件大小；TIFF 在归档时保持无损数据 |
| **添加安静区** | `generator.Parameters.Barcode.XDimension = 2;`（或调整 `Margins`） | 安静区可提升噪声环境下扫描器的可靠性 |
| **从用户输入获取动态文本** | 将硬编码字符串替换为 `Console.ReadLine()` | 支持基于用户数据的运行时生成 |

### 如何在 Web API 中生成 pdf417 条形码

如果您需要通过 ASP.NET Core 端点提供条形码生成服务，可将图像作为字节数组返回：

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

此代码片段演示了如何即时 **生成 pdf417 条形码** 而无需写入磁盘，非常适合微服务或移动后端。

## 测试生成的条形码

验证条形码是否正确创建的方法如下：

1. 在任意图像查看器中打开 PNG 文件。  
2. 使用免费 PDF417 扫描应用（例如 ZXing、PDF417 Decoder）扫描图像。  
3. 确认解码后的文本与原始输入匹配。

如果扫描器报告错误，请再次检查列/行数值，并确保图像分辨率足够高以适配您的设备。

## 结论

现在，您已经掌握了在 C# 中 **生成 pdf417 条形码** 的方法，并能够全面控制列、行以及输出格式。完整示例展示了整个工作流——从创建 `BarcodeGenerator` 到保存 PNG 文件——因此您可以在任何 .NET 项目中集成条形码生成。

接下来，您可以探索相关主题，例如 **pdf417 条形码布局** 优化、在 PDF 报告中嵌入条形码，或在移动设备上解码条形码。调整纠错级别并尝试不同的图像分辨率，将帮助您针对特定使用场景微调解决方案。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于所示技术进行深入。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何在 C# 中生成 PDF417 条形码 – 步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中保存条形码 – 生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [如何生成 PDF417 条形码 – 完整编程指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}