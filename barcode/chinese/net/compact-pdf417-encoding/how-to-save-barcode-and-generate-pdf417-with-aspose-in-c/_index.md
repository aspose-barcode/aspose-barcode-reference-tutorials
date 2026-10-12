---
category: general
date: 2026-09-29
description: 如何在 C# 中使用 Aspose.BarCode 保存条形码并学习生成带宏元数据的 PDF417。请遵循分步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: zh
lastmod: 2026-09-29
og_description: 如何在 C# 中使用 Aspose.BarCode 保存条形码非常简单。本教程展示了如何生成带宏元数据的 PDF417 并设置所有必需的参数。
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: 如何使用 Aspose 保存条形码 – PDF417 生成指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: 如何在 C# 中使用 Aspose 保存条形码并生成 PDF417
url: /zh/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose 在 C# 中保存条形码并生成 PDF417

在 C# 中使用 Aspose.BarCode 保存条形码是需要将数据嵌入图像文件时的常见需求。本文指南将完整演示如何生成带宏元数据的 PDF417 条形码并将结果保存为 PNG 图像。阅读完毕后，你将掌握 **如何生成 PDF417**、**如何设置 PDF417** 选项，以及最关键的 **如何以编程方式保存条形码** 文件。

你将看到一个完整、可直接运行的示例，涵盖从添加 Aspose.BarCode NuGet 包到配置宏字段（如文件 ID、段计数和校验和）的每一步。无需查阅外部文档；只需将代码复制到新的控制台项目中即可立即运行。教程假设你已安装 Visual Studio 2022（或更高版本）和 .NET 6.0。

## 前置条件

- .NET 6.0 SDK（或任何 Aspose.BarCode 23.11+ 支持的 .NET 版本）
- Visual Studio 2022、VS Code 或你喜欢的 C# IDE
- **Aspose.BarCode for .NET** NuGet 包  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- 基本的 C# 语法和控制台应用程序知识

> **专业提示：** 如果尚未拥有商业授权，可使用 Aspose 提供的免费开发者评估许可证。评估版无需修改代码即可使用。

## 如何保存条形码 – 完整示例

下面的代码创建一个 **宏 PDF417** 条形码，填充所有宏字段，并将图像保存为 `ExtPDF417Meta.png`。已包含所有必需的 `using` 指令，可直接粘贴到 `Program.cs` 中使用。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### 每一步的重要性

1. **创建生成器** – `BarcodeGenerator` 构造函数接受条形码类型（`EncodeTypes.MacroPdf417`）和要编码的数据。宏 PDF417 是一种携带文件传输信息的特殊变体，这也是后面需要填充宏字段的原因。
2. **外观设置** – `XDimension.Pixels` 控制窄条宽度；调整它会改变整体图像尺寸，但不会影响数据完整性。`Pdf417.Columns` 定义条形码矩阵的列布局。
3. **宏元数据** – 这些属性（`MacroPdf417FileID`、`MacroPdf417SegmentID` 等）在需要将大文件拆分为多个条形码段时至关重要。正确设置后，扫描仪才能重建原始文件。
4. **保存图像** – `Save` 方法将生成的条形码写入磁盘。你可以选择任意受支持的格式（`Png`、`Jpeg`、`Bmp` 等）。此行演示了本文所要求的 **如何保存条形码** 操作。

> **常见问题：** *如果我需要其他图像格式怎么办？*  
> 将 `BarCodeImageFormat.Png` 改为 `BarCodeImageFormat.Jpeg`（或其他受支持的枚举值），并相应修改文件扩展名。

## 如何生成带宏元数据的 PDF417

如果只需要普通的 PDF417（不带宏数据），可以省略宏部分，仅保留基础生成器：

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

上述代码演示了 **如何快速生成 PDF417**。请注意，`EncodeTypes.Pdf417` 枚举选择的是非宏版本。

## 如何设置 PDF417 – 高级选项

Aspose.BarCode 提供了许多 PDF417 专用参数。以下是你可能会用到的几项：

| 属性 | 描述 | 常用取值 |
|----------|-------------|----------------|
| `Pdf417.Columns` | 每行的列数 | 1‑30（默认 3） |
| `Pdf417.Rows` | 行数（若为 0 则自动计算） | 0‑90 |
| `Pdf417.ErrorLevel` | 错误纠正级别（0‑8） | 2‑4（在尺寸与鲁棒性之间取得平衡） |
| `Pdf417.RowsPerStrip` | 大条形码每条带的行数 | 0（自动） |
| `Pdf417.Pdf417MacroFileID` | 使用宏时文件的标识符 | 任意 32 位整数 |

这些值的设置方式与主示例 **第 2 步** 中展示的模式相同。请在调用 `Save` 之前进行相应调整。

## 预期输出

运行完整程序后，会在可执行文件的工作目录下生成 `ExtPDF417Meta.png`。该图像包含高分辨率的 PDF417 条形码，且已嵌入所有宏字段。使用支持 PDF417 的扫描仪（或移动端应用）扫描该图像，可返回原始数据字符串 `"Åspóse.Barcóde©"`，以及宏元数据（文件 ID、段 ID 等）。

![已保存为 PNG 的条形码 – 保存条形码示例](ExtPDF417Meta.png "使用宏 PDF417 元数据将条形码保存为 PNG 的示例")

*图片替代文字：* **使用 PDF417 宏元数据将条形码保存为 PNG**（匹配主要关键词）。

## 结论

在本教程中，你学习了 **如何使用 Aspose.BarCode 保存条形码**、**如何生成 PDF417**、**如何设置 PDF417** 参数，以及 **如何使用 Aspose 生成普通和宏启用的条形码** 的完整流程。

## 接下来你应该学习什么？

以下教程与本指南紧密相关，进一步扩展了本篇演示的技术要点。每篇资源均提供完整可运行的代码示例，并配有逐步解释，帮助你掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose 生成 PDF417 条形码 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [如何在 C# 中使用 Aspose 生成 PDF417 条形码图像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何在 C# 中使用 Aspose.BarCode 生成条形码并添加元数据](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}