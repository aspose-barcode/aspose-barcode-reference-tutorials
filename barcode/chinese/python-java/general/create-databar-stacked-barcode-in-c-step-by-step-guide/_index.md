---
category: general
date: 2026-08-06
description: 在 C# 中快速创建 DataBar 堆叠条码。学习设置 X 维度、调整宽高比，并使用 DataBar 堆叠全向生成器导出 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: zh
lastmod: 2026-08-06
og_description: 使用 Aspose.BarCode 在 C# 中创建堆叠式数据条码。本教程展示如何配置 X 维度、改变宽高比以及保存 PNG 图像。
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: 在 C# 中创建 DataBar 堆叠条形码 – 完整编程指南
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 在 C# 中创建 Databar 堆叠条码 – 步骤指南
url: /zh/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 databar stacked barcode – 步骤指南

如果您需要在 C# 中**创建 databar stacked barcode**图像，本指南将向您展示如何使用 Aspose.BarCode 库完成此操作。您将学习设置 X 维度、修改条形码宽高比，并将结果保存为 PNG 文件——全部只需几个简洁的步骤。

在需要为零售扫描或物流跟踪编码 GS1‑128 数据时，生成 DataBar Stacked 条形码是常见需求。以下章节将从项目设置到验证输出全部覆盖，帮助您将该解决方案无缝集成到任何 .NET 应用程序中，细节不遗漏。

## 前置条件

* **.NET 6.0**（或更高）已安装 – 代码面向现代 SDK。
* 已获取 **Aspose.BarCode for .NET** 的**授权**副本。免费评估版可用于测试，但会添加水印。
* 采用 **Visual Studio 2022** 或 **VS Code**（配合 C# 扩展）的 IDE。
* 对 **C#** 语法以及 GS1 应用标识符概念有基本了解。

> **专业提示：** 如果使用 NuGet 包管理器，命令 `dotnet add package Aspose.BarCode` 会自动解析所有依赖。

## 步骤 1：创建新控制台项目

在终端或 Package Manager Console 中打开并运行：

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 命令会生成一个最小的 **Program.cs** 文件。添加 **Aspose.BarCode** 包后即可使用 `BarcodeGenerator` 类。

## 步骤 2：初始化 DataBar Stacked Omnidirectional 生成器

打开 **Program.cs**，将默认内容替换为以下代码。第一行创建了一个针对 **DataBar Stacked Omnidirectional** 符号并提供 GS1‑128 负载的 **BarcodeGenerator**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**为什么重要：** `EncodeTypes.DatabarStackedOmniDirectional` 枚举值指示库生成 **databar stacked barcode**，即全向 DataBar 系列的堆叠变体。该符号最多可容纳 14 位数字，非常适合 GTIN‑14 代码。

## 步骤 3：设置 X 维度（模块宽度）

X 维度决定最小条（模块）的宽度。数值过小可能在低分辨率打印机上呈现不佳，数值过大则可能超出标签空间。

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **提示：** `Pixels` 属性便于基于屏幕的测试。针对打印场景，请改用 `generator.Parameters.Barcode.XDimension.Millimeters`。

## 步骤 4：调整宽高比并保存第一张图像

**宽高比**影响堆叠条形码的高宽比例。DataBar Stacked Omnidirectional 类型支持 10 到 30 的比例范围。我们将生成两张图像以展示视觉效果。

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

调用 `generator.Save` 会将 **PNG** 文件写入当前工作目录。`BarCodeImageFormat.Png` 枚举确保无损压缩，适合后续处理或嵌入 PDF。

## 步骤 5：将宽高比改为 30 并保存第二张图像

现在我们通过将宽高比改为 **30** 来提升堆叠条的高度。这会在不改变 X 维度的前提下使条形码更高。

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

运行程序后会生成两个 PNG 文件：

* **DatabarAspectRatio15.png** – 适用于小标签的紧凑条形码。
* **DatabarAspectRatio30.png** – 更高的条形码，可提升在低对比度表面上的扫描可靠性。

您可以使用任意查看器打开图像，以验证条形是否正确堆叠且编码数据与原始 GS1 字符串一致。

## 步骤 6：验证编码值（可选）

如果需要确认条形码确实对应输入字符串，可使用同一库进行解码：

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

解码器应输出 `(01)12345678901231`，证明 **create databar stacked barcode** 过程保留了数据。

## 常见陷阱及规避方法

| 问题 | 产生原因 | 解决方案 |
|------|----------|----------|
| 条形码模糊 | X 维度设置过低，导致输出分辨率不足 | 增加 `XDimension.Pixels`，或在打印时使用 `Millimeters` |
| 扫描仪报告“未找到符号” | 宽高比超出支持的 10‑30 范围 | 保持宽高比在 10 到 30 之间；15 和 30 为安全默认值 |
| PNG 带有水印 | 使用 Aspose.BarCode 免费评估许可证 | 购买正式许可证，或仅在测试时使用试用版 |
| 第二张图像解码失败 | 解码器配置了错误的符号类型 | 读取堆叠条形码时使用 `DecodeType.DatabarStackedOmniDirectional` |

## 后续步骤

现在您已经能够**创建 databar stacked barcode**图像，接下来可能想要：

* 使用 **Aspose.PDF** 等 PDF 库将 PNG 嵌入 PDF 发票中。
* 在 Web API 中实时生成条形码——直接从 ASP.NET Core 控制器返回 PNG 字节。
* 通过更改 `EncodeTypes` 枚举，尝试其他 DataBar 变体（例如 `DatabarExpanded`、`DatabarLimited`）。
* 通过设置 `generator.Parameters.Barcode.ForeColor` 和 `BackColor` 来调整颜色，以实现品牌特定的设计。

上述每个主题都基于本文所述的核心概念：初始化 `BarcodeGenerator`、配置视觉参数，以及使用 `BarCodeImageFormat` 保存结果。

---

### 结论

本教程演示了如何使用 Aspose.BarCode 在 C# 中**创建 databar stacked barcode**图像。您学习了设置 **X 维度**、修改 **条形码宽高比**，并使用 `BarcodeGenerator` 将结果导出为 **PNG** 文件。通过可选的解码步骤，还可以验证编码的 GS1 数据是否准确。将这些模式应用于您的库存、运输或销售点应用程序，并探索库提供的众多自定义选项。祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [一维 DataBar 条形码高度调整](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [生成条形码图像 – GS1 优惠券 UPC-A DataBar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}