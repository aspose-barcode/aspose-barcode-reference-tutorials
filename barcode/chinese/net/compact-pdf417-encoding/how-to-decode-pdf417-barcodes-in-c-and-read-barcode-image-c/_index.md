---
category: general
date: 2026-10-28
description: 如何在 C# 中快速解码 PDF417 条码。学习使用 Aspose.BarCode 在 C# 中读取条码图像，并提供完整可运行的示例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: zh
lastmod: 2026-10-28
og_description: 如何使用 Aspose.BarCode 在 C# 中解码 PDF417 条码。本指南逐步演示如何在 C# 中读取条码图像，并提供完整代码。
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: 如何在 C# 中解码 PDF417 条码 – 读取条码图像 C# 教程
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中解码 PDF417 条码并读取条码图像
url: /zh/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中解码 PDF417 条形码并读取条形码图像 C#

如果您需要在 .NET 应用程序中 **how to decode pdf417**，本指南提供了一个即开即用的解决方案。您将看到如何使用 Aspose.BarCode 库 **read barcode image c#**，提取 macro‑PDF417 字段，并在控制台中显示它们。

解码 PDF417 条形码常见于物流、票务和身份验证系统。通过本教程，您将能够加载包含 Macro PDF417 条形码的任意图像，进行解码，并访问文件 ID、段 ID 和段计数等对组装多段文档至关重要的值。

## 前提条件

在开始之前，请确保您拥有：

* .NET 6.0 SDK 或更高版本已安装  
* Visual Studio 2022（或任何 C# IDE）  
* Aspose.BarCode for .NET NuGet 包 (`Aspose.BarCode`)  
* 包含 Macro PDF417 条形码的图像文件（示例使用 `ExtPDF417Meta.png`）

您可以使用以下命令添加 NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

## 第 1 步：设置项目并导入命名空间

创建一个新的控制台项目并导入所需的命名空间。`using` 指令让您能够访问 `BarCodeReader`、`DecodeType` 以及结果扩展对象。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **为什么这一步很重要** – 导入正确的命名空间可以防止编译时错误，并使后续解码逻辑能够使用相应的 API。

## 第 2 步：指定图像路径

定义条形码图像的完整或相对路径。将路径保存在变量中可以让代码在不同图像之间复用。

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **提示**：如果路径由多个部分组成，请使用 `Path.Combine`；它会在不同操作系统之间正确处理目录分隔符。

## 第 3 步：创建用于 Macro PDF417 解码的 `BarCodeReader`

使用图像路径和 `DecodeType.MacroPdf417` 标志实例化 `BarCodeReader`。这告诉库专门查找 Macro PDF417 符号。

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **为什么这一步很重要** – 选择合适的 `DecodeType` 可以提升性能，因为引擎会跳过不相关的条形码格式。

## 第 4 步：读取所有条形码并显示宏信息

遍历 `reader.ReadBarCodes()` 返回的每个 `BarCodeResult`。结果对象同时包含通用字段（`CodeTypeName`、`CodeText`）和 Macro PDF417 特有的扩展字段（`MacroPdf417FileID`、`MacroPdf417SegmentID`、`MacroPdf417SegmentsCount`）。

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### 每行代码的作用

| 行 | 说明 |
|------|-------------|
| `result.CodeTypeName` | 检测到的条形码类型的可读名称（例如 “MacroPdf417”）。 |
| `result.CodeText` | 条形码中编码的原始数据。 |
| `result.Extended.Pdf417.MacroPdf417FileID` | 将宏 PDF417 文档的所有段关联在一起的标识符。 |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | 当前段在整个文档中的索引。 |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | 文档预期的总段数。 |

> **专业提示**：如果以后需要重新组装完整文档，可将宏字段存入数据库。`File ID` 可帮助您将属于同一来源的段进行分组。

## 第 5 步：运行程序并验证输出

构建并运行控制台应用程序：

```bash
dotnet run
```

典型的控制台输出如下所示：

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

如果图像包含多个 Macro PDF417 符号，循环会依次打印每一个。

### 处理常见边缘情况

| 情况 | 推荐处理方式 |
|-----------|----------------------|
| **未找到条形码** | 在循环前检查 `reader.ReadBarCodes().Any()`，并显示友好的提示信息。 |
| **图像损坏** | 将 `BarCodeReader` 的创建包装在 `try/catch` 块中，以捕获 `BarCodeException`。 |
| **多种条形码格式** | 使用 `DecodeType.AllSupported`，并通过 `result.CodeTypeName == "MacroPdf417"` 过滤结果。 |
| **大图像** | 在解码前对图像进行降采样以提升性能；库接受 `Bitmap` 对象。 |

## 完整源代码

下面是完整的、独立的程序示例。将其复制到新控制台项目的 `Program.cs` 中，并将 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替换为实际图像路径。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## 结论

您现在已经掌握了在 C# 中 **how to decode pdf417** 条形码以及使用 Aspose.BarCode **read barcode image c#** 的方法。教程带您完成了项目设置、图像加载、阅读器配置、结果提取以及边缘情况处理。凭借这些基础，您可以将 PDF417 解码集成到库存系统、票据验证器或任何依赖宏编码数据的工作流中。

### 后续步骤

* 通过更改 `DecodeType`（例如 `DecodeType.QR`、`DecodeType.Code128`）探索其他条形码格式。  
* 将多个解码段组合起来，以重建原始文档。  
* 使用 `BarCodeGenerator` 类即时生成测试用的 PDF417 条形码。  

欢迎尝试不同的图像来源，调整控制台输出，或将解码逻辑嵌入 Web API 实现实时处理。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方式。每个资源都提供完整的可运行代码示例和逐步解释。

- [如何在 C# 中使用条形码阅读器示例解码 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [如何在 C# 中使用 Aspose.BarCode 生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [如何使用 Aspose.BarCode 从图像读取条形码 C#](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}