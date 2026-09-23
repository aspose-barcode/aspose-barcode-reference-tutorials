---
category: general
date: 2026-09-22
description: 学习如何在 C# 中读取 PDF417 条码，并提供完整的条码读取器示例。本教程展示了如何在 C# 中快速、可靠地读取条码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: zh
lastmod: 2026-09-22
og_description: 如何使用简洁的条码读取示例在 C# 中读取 PDF417 条码。按照指南解码 Macro PDF417 图像并提取元数据。
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: 如何在 C# 中读取 PDF417 条码 – 完整条码读取示例
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: 如何在 C# 中读取 PDF417 条码——完整分步指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 条形码 – 完整分步指南

如果您需要在 .NET 应用程序中 **how to read pdf417**，本指南将向您展示所需的完整代码和原理。阅读完前两句话后，您将了解如何使用流行的 `BarCodeReader` 类在 C# 中读取条码图像，并拥有一个可直接运行的示例，提取所有 Macro PDF417 元数据的每个部分。

在处理运输标签、登机牌或安全文件时，读取 PDF417 条形码是常见需求。本教程涵盖从设置读取器到处理边缘情况的全部内容，让您能够自信地集成条码扫描功能。

## 您将实现的目标

- 解码 Macro PDF417 图像文件。
- 打印基本条码信息（类型和文本）。
- 访问所有 Macro PDF417 扩展字段，如文件 ID、段计数和时间戳。
- 了解在处理多段 PDF417 代码时的常见陷阱。

**先决条件**

- .NET 6.0 或更高（代码同样适用于 .NET Framework 4.7+）。
- 对提供 `BarCodeReader`、`DecodeType` 和 `BarCodeResult` 的条码 SDK 的引用（例如 Aspose.BarCode、Dynamsoft，或任何暴露相同 API 的库）。
- 包含 Macro PDF417 条码的图像文件（`ExtPDF417Meta.png`）。

> **专业提示：** 将图像放在相对于项目根目录的文件夹中，并将其 **Copy to Output Directory** 属性设置为 *Copy if newer*，以便在调试期间路径有效。

![使用 C# 读取 PDF417 条码](https://example.com/placeholder-image.png)

## 如何在 C# 中读取 PDF417 条码 – 完整代码

下面是一个可直接粘贴到控制台应用程序中的独立程序。它创建条码读取器，遍历每个解码结果，并打印标准和扩展的 Macro PDF417 字段。

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
            Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
            Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
            Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
            Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
            Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
            Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
            Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
            Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
            Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
            Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
            Console.WriteLine(new string('-', 40));
        }
    }
}
```

### 每一步的重要性

1. **使用 `DecodeType.MacroPdf417` 创建读取器** – Macro PDF417 是一种可以携带文件级元数据的特殊变体。指定解码类型可确保 SDK 解析这些额外字段，而不是将代码视为普通的 PDF417。
2. **遍历 `ReadBarCodes()`** – 一张图像可能包含多个条码（例如 QR 码旁边的 PDF417）。循环确保捕获所有结果。
3. **打印 `CodeTypeName` 和 `CodeText`** – 这些是最常用的属性，提供符号名称和可读的负载。
4. **访问 `Extended.Pdf417`** – `Extended` 对象仅在 PDF417 相关的解码类型中出现。每个属性直接映射到 Macro PDF417 规范，帮助您重建原始文件或验证段顺序。

## 常见变体和边缘情况

### 读取非宏 PDF417 条码

如果源图像包含普通的 PDF417 代码（无宏元数据），请将 `DecodeType.MacroPdf417` 替换为 `DecodeType.Pdf417`。其余代码保持不变，但 `Extended.Pdf417` 块将为空，因为这些字段根本不存在。

### 处理多段 PDF417

Macro PDF417 可以将大型文档拆分为多个条码段。要重新组装原始文件，您必须：

1. 收集每个段的 `Pdf417MacroSegmentID`。
2. 按 ID 对段进行排序。
3. 验证 `Pdf417MacroSegmentsCount` 与收到的段数相匹配。
4. 按顺序连接每个段的 `CodeText`。
5. 可选地验证 `Pdf417MacroChecksum`。

下面是一段简洁的代码片段，演示了重组逻辑：

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### 处理损坏的图像

- **低对比度** – 在传递给 `BarCodeReader` 之前增加图像预处理（例如直方图均衡化）。
- **旋转** – 使用 `barcodeReader.SetRotateAngle(90)`，或如果 SDK 支持则启用自动旋转。
- **部分扫描** – 确保图像分辨率至少为 300 dpi；否则 SDK 可能会漏掉小段。

## c# 条码读取器示例 – 最佳实践

| 实践 | 原因 |
|----------|--------|
| **使用 `using` 释放读取器** | 确保本机资源及时释放，防止内存泄漏。 |
| **验证 `result.Extended` 不为 null** | 某些 SDK 对非宏代码返回 `null`；检查可避免 `NullReferenceException`。 |
| **记录 `Pdf417MacroFileID`** | 此标识符对每个文件唯一，便于审计追踪。 |
| **在 try/catch 中包装解码** | I/O 错误（文件缺失）或不支持的格式会抛出异常，应优雅地处理。 |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## 预期输出

对正确格式的 `ExtPDF417Meta.png` 运行完整程序，将产生类似以下的输出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

如果图像包含多个段，循环将依次打印每个段的元数据。

## 结论

您现在已经了解 **how to read pdf417** 条码在 C# 中的实现，并拥有一个 **c# barcode reader example**，能够提取每个 Macro PDF417 字段。该方案涵盖基础解码、元数据提取、多段重组以及错误处理，为任何文档处理工作流提供了可直接投产的基础。

### 下一步

- 探索使用相同 `BarCodeReader` API 的 **read barcode image C#** 技术，以处理其他符号（QR、DataMatrix）。
- 将条码解码器集成到 ASP.NET Core 服务中，以实时处理上传。
- 尝试图像预处理库（例如 `OpenCvSharp`），提升低质量扫描的成功率。

祝编码愉快，欢迎根据具体需求调整示例！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于所示技术进行扩展。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中保存条码 – 生成 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [如何在 C# 中读取 PDF417 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [如何在 PDF417 条码中设置错误级别 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}