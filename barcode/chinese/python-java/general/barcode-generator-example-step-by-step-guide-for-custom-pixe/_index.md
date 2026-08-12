---
category: general
date: 2026-08-12
description: 条形码生成器示例，展示如何生成具有精确像素尺寸的条形码。学习设置模块宽度、条码高度并创建 Planet 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to generate barcode
- barcode pixel size
- generate planet barcode
- barcode height setting
language: zh
lastmod: 2026-08-12
og_description: 条形码生成器示例演示了如何生成具有精确像素尺寸的条形码。请按照本指南控制 Planet 和 RM4SCC 码的模块宽度和条码高度。
og_image_alt: Screenshot of a barcode generator example showing a Planet barcode with
  custom pixel size
og_title: 条形码生成器示例 – 在 C# 中自定义像素大小
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  headline: barcode generator example – step‑by‑step guide for custom pixel sizes
  type: TechArticle
- description: barcode generator example that shows how to generate barcode with precise
    pixel size. Learn to set module width, bar height and create Planet barcodes.
  name: barcode generator example – step‑by‑step guide for custom pixel sizes
  steps:
  - name: Install the Aspose.BarCode package
    text: 'Open a terminal in your project folder and run:'
  - name: Add the necessary `using` directives
    text: '```csharp using Aspose.BarCode.Generation; using Aspose.BarCode.BarCodeImageFormat;
      ```'
  - name: – generate a Planet barcode with automatically calculated height
    text: '```csharp // Step 1: Generate a Planet barcode with automatically calculated
      height BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate a Planet barcode with an explicit 100‑pixel height
    text: '```csharp // Step 2: Generate a Planet barcode with an explicit 100‑pixel
      height BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet,
      "123456");'
  - name: – generate an RM4SCC barcode with the same explicit height
    text: '```csharp // Step 3: Generate an RM4SCC barcode with the same explicit
      height BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC,
      "123456");'
  - name: What is **barcode pixel size**?
    text: '*Pixel size* refers to the physical number of screen or printer pixels
      that represent a single module (`XDimension`). A larger pixel size yields a
      bigger barcode, which can be easier for low‑resolution scanners but consumes
      more label real‑estate.'
  - name: How does `BarHeight` affect readability?
    text: The `BarHeight` property controls the vertical length of the bars. Standards
      for most 1‑D barcodes (including Planet and RM4SCC) recommend a minimum height
      of 10 mm when printed at 300 dpi, which translates to roughly 118 pixels. Setting
      a height below that can cause read errors, especially on mobil
  - name: When should you let the library calculate height automatically?
    text: If you’re generating barcodes for on‑screen display only, the automatic
      calculation keeps the aspect ratio consistent and reduces the amount of manual
      tweaking needed. For printed labels that must meet strict ISO specifications,
      you should **explicitly set the bar height**.
  - name: Pro tip on performance
    text: When generating thousands of barcodes in a batch job, reuse a single `BarcodeGenerator`
      instance and only change the `CodeText` and size parameters between saves. This
      avoids repeated allocation of internal rendering objects and can cut execution
      time by up to 30 %.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 条形码生成器示例——自定义像素尺寸的逐步指南
url: /zh/python-java/general/barcode-generator-example-step-by-step-guide-for-custom-pixe/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成器示例 – 自定义像素尺寸的分步指南

如果你需要一个 **条形码生成器示例**，能够控制每个像素，本指南将完整演示如何实现。你将学习设置模块宽度、定义固定条码高度，并生成 Planet 和 RM4SCC 条码，确保尺寸可预测。

大多数开发者在“如何生成条形码”图像时都会遇到在不同屏幕或打印机上显示不一致的问题。下面的代码片段通过公开 Aspose.BarCode for .NET 库的像素级参数，帮助你在不猜测的情况下生成一致的输出。

## 你将学到

* 如何安装所需的 NuGet 包。  
* 如何生成高度自动计算的 Planet 条码。  
* 如何生成高度明确为 100 像素的 Planet 条码。  
* 如何使用相同的明确高度生成 RM4SCC 条码。  
* 为什么 **条形码像素尺寸** 对扫描可靠性很重要。  
* 生成 Planet 条码图像时常见问题的排查技巧。

你只需要 .NET 6 或更高版本、基本的 C# 开发环境以及用于获取 NuGet 包的网络连接。

---

## 条形码生成器示例 – 搭建开发环境

在编写任何代码之前，确保 Aspose.BarCode 库已添加到你的项目中。

### 安装 Aspose.BarCode 包

在项目文件夹的终端中运行：

```bash
dotnet add package Aspose.BarCode
```

该命令会将最新稳定版的 **Aspose.BarCode** 添加到你的 `csproj` 中。恢复完成后，即可开始使用 `BarcodeGenerator` 类。

> **专业提示：** 目标设为 .NET 6 或 .NET 7，以获得最新的性能提升和默认的 UTF‑8 处理。

