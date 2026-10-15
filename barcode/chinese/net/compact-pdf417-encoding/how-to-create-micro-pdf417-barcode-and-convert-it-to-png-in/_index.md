---
category: general
date: 2026-10-12
description: 学习使用 C# 创建微型 PDF417 条码并将条码转换为 PNG。一步步指南，附完整代码和技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: zh
lastmod: 2026-10-12
og_description: 使用 C# 创建微型 PDF417 条码并将其转换为 PNG。请参考本完整指南生成标准版和 GS1 版。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 创建微型 PDF417 条码并转换为 PNG – C# 教程
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中创建微型 PDF417 条码并将其转换为 PNG
url: /zh/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建微型 PDF417 条码并将其转换为 PNG

如果您需要在 .NET 应用程序中 **创建微型 PDF417 条码**，本教程将逐步演示。您将看到一个完整、可运行的示例，生成标准微型 PDF417 条码以及符合 GS1 标准的版本，然后 **将条码转换为 PNG**，以便后续的打印或网页显示等使用。

生成条码不仅仅是调用一个方法——选择合适的模块尺寸、列数和编码格式会直接影响扫描的可靠性。阅读完本指南后，您将了解每个设置为何重要，以及如何为自己的项目进行调整。

## 前置条件

在开始之前，请确保您具备以下条件：

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK 或更高版本 | 为 C# 控制台应用提供运行时 |
| Visual Studio 2022（或任意 C# IDE） | 便于编辑和调试 |
| **Aspose.BarCode for .NET** NuGet 包 | 提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 类 |
| 对输出文件夹的写入权限 | `Save` 调用需要在该文件夹创建 PNG 文件 |

您可以通过 CLI 添加 Aspose.BarCode 包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：创建最小化的控制台项目

新建一个控制台项目并引用条码库。下面的 `Program.cs` 包含所有必要代码，无需外部文件。

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### 为什么每行代码都很重要

* **`EncodeTypes.MicroPdf417` 与 `EncodeTypes.Gs1MicroPdf417`** – 前者生成普通微型 PDF417 条码，后者遵循 GS1 标准，嵌入应用标识符（AIs）。根据下游系统是否需要 GS1 数据进行选择。
* **`XDimension.Pixels = 2`** – 控制模块宽度。数值越小图像越密集，但在低分辨率扫描仪上可能难以读取。两像素是大多数标签打印机的安全默认值。
* **`Pdf417.Columns = 4`** – 微型 PDF417 允许限制列数，从而降低整体宽度。四列在保持短负载数据容量的同时，使条码保持紧凑。
* **`BarCodeImageFormat.Png`** – PNG 保持无损质量，对条码清晰度至关重要。这也是我们 **将条码转换为 PNG** 而非 JPEG 的原因。

## 步骤 2：运行程序并验证输出

1. 构建项目：`dotnet build`。  
2. 执行：`dotnet run`。

您应在控制台看到类似以下的消息：

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

使用任意图像查看器打开生成的 PNG 文件。两张图片均显示清晰、高对比度的条码，已准备好进行扫描。

### 预期的视觉效果

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | 具有 4 列的矩形小图案，可被大多数 2‑D 条码扫描仪读取。 |
| **GS1 Micro PDF417** | 大小相同，但编码了 GS1 AI；支持 GS1 的扫描仪将返回 GTIN 和序列号等信息。 |

如果扫描仪无法读取图像，请尝试将 `XDimension.Pixels` 提高到 **3** 或 **4**，或将标准微型 PDF417 的列数调低。

## 常见陷阱及规避方法

| Issue | Cause | Fix |
|-------|-------|-----|
| 打印后条码模糊 | 打印机 DPI 设置过低 | 将 PNG 导出为 300 dpi 或更高，或让打印机驱动自行处理缩放。 |
| 扫描仪返回 “invalid data” | 缺少或格式错误的 GS1 AI | 确保每个 AI 都用括号包裹，并遵循 GS1 规范（例如 `(01)` 表示 GTIN‑14）。 |
| 未生成图像文件 | 输出文件夹没有写入权限 | 以提升的权限运行程序，或选择如 `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)` 之类的文件夹。 |
| 条码尺寸超出标签 | 默认列数过高 | 将 `Pdf417.Columns` 降低（例如 **3**），或增大 `XDimension` 以缩小整体尺寸。 |

## 扩展示例

* **不同的图像格式** – 如需其他格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Bmp`。PNG 仍是无损质量的最佳选择。
* **动态数据** – 将用户输入或数据库值传递给 `BarcodeGenerator` 构造函数，以实现即时生成条码。
* **批量生成** – 将创建逻辑封装在循环中，从 CSV 文件读取行并为每个条码保存唯一文件名。

## 结论

现在，您已经掌握了在 C# 中 **创建微型 PDF417 条码** 并 **将条码转换为 PNG** 的完整流程，涵盖标准和符合 GS1 的两种场景。完整、可运行的代码演示了关键设置——X 维度、列数以及编码类型——帮助您在任何需要紧凑、高质量 2‑D 条码的 .NET 项目中灵活应用。

*下一步*：探索 Aspose.BarCode 支持的其他符号（如 QR、DataMatrix），尝试不同的 `XDimension` 值以实现高分辨率打印，或将生成的 PNG 集成到提供按需条码的 Web API 中。

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中创建微型 pdf417 条码并保存为 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [在 C# 中创建条码 PNG – GS1 微型 PDF417 完整指南](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [在 C# 中生成微型 PDF417 条码 – 完整指南](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}