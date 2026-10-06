---
category: general
date: 2026-08-19
description: 快速在 C# 中生成 PDF417 条码。学习如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条码，使用紧凑模式和自定义设置。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: zh
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 条码。本教程展示了如何在紧凑模式下生成 PDF417 条码、设置
  X 维度并保存为 PNG。
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: 在 C# 中生成 PDF417 条码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 在 C# 中生成 PDF417 条码 – 完整指南（紧凑布局）
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中生成 PDF417 条码 – 完整指南

如果您需要在 .NET 应用程序中 **生成 PDF417 条码**，本教程将准确展示如何操作。您将看到一个简洁、可用于生产环境的示例，能够创建紧凑的 PDF417 条码、自定义 X 维度，并将结果保存为 PNG 图像。

在需要将大量数据（例如票务信息、装运清单或身份证件）编码为机器可读格式时，生成 PDF417 条码是常见需求。使用 Aspose.BarCode 可让过程变得直截了当，代码兼容 .NET 6+ 或 .NET Framework 4.7.2 及更高版本。

在本指南中，您将：

* 安装 Aspose.BarCode NuGet 包。
* 编写一个独立的 C# 程序，**生成 PDF417 条码**，使用小列数和紧凑（截断）模式。
* 调整条码宽度（X‑dimension）以获得更清晰的渲染。
* 将条码保存为 PNG 文件。
* 探索变体、边缘情况以及最佳实践技巧。

## 前提条件

在开始之前，请确保您具备：

* 已安装 .NET 6 SDK 的 Visual Studio 2022（或任意 C# IDE）。
* 可访问互联网以下载 **Aspose.BarCode** NuGet 包。
* 对将保存 PNG 文件的文件夹拥有写入权限。

无需额外库；Aspose.BarCode 在内部处理图像编码。

## 第 1 步：添加 Aspose.BarCode 包

在 Visual Studio 中打开项目，右键单击解决方案，选择 **Manage NuGet Packages**。搜索 `Aspose.BarCode` 并安装最新的稳定版本。

```bash
dotnet add package Aspose.BarCode
```

> **专业提示：** 保持包的最新状态。新版本通常包含性能改进并支持最新的 .NET 运行时。

## 第 2 步：创建最小化的控制台应用程序

如果还没有项目，创建一个新的 C# 控制台项目：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

将 `Program.cs` 的内容替换为下面的完整示例。该程序演示了 **如何在 C# 中生成 PDF417 条码** 的全过程。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 为什么每行代码都很重要

* **`EncodeTypes.Pdf417`** – 选择 PDF417 编码方式，支持约 1.1 KB 的数据。
* **`XDimension.Pixels = 2`** – 设置基础条宽。数值越小条码越细，数值越大在低分辨率设备上可提升可读性。
* **`Pdf417.Columns = 3`** – 限制列数，迫使生成器使用更多行，从而得到更高但更窄的条码。
* **`Pdf417.Truncate = true`** – 启用紧凑模式，去除停止图案并在不失去数据完整性的前提下缩小图像。
* **`Save(..., BarCodeImageFormat.Png)`** – 将文件写入 PNG 格式。也可以根据下游需求选择 `Jpeg`、`Bmp` 或 `Svg`。

运行程序：

```bash
dotnet run
```

您应该会在控制台看到确认文件位置的输出，文件夹中会出现 `CompactPdf417.png`。打开该 PNG 可看到清晰、紧凑的 PDF417 条码，已编码 Unicode 字符串。

## 第 3 步：验证条码（可选但推荐）

为确保条码可被读取，您可以使用智能手机上的任意标准 PDF417 扫描应用或桌面解码库。解码后的文本应与原始 `data` 字符串完全一致，包括特殊字符。

如果遇到解码问题：

* 将 `XDimension` 提高到 3 或 4 像素。
* 减少列数（例如设为 `Columns = 2`）。
* 关闭 `Truncate`（`Truncate = false`）以添加停止图案。

这些调整在尺寸与可读性之间进行权衡，适用于低分辨率打印机或扫描仪。

## 第 4 步：探索常见变体

### 4️⃣ 为打印生成高密度 PDF417

如果需要在小标签上放置条码，可增加列数并降低 X‑dimension：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ 将输出格式改为 SVG 以实现矢量缩放

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG 输出可在不失真情况下任意缩放，适合响应式网页。

### 6️⃣ 编码二进制数据（例如字节数组）

若需嵌入二进制负载，先将其转换为 Base64 字符串：

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

条码现在携带二进制信息，解码器需要逆向执行 Base64 步骤。

## 常见问题

| 问题 | 回答 |
|----------|--------|
| **我可以不使用 Aspose 生成 PDF417 吗？** | 可以，其他库如 ZXing.Net 或 Dynamsoft 也能实现，但 Aspose.BarCode 提供更丰富的布局控制（列数、截断）和更好的 Unicode 处理。 |
| **最大数据长度是多少？** | PDF417 最多可编码 1,108 字节（≈ 1 KB）的二进制数据。如果超过此限制，建议将数据拆分到多个条码中。 |
| **紧凑模式符合标准吗？** | 截断 PDF417 属于 ISO/IEC 15438 规范的一部分，得到广泛支持，但请确认目标扫描仪明确支持该模式。 |
| **如何更改背景颜色？** | 在保存之前设置 `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` 并 `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;`。 |

## 结论

现在，您已经掌握了使用 Aspose.BarCode **在 C# 中生成 PDF417 条码** 的方法，了解了如何微调 X‑dimension、启用紧凑模式，并将结果导出为 PNG 图像。完整、可运行的示例可直接复制到任意 .NET 项目中，而本文展示的变体则帮助您根据打印、网页或二进制负载场景进行适配。

接下来可以进一步探索：

* 将条码生成集成到 ASP.NET Core API 中，按需返回图像。
* 在同一标签上同时放置 PDF417 与 QR 码，实现双格式扫描。
* 使用 Aspose.BarCode 的 `Reader` 类对生成的图像进行解码，以编程方式验证数据。

祝编码愉快，尽情享受 **生成 PDF417 条码** 解决方案为您的应用带来的灵活性！

## 接下来应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步说明。

- [如何使用 Aspose.BarCode 创建条码 – 紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 生成带有补充空格自定义的条码图像](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义宽高比的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}