### 添加必要的 `using` 指令

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;
```

这些命名空间公开了后续教程中使用的 `BarcodeGenerator` 类和 `BarCodeImageFormat` 枚举。

---

## 如何使用自定义像素尺寸生成条形码

以下三个步骤完整演示 **条形码生成器示例**。每一步都基于前一步，你可以将整段代码复制粘贴到控制台应用中，直接运行。

### 步骤 1 – 生成高度自动计算的 Planet 条码

```csharp
// Step 1: Generate a Planet barcode with automatically calculated height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set module width (x‑dimension) to 4 pixels
planetAuto.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG
planetAuto.Save("PlanetAuto.png", BarCodeImageFormat.Png);
```

**工作原理：**  
*`XDimension` 属性定义单个条码模块（最小的黑白单元）的宽度。当省略 `BarHeight` 时，库会计算一个保持 Planet 码标准宽高比的高度。*

**预期输出：** 一个名为 `PlanetAuto.png` 的 PNG 文件，包含清晰的 Planet 条码。其高度会随 4 像素的模块宽度自动适配，通常约为 60 像素（对应六字符负载）。

### 步骤 2 – 生成高度明确为 100 像素的 Planet 条码

```csharp
// Step 2: Generate a Planet barcode with an explicit 100‑pixel height
BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same module width
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Force the bar height to 100 pixels
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
planetFixed.Save("PlanetHeight100.png", BarCodeImageFormat.Png);
```

**为何需要这样做：**  
有时扫描设备要求最小条码高度以确保可靠检测。通过设置 `BarHeight.Pixels`，你可以保证每张生成的图像都满足该要求，无论编码数据长度如何。

**预期输出：** `PlanetHeight100.png` 显示与前一步相同的数据，但条码高度恰好为 100 像素，让你完全掌控视觉尺寸。

### 步骤 3 – 使用相同的明确高度生成 RM4SCC 条码

```csharp
// Step 3: Generate an RM4SCC barcode with the same explicit height
BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Use the same module width for consistency
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;

// Apply the 100‑pixel bar height
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the image
rm4sccFixed.Save("RM4SCCHeight100.png", BarCodeImageFormat.Png);
```

**意义所在：**  
`EncodeTypes.RM4SCC` 是物流中使用的堆叠线性条码。将其条码高度与 Planet 条码保持一致，可简化同一标签上出现多种符号时的批处理工作。

**预期输出：** `RM4SCCHeight100.png` 展示尺寸完美的 RM4SCC 条码，高度与 Planet 条码设定的 100 像素保持一致。

> **结果验证：** 在图像查看器中打开每个 PNG，确认黑条宽度恰为 4 像素，且在你指定的情况下高度为 100 像素。也可以将文件导入条码扫描应用，确保解码结果为 “123456”。

---

## 理解条形码像素尺寸与条码高度

### 什么是 **条形码像素尺寸**？

*像素尺寸* 指的是在屏幕或打印机上表示单个模块（`XDimension`）所需的实际像素数量。更大的像素尺寸会生成更大的条码，低分辨率扫描仪更易读取，但会占用更多标签空间。

### `BarHeight` 如何影响可读性？

`BarHeight` 属性控制条码的垂直长度。大多数 1‑D 条码（包括 Planet 和 RM4SCC）的标准建议在 300 dpi 打印时最小高度为 10 mm，约合 118 像素。低于此高度可能导致读取错误，尤其在移动摄像头上更为明显。

### 何时让库自动计算高度？

如果仅用于屏幕显示，自动计算可保持宽高比一致，减少手动调节的工作量。对于必须符合严格 ISO 规范的印刷标签，建议 **显式设置条码高度**。

---

## 生成 Planet 条码时的常见陷阱与最佳实践

| 陷阱 | 产生原因 | 解决方案 |
|------|----------|----------|
| 条码过细或过粗 | 高分辨率显示器上 `XDimension` 保持默认（1 像素） | 将 `XDimension.Pixels` 设置为至少 3‑4，以提升可视清晰度 |
| 扫描仪无法读取 | `BarHeight` 对扫描仪焦距太小 | 对大多数移动扫描仪使用 `BarHeight.Pixels` ≥ 100 |
| 缩放后图像模糊 | 保存为 JPEG 会产生压缩伪影 | 使用 PNG (`BarCodeImageFormat.Png`) 保存，确保无损 |
| 条码类型意外 | 使用了错误的 `EncodeTypes` 枚举值 | 确认使用 `EncodeTypes.Planet` 生成 Planet 符号 |

### 性能小技巧

在批量生成数千条条码时，复用同一个 `BarcodeGenerator` 实例，仅在保存前更改 `CodeText` 和尺寸参数。这样可避免重复分配内部渲染对象，执行时间可降低约 30 %。

---

## 完整示例 – 综合所有步骤

创建一个新控制台项目（`dotnet new console -n BarcodeDemo`），并将 `Program.cs` 内容替换为以下代码：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Directory where PNG files will be saved
            string outputDir = Environment.CurrentDirectory;

            // ---------- Planet barcode – automatic height ----------
            var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputDir}/PlanetAuto.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetAuto.png generated.");

            // ---------- Planet barcode – fixed 100‑pixel height ----------
            var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputDir}/PlanetHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("PlanetHeight100.png generated.");

            // ---------- RM4SCC barcode – same fixed height ----------
            var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputDir}/RM4SCCHeight100.png", BarCodeImageFormat.Png);
            Console.WriteLine("RM4SCCHeight100.png generated.");

            Console.WriteLine("All barcodes created successfully.");
        }
    }
}
```

使用 `dotnet run` 运行程序。执行完毕后，你将在项目文件夹中看到三个 PNG 文件，分别演示了不同的 **条形码生成器示例** 场景。

---

## 后续步骤与相关主题

* **如何生成其他格式的条码** – 探索 `EncodeTypes.Code128`、`EncodeTypes.QR` 与 `EncodeTypes.DataMatrix`，满足 2‑D 需求。  
* **在 PDF 中嵌入条码** – 将 Aspose.BarCode 与 Aspose.PDF 结合，直接在发票模板上放置条码。  
* **基于用户输入的动态条码尺寸** – 计算  

## 接下来该学习什么？

以下教程与本指南紧密相关，帮助你进一步掌握 API 功能并在项目中尝试不同实现方式，每篇都提供完整可运行的代码示例和逐步说明。

- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)
- [How to Generate Barcode in Java Create and Set Size for Whole Picture](/barcode/english/java/barcode-basics/creating-setting-size-whole-picture-barcode/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}