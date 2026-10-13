---
category: general
date: 2026-09-22
description: 学习如何在 C# 中创建 PDF417 条码，设置条码尺寸，并通过清晰的逐步代码示例生成条码图像文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: zh
lastmod: 2026-09-22
og_description: 在 C# 中快速创建 PDF417 条码。本教程展示如何设置条码尺寸、启用紧凑模式，并为任何 .NET 项目输出 PNG 图像。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: 在 C# 中创建 PDF417 条码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: 如何在 C# 中创建 PDF417 条码并设置其大小
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建 PDF417 条形码并设置其尺寸

如果您需要在 C# 中 **创建 PDF417 条形码**，本指南将向您展示如何生成条形码、控制其尺寸，并将结果保存为图像文件。无论您是在构建票务系统、物流标签还是安全凭证，掌握 PDF417 格式都能让您在紧凑的视觉形式中编码大量数据。

在本教程中，您将学习：

* 使用 Aspose.BarCode（或任何兼容）库 **创建 PDF417 条形码**。  
* 通过调整 X‑dimension 和列数 **设置条形码尺寸**。  
* 在 C# 中生成 PNG、JPEG 或 BMP 格式的 **条形码图像**。  

示例使用 Aspose.BarCode for .NET 的免费社区版，但相同概念同样适用于其他提供类似属性的库。

## 前提条件

开始之前，请确保您已具备：

* 已安装 .NET 6.0 SDK 或更高版本。  
* C# 开发环境（Visual Studio、Visual Studio Code、Rider 等）。  
* `Aspose.BarCode` NuGet 包（`dotnet add package Aspose.BarCode`）。  

无需额外配置；该库可在 Windows、Linux 和 macOS 上运行。

## 步骤 1：创建基本的 PDF417 条形码并设置尺寸

第一步是使用 `EncodeTypes.Pdf417` 枚举实例化 `BarcodeGenerator`，并提供要编码的文本。随后调整 **X‑dimension**（模块宽度）和 **列数** 以控制整体尺寸。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**为何这些设置很重要**

* `XDimension.Pixels` 决定最窄条的宽度。数值越小，条形码越紧凑；数值越大，可提升低分辨率扫描仪的可读性。  
* `Pdf417.Columns` 影响条形码的宽高比。列数少会使条形码更高，列数多则更扁平。通过调整列数是 **设置条形码尺寸** 的主要方式，而无需更改编码数据。

运行代码后，您将在指定文件夹中看到 `Pdf417Basic.png`。图像效果类似下方截图：

<img src="images/pdf417-basic.png" alt="创建 PDF417 条形码示例，展示基本条形码布局">

## 步骤 2：使用相同尺寸创建紧凑的 PDF417 条形码（截断模式）

有时空间受限，需要更短的条形码。PDF417 提供 *截断*（紧凑）模式，可去除停止图案并降低整体高度。属性 `Truncate` 用于切换此行为。

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true` 会有什么变化？**

* 条形码在垂直方向上大约缩短 15‑20 %，适用于小标签或移动设备屏幕。  
* 数据仍然可以完整恢复；大多数现代扫描仪会自动识别截断模式。

生成的 `CompactPdf417.png` 看起来是基本条形码的更纤细版本。

## 步骤 3：创建 Micro PDF417 条形码，调整列数并保存

Micro PDF417 是一种面向极小空间（如身份证）的高密度变体，仅支持 1‑4 列。库同样通过 `XDimension` 属性控制尺寸。

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Micro PDF417 的关键要点**

* `EncodeTypes.MicroPdf417` 枚举会自动选择微型变体。  
* 由于符号更密集，可能需要 300 dpi 或更高的打印机才能保持可读性。  
* 调整列数是唯一可用的尺寸调节手段；库仍然遵循 `XDimension` 设置。

## 如何为不同输出格式设置条形码尺寸

上面的示例使用 PNG，但相同的 `Save` 方法同样适用于 JPEG、BMP 或 TIFF。如果需要特定的图像尺寸（例如 300 × 150 px），可以将 `XDimension` 与 `ResolutionX`/`ResolutionY` 结合使用：

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

在放大 `XDimension` 的同时提升 `ImageResolution`，可在高分辨率打印时保持视觉质量。

## 常见陷阱与专业技巧

| 问题 | 产生原因 | 解决方案 |
|------|----------|----------|
| 条形码在屏幕上模糊 | DPI 低且 `XDimension` 较小 | 提高 `ImageResolution` 和/或 `XDimension.Pixels` |
| 扫描仪无法读取截断模式 | 老旧扫描仪固件不支持 | 对于旧硬件使用完整（非截断）模式 |
| Micro PDF417 难以读取 | 打印分辨率低于 300 dpi 或对比度不足 | 使用 300 dpi 或更高的哑光纸打印，确保前景颜色足够深 |
| 输出文件损坏 | 目标文件夹缺少写入权限 | 确认 `YOUR_DIRECTORY` 已存在且可写 |

**专业提示**：当需要无损质量进行后续处理（例如嵌入 PDF）时，始终将条形码保存为 PNG。PNG 能保留精确像素值，而 JPEG 会引入压缩伪影，可能影响条形码可读性。

## 完整可运行示例

下面是一个完整的控制台应用程序示例，演示一次性生成三种条形码。将代码复制到新的 .NET 控制台项目中并执行。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**预期输出**

运行程序后，会在 `Barcodes` 文件夹内生成三个 PNG 文件：

* `Pdf417Basic.png` – 标准 PDF417 条形码，使用三列。  
* `CompactPdf417.png` – 相同数据的截断（紧凑）模式，略微更短。  
* `MicroPdf417.png` – 高密度 Micro PDF417 变体，使用四列。

使用任意图像查看器打开这些文件，即可看到独特的堆叠式条形码外观。

## 接下来该学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您进一步掌握 API 功能并探索在项目中的其他实现方式。

- [如何使用 Aspose.BarCode 创建紧凑 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 PDF417 条形码中设置错误级别 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [在 C# 中创建 PDF417 条形码元数据 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}