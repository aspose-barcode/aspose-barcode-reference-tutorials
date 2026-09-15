---
category: general
date: 2026-07-18
description: 条形码生成器示例，展示如何设置尺寸并在 C# 中生成 DataBar Stacked Omni‑Directional 条码图像。快速了解条码编码类型。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: zh
lastmod: 2026-07-18
og_description: 条形码生成器示例向您展示如何设置尺寸、选择条形码编码类型，并使用最少的代码创建条形码图像的 C# 项目。
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: 条形码生成器示例 – 使用 C# 快速创建 DataBar 图像
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: 条码生成器示例 – 使用 C# 构建 DataBar 图像
url: /zh/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成器示例 – 在 C# 中构建 DataBar 图像

有没有需要一个**条形码生成器示例**，能够真正生成可用的条形码而不让你抓狂？你并不孤单。大多数开发者在尝试弄清楚**如何设置尺寸**以生成 DataBar Stacked Omni‑Directional 条形码时会卡住，尤其是当文档被大量行话埋得很深时。

在本教程中，我们将逐步演示一个完整、可直接运行的 C# 程序，展示**如何生成 databar** 图像，选择正确的**条形码编码类型**，并最终**创建 barcode image c#** 文件，您可以将其嵌入任何项目。没有冗余——只提供可复制粘贴的代码，并解释每一行的原理。

## 您需要的环境

- **.NET 6**（或任何近期的 .NET 版本）——我们使用的 API 面向 .NET Standard，因此在 .NET Framework 上也可运行。  
- **Aspose.BarCode for .NET**——提供 `BarcodeGenerator` 的库。您可以通过 `Install-Package Aspose.BarCode` 从 NuGet 获取。  
- 一个**C# IDE**——Visual Studio、Rider 或 VS Code 都可以。  
- 磁盘上的一个文件夹，用于保存 PNG 文件（代码会生成 `DatabarAspectRatio15.png` 和 `DatabarAspectRatio30.png`）。

准备好了吗？很好——让我们开始吧。

## 条形码生成器示例 – 初始化生成器

首先，我们需要一个配置为 **DataBar Stacked Omni‑Directional** 符号的 `BarcodeGenerator` 实例。这就是我们将使用的**条形码编码类型**。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **为什么这很重要：** `EncodeTypes.DatabarStackedOmniDirectional` 明确告知 Aspose 渲染哪种符号。如果选择错误的类型，扫描仪无论图像多漂亮都无法识别条形码。

## 如何为条形码设置尺寸

条形码的可读性取决于其**X‑dimension**（最窄条的宽度）。大多数情况下 2 像素的值足够，但您可以根据打印机或屏幕进行微调。

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **专业提示：** 如果您想了解**如何为其他条形码系列设置尺寸**，同样的属性链 (`Parameters.Barcode.XDimension`) 适用——只需更改 `Pixels` 的数值。

## 如何生成 DataBar Stacked Omni‑Directional 条形码

生成器准备好后，我们将使用 **aspect ratio** 属性。它控制 DataBar 的高宽比，让您可以生成短而方形或高而窄的符号。

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **发生了什么？** `AspectRatio = 15` 告诉引擎将条的高度设为宽度的 15 倍。生成的 PNG 会保存在可执行文件旁边。

## 创建条形码图像 C# – 更改宽高比

让我们通过将比例改为 30 并保存第二个文件来验证其灵活性。

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

运行程序后，您将得到两个 PNG 文件：

| 文件 | 宽高比 | 大约尺寸 |
|------|--------|----------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

在任意图像查看器中打开它们——您应该能看到清晰、可扫描的 DataBar 符号。

## 条形码编码类型概览（可选但实用）

如果您想了解 Aspose 支持的其他**条形码编码类型**，这里有一个快速速查表：

| EncodeTypes Enum | 描述 |
|------------------|------|
| `EncodeTypes.Code128` | 高密度字母数字 |
| `EncodeTypes.QR` | 二维矩阵码 |
| `EncodeTypes.DatabarExpanded` | 零售用 GS1 DataBar |
| `EncodeTypes.DatabarStackedOmniDirectional` | **我们的重点** – 紧凑、全方向 |

## 常见陷阱及避免方法

- **缺少 NuGet 包** – 没有 `Aspose.BarCode` 代码无法编译。请先运行 `dotnet add package Aspose.BarCode`。  
- **错误的文件路径** – 如果使用绝对路径，请检查 Windows 上的反斜杠 (`\\`)。如示例所示的相对路径更具可移植性。  
- **宽高比过于极端** – 超过 50 的比例会使条形码对普通扫描仪来说过高。大多数情况下请保持在 15‑30 之间。

## 完整源代码（可直接复制粘贴）

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

运行程序（`dotnet run` 或在 Visual Studio 中按 **F5**）后，您会在控制台看到确认文件已生成的消息。

![条形码生成器示例输出，显示宽高比为 15 的 DataBar 条形码](placeholder/path/to/image.png){: .align-center alt="条形码生成器示例输出，显示宽高比为 15 的 DataBar 条形码"}

## 总结

我们刚刚完成了一个**条形码生成器示例**，演示了**如何设置尺寸**，选择正确的**条形码编码类型**，并最终**创建 barcode image c#** 文件，可嵌入任何地方。代码简洁，概念清晰，您现在拥有了扩展此方案的坚实基础——比如添加文字说明、旋转图像或切换到其他符号。

### 接下来做什么？

- 尝试不同的 **X‑dimension**，观察扫描仪容差的变化。  
- 尝试其他 **EncodeTypes** 如 `Code128` 或 `QR`，丰富您的工具箱。  
- 自动化批量生成：遍历包含产品 ID 的 CSV，为每个生成 PNG。

如果遇到问题，请在下方留言或查阅 Aspose.BarCode 文档——其中包含大量与本教程相辅相成的示例。

祝编码愉快，愿您的条形码总能一次成功扫描！

## 接下来应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本教程展示的技术进行扩展。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何生成条形码 - 一维条形码类型](/barcode/english/net/one-dimensional-barcode-types/)
- [创建条形码图像 C# – GS1 DataMatrix 示例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}