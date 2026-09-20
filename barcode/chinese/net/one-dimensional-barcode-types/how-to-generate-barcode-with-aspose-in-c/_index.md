---
category: general
date: 2026-09-19
description: 如何在 C# 中使用 Aspose 生成条形码——一步一步的指南，快速可靠地创建条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: zh
lastmod: 2026-09-19
og_description: 如何在 C# 中使用 Aspose 生成条形码。请按照本指南创建 Aspose 条形码，配置 MacroPdf417，并保存为 PNG。
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: 如何使用 Aspose 生成条形码——完整 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: 如何在 C# 中使用 Aspose 生成条形码
url: /zh/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose 生成条形码

在使用 Aspose.BarCode 库时，生成条形码非常简单。本教程将一步步演示 **使用 Aspose 创建条形码**，涵盖 MacroPdf417 格式、常见外观设置以及如何将结果保存为 PNG 图像。

您将学习：

* 安装并引用 Aspose.BarCode for .NET  
* 配置 MacroPdf417 特有的属性，如文件 ID、段 ID 和校验和  
* 调整 X‑dimension、列数等视觉选项  
* 将条形码导出为图像文件  

无需事先了解 Aspose——只要具备 C# 和 Visual Studio 的基础知识即可。

## 前置条件

开始之前，请确保您具备以下条件：

| Requirement | Detail |
|-------------|--------|
| .NET runtime | .NET 6.0 或更高（代码同样适用于 .NET Framework 4.7+） |
| IDE | Visual Studio 2022、Rider 或任何支持 C# 的编辑器 |
| Aspose.BarCode | NuGet 包 `Aspose.BarCode`（免费试用版或正式授权版） |
| Basic C# knowledge | 熟悉 `using` 语句和对象初始化 |

您可以通过 NuGet 包管理器将 Aspose.BarCode 添加到项目中：

```bash
dotnet add package Aspose.BarCode
```

## 在 C# 中生成条形码的整体工作流

该过程包括四个逻辑步骤：

1. **创建 `BarcodeGenerator` 实例**，指定所需的编码类型（MacroPdf417）以及要编码的文本。  
2. **设置通用外观选项**，如 X‑dimension 和列数。  
3. **配置 MacroPdf417 特有属性**，包括文件 ID、段 ID 和时间戳等。  
4. **将条形码保存**为您选择的文件格式（本例中为 PNG）。

下面将对每一步进行详细说明。

## 步骤 1：为 MacroPdf417 创建条形码生成器

`BarcodeGenerator` 类是所有条形码创建任务的入口。实例化时，需要传入两个参数：

* `EncodeTypes.MacroPdf417` – 告诉 Aspose 使用 MacroPdf417 符号。  
* 数据字符串 – 将被编码进条形码的文本。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **为什么重要：** MacroPdf417 是一种二维条形码，能够携带大量数据，并支持宏功能（如文件分段），这在将大文件分块传输时非常有用。

## 步骤 2：设置通用条形码外观选项

虽然 MacroPdf417 拥有许多专用设置，但您仍然需要控制视觉密度和布局。最常用的参数包括：

* **X‑dimension** – 最小模块（像素）的宽度。数值越小图像越密集。  
* **Columns** – 每行的数据列数；列数越多条形码高度越低。

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **提示：** 对于大多数屏幕显示场景，将 `XDimension` 保持在 2 到 4 像素之间。较大的数值可提升低分辨率打印机的可读性，但会增大整体图像尺寸。

## 步骤 3：配置 MacroPdf417 特有属性

MacroPdf417 增加了一组元数据字段，帮助您将大文件拆分为多个条形码段。常用属性如下：

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | 整个文件的唯一标识符（最多 8 位数字）。 |
| `MacroPdf417SegmentID` | 当前段的索引（从 0 开始）。 |
| `MacroPdf417SegmentsCount` | 文件的总段数。 |
| `MacroPdf417FileName` | 原始文件的可读名称。 |
| `MacroPdf417Checksum` | 可选的 CCITT‑16 校验和，用于错误检测。 |
| `MacroPdf417FileSize` | 原始文件的字节大小。 |
| `MacroPdf417TimeStamp` | 文件生成的时间戳。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 可选的收发方标识字符串。 |
| `MacroPdf417Terminator` | 指定条形码是否为最后一段（`Set`）或中间段（`Unset`）。 |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **这些字段的价值所在：**  
> *当需要通过低带宽通道传输大型文档时，您可以将文档拆分为多个 MacroPdf417 条形码。接收方通过读取每段的元数据来重建原始文件。*

## 步骤 4：将生成的条形码保存为图像

Aspose 支持多种输出格式：PNG、JPEG、BMP、TIFF、SVG 和 PDF。PNG 是一种无损格式，适合网页或 UI 显示。

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

运行程序后，您将在下方看到类似示例的 PNG 文件。

![使用 Aspose 在 C# 中生成的 MacroPdf417 条形码](placeholder-image.png){.img-fluid alt="使用 Aspose 在 C# 中生成条形码的方式"}

> **预期输出：** 一个 300 × 150 像素的 PNG，展示了包含文本 “Sample” 以及您提供的宏元数据的 MacroPdf417 条形码。

## 完整、可运行的示例

将上述所有代码整合后，得到以下完整程序，您可以直接复制、粘贴并运行：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

使用 `dotnet run`（或在 Visual Studio 中按 **F5**）运行程序。执行完毕后，请确认 PNG 文件已生成且能够正常打开。

## 常见问题与边缘情况处理

### 如果需要其他图像格式怎么办？
Aspose 支持 `BarCodeImageFormat.Jpeg`、`Bmp`、`Tiff`、`Svg` 和 `Pdf`。只需将 `BarCodeImageFormat.Png` 替换为相应的枚举值即可。

### 如何自动生成多个段？
可以将上述代码放入循环中，在每次迭代时递增 `MacroPdf417SegmentID` 并更新数据字符串。记得在所有段中保持 `MacroPdf417SegmentsCount` 的值一致。

### 当数据超出单个 MacroPdf417 符号的容量时怎么办？
MacroPdf417 设计用于大容量负载，但每个条形码仍有理论最大容量（约 1.1 KB/段）。请将源文件拆分为符合此限制的块，然后分别编码为独立的段。

### 校验和需要手动计算吗？
如果将 `MacroPdf417Checksum` 设置为 `0`，Aspose 会自动生成 CCITT‑16 校验和。示例中使用了硬编码值仅作演示；在生产代码中通常让库自行计算。

### 如何更改条形码的前景色/背景色？
使用 `BarColor` 和 `BackColor` 属性：

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## 结论

现在，您已经掌握了 **在 C# 中使用 Aspose.BarCode 生成条形码** 的方法，特别是 **使用 Aspose 为 MacroPdf417 符号创建条形码** 的完整流程。教程涵盖了安装、外观配置以及宏特定字段的设置。

## 接下来您可以学习什么？

以下教程涉及与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并探索在项目中的其他实现方式。

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}