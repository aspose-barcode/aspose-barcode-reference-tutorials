---
category: general
date: 2026-10-28
description: 使用 Aspose.BarCode 生成自定义文本条形码——面向 .NET 开发者的逐步创建 Aspose 条形码图像指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: zh
lastmod: 2026-10-28
og_description: 如何使用 Aspose.BarCode 在 .NET 中生成带自定义文本的条形码。请遵循本完整指南，创建并保存 Macro PDF417
  条码。
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: 如何使用自定义文本生成条形码 – Aspose.BarCode 教程
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: 如何使用 Aspose.BarCode for .NET 生成带自定义文本的条形码
url: /zh/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 生成带自定义文本的条形码

在需要将标识符、时间戳或其他元数据直接嵌入可视化码时，生成带自定义文本的条形码是常见需求。本教程演示如何使用 **Aspose.BarCode** 库 for .NET 生成携带自定义文本和完整元数据集的 Macro PDF417 条形码。

您将学习如何配置生成器、应用自定义文本、设置 Macro PDF417 特定字段，并将结果保存为 PNG 图像。无需外部工具——只需 Aspose.BarCode NuGet 包和 .NET 开发环境。

## 前提条件

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 包 (`Install-Package Aspose.BarCode`)  

这些前提条件可确保代码编译并运行，无需额外配置。

## 步骤 1：安装 Aspose.BarCode 包

在项目文件夹中打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该命令将最新稳定版的 Aspose.BarCode 添加到项目中，使您能够访问 `BarcodeGenerator` 类及所有相关参数。

## 步骤 2：创建新的控制台应用程序

创建一个最小的控制台应用程序来承载条形码生成逻辑：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### 每行代码的重要性

* **EncodeTypes.MacroPdf417** – 选择 Macro PDF417 符号集，支持分段数据和元数据。  
* **XDimension.Pixels** – 控制每个模块的大小；2 像素的值可产生清晰、可扫描的图像。  
* **Pdf417.Columns** – 减少整体宽度，使条形码在打印标签时更紧凑。  
* **MacroPdf417* properties** – 将文件级信息（ID、段计数、时间戳等）直接嵌入条形码。此功能是 Macro PDF417 所独有，常用于物流或文档管理系统。  
* **Save(..., BarCodeImageFormat.Png)** – 写入无损 PNG 文件，保留条形码的锐利边缘，以确保可靠扫描。

## 步骤 3：运行程序并验证输出

构建并执行控制台应用程序：

```bash
dotnet run
```

程序会在项目工作目录中生成 `ExtPDF417Meta.png`。打开该文件可看到一个 Macro PDF417 条形码，编码了文本 **“Åspóse.Barcóde©”** 以及您提供的元数据。

**预期输出** – 与下图类似的 PNG 图像：

![如何生成条形码示例输出 PNG 图像，展示 Macro PDF417 条形码](ExtPDF417Meta.png)

*图像的 alt 文本（“如何生成条形码示例输出 PNG 图像”）强化了主要关键词，以提升可访问性和 SEO。*

## 常见变体和边缘情况

### 使用不同的条形码类型

如果需要为 QR 码而非 Macro PDF417 **生成条形码自定义文本**，请将 `EncodeTypes.MacroPdf417` 替换为 `EncodeTypes.QR`。其余参数结构保持不变，但 QR 码不支持 Macro 元数据字段。

### 处理 Unicode 字符

示例已包含 Unicode 字符（`Å`, `ó`, `©`）。Aspose.BarCode 开箱即支持 UTF‑8 输入，但您应确保源文件以 UTF‑8 编码保存，以避免编译时警告。

### 保存为其他图像格式

Aspose.BarCode 除 PNG 外还支持 BMP、JPEG、TIFF 和 SVG。相应地更改 `BarCodeImageFormat` 枚举值：

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### 大数据集

Macro PDF417 可以将数据拆分为多个段。当文本超出单个段的容量时，递增 `MacroPdf417SegmentID` 并在所有生成的部分中保持 `MacroPdf417SegmentsCount` 一致。此方法在 **create barcode aspose** 场景中至关重要，因为负载大于单个条形码所能容纳的容量。

### 错误处理

将生成逻辑包装在 try‑catch 块中，以捕获运行时问题，如无效的文件路径或不支持的字符：

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## 可靠条形码生成的专业技巧

* **Validate the barcode** 在创建后使用 `BarCodeReader` 验证。此额外步骤确认编码数据符合您的预期。

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Keep X‑dimension between 2 – 4 pixels** 对大多数扫描仪而言。较小的值可能在低分辨率设备上产生不可读的图像。

* **Avoid very long file names** 在 `MacroPdf417FileName` 中。规范将该字段限制为 32 个字符。

* **Use consistent timestamps** (UTC) 在生成多个段时使用一致的时间戳，以简化后续处理。

## 结论

现在，您已经了解如何使用 Aspose.BarCode for .NET **生成带自定义文本的条形码**，如何配置 Macro PDF417 元数据，以及如何将结果保存为 PNG 图像。完整的可运行示例演示了每个必需步骤——从安装 NuGet 包到处理 Unicode 字符再到保存输出。

从这里您可以：

* **Generate barcode custom text** 用于其他符号集（QR、DataMatrix 等）  
* **Create barcode Aspose** 工作流，以批量处理数千张图像  
* 将条形码生成代码集成到 ASP.NET Core 服务、Windows 服务或 Azure Functions 中  

尝试不同的参数，探索更多元数据字段，并将条形码整合到您的文档自动化流水线中。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于所示技术进行扩展。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [如何使用 Aspose 创建 PDF417 条形码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [使用 Aspose.BarCode 从文本生成条形码 – C# 指南](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [如何在 .NET 中使用 Aspose.BarCode 创建 DataMatrix 代码文本](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}