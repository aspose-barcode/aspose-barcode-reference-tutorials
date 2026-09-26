---
category: general
date: 2026-09-26
description: 快速学习如何在 C# 中创建 Planet 条码。本指南涵盖实心和空心 Planet 条码、X 维度设置以及图像导出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: zh
lastmod: 2026-09-26
og_description: 使用 C# 创建 Planet 条形码并提供完整代码示例。生成实心和空心的 Planet 条形码，设置条宽，并保存为 PNG。
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: 使用 C# 创建行星条形码图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 BarcodeGenerator 创建行星条码图像
url: /zh/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 BarcodeGenerator 在 C# 中创建 Planet 条形码图像

如果您需要在 .NET 应用程序中**创建 planet 条形码**图像，本教程将向您展示完整步骤。您将学习如何生成实心和空白的 Planet 条形码，调整条宽，并将结果导出为 PNG 文件——全部使用 Aspose.BarCode for .NET 库。

生成 **Planet barcode C#** 解决方案非常直接，只要您了解关键的 **barcode generator parameters**。在接下来的章节中，我们将逐步演示完整的可运行代码，解释每个设置为何重要，并指出常见的陷阱，以便您一次成功。

## 前置条件

在开始之前，请确保您拥有：

* 已安装 .NET 6.0 SDK 或更高版本。
* Visual Studio 2022（或您喜欢的任何 C# IDE）。
* 已在项目中添加 **Aspose.BarCode for .NET** NuGet 包（`Aspose.BarCode`）。

您可以通过 NuGet 包管理器控制台添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：设置 BarcodeGenerator

`BarcodeGenerator` 类是所有条形码创建任务的入口点。它需要两个参数：条形码类型（`EncodeTypes.Planet`）和要编码的数据。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*为什么这很重要：* 使用 `EncodeTypes.Planet` 实例化生成器会告诉库使用 **Planet 条形码** 符号，该符号在某些国家的邮政服务中常用。字符串 `"123456"` 是将在条形码中显示的负载。

## 步骤 2：配置 X‑dimension（条宽）

X‑dimension 控制每根条的实际宽度。屏幕渲染的典型值是 4 像素，但您可以根据打印需求进行调整。

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*为什么这很重要：* 设置 `XDimension.Pixels` 可确保生成的条形码既不会太细（导致扫描失败），也不会太粗（浪费空间）。相同的设置将在空白条形码中复用。

## 步骤 3：保存实心 Planet 条形码

使用 `Save` 方法将条形码导出为 PNG 文件。`BarCodeImageFormat.Png` 枚举指示库生成适合后续处理的无损图像。

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

运行程序后，您将在输出文件夹中找到 `PostalPlanetFilledBars.png`。打开它以验证条是实心（filled）的。

## 步骤 4：为空白 Planet 条形码创建生成器

**empty planet barcode** 显示相同的数据，但条是未填充（白色）的。这对于在彩色背景上叠加条形码的视觉设计非常有用。

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

构造函数调用与实心版本完全相同；区别在于我们接下来要更改的参数。

## 步骤 5：复用相同的 X‑dimension

为保持视觉尺寸一致，将相同的条宽应用于空白条形码。

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

复用 **barcode generator parameters** 可确保两张图像并排放置时完美对齐。

## 步骤 6：切换为未填充的条

`FilledBars` 标志决定条是以实心黑色（默认）还是透明白色渲染。

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*为什么这很重要：* 将 `FilledBars = false` 会切换渲染模式，这是实心与空白 Planet 条形码之间的关键区别。

## 步骤 7：保存空白 Planet 条形码

最后，将空白版本导出为 PNG。

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

运行程序后，会出现两个文件：

* `PostalPlanetFilledBars.png` – 实心黑色条。
* `PostalPlanetEmptyBars.png` – 透明（未填充）条。

两张图像包含相同的数据（`123456`）并共享相同的 X‑dimension，因而在大多数 UI 场景中可以互换使用。

## 完整、可运行的示例

将所有内容组合在一起，以下是您可以复制粘贴到新控制台项目中的完整源文件：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**预期输出**

运行程序会在可执行文件的工作目录中创建两个 PNG 文件。使用任意图像查看器打开它们：

* **实心版本** – 深色、实心条，标准扫描仪可轻松读取。
* **空白版本** – 条在黑色背景上呈现为白色间隙，适用于叠加效果。

## 常见陷阱与专业提示

| 问题 | 原因 | 解决方法 |
|-------|----------------|---------------|
| 条宽看起来太细 | X‑dimension 保持默认值（1 像素） | 将 `XDimension.Pixels` 设置为 3‑5 像素用于屏幕显示；打印高分辨率时可增大。 |
| 空白条形码完全呈黑色 | `FilledBars` 未设置为 `false` | 确保在设置 X‑dimension 之后执行 `emptyPlanet.Parameters.Barcode.FilledBars = false;` |
| PNG 文件缺失 | 输出路径不正确或目录不存在 | 提供完整路径（例如 `@"C:\Barcodes\PostalPlanetFilledBars.png"`）或使用 `Directory.CreateDirectory` 预先创建目录。 |
| 条形码无法扫描 | 数据字符串包含 Planet 符号不允许的字符 | Planet 条形码仅接受数字负载；请使用 `int.TryParse` 验证输入。 |

**专业提示：** 如果需要将条形码嵌入 PDF，可以使用 Aspose.PDF 将生成的 PNG 加载到 `PdfDocument` 中，或直接将条形码作为图像流添加而无需写入磁盘。

## 后续步骤

现在您已经能够**创建 planet 条形码**图像，建议进一步探索以下相关主题：

* **Planet barcode C#** – 自定义颜色、添加可读文本，或将条形码嵌入 PDF。
* **Barcode generator parameters** – 调整错误纠正级别、安静区或旋转角度。
* **Batch generation** – 循环处理邮政编码列表，生成 PNG 压缩包。
* **Alternative formats** – 导出为 SVG 或 JPEG，以实现 Web 友好的交付。

尝试不同的 `XDimension` 值和 `FilledBars` 标志，观察它们对扫描可靠性和视觉风格的影响。准备就绪后，将生成代码集成到您的 Web API 或桌面应用中，实现邮政条形码的即时自动化创建。

---

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方案。每个资源都提供完整的可运行代码示例和逐步解释。

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}