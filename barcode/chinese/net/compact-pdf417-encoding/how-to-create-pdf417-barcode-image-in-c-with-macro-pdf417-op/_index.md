---
category: general
date: 2026-09-13
description: 学习如何使用 BarcodeGenerator 和 Macro PDF417 选项在 C# 中创建 PDF417 条码图像。逐步代码、技巧及完整示例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: zh
lastmod: 2026-09-13
og_description: 使用 BarcodeGenerator 在 C# 中创建 PDF417 条码图像。按照本详细教程配置 Macro PDF417 选项并保存
  PNG 条码。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: 在 C# 中创建 PDF417 条形码图像 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: 如何在 C# 中使用 Macro PDF417 选项创建 PDF417 条形码图像
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Macro PDF417 选项创建 PDF417 条形码图像

如果您需要在 C# 中**创建 PDF417 条形码图像**，本指南将向您展示如何使用**BarcodeGenerator 类**完成此操作。无论您是构建文档跟踪系统还是对大文件进行编码，下面的分步说明都涵盖了从设置 Macro PDF417 选项到保存最终 PNG 的全部内容。

生成条形码一旦了解关键参数就非常简单。在本教程中，您将学习如何：

* 为 **Macro PDF417** 初始化 `BarcodeGenerator`。
* 调整条形码模块大小（`XDimension`）。
* 配置段特定设置，如文件 ID、段 ID 和校验和。
* 将结果保存为 **条形码图像格式**（PNG），可在任何 UI 中显示。

唯一的前提是拥有 .NET 开发环境（Visual Studio 2022 或更高）以及 Aspose.BarCode for .NET NuGet 包，该包提供了示例中使用的 `BarcodeGenerator` API。

---

## 在 C# 中创建 PDF417 条形码图像 – 概览

创建 PDF417 条形码图像包括四个逻辑步骤：

1. **创建生成器** – 使用 `EncodeTypes.MacroPdf417` 和要编码的数据实例化 `BarcodeGenerator`。  
2. **定义模块大小** – 设置 `XDimension.Pixels` 以控制每个条形码元素的物理宽度。  
3. **配置 Macro PDF417 选项** – 指定列数、文件标识符、段号以及可选校验和。  
4. **保存条形码** – 使用支持的 **条形码图像格式**（如 PNG）将生成的图像写入磁盘。

下面将详细解释每一步，并提供完整、可运行的 C# 代码。

---

## 步骤 1：为 Macro PDF417 初始化 BarcodeGenerator

第一行创建了一个 `BarcodeGenerator` 对象，告诉它必须生成 **Macro PDF417** 条形码。构造函数接受两个参数：编码类型和原始数据字符串。

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**为什么这很重要：**  
`EncodeTypes.MacroPdf417` 告诉库将条形码视为多段容器，这在需要将大文件拆分为多个符号时至关重要。`BarcodeGenerator` 实例实现了 `IDisposable`，因此 `using` 块可确保在保存图像后释放所有非托管资源。

---

## 步骤 2：设置条形码模块大小 (XDimension)

`XDimension` 控制单个条形码模块（最小的黑或白条）的像素宽度。**2 像素** 的值可产生紧凑且易读的图像。

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**实用技巧：**  
如果目标打印机的 DPI 较低，可增加像素计数（例如 `3` 或 `4`），以避免模糊。相反，在屏幕显示时可以保持较低值以减小文件大小。

---

## 步骤 3：配置 Macro PDF417 特定选项

Macro PDF417 添加了元数据，使扫描仪能够从多个条形码段重建原始文件。最常用的选项如下：

| 属性 | 含义 |
|----------|---------|
| `Columns` | 每个符号的列数（影响宽度）。 |
| `MacroPdf417FileID` | 整个文件的唯一标识符。 |
| `MacroPdf417SegmentID` | 当前段的索引（从 1 开始）。 |
| `MacroPdf417SegmentsCount` | 构成文件的段总数。 |
| `MacroPdf417FileName` | 原始文件名（可选，用于显示）。 |
| `MacroPdf417Checksum` | 可选的 16 位校验和，用于完整性验证。 |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**为什么这些设置很重要：**  
- **Columns** 影响可读性和整体图像尺寸。  
- **FileID** 必须在所有段中保持一致，以便解码器知道它们属于同一文件。  
- **SegmentID** 和 **SegmentsCount** 使扫描仪能够正确排序各段。  
- **FileName** 和 **Checksum** 为可选项，但可提升用户体验和数据完整性。

**边缘情况：** 如果生成的段数超过 999，`SegmentID` 字段会溢出；此时请将数据拆分为多个文件。

---

## 步骤 4：将生成的条形码保存为 PNG 图像

最后一步将条形码写入磁盘。`BarCodeImageFormat.Png` 生成无损图像，适用于 Web、桌面和移动平台。

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**可选格式：**  
如果下游系统需要特定格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Gif`。请注意，JPEG 会引入压缩伪影，可能降低扫描可靠性。

**预期输出：**  
文件 `MacroPdf417.png` 将包含高对比度的多段 PDF417 条形码。打开后应与下图类似。

![创建 PDF417 条形码图像示例](image.png){: .align-center alt="C# 代码生成的 PDF417 条形码图像示例"}

---

## 完整源代码 – 可直接复制运行

下面是完整的、独立的程序示例。它包含必要的 `using` 指令、`Main` 方法以及解释每行非显而易见代码的注释。

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**运行程序：**  

1. 创建一个新的 .NET 6（或更高）控制台项目。  
2. 添加 Aspose.BarCode NuGet 包（`dotnet add package Aspose.BarCode`）。  
3. 用上述代码替换生成的 `Program.cs`。  
4. 将 `outputPath` 调整为您有写入权限的文件夹。  
5. 构建并运行——控制台将确认图像所在位置。

---

## 常见问题与故障排除

| 问题 | 答案 |
|----------|--------|
| *如果条形码对我的标签来说太宽怎么办？* | 减少 `Columns` 或增加 `XDimension.Pixels` 以在宽度和可读性之间取得平衡。 |
| *我需要设置校验和吗？* | 校验和是可选的 |

---

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每个资源均提供完整的可运行代码示例和分步解释。

- [在 C# 中创建 PDF417 条形码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [在 C# 中创建 PDF417 条形码元数据 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [生成带文本的条形码 – 完整 PDF417 Macro 指南](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}