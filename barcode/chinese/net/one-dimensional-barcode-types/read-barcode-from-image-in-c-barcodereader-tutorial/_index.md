---
category: general
date: 2026-08-15
description: 使用 BarCodeReader 在 C# 中读取图像中的条形码。了解如何在 C# 中读取多个条形码、读取 PDF417 条形码，并查看完整的
  C# BarCodeReader 示例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: zh
lastmod: 2026-08-15
og_description: 使用分步指南在 C# 中从图像读取条形码。了解如何在 C# 中读取多个条形码、解码 PDF417 符号，并运行完整的 C# BarCodeReader
  示例。
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: 在 C# 中从图像读取条形码 – BarCodeReader 教程
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: 在 C# 中从图像读取条形码 – BarCodeReader 教程
url: /zh/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中从图像读取条码 – BarCodeReader 教程

如果您需要在 .NET 应用程序中 **从图像读取条码**，本指南将向您展示如何使用 `BarCodeReader` 类完成此操作。您还将了解如何 **在 C# 中读取多个条码**、解码 PDF417 符号，以及获取一个完整的 **C# BarCodeReader 示例**，可以直接复制到您的项目中。

本教程涵盖每一步——从添加所需的 NuGet 包到打印扩展的 PDF417 字段——让您最终得到一个可运行的控制台程序。无需查阅外部文档，所有代码和说明均已包含。

## 您需要的准备

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Core 和 .NET Framework）
* Visual Studio 2022 或任意支持 C# 的编辑器
* `Aspose.BarCode` NuGet 包（或提供 `BarCodeReader` 的等效库）
* 包含 Macro PDF417 条码的图像文件（例如 `ExtPDF417Meta.png`）

拥有这些前置条件可确保示例能够在无需额外配置的情况下编译通过。

## 使用 BarCodeReader 从图像读取条码

第一步是创建一个指向图像文件的 `BarCodeReader` 实例，并告知库要查找的条码类型。

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**工作原理说明：**  
`BarCodeReader` 会打开图像，扫描指定的 `DecodeType`，并返回一个 `BarCodeResult` 对象集合。每个结果都包含通用的条码数据（`CodeTypeName`、`CodeText`），对于 Macro PDF417，还会提供一个 `Extended.Pdf417` 对象，公开标准定义的所有额外字段。

## 在单张图像中读取多个条码（C#）

有时图像中会包含多个条码（例如 QR 码旁边还有 PDF417）。要处理这种情况，只需省略显式的 `DecodeType`，或传入 `DecodeType.AllSupported`，然后遍历结果即可。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**为何需要这样做：**  
指定 `AllSupported` 会让引擎尝试它已知的所有条码格式，从而保证捕获图像中的每一个符号。这是在无法预先确定条码类型时的推荐做法。

## 使用 C# 读取 PDF417 条码

如果您只关心经典的 PDF417（非宏）格式，只需将 `DecodeType` 改为 `Pdf417`。其余代码保持不变，只是没有扩展字段可用。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**意义所在：**  
经典 PDF417 不会暴露宏特有的属性，因此 `Extended.Pdf417` 块是多余的。使用精确的 `DecodeType` 还能加快扫描速度，因为库会跳过不支持的算法。

## 完整的 C# BarCodeReader 示例（可直接复制）

下面是将上述三种场景合并到一个易于运行的控制台应用程序中的完整代码。请将 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替换为实际的图像路径。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### 预期输出

当示例图像包含 Macro PDF417 条码时，控制台会打印类似以下内容：

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

如果图像仅包含普通 PDF417，则 “Macro PDF417” 部分将为空，而 “Classic PDF417” 部分会显示解码后的文本。

## 结论

现在您已经掌握了如何在 C# 中使用 `BarCodeReader` **从图像读取条码**，以及如何在单个文件中 **读取多个条码 C#**，并了解了 **读取 PDF417 条码** 的完整步骤——包括宏和经典两种变体。完整的 **C# BarCodeReader 示例** 已准备好粘贴到任何 .NET 项目中，您还可以进一步扩展以支持其他格式或将其集成到更大的图像处理流水线中。

**后续步骤**

* 探索在读取器代码块周围使用 `try / catch` 的错误处理模式。  
* 尝试使用 `ReaderParameters` 对象来调节检测速度和准确度。  
* 将条码读取与图像预处理库结合使用（


## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步提升。每篇资源都提供完整的可运行代码示例，并配有逐步解释，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}