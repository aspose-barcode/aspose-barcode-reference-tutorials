---
category: general
date: 2026-09-19
description: 条形码生成器示例，展示如何更改高度、创建 DataBar Omni‑Directional 条码，以及调整 C# 图像输出的条码尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: zh
lastmod: 2026-09-19
og_description: 条形码生成器示例，教授如何更改高度、创建 DataBar 全方向（Omni‑Directional）以及调整 C# PNG 图像的条形码尺寸
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: C# 条形码生成器示例 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中构建条形码生成器示例
url: /zh/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 条形码生成器示例 – 完整编程指南

如果您需要一个 .NET 项目的 **barcode generator example**，本指南将准确展示如何使用 C# 创建、配置并保存 DataBar Omni‑Directional 条码。您将学习如何更改高度、调整条码尺寸以及输出高质量的 PNG 图像——全部在一个可运行的控制台应用程序中。

下面的步骤涵盖了从安装所需 SDK 到微调 X‑dimension 和条码高度的全部内容。教程结束时，您将拥有一个可直接用于发票、库存或任何扫描工作流的条码生成器。

## 前提条件

在开始之前，请确保您拥有：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* 有效的 **Aspose.BarCode for .NET** 许可证（免费试用可用于测试）  

如果您更倾向于使用其他库，调整尺寸和保存图像的概念保持不变，只需相应替换 API 调用即可。

## Step 1: Set up the project and add the Aspose.BarCode package

创建一个新的控制台项目并引用条码库。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet add package` 命令会拉取最新的稳定版 Aspose.BarCode，其中已完整支持 DataBar Omni‑Directional 符号。

## Step 2: Write the complete barcode generator example

打开 **Program.cs** 并将其内容替换为以下代码。此代码块包含完整的 **barcode generator example**——没有缺失的部分。

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 为什么每行代码都很重要

* **Create a barcode generator** – `BarcodeGenerator` 构造函数将编码类型 (`EncodeTypes.DatabarOmniDirectional`) 与您想要嵌入的数据关联。这是 **how to create databar** 步骤的核心。  
* **Adjust barcode dimensions** – `XDimension.Pixels` 属性定义最窄条的宽度。更改此值会影响整体尺寸和扫描可靠性。  
* **How to change height** – `BarHeight.Pixels` 属性控制垂直尺寸。增加高度可提升手持扫描器的可读性，降低高度则可在小标签上节省空间。  
* **Optional tweaks** – 设置前景/背景颜色或错误纠正级别是可选的，但演示了如何扩展 **adjust barcode dimensions** 概念。  
* **Create barcode image C#** – `Save` 方法将条码写入磁盘。使用 `BarCodeImageFormat.Png` 可确保无损压缩，适用于大多数应用场景。

## Step 3: Build and run the example

编译并执行程序：

```bash
dotnet run
```

您应该会看到控制台输出：

```
Barcode saved to DatabarOmniDirectional.png
```

项目文件夹中会出现名为 **DatabarOmniDirectional.png** 的文件。打开该图像即可看到清晰的 DataBar Omni‑Directional 条码，已准备好进行扫描。

## How to change height after the fact

如果需要生成不同高度的条码，请将高度赋值封装在方法中：

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

在 `Save` 之前调用 `SetBarHeight(generator, 45);`。此方式可让您 **how to change height** 根据用户输入或配置文件动态调整。

## How to create DataBar Omni‑Directional barcodes with different data

DataBar Omni‑Directional 符号支持 GTIN‑14、GTIN‑13 等数值标识符。要编码不同的值，只需在构造函数中替换字符串：

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

请确保数据为数值且格式正确；否则生成器会抛出 `BarcodeException`。

## Adjust barcode dimensions for different printing scenarios

不同的打印机和标签尺寸需要不同的 X‑dimension 和高度。以下表格可作为快速参考：

| 场景                     | X 维度（像素） | 条码高度（像素） |
|--------------------------|----------------|------------------|
| 小标签 (25 mm × 15 mm)   | 1              | 20               |
| 中标签 (50 mm × 30 mm)   | 2              | 30               |
| 大标签 (100 mm × 50 mm)  | 3              | 45               |

通过设置 `generator.Parameters.Barcode.XDimension.Pixels` 和 `BarHeight.Pixels` 来应用这些数值。

## Pro tip: validate the generated barcode

在发货前，您可以通过代码验证条码的可读性：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

此代码片段演示了一个快速的 **adjust barcode dimensions** 完整性检查，确保条码满足扫描要求。

## Common pitfalls and how to avoid them

| 常见问题                              | 产生原因                                 | 解决方案                                                                 |
|--------------------------------------|------------------------------------------|-------------------------------------------------------------------------|
| 使用非数值数据生成 DataBar            | DataBar 需要数值 GTIN 格式                | 确保字符串符合 `(01)XXXXXXXXXXXXX` 模式。                               |
| 将 X‑dimension 设置为 0 或负数        | 库会抛出 `ArgumentOutOfRangeException`   | 使用最小 1 像素；先在目标打印机上进行测试。                             |
| 保存到只读文件夹                      | `Save` 时出现 `UnauthorizedAccessException` | 选择可写目录或以适当权限运行应用程序。                                   |
| 忘记释放 `BarCodeReader`              | 长期运行服务会导致内存泄漏                | 将读取器放在 `using` 块中，或手动调用 `Dispose()`。                     |

提前处理这些问题可节省调试时间并提升生产环境的稳定性。

## Full source code recap

下面是完整的、可直接复制的程序，实现了从头到尾的 **barcode generator example**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

运行此程序会生成如下所示的 PNG 文件（示意）：

![C# 生成的 DataBar Omni‑Directional 条码](https://example.com/og-image.png "C# 生成的 DataBar Omni‑Directional 条码")

*图片替代文字*：**DataBar Omni‑Directional barcode generated in C#**（匹配 `og_image_alt`）。

## Conclusion

您现在拥有一个 **barcode generator example**，演示了如何更改高度、如何创建 DataBar Omni‑Directional 符号，以及如何 **adjust barcode dimensions** 以获得最佳扫描效果。完整的 C# 代码可保存 PNG 图像、进行验证，并可扩展用于批量生成或集成到 Web 服务中。

接下来，您可以探索以下相关主题，如 **使用 Aspose.BarCode 创建 QR 码**、**批量处理多个条码值**，或 **将条码嵌入 PDF 文档**。这些内容都基于本指南中讲解的基础。

祝编码愉快，愿您的条码始终可被扫描！

## What Should You Learn Next?

以下教程涵盖了与本指南技术紧密相关的主题，每篇都提供完整可运行的代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中尝试不同实现方式。

- [条形码生成器示例 – 在 C# 中构建 DataBar 图像](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [如何使用 Aspose.BarCode for .NET 生成并调整一维 Databar 条码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [C# 条形码生成器示例 – 设置宽度和高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}