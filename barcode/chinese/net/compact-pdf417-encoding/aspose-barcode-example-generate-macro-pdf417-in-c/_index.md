---
category: general
date: 2026-08-09
description: Aspose 条码示例展示如何使用 C# 条码生成器创建具有完整元数据支持的宏 PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: zh
lastmod: 2026-08-09
og_description: Aspose 条形码示例演示如何使用 C# 条形码生成器生成包含文件 ID、段数据、时间戳及其他元数据的 Macro PDF417
  条码。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose 条码示例 – 使用 C# 创建宏 PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: Aspose 条形码示例：在 C# 中生成宏 PDF417
url: /zh/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose 条形码示例：在 C# 中生成 Macro PDF417

如果您需要一个 **aspose barcode example** 来创建 Macro PDF417 条形码，本指南将展示如何使用 **barcode generator C#** 实现。您将看到所有必需的设置，从基本尺寸到完整的 Macro PDF417 元数据字段，最终得到一张可供后续处理的 PNG 图像。

本教程涵盖完整工作流，解释每个参数的重要性，并提供可直接运行的代码示例。无需外部引用；复制代码、调整数值后即可立即运行。

## 前置条件

在开始之前，请确保您已具备：

- 已安装 .NET 6.0（或更高版本）  
- Visual Studio 2022 或任意支持 C# 的 IDE  
- 有效的 **Aspose.BarCode for .NET** 许可证（免费试用版即可运行本示例）  

将 Aspose.BarCode NuGet 包添加到项目中：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：创建 barcode generator C# 实例

第一步是使用 `EncodeTypes.MacroPdf417` 枚举值和要编码的文本实例化 `BarcodeGenerator`。文本可以包含 Unicode 字符，库会自动处理。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*为什么重要*：`EncodeTypes.MacroPdf417` 告诉引擎生成 Macro PDF417 符号，该符号支持分段数据和额外的文件级元数据。`using` 语句确保在保存图像后释放非托管资源。

## 第二步：定义条形码的基本外观

Macro PDF417 条形码由方形模块组成。控制模块大小和列数会影响可读性和文件大小。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*为什么重要*：`XDimension.Pixels` 决定视觉密度；2 像素的值在屏幕显示时效果良好且保持图像体积小。根据布局约束调整列数——列数越多，条形码越宽、越短。

## 第三步：设置 Macro PDF417 特定元数据

Macro PDF417 在标准 PDF417 格式基础上扩展了字段，以便从多个条形码段重建大文件。每个字段都是可选的，但设置它们可以展示 API 的全部功能。

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

*为什么重要*：  
- `MacroPdf417FileID` 将属于同一逻辑文件的所有段关联起来。  
- `MacroPdf417SegmentID` 与 `MacroPdf417SegmentsCount` 使解码器能够正确重新排序片段。  
- `MacroPdf417Checksum` 提供快速完整性校验，无需解码整个负载。  
- `MacroPdf417FileSize` 与 `MacroPdf417TimeStamp` 让下游系统验证重建文件是否与原始文件匹配。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` 在物流或文档交换场景中非常有用。  
- 将 `MacroPdf417Terminator` 设置为 `Set` 标记此条形码为最后一个段，简化重建算法。

## 第四步：保存生成的条形码图像

最后，将条形码写入 PNG 文件。您可以选择任何受支持的格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*为什么重要*：PNG 保留无损像素数据，确保扫描仪读取您配置的精确模块图案。更改格式可能会影响视觉质量和文件大小。

### 预期输出

运行完整程序后会生成名为 **ExtPDF417Meta.png** 的文件。打开图像可看到一个矩形的 Macro PDF417 条形码，已编码文本为 “Åspóse.Barcóde©”，视觉密度与您设置的 2 像素 X 维度相匹配。使用兼容 PDF417 的阅读器扫描该图像，可返回第 3 步中定义的所有元数据字段。

## 完整可运行示例

将以下代码复制到新建的控制台项目（`dotnet new console`）中，并将 `YOUR_DIRECTORY` 替换为您机器上存在的绝对或相对路径。

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

运行程序（`dotnet run`）。执行完毕后，确认 PNG 文件出现在您指定的位置。使用任何支持 Macro PDF417 的条形码读取应用，验证元数据已正确嵌入。

## 常见变体和边缘情况

- **不同的图像格式**：如果下游系统偏好其他格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Tiff`。  
- **更改模块大小**：较大的 `XDimension.Pixels` 值可提升低分辨率扫描仪的扫描可靠性，但会增大图像尺寸。  
- **多个段**：若要生成多段文件，生成一系列条形码，为每个条形码递增 `MacroPdf417SegmentID`，并保持 `MacroPdf417FileID` 不变。仅最后一个段应将 `MacroPdf417Terminator` 设置为 `Set`。  
- **Unicode 支持**：生成器会自动编码 Unicode 字符；如果从外部文件读取源字符串，请确保使用 UTF-8 编码。  
- **错误处理**：将 `using` 块包装在 try‑catch 中，以捕获 `BarCodeException`，处理参数无效（例如列数超出范围）等错误。

## 专业技巧

- **性能**：在创建大量具有相同设置的条形码时，复用单个 `BarcodeGenerator` 实例；仅在保存之间更改 `CodeText` 属性。  
- **文件大小估算**：`MacroPdf417FileSize` 字段应与原始负载的字节数相匹配；不匹配可能导致下游验证失败。  
- **测试**：使用 Aspose 内置解码器 (`BarCodeReader`) 与第三方扫描器同时验证生成的条形码，以确保互操作性。

## 结论

此 **aspose barcode example

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方式。每个资源都提供完整的可运行代码示例和逐步解释。

- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 为 Code 16K 条形码创建静默区](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 为 ITF-14 条形码创建静默区](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}