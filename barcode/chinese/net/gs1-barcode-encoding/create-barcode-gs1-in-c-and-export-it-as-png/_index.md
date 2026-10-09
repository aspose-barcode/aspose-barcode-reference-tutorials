---
category: general
date: 2026-09-29
description: 在 C# 中创建 GS1 条码并使用 BarcodeGenerator 生成条码 PNG 图像。按照分步指南高效导出条码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: zh
lastmod: 2026-09-29
og_description: 使用 C# 创建 GS1 条码并使用 BarcodeGenerator 生成条码 PNG 文件。遵循本完整指南，快速导出条码图像。
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: 在 C# 中创建 GS1 条码 – 几分钟内导出为 PNG
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: 在 C# 中创建 GS1 条形码并导出为 PNG
url: /zh/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 GS1 条形码并导出为 PNG

如果你需要在 .NET 应用程序中 **创建 GS1 条形码**，本指南将一步步展示如何实现。你将看到一个简洁的解决方案，使用 Aspose.BarCode 的 `BarcodeGenerator` 类生成条形码 PNG 图像并将其导出到磁盘。

生成 GS1 条形码是库存、运输和销售点系统的常见需求。完成本教程后，你将能够编写一个小型 C# 程序，创建符合 GS1 标准的 MicroPDF417 条形码并保存为高质量的 PNG 文件。

## 前置条件

在开始之前，请确保你已具备：

* **.NET 6**（或更高版本）已安装。  
* **Visual Studio 2022** 或任何支持 C# 的 IDE。  
* **Aspose.BarCode for .NET** NuGet 包（`Aspose.BarCode`）——它提供了示例中使用的 `BarcodeGenerator` API。  
* 对 C# 语法有基本了解。

> **小贴士：** 在实验时使用 Aspose.BarCode 的免费社区版；完整版会去除评估水印。

## 第一步 – 使用 BarcodeGenerator 创建 GS1 条形码

首先，需要实例化用于 *MicroPDF417* 格式的 `BarcodeGenerator`，并为其提供 GS1 数据字符串。GS1 应用标识符（AI）需用括号包裹，例如 GTIN‑14 使用 `(01)`，序列号使用 `(21)`。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**为什么重要：**  
`EncodeTypes.MicroPdf417` 在字符串包含有效 AI 时会自动将输入视为 GS1 数据。这确保生成的条形码符合 GS1 规范，无需额外配置。

## 第二步 – 为最佳尺寸设置条形码尺寸

条形码的视觉大小由 **X‑dimension**（单个模块的宽度）控制。调整 `XDimension.Pixels` 可以在保持可读性的前提下微调最终图像尺寸。

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **如何生成条形码 PNG** – X‑dimension 不影响编码的数据，仅改变生成图像的物理尺寸。如果需要更大的条形码用于高分辨率打印，可增大此值（例如 `3` 或 `4`）。

## 第三步 – 生成条形码 PNG 并导出条形码图像

现在可以渲染条形码并写入 PNG 文件。`Save` 方法接受目标路径和所需的图像格式。

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**内部工作原理：**  
`BarcodeGenerator.Save` 将条形码光栅化为位图，应用前面设置的 X‑dimension，并将位图编码为 PNG 文件。生成的文件可直接用于网页、标签打印或嵌入 PDF。

## 完整源代码示例

下面是一个完整的、独立的控制台应用程序示例，你可以复制、粘贴并运行。它演示了 **如何生成条形码 PNG**、**导出条形码图像**，并包含基本的错误处理。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### 预期输出

运行程序后，你应该看到：

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

打开 PNG 文件会显示清晰的 **GS1 MicroPDF417** 条形码，编码了 GTIN‑14 `12345678901234` 和序列号 `ABC123`。使用任何兼容 GS1 的扫描器扫描，都将返回原始数据字符串。

## 常见陷阱与最佳实践

| 问题 | 产生原因 | 如何避免 |
|------|----------|----------|
| **AI 格式不正确** | 缺少括号或顺序错误导致条形码非 GS1。 | 始终为每个 AI 加上括号，例如 `(01)`。 |
| **X‑dimension 过小** | 条形码在低分辨率设备上难以读取。 | 对大多数打印机保持 `XDimension.Pixels` ≥ 2；对高 DPI 输出适当增大。 |
| **输出文件夹不存在** | `Save` 抛出 `DirectoryNotFoundException`。 | 在调用 `Save` 前使用 `Directory.CreateDirectory` 创建目录。 |
| **使用了错误的 EncodeType** | 某些类型（如 `Code128`）默认不支持 GS1 数据。 | 选择 `EncodeTypes.MicroPdf417` 或其他兼容 GS1 的类型。 |
| **缺少 NuGet 引用** | 编译时出现 `The type or namespace name 'Aspose' could not be found` 等错误。 | 通过 NuGet 安装 `Aspose.BarCode` 包。 |

## 扩展示例

* **不同的图像格式** – 如需其他格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Gif` 或 `Bmp`。  
* **更高分辨率输出** – 在保存前设置 `generator.Parameters.ImageResolution.DpiX` 与 `DpiY`。  
* **嵌入 PDF** – 使用 `Aspose.Pdf` 将 PNG 放入 PDF 发票或标签中。

## 结论

现在，你已经掌握了如何在 C# 中使用 Aspose.BarCode 的 `BarcodeGenerator` **创建 GS1 条形码**、**生成条形码 PNG**，并 **导出条形码图像** 到文件系统。本指南覆盖了从使用 GS1 数据初始化生成器、调整 X‑dimension，到保存最终 PNG 文件的每一步，并提供了常见错误的解决方案和扩展思路。

欢迎尝试其他 GS1 应用标识符、不同的条形码符号或更高分辨率的图像。掌握这些基础后，生成符合库存、运输或零售需求的合规条形码将成为你的 .NET 工具箱中的常规操作。

## 接下来你应该学习什么？

以下教程与本指南紧密相关，进一步扩展所示技术。每篇资源都包含完整的可运行代码示例和逐步解释，帮助你掌握更多 API 功能并在项目中探索替代实现方式。

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}