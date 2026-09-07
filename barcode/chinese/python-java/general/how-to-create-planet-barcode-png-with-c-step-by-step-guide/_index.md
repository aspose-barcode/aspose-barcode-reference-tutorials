---
category: general
date: 2026-09-07
description: 在 C# 中快速创建行星条形码 PNG。了解如何使用 Aspose.BarCode 生成带有实心和空心条的行星条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: zh
lastmod: 2026-09-07
og_description: 在 C# 中快速创建行星条码 PNG。请按照本指南学习如何使用 Aspose.BarCode 生成带有实心和空心条的行星条码图像。
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: 在 C# 中创建行星条形码 PNG – 完整编码教程
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# 创建 Planet 条码 PNG – 步骤指南
url: /zh/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 创建 Planet 条形码 PNG – 步骤指南

如果您需要在 C# 中 **创建 Planet 条形码 PNG** 文件，本指南将为您展示完整步骤。无论是构建邮政服务集成还是物流仪表盘，您都将学习 **如何生成带填充和空白条的 Planet 条形码** 图像，使用 Aspose.BarCode 库。

在本教程中，您将：

* 设置图像的输出文件夹。  
* 为 Planet 符号配置 `BarcodeGenerator`。  
* 生成默认填充条样式的 PNG。  
* 生成空白条以实现视觉对比的 PNG。  

无需外部服务——所有操作均在本地 .NET 6 或更高版本上运行。

## 前置条件

在开始之前，请确保您具备以下条件：

| 要求 | 重要原因 |
|------|----------|
| .NET 6 SDK（或更高） | 为 C# 控制台应用提供运行时。 |
| Visual Studio 2022 或 VS Code | 任意能够编译 C# 项目的 IDE。 |
| Aspose.BarCode for .NET（NuGet 包 `Aspose.BarCode`） | 提供用于渲染 Planet 条形码的 `BarcodeGenerator` 类。 |
| 对磁盘文件夹的写入权限 | PNG 文件将保存到该位置。 |

使用以下命令安装 NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：创建新控制台项目

打开终端并运行：

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

此命令会创建一个名为 **PlanetBarcodeDemo** 的最小 C# 控制台应用程序。

## 步骤 2：定义输出目录

下面的代码决定生成的 PNG 文件将存放的位置。可以使用绝对路径或相对路径；只需确保文件夹已存在，或让程序自行创建。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*为什么要这么做？* 将输出与源代码分离可以保持项目整洁，避免意外覆盖。

## 步骤 3：生成填充条的 Planet 条形码

Planet 条形码由同心圆组成（默认填充）。我们配置 X 维度（每条的像素宽度），然后将图像保存为 PNG。

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**说明**

* `EncodeTypes.Planet` 告诉 Aspose 使用 Planet 符号，这在邮政服务中很常见。  
* `XDimension.Pixels = 4` 可得到清晰、可打印的尺寸，无需手动缩放。  
* `Save` 方法写入 PNG 文件；您也可以通过更改 `BarCodeImageFormat` 选择 JPEG 或 BMP。

## 步骤 4：生成空白条的 Planet 条形码

有时需要空（透明）条的视觉效果，例如将条形码叠加在彩色背景上。将 `FilledBars` 设置为 `false` 即可生成此样式。

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**说明**

* `FilledBars = false` 关闭实心圆，仅保留轮廓。  
* 其他设置（X 维度、数据字符串）保持不变，确保两张图像表示相同的数据。

## 步骤 5：运行程序并验证输出

编译并执行：

```bash
dotnet run
```

您应在控制台看到确认已保存文件的消息，`Barcodes` 文件夹中将包含：

* `PostalPlanetFilledBars.png` – 经典的填充条 Planet 条形码。  
* `PostalPlanetEmptyBars.png` – 使用空白条渲染的相同数据。

使用任意图像查看器打开 PNG。两张图像均编码数字串 **123456**，可被标准邮政条形码阅读器扫描。

## 常见问题与边缘情况处理

### 如果需要不同的数据格式怎么办？

Planet 条形码接受最长 12 位的数字字符串。若传入非数字值，Aspose 会抛出 `ArgumentException`。在创建生成器前请先验证输入：

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### 如何在不改变条宽的情况下修改图像尺寸？

使用 `Resolution` 属性或在保存后对位图进行缩放：

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### 能生成其他图像格式吗？

可以。将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`、`Bmp` 或 `Gif`。API 支持所有常见的栅格格式。

### 如何自定义颜色？

在 `Barcode` 参数上设置 `BarColor` 和 `BackColor`：

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

这些选项对填充条和空白条版本均适用。

## 生产环境使用的专业技巧

* **缓存生成器**：当需要使用相同设置渲染大量条形码时，缓存 `BarcodeGenerator` 可减少初始化开销。  
* **释放资源**：如果在循环中创建大量实例，请 `Dispose` `BarcodeGenerator`（它实现了 `IDisposable`）。  
* **提前验证输出文件夹**：避免在受写保护的目录中写入导致的运行时异常。

## 结论

现在您已经掌握了在 C# 中 **创建 Planet 条形码 PNG** 文件的方法，并了解了 **如何生成填充条和空白条两种样式** 的条形码图像。完整的可运行示例演示了如何设置输出目录、配置 `BarcodeGenerator`，以及将结果保存为 PNG。

接下来，您可以尝试：

* 在条形码下方添加 **可读文本**（`planetFilled.Parameters.Caption.Visible = true`）。  
* 使用 Aspose.PDF 将生成的 PNG 集成到 **PDF 发票** 中。  
* 切换到其他邮政符号，如 **IMB** 或 **ITF**（`EncodeTypes.IMB`、`EncodeTypes.ITF`）。  

欢迎尝试不同的条宽、颜色和图像分辨率，以满足您的具体应用需求。祝编码愉快！


## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，提供完整的代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方式。

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}