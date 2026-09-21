---
category: general
date: 2026-08-06
description: 使用 Aspose.BarCode 在 C# 中生成条形码图像。了解如何生成 Databar、调整自定义条形码尺寸以及通过简易代码更改条形码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: zh
lastmod: 2026-08-06
og_description: 使用 Aspose.BarCode 在 C# 中生成条形码图像。本教程展示如何创建 Databar 全向条码、定制其尺寸以及高效地更改条码高度。
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: 在 C# 中生成条形码图像 – 完整 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: 使用 Aspose.BarCode 在 C# 中生成条形码图像
url: /zh/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中使用 Aspose.BarCode 生成条形码图像

如果您需要以编程方式**生成条形码图像**，本指南将准确展示如何操作。无论您是在构建零售库存系统还是物流跟踪门户，您都将看到创建 Databar Omnidirectional 条码、调整其尺寸并将结果保存为 PNG 文件的完整工作流。

生成条形码图像是常见需求，但开发者常常想知道**如何生成具有精确尺寸的 Databar**。在本教程中，您将学习创建 Databar 条码、定制其宽度和高度，以及在不重写整个生成器的情况下更改条码高度。

## 前提条件

* .NET 6.0 SDK 或更高版本（代码兼容 .NET Core 和 .NET Framework）
* Visual Studio 2022（或任何支持 C# 的 IDE）
* 有效的 Aspose.BarCode for .NET 许可证（免费评估版可用于测试）
* 对 C# 语法有基本了解

## 第一步：安装 Aspose.BarCode

将 Aspose.BarCode NuGet 包添加到您的项目中：

```bash
dotnet add package Aspose.BarCode
```

该包包含本教程中使用的 `BarcodeGenerator` 类。安装完成后，恢复项目以获取依赖项。

## 第二步：创建基础条码生成器

第一行代码创建一个**条码生成器**，用于生成 Databar Omnidirectional 符号。`EncodeTypes.DatabarOmniDirectional` 枚举告诉库使用哪种符号系统，数据字符串遵循 GS1 应用标识符语法。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**为什么这很重要：**`BarcodeGenerator` 对象是所有条码操作的入口。选择 `DatabarOmniDirectional` 可确保输出符合零售扫描的 GS1 标准。

## 第三步：设置自定义 X 维度（模块宽度）

X 维度控制最窄条的宽度。将其设置为较小的像素值可获得紧凑的条码，而较大的值会增加整体宽度。

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**说明：**2 像素的 X 维度是高分辨率屏幕的常用选择。如果需要更紧凑或更稀疏的视觉密度，请调整此值。

## 第四步：生成具有特定高度的首个条码图像

条码高度独立于 X 维度。在此我们将条码高度设置为 **30 px**，然后将图像保存为 PNG。

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**结果：**您现在拥有一个名为 `DatabarBarHeight30Pixels.png` 的文件，显示了高度为 30 px 的 Databar 条码。这演示了针对小标签等特定用例的**自定义条码尺寸**功能。

## 第五步：更改条码高度以生成更大版本

如果同一条码需要出现在更大的标签上，只需修改高度属性并复用同一生成器实例。

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**为什么可以复用生成器：**更改 `BarHeight.Pixels` 会更新内部布局，而无需重新创建对象，这可以节省内存并保持数据字符串不变。这是实时**更改条码高度**的推荐方式。

## 第六步：验证输出

在任意图像查看器中打开这两个 PNG 文件。您应该会看到两个 Databar Omnidirectional 条码，它们编码相同的 GTIN，但垂直尺寸不同：

* `DatabarBarHeight30Pixels.png` – 高度 30 px，适用于紧凑收据。
* `DatabarBarHeight60Pixels.png` – 高度 60 px，适用于更大的货架边标签。

两个图像保持相同的 X 维度，因此条与空的比例保持一致，仅整体高度按比例放大。

## 常见变体和边缘情况

| Situation | How to handle it |
|-----------|------------------|
| **不同的条码符号系统** | 将 `EncodeTypes.DatabarOmniDirectional` 替换为其他枚举值（例如 `EncodeTypes.Code128`），其余代码保持不变。 |
| **非像素维度** | 如果需要用于打印的物理尺寸，请使用 `generator.Parameters.Barcode.XDimension.Millimeters` 或 `BarHeight.Millimeters`。 |
| **透明背景** | 在调用 `Save` 之前设置 `generator.Parameters.ImageBackgroundColor = Color.Transparent;`。 |
| **高分辨率输出** | 按比例同时增大 `XDimension.Pixels` 和 `BarHeight.Pixels`，或保存为 `BarCodeImageFormat.Tiff` 以获得无损质量。 |
| **在同一图像中包含多个条码** | 创建多个 `BarcodeGenerator` 实例，将每个渲染为 `Bitmap`，然后使用 `Graphics.DrawImage` 将它们合成。 |

**专业提示：**在投入生产前，请始终使用真实扫描仪测试生成的条码。扫描仪可能会因光照和传感器质量的不同而对极细的条产生不同的解释。

## 完整源代码供参考

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

将代码复制到新的控制台项目中，运行后您将在输出文件夹中看到两个 PNG 文件。

## 常见问题

**问：我可以在不安装许可证的情况下生成条码吗？**  
**答：**Aspose.BarCode 的评估版可以在没有许可证的情况下工作，但会添加小水印。生产环境请使用 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` 应用购买的许可证。

**问：更改 X 维度会影响可读性吗？**  
**答：**会。非常小的 X 维度会导致低分辨率打印机无法读取条码。屏幕渲染建议最小 1 px；打印时建议至少 0.25 mm。

**问：如果需要以 JPEG 格式生成条码怎么办？**  
**答：**将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`。您还可以设置 `generator.Parameters.ImageQuality` 来控制压缩率。

## 结论

您现在已经了解如何在 C# 中使用 Aspose.BarCode **生成条码图像**，如何 **创建 Databar 条码**，调整 **自定义条码尺寸**，以及按需 **更改条码高度**。完整示例展示了最常见的工作流，变体表格帮助您应对实际场景中的边缘情况。

接下来，您可以探索相关主题，如 **在 PDF 文档中嵌入条码**、**批量生成多个条码**，以及 **使用二维码进行移动支付**。这些场景都基于本指南的相同原理，您可以自信地扩展此知识。

祝编码愉快，愿您的条码扫描顺利！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本指南展示的技术。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [生成条码图像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [使用 Aspose.BarCode for .NET 生成自定义宽高比的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [生成条码 – Code 39 配置（使用 Aspose.BarCode）](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}