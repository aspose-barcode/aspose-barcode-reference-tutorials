---
category: general
date: 2026-10-08
description: 使用 C# 创建空的星球条形码，并学习如何使用 Aspose.BarCode 生成邮政条形码。包括一步一步的代码和技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: zh
lastmod: 2026-10-08
og_description: 使用 Aspose.BarCode 在 C# 中创建空的 Planet 条形码，并了解如何为邮件应用生成邮政条形码图像。
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: 创建空星球条码 – C# 邮政条码指南
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: 在 C# 中创建空星条码并生成邮政条码
url: /zh/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 创建空的 Planet 条码，生成邮政条码

如果您需要为邮件系统 **创建空的 planet 条码**，本指南将向您展示如何使用 Aspose.BarCode for .NET 完成此操作。您还将学习 **如何生成邮政条码** 图像，如 Planet 和 RM4SCC，定制条宽，并控制 filled‑bars 选项。

生成邮政条码不需要额外的图形库。Aspose.BarCode SDK 提供了一个统一的 API，处理编码、图像渲染以及图像格式选择。完成本教程后，您将拥有三个可直接使用的 PNG 文件：

* `PostalPlanetEmptyBars.png` – 空条的 Planet 条码  
* `PostalPlanetFilledBars.png` – 默认填充条的 Planet 条码  
* `PostalRM4SCCFilledBars.png` – 填充条的 RM4SCC 条码  

您可以将这些文件放入任何邮件标签模板，打印在信封上，或传递给第三方服务。

## 前置条件

* .NET 6.0 或更高（代码同样适用于 .NET Framework 4.7+）。  
* Visual Studio 2022 或任意 C# IDE。  
* Aspose.BarCode for .NET – 通过 NuGet 安装：

```bash
dotnet add package Aspose.BarCode
```

无需其他依赖。

## 使用 Aspose.BarCode 创建空的 planet 条码

Planet 符号是美国邮政服务（USPS）条码系列的一部分。默认情况下 SDK 绘制 **填充** 条。要 **创建空的 planet 条码**，只需禁用 `FilledBars` 标志。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**工作原理说明：**  
`EncodeTypes.Planet` 告诉生成器使用 Planet 符号。`XDimension.Pixels` 控制每根条的实际宽度，这对期望特定模块尺寸的邮政扫描仪至关重要。将 `FilledBars` 设置为 `false` 可让渲染器仅绘制每根条的轮廓，从而产生某些邮件标准要求的 *空* 外观。

### 预期输出

您将在目标文件夹中找到 `PostalPlanetEmptyBars.png`。该图像展示了每根条都是轮廓而非实心矩形的 Planet 条码。

![空的 Planet 条码示例](empty-planet.png){: .align-center alt="创建空的 planet 条码 – 空条 Planet 条码示例"}

## 如何生成邮政条码图像（填充版）

大多数邮政工作流使用默认的填充条版本。相同的 API 只需几行代码即可生成填充的 Planet 条码和 RM4SCC 条码。

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**为何可能需要 RM4SCC：**  
RM4SCC 是更新的 USPS 条码，使用更高密度对同样的数据进行编码。部分运营商要求使用 RM4SCC 以获取批量邮件折扣。上面的代码演示了如何 **生成邮政条码**，同时兼容两种标准，而无需更改整体工作流。

### 预期输出

* `PostalPlanetFilledBars.png` – 经典的填充条 Planet 条码。  
* `PostalRM4SCCFilledBars.png` – 填充条的 RM4SCC 条码，外观相似但间距更紧凑。

两文件均可在任意图像查看器中打开，以验证条纹模式。

## 为不同打印分辨率调整条宽

邮政扫描仪通常规定最小模块宽度（例如 0.013 英寸）。如果您的打印机分辨率为 300 dpi，则 4 像素模块对应 0.013 英寸。请调整 `XDimension.Pixels` 的值以匹配您的硬件：

| 期望模块宽度（英寸） | DPI | 所需像素 (`XDimension`) |
|----------------------|-----|--------------------------|
| 0.013                | 300 | 4                        |
| 0.013                | 600 | 8                        |
| 0.015                | 300 | 5                        |

**小贴士：** 始终测试 a

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步深入。每个资源都提供完整的可运行代码示例，并配有逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}