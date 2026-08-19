---
category: general
date: 2026-08-19
description: 使用 Aspose.BarCode 在 C# 中创建 DataBar PNG 文件。了解如何生成 DataBar 图像、配置 DataBar
  参数并保存 PNG 输出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: zh
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 在 C# 中创建 DataBar PNG 文件。本教程将指导您如何生成 DataBar 图像、配置
  DataBar 参数（如 X 维度和纵横比），并保存高质量的 PNG 文件以用于打印或网页使用。
og_image_alt: create databar PNG example
og_title: 在 C# 中创建 databar PNG 图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: 如何使用 C# 和 Aspose.BarCode 创建 DataBar PNG 图像
url: /zh/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 和 Aspose.BarCode 创建 databar PNG 图像

如果您需要在 .NET 应用程序中 **创建 databar PNG** 文件，本指南将一步步演示完整可运行的示例，生成堆叠全向 DataBar 条码，配置关键参数，并保存两个具有不同宽高比的 PNG 文件。

生成 DataBar 图像不仅仅是调用一个方法。您还必须 **配置 databar 参数**，例如 X 维度（模块宽度）和宽高比，以满足打印或扫描规范。完成本教程后，您将了解 **如何生成在实际场景中可靠工作的 databar** 图形。

## 前置条件

- .NET 6.0 或更高（代码同样适用于 .NET Framework 4.7+）
- Visual Studio 2022 或任何支持 C# 的 IDE
- 有效的 **Aspose.BarCode for .NET** 许可证（免费评估版可用于测试）
- 基本的 C# 语法了解

> **专业提示：** 如果您还没有许可证，可以从 Aspose 门户申请临时评估密钥。API 行为保持一致，仅水印会有所不同。

## 第一步：安装 Aspose.BarCode NuGet 包

在 Visual Studio 中打开项目，右键单击解决方案，选择 **Manage NuGet Packages**。搜索 `Aspose.BarCode` 并安装最新的稳定版本。

```bash
dotnet add package Aspose.BarCode
```

此命令会将 `Aspose.BarCode` 程序集添加到项目中，并使 `BarcodeGenerator` 类可用。

## 第二步：为堆叠全向 DataBar 初始化条码生成器

`BarcodeGenerator` 构造函数接受两个参数：条码类型和原始数据字符串。对于堆叠全向 DataBar，使用 `EncodeTypes.DatabarStackedOmniDirectional`。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**为什么重要：** `EncodeTypes.DatabarStackedOmniDirectional` 常量告诉库生成可从任意方向读取的条码，非常适合零售货架标签。

## 第三步：以像素配置 X 维度（模块宽度）

X 维度控制最小条形元素的大小。以像素设置可精确控制最终图像尺寸。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**2 像素** 的值在大多数标签打印机上在可读性和紧凑性之间取得了良好平衡。如需更大或更小的模块，请相应调整此值。

## 第四步：设置第一个宽高比并保存 PNG

宽高比影响堆叠 DataBar 的高度。宽高比 **15** 生成相对较短的条码，而 **30** 则使其更高。

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 方法将生成的条码写入 PNG 文件。PNG 为无损格式，可保留条码扫描仪所需的清晰边缘。

## 第五步：更改宽高比并保存第二个 PNG

您可以复用同一个 `BarcodeGenerator` 实例，只需更改宽高比即可生成不同的变体。

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

现在您拥有两个 PNG 文件——`DatabarAspectRatio15.png` 和 `DatabarAspectRatio30.png`——它们的视觉密度各不相同。

## 第六步：验证输出

在任意图像查看器中打开生成的 PNG 文件。您应该看到清晰、高对比度的 DataBar 条码。使用智能手机条码扫描器扫描图像，可确认两种宽高比均能解码为原始 GTIN 值 `12345678901231`。

![创建 databar PNG 示例](databar_example.png)

*上图展示了并排的两个 PNG 文件。左侧图像使用宽高比 15，右侧使用宽高比 30。*

## 常见变体和边缘情况

| 场景 | 需要更改的内容 | 原因 |
|----------|----------------|--------|
| **不同的数据** | 将字符串 `(01)12345678901231` 替换为任意有效的 GS1 应用标识符及数据 | 允许您编码产品 ID、序列号等 |
| **更高分辨率** | 将 `XDimension.Pixels` 提升至 3 或 4 | 当条码需在大尺寸或远距离扫描时必需 |
| **其他 DataBar 类型** | 使用 `EncodeTypes.DatabarStacked` 或 `EncodeTypes.DatabarExpanded` | 选择最适合标签布局的类型 |
| **透明背景** | 传入 `BarCodeImageFormat.Png` 并使用 `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | 便于将条码叠加在彩色标签上 |

> **注意：** 将 X 维度设置得过小（< 1 像素）会导致条码在放大后出现模糊。

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，进一步扩展您对 API 功能的掌握，并提供可直接在项目中使用的完整代码示例和逐步说明。

- [如何使用 Aspose.BarCode for .NET 生成并调整一维 Databar 条码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [使用 Aspose.BarCode 创建一维 Databar GS1 编码](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [使用 .NET API 生成 Aspose.BarCode Databar 条码 – 行列配置](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}