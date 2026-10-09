---
category: general
date: 2026-09-29
description: 学习如何使用 Aspose.BarCode 在 C# 中创建全向 Databar 条码。调整 X 维度，设置宽高比，并保存为 PNG 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: zh
lastmod: 2026-09-29
og_description: 使用 Aspose.BarCode 在 C# 中创建全向 Databar 条码。学习设置 X 维度、调整宽高比并导出 PNG 文件。
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: 在 C# 中创建全向 Databar 条码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中创建全向 Databar 条码
url: /zh/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建全向 DataBar 条形码

如果您需要在 .NET 应用程序中 **创建全向 DataBar 条形码**，本指南将展示完整步骤。您将看到如何初始化 DataBar 堆叠全向条形码、配置 X 维度、修改宽高比，并使用 Aspose.BarCode 生成 PNG 图像。

生成 **DataBar 堆叠全向条形码** 在必须为零售扫描仪编码产品标识符时非常常见。在本教程中，您将学习 **设置条形码宽高比**、控制模块大小，以及在不离开 IDE 的情况下导出结果。

## 前置条件

在开始之前，请确保您具备：

- 已安装 .NET 6.0 或更高版本
- Visual Studio 2022（或任何支持 C# 的 IDE）
- **Aspose.BarCode for .NET** NuGet 包（版本 23.12 或更新）

您可以通过 NuGet 包管理器添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：初始化全向 DataBar 条形码

第一步是创建一个针对 **DataBar 堆叠全向** 符号的 `BarcodeGenerator` 实例。构造函数接受编码类型和数据字符串。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**为什么重要：** `EncodeTypes.DatabarStackedOmniDirectional` 值告诉 Aspose.BarCode 渲染特定的全向 DataBar 格式，这对于双向扫描是必需的。

## 步骤 2：定义 X 维度（模块大小）

X 维度控制单个条形码模块的像素宽度。`2` 像素的值在屏幕渲染和大多数打印机上表现良好。

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么重要：** 一致的 X 维度可确保条形码符合零售扫描仪的最小尺寸规范，同时保持图像文件大小在可接受范围内。

## 步骤 3：设置首个宽高比并保存图像

**宽高比** 决定 DataBar 的高宽关系。宽高比为 `15` 时会生成紧凑且高的条形码，适合狭窄的标签空间。

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**为什么重要：** 调整宽高比可让您在不同标签布局中放置条形码而不牺牲可读性。保存的 PNG 可以在任何图像查看器中检查。

## 步骤 4：更改宽高比并生成第二张图像

有时需要更宽的条形码，例如标签拥有更多水平空间时。将比例改为 `30` 可产生更平坦的外观。

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**为什么重要：** 通过公开 **set barcode aspect ratio** 属性，您可以从同一代码库生成多种条形码变体，简化自动化标签生成流水线。

## 预期输出

运行程序后，应用程序的输出文件夹中会生成两个 PNG 文件：

| 文件名 | 宽高比 | 可视化描述 |
|---------------------------|----------|----------------------------------------------|
| `DatabarAspectRatio15.png` | 15 | 高而窄的条形码，适用于狭窄标签 |
| `DatabarAspectRatio30.png` | 30 | 更宽的条形码，填充更多水平空间 |

您可以在报表中嵌入这些图像、将其打印在产品包装上，或发送至 Web 服务进行进一步处理。

![创建全向 DataBar 条形码示例](databar-example.png "创建全向 DataBar 条形码示例")

*截图显示了并排生成的两个 PNG 文件。*

## 常见问题与边缘情况

### 如果需要不同的 X 维度怎么办？

您可以为 `XDimension.Pixels` 赋任意整数值。小于 `1` 的值会被忽略，超过 `10` 的值可能会产生超出打印机边距的过大模块。每次更改后请测试视觉输出。

### 如何编码其他 AI 生成的数据（例如 UPC、EAN）？

将 `BarcodeGenerator` 构造函数中的数据字符串替换为相应的应用标识符（AI）。对于 UPC‑A 码，使用不带 AI 前缀的 `"012345678905"`。

### 能否导出为 PNG 之外的格式？

可以。`Save` 方法支持 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Gif`、`BarCodeImageFormat.Tiff` 和 `BarCodeImageFormat.Bmp`。选择符合下游工作流的格式即可。

## 专业技巧：复用生成器进行批量处理

如果需要生成大量条形码且宽高比各不相同，保持 `BarcodeGenerator` 实例存活，仅在每次 `Save` 前修改 `DataBar.AspectRatio`。这样可避免为每张图像重新实例化生成器的开销。

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## 结论

现在您已经掌握了如何使用 Aspose.BarCode 在 C# 中 **创建全向 DataBar 条形码**。通过初始化 `BarcodeGenerator`、设置 X 维度、调整 **set barcode aspect ratio**，并保存 PNG 文件，您可以生成满足各种标签需求的条形码图像。

接下来，您可以探索诸如 **generate barcode image**（生成二维码图像）、**DataBar 堆叠全向条形码** 验证，或将生成的 PNG 集成到使用 Aspose.PDF 的 PDF 发票中。尝试不同的宽高比和模块大小，以找到最适合您特定打印硬件的配置。

---


## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步使用这些技巧。每个资源都提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并探索替代实现方案。

- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to generate barcode in C# – create barcode image c# with DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}