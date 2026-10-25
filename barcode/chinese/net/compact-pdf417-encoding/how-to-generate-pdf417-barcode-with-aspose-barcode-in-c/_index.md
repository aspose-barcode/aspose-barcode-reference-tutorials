---
category: general
date: 2026-10-24
description: 学习如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条码，采用紧凑设置并控制条码的 XDimension。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: zh
lastmod: 2026-10-24
og_description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 条码。请参阅本完整指南，了解如何创建紧凑的 PDF417 图像、控制
  XDimension 并设置列数。
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: 使用 Aspose.BarCode 生成 PDF417 条码 – C# 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: 如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 生成 PDF417 条码

如果您需要在 .NET 应用程序中**生成 PDF417 条码**，本指南提供了一个完整、可直接运行的解决方案。您将看到 Aspose.BarCode 如何简化该过程，同时让您对**紧凑 PDF417**、**条码 XDimension**和**PDF417 列数**进行细粒度控制。

创建条码是库存系统、票务平台和文档工作流的常见需求。完成本教程后，您将拥有一个独立的 C# 程序，能够生成清晰的 PNG 格式 PDF417 条码图像，可嵌入任何 UI 或打印在标签上。

## 您需要的环境

- .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.6+）
- Visual Studio 2022 或您喜欢的任何 C# 编辑器
- 有效的 Aspose.BarCode for .NET 许可证（免费试用可用于开发）
- 对 C# 语法的基本了解

> **专业提示：** 如果您正在评估 Aspose.BarCode，请从官方网站下载试用版并将 NuGet 包 `Aspose.BarCode` 添加到项目中。试用版会在生成的图像上添加一个小水印，激活许可证后水印即会消失。

## 第 1 步：安装 Aspose.BarCode NuGet 包

在解决方案文件夹中打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该命令会拉取最新的稳定版本（截至 2026 年 10 月，版本 23.12）。添加该包后即可使用 `Aspose.BarCode.Generation` 命名空间来**生成 PDF417 条码**图像。

## 第 2 步：创建基础 C# 控制台项目

如果还没有项目，请创建一个：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

打开 `Program.cs`。该骨架已包含一个 `Main` 方法，我们将在其中放置条码生成代码。

## 第 3 步：初始化条码生成器

首先，导入所需的命名空间：

```csharp
using Aspose.BarCode.Generation;
```

然后，在 `Main` 中实例化 `BarcodeGenerator`，使用 PDF417 符号并传入要编码的数据：

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

该字符串包含 Unicode 字符，以演示 Aspose.BarCode 能正确处理非 ASCII 输入。如果只需要 ASCII，请将文本替换为任意普通字符串。

## 第 4 步：调整条码 XDimension（模块大小）

**条码 XDimension** 决定最小条（模块）的宽度。以像素为单位设置可让您对最终图像尺寸实现像素级精确控制：

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

将值设为 `2` 像素可在不牺牲扫描可靠性的前提下生成紧凑图像。需要更大条码时增大该值，极度密集布局时可减小。

## 第 5 步：配置紧凑 PDF417 选项

两个 PDF417 专属设置会显著影响视觉占用：

| 设置 | 含义 | 紧凑输出的典型值 |
|------|------|-------------------|
| `Columns` | 数据列数 | `3` |
| `Truncate` (compact mode) | 去除右侧安静区并减少行数 | `true` |

按如下方式应用：

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

将 **PDF417 columns** 设置为 `3` 并将 `Truncate = true` 组合使用，可生成*紧凑 PDF417* 条码，既能在标准标签上良好适配，又能被大多数扫描仪读取。

## 第 6 步：保存条码图像

最后，将条码写入磁盘。示例保存为 PNG，但 Aspose.BarCode 同样支持 BMP、JPEG、GIF、TIFF 和 SVG：

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`BarCodeImageFormat.Png` 常量指示库生成无损 PNG，适合后续处理或打印。

## 完整、可运行的源代码

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

运行程序后会在项目根目录生成 `CompactPdf417.png`。使用任意图像查看器打开文件，您将看到一个紧凑排列的 PDF417 条码，编码的字符串为 *Åspóse.Barcóde©*。

![使用 Aspose.BarCode 生成的 PDF417 条码截图](placeholder-image.png "生成的 PDF417 条码")

*图片替代文字：使用 Aspose.BarCode 生成的 PDF417 条码截图* – 该替代文字包含了用于可访问性和 SEO 的主要关键词。

## 验证结果

1. 打开 PNG 文件。条码应由三列垂直数据列组成，布局紧凑（右侧无额外安静区）。
2. 使用支持 PDF417 的智能手机条码扫描器扫描图像。解码后的文本必须与原始输入字符串一致。
3. 若扫描失败，可尝试将 `XDimension.Pixels` 提升至 `3` 或 `4`。更大的模块有助于在低分辨率设备上提升可读性。

## 常见变体与边缘情况

### 1. 更改图像格式

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG 为矢量格式，可在任意缩放级别保持条码清晰——适用于网页。

### 2. 编码大量数据

PDF417 可存储约 1.1 KB 文本。当负载超过三列的容量时，库会自动增加行数。若想保持条码紧凑，可：

- 缩短数据长度（例如使用标识符而非完整消息）
- 增加 **PDF417 columns** 数量（例如 `generator.Parameters.Barcode.Pdf417.Columns = 5;`）

### 3. 使用许可证去除试用水印

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

将许可证文件放置在可执行文件旁。授权后，生成的图像将不再包含水印。

### 4. 处理异常

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

常见错误包括写入权限不足或不支持的图像格式。

## 为什么这些设置很重要

- **条码 XDimension** – 控制每根条的视觉粗细。过小导致条码不可读，过大则浪费空间。
- **PDF417 columns** – 列数越少条码越窄，但会增加行数。

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generate PDF417 barcode with compact settings in C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}