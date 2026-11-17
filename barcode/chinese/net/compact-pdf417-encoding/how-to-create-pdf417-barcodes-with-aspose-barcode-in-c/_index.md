---
category: general
date: 2026-11-17
description: 如何使用 Aspose.BarCode 创建 PDF417 条码——一步一步的指南，并展示如何在 C# 中创建 Aspose 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: zh
lastmod: 2026-11-17
og_description: 如何使用 Aspose.BarCode 创建 PDF417 条形码。本教程将逐步指导您创建条形码、配置 Macro PDF417 元数据并保存图像。
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: 使用 Aspose.BarCode 创建 PDF417 条形码的完整 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: 如何在 C# 中使用 Aspose.BarCode 创建 PDF417 条形码
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码

如果您需要为库存、运输或文档跟踪 **创建 PDF417** 条形码，本指南将向您展示使用 Aspose.BarCode 的完整步骤。您将看到如何创建条形码、配置 Macro PDF417 字段，并将结果导出为 PNG 图像——全部在一个可运行的 C# 程序中。

在需要以紧凑、机器可读的格式编码大量数据时，创建 PDF417 条形码是常见需求。Aspose.BarCode 使该过程简便，允许您微调尺寸、列数以及完整的 Macro PDF417 元数据集。完成本教程后，您将拥有一个完整的、独立的示例，可直接嵌入任何 .NET 项目中。

## 前置条件

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7+）。
* 有效的 Aspose.BarCode for .NET 许可证（免费评估版可用于测试）。
* Visual Studio 2022、VS Code 或任何兼容 C# 的 IDE。
* 对 C# 语法和 `using` 语句有基本了解。

> **小贴士：** 如果在没有许可证的情况下运行示例，Aspose 会在生成的图像上添加一个小水印。

## 如何使用 Aspose.BarCode 创建 PDF417 条形码

以下章节将实现过程分为四个清晰的步骤。每一步都包含代码片段、对代码为何必要的 **解释**，以及可应用于您项目的实用技巧。

### 步骤 1：设置项目并导入 Aspose.BarCode

创建一个新的控制台项目并添加 Aspose.BarCode NuGet 包：

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

然后打开 `Program.cs` 并添加所需的命名空间：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*为何重要：* 导入 `Aspose.BarCode.Generation` 可让您使用 `BarcodeGenerator` 和 `EncodeTypes` 枚举，它们是条形码创建的核心类。

### 步骤 2：为 Macro PDF417 初始化 `BarcodeGenerator`

`BarcodeGenerator` 构造函数接受条形码类型和要编码的文本。对于 Macro PDF417，使用 `EncodeTypes.MacroPdf417`。

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*为何重要：* `using` 语句确保及时释放非托管资源（如 GDI+ 句柄），防止长时间运行的服务出现内存泄漏。

### 步骤 3：配置外观和 Macro PDF417 元数据

#### 3.1 调整视觉参数

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 填充 Macro PDF417 字段

Macro PDF417 允许您将大型文档拆分为多个条形码段。以下字段为可选，但在物流或文档管理系统中常常需要。

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*这些字段的用途：*
* **FileID** 将所有段关联在一起，以便重建。
* **SegmentID** 和 **SegmentsCount** 让扫描仪了解顺序以及何时完成整个系列。
* **Checksum** 和 **FileSize** 提供快速完整性检查，无需解码整个负载。

> **注意：** `MacroPdf417FileID` 必须在每个逻辑文档中唯一。对不相关的文件重复使用相同 ID 可能导致重建错误。

### 步骤 4：保存条形码图像

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*为何使用 PNG？* PNG 能保留精确的像素数据而不产生压缩伪影，这对于依赖清晰边缘的条形码扫描仪非常理想。

### 完整、可运行的示例

将所有内容组合在一起，以下是您可以立即编译并运行的完整程序：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**预期输出：** 运行程序后，您将在项目文件夹中看到 `MacroPdf417.png`。打开该图像会显示一个密集、高对比度的 PDF417 条形码，编码了 “Sample text for PDF417” 以及您提供的宏元数据。

## 常见问题与边缘情况处理

| Question | Answer |
|----------|--------|
| *我可以在循环中生成多个段吗？* | 可以。每次迭代递增 `MacroPdf417SegmentID`，保持 `MacroPdf417FileID` 不变，并在知道段的总数后再更新 `MacroPdf417SegmentsCount`。 |
| *如果数据超过单个 PDF417 符号怎么办？* | Macro |

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中使用 Aspose.BarCode 创建宏 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 中使用 Aspose.BarCode 创建微 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [如何使用 Aspose.BarCode 创建条形码 – 紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}