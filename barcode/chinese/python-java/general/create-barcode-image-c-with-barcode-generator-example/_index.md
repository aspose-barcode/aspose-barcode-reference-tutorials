---
category: general
date: 2026-09-10
description: 使用条码生成器示例 C# 快速创建条码图像，演示如何设置尺寸并保存为 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: zh
lastmod: 2026-09-10
og_description: 使用简洁的 C# 条码生成器示例创建条码图像，学习在几分钟内配置尺寸、高度并导出 PNG 文件。
og_image_alt: Screenshot of a barcode image created with C# code
og_title: 使用 C# 创建条形码图像 – 步骤式生成示例
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 使用条码生成器示例在 C# 中创建条码图像
url: /zh/python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用条码生成器示例创建条码图像 C#

如果您需要 **create barcode image C#** 用于产品标签、库存跟踪或移动扫描，本指南提供完整的解决方案。您将看到一个 **barcode generator example C#**，它配置模块宽度、条码高度，并仅用几行代码保存 PNG 文件。

本教程涵盖了从安装所需库到运行可直接编译的控制台程序的全部步骤。完成后，您将拥有两个条码 PNG 文件——一个条码高度为 30 像素，另一个为 60 像素——可在任何 .NET 应用程序中使用。

## 前置条件

在开始之前，请确保您具备以下条件：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022 或 VS Code 等开发环境  
* **Aspose.BarCode** NuGet 包（代码使用该库中的 `BarcodeGenerator`）  

您可以使用以下 CLI 命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：设置控制台项目

创建一个新的控制台项目并引用条码库。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

该命令会生成一个 `Program.cs` 文件，您将在其中放置 **barcode generator example C#** 代码。

## 第二步：编写完整的条码生成程序

将 `Program.cs` 的内容替换为下面完整且可运行的示例。该程序演示了如何使用自定义尺寸 **create barcode image C#** 并将结果保存为 PNG 文件。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 每行代码的意义

* **EncodeTypes.DatabarOmniDirectional** – 选择 DataBar Omnidirectional 符号集，可编码数字数据，广泛用于零售。  
* **XDimension.Pixels = 2** – 设置模块宽度；数值越小，条码越紧凑。  
* **BarHeight.Pixels** – 控制条码的可视高度。调整该值可让条码适配不同标签尺寸。  
* **Save 方法** – 将条码写入 PNG 文件，该格式保留锐利边缘并兼容大多数图像库。

## 第三步：构建并运行程序

在项目文件夹中执行以下命令：

```bash
dotnet run
```

程序完成后，您将在 `output` 子文件夹中看到两个 PNG 文件：

* `DatabarBarHeight30Pixels.png` – 条码高度为 30 像素  
* `DatabarBarHeight60Pixels.png` – 条码高度为 60 像素  

两个图像编码相同的数据，但在视觉高度上不同，展示了 **barcode generator example C#** 如何根据不同标签需求进行调整。

## 第四步：验证生成的条码

使用任意图像查看器打开 PNG 文件。您应该能看到清晰、高对比度的 DataBar 条码。为确认条码可读，可使用移动扫描应用（如基于 ZXing 的应用）或桌面库 **Aspose.BarCode** 的解码模式：

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

如果输出与 `(01)12345678901231` 相匹配，则生成成功。

## 常见变体和边缘情况

| 情况 | 调整 | 代码片段 |
|-----------|------------|--------------|
| **不同的符号**（例如 QR、Code128） | 更改 `EncodeTypes` 值 | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **自定义图像格式**（JPEG、BMP） | 使用不同的 `BarCodeImageFormat` 枚举 | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **动态数据**（用户输入） | 将硬编码字符串替换为变量 | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **无效的数据长度** | 捕获生成器抛出的 `ArgumentException` | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

技巧提示：始终验证所选符号集的输入长度；如果数据不符合规范，Aspose.BarCode 会抛出异常。

## 故障排查清单

* **Directory not found** – `SaveBarcode` 辅助方法会自动创建 `output` 文件夹，但请确保应用程序拥有写入权限。  
* **Unexpected image size** – 在调用 `Save` 之前确认已设置 `XDimension.Pixels` 和 `BarHeight.Pixels`。保存后再更改这些值不会影响已写入的文件。  
* **Unreadable barcode** – 使用 DataBar 符号时，请确保编码字符串符合 GS1 格式。缺少括号或应用标识符错误会导致解码失败。

## 结论

您现在已经掌握了使用实用的 **barcode generator example C#** 来 **create barcode image C#** 的方法。完整程序仅用最少代码即可设置模块宽度、调整条码高度并保存 PNG 文件。接下来，您可以探索颜色自定义、多页 PDF 导出或在 ASP.NET Core Web API 中实现实时生成等高级功能。

**Next steps**

* 试验其他符号集（`EncodeTypes.Code128`、`EncodeTypes.QR`），以扩展扫描选项。  
* 将生成器集成到按需返回条码图像的 Web 服务中。  
* 使用 Aspose.PDF 将条码与产品元数据合并到 PDF 发票中。

祝编码愉快，尽情享受 C# 在条码图像创建方面的灵活性！

## 接下来您应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步提升。每个资源都提供完整可运行的代码示例，并配有逐步解释，助您掌握更多 API 功能并在项目中探索替代实现方案。

- [C# 条码生成器示例 – 设置列、行并导出图像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [创建条码图像 C# – GS1 DataMatrix 示例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [条码生成器示例 – 在 C# 中构建 DataBar 图像](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}