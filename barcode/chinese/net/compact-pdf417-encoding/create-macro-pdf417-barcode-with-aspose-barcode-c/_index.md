---
category: general
date: 2026-09-22
description: 使用 Aspose.BarCode 在 C# 中创建宏 PDF417 条码。一步步学习如何使用 Aspose 生成条码、配置元数据并保存为
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: zh
lastmod: 2026-09-22
og_description: 使用 Aspose.BarCode 在 C# 中创建宏 PDF417 条形码。本指南展示如何使用 Aspose 生成条形码、设置宏元数据并导出图像。
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: 使用 Aspose.BarCode (C#) 创建宏 PDF417 条码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: 使用 Aspose.BarCode (C#) 创建宏 PDF417 条码
url: /zh/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode (C#) 创建宏 PDF417 条码

如果您需要在 .NET 应用程序中 **创建宏 PDF417 条码**，本教程将向您展示如何使用 Aspose.BarCode 完成此操作。您将看到一个完整的、可运行的示例，**使用 Aspose 生成条码**，配置所有宏特定字段，并将结果保存为 PNG 图像。

条码常用于库存、运输或文档跟踪，而 Macro PDF417 变体允许您在条码本身中嵌入额外的文件级元数据。阅读完本指南后，您将能够生成符合 ISO/IEC 15438 标准的完整功能宏 PDF417 条码。

## 您需要的条件

* .NET 6.0 SDK 或更高版本（代码兼容 .NET Core 和 .NET Framework）
* Visual Studio 2022（或任何 C# IDE）
* 可访问 NuGet 的互联网连接，用于获取 Aspose.BarCode 包
* 对 C# 语法有基本了解

这些前提条件可确保代码在无需额外配置的情况下编译通过。

## 步骤 1：安装 Aspose.BarCode NuGet 包

Aspose.BarCode 库提供了本教程中贯穿使用的 `BarcodeGenerator` 类。

```bash
dotnet add package Aspose.BarCode
```

运行该命令会将最新的稳定版本添加到项目文件 (`*.csproj`) 中。该包支持 PDF417、Macro PDF417 以及许多其他符号体系。

## 步骤 2：创建新的控制台项目（可选）

如果您希望从头开始，可以生成一个控制台应用程序：

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

生成的 `Program.cs` 将承载条码生成代码。

## 步骤 3：初始化条码生成器

生成器使用 `EncodeTypes.MacroPdf417` 枚举值以及您想要编码的文本进行创建。Aspose.BarCode 会自动处理 Unicode 字符，因此您可以直接包含带重音的字母或符号。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### 为什么这很重要
`EncodeTypes.MacroPdf417` 告诉库使用 PDF417 的宏版本，从而能够嵌入文件级元数据（文件 ID、段计数等）。文本 `"Åspóse.Barcóde©"` 演示了生成器能够正确编码 UTF‑8 字符。

## 步骤 4：设置条码基本尺寸

PDF417 允许您控制列数和 X‑dimension（单个模块的宽度）。调整这些数值会影响条码的实际尺寸和扫描可靠性。

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – 较小的数值会产生更密集的条码；较大的数值则便于低分辨率扫描仪读取。
* **Columns** – 控制数据列的数量；典型取值范围为 1 到 30。

## 步骤 5：配置 Macro PDF417 元数据

Macro PDF417 包含描述条码所代表文件的额外字段。每个字段都是可选的，但设置它们可以提升与支持宏格式的扫描仪的互操作性。

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 各字段说明

| 属性 | 用途 | 典型范围 |
|----------|---------|---------------|
| **MacroPdf417FileID** | 逻辑文件的唯一标识符，文件可能被拆分到多个条码中。 | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | 当前段的索引（从 0 开始）。 | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | 构成完整文件的段总数。 | 1‑99 |
| **MacroPdf417FileName** | 文件的可读名称。 | 最多 255 个字符 |
| **MacroPdf417Checksum** | 用于错误检测的可选校验和。 | 0‑65535 |
| **MacroPdf417FileSize** | 原始文件的字节大小。 | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | 文件创建或修改的时间戳。 | 任意 `DateTime` |
| **MacroPdf417Addressee** | 目标标识符（例如部门或机器）。 | 自由格式字符串 |
| **MacroPdf417Sender** | 来源标识符（例如公司名称）。 | 自由格式字符串 |
| **MacroPdf417Terminator** | 指示该段是否为最后一段。 | `Set` 或 `Unset` |

**技巧提示：** 如果您将大文件拆分为多个条码，请确保每个段的 `SegmentID` 按顺序递增，并且所有段的 `SegmentsCount` 保持一致。扫描仪依赖这些值来重建原始文件。

## 步骤 6：保存条码图像

Aspose.BarCode 支持多种输出格式（PNG、JPEG、BMP、SVG 等）。PNG 提供无损质量，适合用于测试和文档。

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

运行程序后会在项目的输出目录 (`bin/Debug/net6.0/`) 中生成名为 `ExtPDF417Meta.png` 的文件。使用任意查看器打开该图像，以验证条码是否正确渲染。

## 步骤 7：验证生成的条码（可选）

如果您有 PDF417 扫描应用（移动端或桌面端），扫描保存的 PNG。扫描器应返回：

* 编码文本 `"Åspóse.Barcóde©"`
* 您配置的所有宏字段（文件 ID、段 ID 等）

对于自动化验证，Aspose.BarCode 还提供了 `BarCodeReader` 类：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

此代码片段演示了如何以编程方式读取宏元数据，确认 **使用 Aspose 生成条码** 能够端到端工作。

## 边缘情况和最佳实践

| 情况 | 推荐处理方式 |
|-----------|----------------------|
| **Unicode 字符** | 确保源字符串为 UTF‑8（.NET 默认）。Aspose.BarCode 会自动编码 Unicode，但请验证扫描仪的字符集。 |
| **大文件大小** | Macro PDF417 将文件拆分为最多 99 段。如果文件超过 400 KB，请增加 `SegmentsCount` 并生成多个条码，每个条码的 `SegmentID` 按顺序递增。 |
| **时间戳精度** | 使用 `DateTime.UtcNow` 获取通用时间；某些扫描仪期望使用 UTC。 |
| **校验和验证** | 如果计划在接收端验证完整性，请提供正确的校验和。 |
| **不同图像格式** | 当需要无限可缩放的条码时，使用 `BarCodeImageFormat.Svg` 生成矢量图形。 |
| **性能** | 在生成大量条码时复用同一个 `BarcodeGenerator` 实例；仅在迭代之间更改 `Parameters`。 |

## 完整、可运行的示例

下面是完整的程序，您可以直接复制、粘贴并运行（前提是已安装 NuGet 包）。



## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [Aspose 条码示例：在 C# 中生成 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [在 C# 中创建 PDF417 条码元数据 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [如何使用 Aspose 在 C# 中生成 PDF417 条码图像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}