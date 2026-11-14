---
category: general
date: 2026-11-14
description: 使用 Aspose.BarCode 在 C# 中创建微型 PDF417 条码 – 步骤指南，涵盖生成器设置、X 维度、列数以及 PNG 导出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: zh
lastmod: 2026-11-14
og_description: 使用 Aspose.BarCode 在 C# 中创建微型 PDF417 条码。学习如何配置生成器、设置 XDimension、选择列数，并导出为
  PNG。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 在 C# 中创建微型 PDF417 条码 – 完整编程指南
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: 如何在 C# 中创建微型 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建微型 PDF417 条码  

如果您需要**快速创建微型 PDF417 条码**，本指南提供了一个完整、可直接运行的解决方案。您将看到如何实例化条码生成器、配置 X‑dimension、选择列数，最后将结果保存为 PNG 图像——全部使用 Aspose.BarCode for .NET 库。

生成微型 PDF417 条码并不需要复杂的构建流水线。完成本教程后，您将拥有一个单独的 C# 文件，能够生成高质量的条码图像，可嵌入报告、标签或移动应用中。

## 前置条件  

在开始之前，请确保您拥有：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7+）。  
* Visual Studio 2022、VS Code 或 Rider 等开发环境。  
* Aspose.BarCode for .NET 许可证（或免费评估密钥）。您可以从 [Aspose 网站](https://purchase.aspose.com/barcode/net) 获取。  

> **专业提示：** 如果使用评估版，生成的 PNG 将包含一个小的 “Evaluation” 水印。正式授权版会自动移除该水印。

## 第一步：设置项目  

创建一个新的控制台项目并添加 Aspose.BarCode NuGet 包。

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

`dotnet add package` 命令会自动拉取 **Aspose.BarCode C# 示例** 所需的依赖，您无需手动管理 DLL。

## 第二步：编写完整代码  

用以下代码替换自动生成的 `Program.cs`。该示例演示了如何**从头到尾创建微型 pdf417 条码**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### 每行代码的意义  

* **BarcodeGenerator 构造函数** – 使用您想要编码的文本实例化 **微型 pdf417 条码生成器**。  
* **XDimension.Pixels** – 控制模块宽度；设置为 `2` 像素可生成密集且高分辨率的条码，适用于大多数扫描仪。  
* **Pdf417.Columns** – MicroPDF417 仅支持 1‑4 列。选择 `4` 可降低条码高度，适用于垂直空间受限的场景。  
* **Save 方法** – 将条码写入 PNG 文件。PNG 为无损格式，确保扫描仪读取到您生成的精确图案。

## 第三步：构建并运行  

编译并执行程序：

```bash
dotnet run
```

您应当在控制台看到以下输出：

```
Micro PDF417 barcode saved to MicroPdf417.png
```

项目文件夹中会出现名为 **MicroPdf417.png** 的文件。使用任意图像查看器打开它，您将看到一个清晰的微型 PDF417 条码，编码的字符串为 `"Åspóse.Barcóde©"`。

![生成的微型 PDF417 条码示例](MicroPdf417.png "生成的微型 PDF417 条码示例"){.center-image width=400 alt="生成的微型 PDF417 条码图像示例"}

*上图为第 2 步代码的运行结果。*

## 第四步：常见变体和边缘情况  

| 情形 | 如何调整代码 |
|-----------|----------------------|
| **不同的数据长度** | MicroPDF417 最多可编码 1 200 个字符。只需更改 `BarcodeGenerator` 的第二个参数即可。 |
| **更高分辨率** | 将 `XDimension.Pixels` 提升至 `3` 或 `4`。更大的模块在低分辨率扫描仪上可提升可读性，但会增大图像尺寸。 |
| **自定义颜色** | 在创建生成器后，设置 `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` 并 `generator.Parameters.Barcode.BackgroundColor = Color.White;`。 |
| **保存为其他格式** | 将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Gif`，根据下游需求选择。 |
| **嵌入 PDF** | 使用 `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);`，随后可使用 Aspose.PDF 将该 PDF 与其他文档合并。 |

> **注意：** 将 `XDimension.Pixels` 设置低于 `1` 会抛出 `ArgumentOutOfRangeException`。请始终保持在 `1` 或以上。

## 第五步：验证条码  

确保条码能够正确扫描：

1. 在图像查看器中打开 PNG。  
2. 使用任何支持 PDF417 的手机条码扫描应用（大多数 “二维码扫描器” 应用都包含此功能）。  
3. 扫描图像；应用应显示原始文本 `"Åspóse.Barcóde©"`。

如果扫描失败，请再次检查 **X‑dimension** 和 **列数** 设置——模块宽度过小或列数不受支持都会导致图案不可读。

## 结论  

现在您已经掌握了如何使用 Aspose.BarCode 在 C# 中**创建微型 pdf417 条码**。本教程涵盖了：

* 实例化 **微型 pdf417 条码生成器**。  
* **设置 XDimension 像素** 以控制模块宽度。  
* **定义条码列数** 以调整形状。  
* **将条码保存为 PNG**，实现无损图像输出。  

接下来，您可以探索颜色自定义、在 PDF 中嵌入条码，或在 ASP.NET Core Web API 中实时生成条码等高级功能。祝编码愉快！


## 接下来您应该学习什么？


以下教程涵盖了与本指南技术紧密相关的主题，帮助您在实际项目中进一步运用这些技巧。每篇资源均提供完整可运行的代码示例和逐步说明，助您掌握更多 API 功能并探索替代实现方案。

- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}