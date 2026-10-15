---
category: general
date: 2026-10-12
description: 如何快速在 C# 中生成条形码。学习创建空白条形码并自定义条宽，以获得清晰的邮政条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: zh
lastmod: 2026-10-12
og_description: 如何使用 Aspose.BarCode 在 C# 中生成条形码。本指南向您展示如何创建空条形码并调整条码尺寸以符合邮政标准。
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: 如何在 C# 中生成条形码图像——一步步指南
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何使用 Aspose.BarCode 在 C# 中生成条形码图像
url: /zh/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中生成条形码图像

如果您需要 **如何生成条形码** 图像（从字符串生成）在 .NET 应用程序中，本指南提供了完整、可直接运行的解决方案。您将看到如何生成标准的 Planet 和 RM4SCC 条形码，调整条宽以提升可读性，以及 **创建空白条形码**（条纹未填充）变体。代码适用于最新的 Aspose.BarCode for .NET（v.24.10），并可在 .NET 6 或更高版本上运行。

生成条形码是运输标签、库存系统和票务平台的常见需求。完成本教程后，您将能够以编程方式生成实心和空白条形码，而无需外部工具。

## 前提条件

在开始之前，请确保您拥有：

* .NET 6 SDK（或任意更新的 .NET 版本）
* Visual Studio 2022 或 VS Code
* 有效的 Aspose.BarCode for .NET 许可证（免费评估版可用于测试）
* 对 C# 控制台应用程序的基本了解

您可以使用以下方式安装 Aspose.BarCode NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：创建最小化的控制台项目

新建一个控制台项目并添加所需的 `using` 指令。下面的代码是一个自包含示例；将其复制到 `Program.cs` 并运行即可。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### 为什么这一步很重要

* **项目脚手架** 确保教程可以在无需额外配置的情况下运行。
* `using Aspose.BarCode.Generation;` 和 `using Aspose.BarCode;` 命名空间公开了 `BarcodeGenerator` 类和图像格式。
* 通过代码创建输出文件夹可避免首次运行时出现 “目录未找到” 错误。

## 第二步：生成实心 Planet 条形码

第一次调用 `GeneratePlanetBarcode` 时传入 `filled: true`。这会生成标准的 Planet 条形码，每根条纹都渲染为实心的黑色矩形。

* **生成的文件：** `PostalPlanetFilledBars.png`
* **视觉提示：** 条纹为黑色，符合邮政印刷规范。

### 预期输出

运行程序后会创建如下图所示的图像（此处不显示实际图像，但打开文件后您会看到清晰的 6 位条形码）。

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## 第三步：创建空白条形码（Planet 未填充的条纹）

要 **创建空白条形码**，只需将同一方法的 `filled` 参数设为 `false`。`FilledBars` 属性告诉 Aspose.BarCode 只绘制条纹的轮廓，内部保持透明。

* **生成的文件：** `PostalPlanetEmptyBars.png`
* **使用场景：** 当您希望背景显示徽标或颜色，同时仍保持条形码可读性时，空白条形码非常有用。

### 预期输出

生成的 PNG 仅包含条纹轮廓：

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## 第四步：生成实心 RM4SCC 条形码

RM4SCC 是荷兰邮政条形码标准。示例使用相同的 X 维度（4 像素），以保持与 Planet 条形码的视觉一致性。

* **生成的文件：** `PostalRM4SCCFilledBars.png`
* **为何选择 RM4SCC？** 它以紧凑的格式编码数字，受到许多欧洲邮政服务的接受。

### 预期输出

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## 实用技巧与常见陷阱

| 提示 | 说明 |
|-----|------|
| **保持一致的 X 维度** | 在不同的符号体系中使用相同的 `XDimension.Pixels` 值，可确保打印标签外观统一。 |
| **不要复用同一个生成器实例** | 在已有的生成器上更改 `FilledBars` 可能产生意外结果；对每个不同的条形码请实例化新的 `BarcodeGenerator`。 |
| **验证图像格式** | PNG 为无损格式，最适合条形码；JPEG 的压缩可能导致细条模糊，进而扫描失败。 |
| **许可证处理** | 若未使用许可证运行代码，生成的图像会带有水印。请在 `Main` 方法开头尽早添加如下代码：`License license = new License(); license.SetLicense("Aspose.BarCode.lic");` |
| **线程安全** | `BarcodeGenerator` **不**是线程安全的。若在并行生成条形码，请为每个线程创建独立实例。 |

## 可能遇到的边缘情况

* **数据长度限制** – Planet 条形码最多接受 6 位数字字符。输入超出长度会抛出 `ArgumentException`。请在调用生成器前验证输入长度。 |
* **非数字数据** – RM4SCC 也要求数字输入。若需处理字母数字数据，请使用其他符号体系（如 Code128）。`FilledBars` 的设置方式对任何支持该属性的条形码类型均适用。 |
* **高分辨率打印** – 若需要比屏幕显示更大的条形码，可增大 `XDimension.Pixels`（例如 8 或 10），并可在 `generator.Parameters.Image` 中设置 `Resolution`。这可在 300 dpi 打印时保持条纹清晰。 |

## 完整源码回顾

下面再次提供完整源码，方便快速复制粘贴。代码包含所有步骤、注释以及可选的许可证片段（已注释掉）。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## 结论

您现在已经掌握了 **如何在 C# 中使用 Aspose.BarCode 生成条形码图像**，并且可以通过切换 `FilledBars` 属性 **创建空白条形码** 变体。教程涵盖了：

* 设置控制台项目并安装 Aspose.BarCode 包
* 生成实心 Planet 与 RM4SCC 条形码
* 生成仅轮廓的 Planet 空白条形码
* 调整条宽以提升可读性并处理常见陷阱

接下来，您可以探索其他符号体系（Code128、QR、DataMatrix），并尝试颜色、尺寸和图像格式的自定义。将条形码生成集成到 Web API 或 Windows 服务中，只需将控制台的 `Main` 方法替换为您应用的入口点即可，模式相同。

祝编码愉快，让您的应用开始扫描吧！

## 接下来您应该学习什么？

以下教程与本指南紧密相关，基于本教程展示的技术进一步扩展。每篇资源都包含完整可运行的代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中尝试不同实现方式。

- [如何使用 Aspose.BarCode 在 C# 中创建邮政条形码图像](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [如何在 C# 中使用自定义尺寸生成邮政条形码](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [如何在 C# 中使用 Aspose.BarCode 生成条形码图像](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}