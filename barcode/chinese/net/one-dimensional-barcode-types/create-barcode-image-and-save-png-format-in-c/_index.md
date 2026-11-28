---
category: general
date: 2026-11-27
description: 在 C# 中使用 Aspose.BarCode 创建条形码图像并保存为 PNG 格式 – 步骤指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: zh
lastmod: 2026-11-27
og_description: 使用 Aspose.BarCode 在 C# 中创建条形码图像并保存为 PNG 格式。按照本教程一步步生成 Macro PDF417
  条码。
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: 在 C# 中创建条形码图像并保存为 PNG 格式 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 在 C# 中创建条形码图像并保存为 PNG 格式
url: /zh/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建条形码图像并保存为 PNG 格式

如果您需要在 .NET 应用程序中 **创建条形码图像**，本指南将向您展示如何使用 Aspose.BarCode 生成 Macro PDF417 条形码并 **以 PNG 格式保存图像**。您将获得完整的可运行示例以及每个设置的说明，方便您根据自己的需求进行调整。

生成条形码不仅仅是调用一个方法；您还必须配置模块大小、宏参数以及输出格式。阅读完本教程后，您将了解每个属性的作用、常见边缘情况的处理方式，以及如何验证 PNG 文件是否正确写入。

## 您需要的环境

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.6+）
- Aspose.BarCode for .NET（可通过 NuGet 获取：`Install-Package Aspose.BarCode`）
- Visual Studio 2022 或 Visual Studio Code 等 IDE
- 对将要保存 PNG 文件的文件夹拥有写入权限

## 第一步：初始化条形码生成器

第一步是创建一个 `BarcodeGenerator` 实例，指定 `EncodeTypes.MacroPdf417` 编码类型以及要编码的文本。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**为什么重要：**  
`EncodeTypes.MacroPdf417` 告诉库使用 PDF417 的宏变体，该变体支持文件分段和额外的元数据。构造函数同时接收将在条形码中编码的可读文本。

## 第二步：定义模块大小（X‑dimension）

X‑dimension 控制单个条形码模块（最小的黑白单元）的宽度。`2` 像素的值在屏幕显示的 PNG 中效果良好。

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**实用提示：**  
如果计划打印条形码，请增大像素值（例如 `4` 或 `5`），以避免在低分辨率打印机上出现模糊。

## 第三步：配置 PDF417 宏参数

Macro PDF417 添加了若干可选字段，用于标识源文件、分段顺序和完整性校验。下面是一组常用的完整参数，您可以根据需要省略其中任何一个。

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**这些字段为何有用：**  

| 参数 | 用途 |
|-----------|---------|
| `Columns` | 控制条形码宽度；列数越少，条形码越高。 |
| `MacroPdf417FileID` | 将所有分段关联在一起的唯一标识符。 |
| `MacroPdf417SegmentID` | 当前分段在整个文件中的位置。 |
| `MacroPdf417SegmentsCount` | 分段总数；用于重建文件时必需。 |
| `MacroPdf417FileName` | 可读的文件名，可由扫描应用显示。 |
| `MacroPdf417Checksum` | 帮助接收方验证数据完整性（CCITT‑16）。 |
| `MacroPdf417FileSize` | 原始文件的可选大小提示。 |
| `MacroPdf417TimeStamp` | 原始文件创建的时间戳。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 用于路由或所有权的元数据。 |
| `MacroPdf417Terminator` | 表示此分段是否为最后一个（`Set`）或中间分段（`Unset`）。 |

**边缘情况：** 如果生成的是单段条形码，请将 `MacroPdf417SegmentsCount` 设置为 `1`，并将 `MacroPdf417Terminator` 设置为 `Unset`。库会自动省略不适用的分段相关字段。

## 第四步：将生成的条形码保存为 PNG 图像

最后，使用 `Save` 方法并传入文件路径以及 `BarCodeImageFormat.Png` 枚举值。该方法会以无损 PNG 格式将图像写入磁盘。

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**为什么选择 PNG？**  
PNG 能保留精确的像素值，这对依赖锐利对比度的条形码扫描器至关重要。JPEG 压缩会产生可能破坏条形码图案的伪影。

### 验证输出

程序运行后，您应在执行目录中看到名为 `ExtPDF417Meta.png` 的文件。使用任意图像查看器打开，它会显示一个密集的矩形条形码。您可以使用支持 PDF417 宏的移动条形码阅读器扫描该图像，应用通常会显示嵌入的元数据（文件 ID、分段号等）。

## 常见陷阱及规避方法

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| 条形码模糊 | 对所选 DPI 来说 X‑dimension 太低 | 增大 `XDimension.Pixels` 或在更高 DPI（`generator.Parameters.ImageResolution`）下渲染。 |
| 扫描器报 “checksum error” | `MacroPdf417Checksum` 值不正确 | 通过省略该属性让 Aspose 自动计算校验和，或确保值符合 CCITT‑16 算法。 |
| PNG 文件为空或未创建 | 输出路径无效或缺少写入权限 | 使用 `Path.Combine` 并指向已知的可写文件夹（例如 `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`）。 |
| 宏字段被忽略 | `EncodeTypes` 使用了普通 `Pdf417` 而非 `MacroPdf417` | 确认构造函数中使用的是 `EncodeTypes.MacroPdf417`。 |

## 完整可运行示例

下面是可以直接复制到控制台应用程序中的完整代码。它在 .NET 6.0 下编译，并生成上述 PNG 文件。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**预期控制台输出：**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

打开 `ExtPDF417Meta.png` 即可看到清晰的 Macro PDF417 条形码，准备就绪供扫描。

## 后续步骤

- **更改图像格式** – 如需其他文件类型，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Bmp`。请记住 JPEG 会引入压缩伪影，可能影响扫描可靠性。
- **调整分辨率** – 使用

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方案。每个资源均提供完整的可运行代码示例和逐步说明。

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}