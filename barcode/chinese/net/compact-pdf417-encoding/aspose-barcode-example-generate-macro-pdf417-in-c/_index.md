---
category: general
date: 2026-10-09
description: 了解如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码——生成具备完整 metadata 支持的 Macro
  PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: 了解如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码——生成具备完整 metadata 支持的 Macro
  PDF417，包括 file ID、segment data、timestamp 等。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: 如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: 如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条形码
url: /zh/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中创建 PDF417 条码

如果您需要快速且可靠地 **create PDF417 barcode C#**，本教程将使用 Aspose.BarCode 带您完成整个过程。您将看到所有必需的设置，从基本尺寸到完整的 Macro PDF417 元数据字段，并最终得到可用于下游处理的 PNG 图像。

## 快速答案
- **哪个库生成 PDF417 条码？** Aspose.BarCode for .NET.
- **示例输出的格式是什么？** A loss‑less PNG image.
- **我需要许可证吗？** A free trial works for the sample; a commercial license is required for production.
- **支持哪个 .NET 版本？** .NET 6.0 or later.
- **我可以向条码添加元数据吗？** Yes – Macro PDF417 supports file ID, segment count, timestamps, and more.

## PDF417 条码是什么？
PDF417 条码是一种堆叠线性符号，可在每个符号中编码约 1 KB 的数据，并支持用于多段文件的可选宏元数据。它由多行堆叠的线性图案组成，既提供高数据容量，又能被标准 2‑D 扫描仪读取。该格式还包括错误纠正级别以提高可靠性，可选的宏功能允许将大文件拆分为多个条码，并通过元数据帮助重新组装。

## 为什么使用 Aspose.BarCode 生成 PDF417？
Aspose.BarCode 支持 **超过 50 种条码符号**，并且能够生成最多 **2 000 列** 的 Macro PDF417 条码，处理大于 **10 MB** 的文件而无需将整个负载加载到内存中。此量化能力确保高吞吐量的企业场景顺利运行，并提供广泛的自定义选项。

## 先决条件

在开始之前，请确保您已具备：

- .NET 6.0（或更高）已安装  
- Visual Studio 2022 或任何兼容 C# 的 IDE  
- 有效的 **Aspose.BarCode for .NET** 许可证（免费试用适用于本示例）  

将 Aspose.BarCode NuGet 包添加到您的项目中：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中创建 PDF417 条码？

`BarcodeGenerator` 是用于创建条码图像的主要类。  
`EncodeTypes.MacroPdf417` 选择用于条码生成的 Macro PDF417 符号。  
`Save` 将生成的条码写入图像文件。

使用 `EncodeTypes.MacroPdf417` 枚举和目标文本加载 `BarcodeGenerator`，然后调用 `Save` —— 这就是三行代码完成的完整创建流程。生成器会自动处理 Unicode，`using` 语句确保在图像保存后释放非托管资源。

### 步骤 1：创建条码生成器 C# 实例

`BarcodeGenerator` 类用于创建和配置条码图像。  

使用 `EncodeTypes.MacroPdf417` 枚举值和要编码的文本实例化 `BarcodeGenerator`。文本可以包含 Unicode 字符，库会自动处理。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*为什么这很重要*：`EncodeTypes.MacroPdf417` 告诉引擎生成 Macro PDF417 符号，支持分段数据和额外的文件级元数据。`using` 语句确保在图像保存后释放非托管资源。

### 步骤 2：定义条码基本外观

`XDimension.Pixels` 设置每个条码模块的像素大小。

Macro PDF417 条码由方形模块组成。控制模块大小和列数会影响可读性和文件大小。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*为什么这很重要*：`XDimension.Pixels` 决定视觉密度；2 像素的值在屏幕显示时效果良好且保持图像小巧。根据布局约束调整列数——列数越多，条码越宽、越短。

### 步骤 3：设置 Macro PDF417 特定元数据

`MacroPdf417FileID` 标识所有条码段所属的文件。

Macro PDF417 在标准 PDF417 格式上扩展了字段，使得可以从多个条码段重建大文件。每个字段都是可选的，但设置它们可展示 API 的全部功能。

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*为什么这很重要*：  
- `MacroPdf417FileID` 将属于同一逻辑文件的所有段链接在一起。  
- `MacroPdf417SegmentID` 和 `MacroPdf417SegmentsCount` 使解码器能够正确重新排序片段。  
- `MacroPdf417Checksum` 提供快速完整性检查，无需解码整个负载。  
- `MacroPdf417FileSize` 和 `MacroPdf417TimeStamp` 让下游系统验证重建文件是否与原始文件匹配。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` 在物流或文档交换场景中很有用。  
- 将 `MacroPdf417Terminator` 设置为 `Set` 将此条码标记为最后一个段，简化重建算法。

### 步骤 4：保存生成的条码图像

`Save` 将条码图像写入指定的文件路径。

最后，将条码写入 PNG 文件。您可以选择任何受支持的格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*为什么这很重要*：PNG 保留无损像素数据，确保扫描仪读取您配置的精确模块模式。更改格式可能会影响视觉质量和文件大小。

#### 预期输出

运行完整程序会生成名为 **ExtPDF417Meta.png** 的文件。打开图像可看到一个矩形的 Macro PDF417 条码，已编码文本 “Åspóse.Barcóde©”，视觉密度与您设置的 2 像素 X 维度相匹配。使用兼容 PDF417 的阅读器扫描该图像会返回步骤 3 中定义的所有元数据字段。

## 完整工作示例

将下面的代码复制到新的控制台项目中（`dotnet new console`），并将 `YOUR_DIRECTORY` 替换为您机器上存在的绝对或相对路径。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

运行程序（`dotnet run`）。执行后，确认 PNG 文件出现在您指定的位置。使用任何支持 Macro PDF417 的条码读取应用程序，确认元数据已正确嵌入。

## 常见变体和边缘情况

- **不同的图像格式**：如果下游系统偏好其他格式，将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Tiff`。  
- **更改模块大小**：更大的 `XDimension.Pixels` 值可提高低分辨率扫描仪的扫描可靠性，但会增加图像大小。  
- **多个段**：要生成多段文件，生成一系列条码，为每个条码递增 `MacroPdf417SegmentID`，并保持 `MacroPdf417FileID` 不变。只有最后一个段应设置 `MacroPdf417Terminator`。  
- **Unicode 支持**：生成器会自动编码 Unicode 字符；如果从外部文件读取，请确保源字符串使用 UTF-8 编码。  
- **错误处理**：将 `using` 块包装在 try‑catch 中，以捕获 `BarCodeException`，处理无效参数（例如列数超出范围）。

## 专业技巧

- **性能**：在使用相同设置创建大量条码时，复用单个 `BarcodeGenerator` 实例；仅在保存之间更改 `CodeText` 属性。  
- **文件大小估算**：`MacroPdf417FileSize` 字段应与原始负载的字节数匹配；不匹配可能导致下游验证失败。  
- **测试**：使用 Aspose 内置解码器 (`BarCodeReader`) 和第三方扫描仪验证生成的条码，以确保互操作性。

## 结论

本 **Aspose.BarCode** 示例展示了如何 **create PDF417 barcode C#** 并完整支持 Macro 元数据，为构建可靠的基于条码的数据交换管道提供了坚实基础。

## 接下来应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方法。

- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 为 Code 16K 创建条码安静区](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 为 ITF-14 创建条码安静区](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**最后更新：** 2026-10-09  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose 在 C 中生成 Pdf417 条码图像](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条码](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [条码生成器教程：如何生成 Pdf417 条码](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}