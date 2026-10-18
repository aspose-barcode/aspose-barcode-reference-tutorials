---
category: general
date: 2026-10-18
description: 学习如何使用 Aspose.BarCode 在 C# 中从图像读取条形码，涵盖 Macro PDF417 元数据提取以及完整示例代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: zh
lastmod: 2026-10-18
og_description: 如何使用 C# Aspose.BarCode 从图像读取条形码。请按照本分步教程提取 Macro PDF417 元数据并处理常见场景。
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: 如何在 C# 中从图像读取条形码 – 完整的 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Aspose.BarCode 从图像读取条形码
url: /zh/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 从图像读取条形码

如果您需要在 .NET 应用程序中 **how to read barcode from image**，本指南展示了使用 Aspose.BarCode 的具体步骤。无论您是在处理扫描文档、收据还是库存标签，您都将看到如何读取条形码、提取 Macro PDF417 元数据，并处理常见的边缘情况。

从图像读取条形码是常规任务，但提取扩展的 Macro PDF417 字段会增加复杂性。本教程涵盖完整工作流，从项目设置到可直接运行的示例，您可以复制粘贴代码并立即看到结果。

## 您将学习的内容

- 如何为 C# 项目设置 Aspose.BarCode。  
- 为 Macro PDF417 图像实例化 **C# barcode reader** 的正确方法。  
- 如何遍历每个检测到的条形码并输出基本信息。  
- 如何访问 **Macro PDF417 metadata**（如文件 ID、段 ID 和校验和）。  
- 处理缺失元数据、大图像和常见解码错误的技巧。  

**先决条件**

- 已安装 .NET 6.0（或更高版本）。  
- 对 C# 和 Visual Studio 有基本了解（任何 IDE 都可）。  
- 包含 Macro PDF417 条形码的图像文件（例如 `ExtPDF417Meta.png`）。  

## 步骤 1：安装 Aspose.BarCode

在项目文件夹中打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该包包含 **BarCodeReader class**，实现了本教程所需的 **C# barcode reader** 功能。

## 步骤 2：设置开发环境

如果尚未创建控制台应用程序，请新建一个：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

在 `Program.cs` 顶部添加 `using` 指令：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

这些命名空间公开了 **BarCodeReader class** 和用于 Macro PDF417 解码的 `DecodeType` 枚举。

## 步骤 3：为 Macro PDF417 初始化 BarCodeReader

**how to read barcode from image** 的核心是创建一个针对特定 `DecodeType` 的 `BarCodeReader` 实例。对于 Macro PDF417，必须传入 `DecodeType.MacroPdf417`：

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**为什么这很重要：**  
选择 `DecodeType.MacroPdf417` 告诉库去查找扩展的 Macro PDF417 格式，该格式包含超出基本条形码数据的附加字段。如果使用通用的 `DecodeType.Pdf417`，这些额外字段将被忽略。

## 步骤 4：遍历检测到的条形码

单张图像可能包含多个条形码。`ReadBarCodes()` 方法返回 `BarCodeResult` 对象的可枚举集合。遍历它们以输出每个条形码的基本信息：

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` 告诉您确切的条形码符号（例如 “MacroPdf417”），而 `CodeText` 保存解码后的字符串。

## 步骤 5：提取并显示 Macro PDF417 元数据

当条形码为 Macro PDF417 时，`Extended.Pdf417` 属性提供丰富的元数据字段。如下直接访问它们：

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

这些字段提供了重建原始多段文件、验证完整性以及将条形码与特定文档或发送者关联所需的全部信息。

### 预期的控制台输出

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

如果图像不包含 Macro PDF417 条形码，`Extended.Pdf417` 对象将为 `null`。请做好防护以避免 `NullReferenceException`：

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## 步骤 6：处理常见错误和边缘情况

### 大图像

读取非常大的图像会消耗大量内存。使用接受 `ReaderParameters` 的 `BarcodeReader` 重载来限制最大图像尺寸：

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### 缺失或损坏的元数据

如果任何 Macro 字段缺失，相应属性将返回 `null` 或 `0`。记录这些情况并决定是否将条形码视为不完整。

### 单张图像中的多种条形码类型

如果图像可能包含其他条形码格式，您可以传入 `DecodeType` 值的数组：

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

此方法在不牺牲性能的前提下，使 **how to read barcode from image** 逻辑保持灵活。

## 步骤 7：完整源代码

下面是完整的可直接运行的程序。将 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替换为您自己的图像路径。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

使用以下命令运行程序：

```bash
dotnet run
```

您应该会在控制台看到条形码类型、解码文本以及所有可用的 Macro PDF417 字段。

## 结论

在本教程中，您学习了使用 Aspose.BarCode for C# **how to read barcode from image**。本指南涵盖了设置 **C# barcode reader**，

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，构建在本教程演示的技术之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [从图像读取条形码 C# – 包含 Macro PDF417 的完整指南](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [如何在 C# 中使用 Aspose.BarCode 创建 Macro PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何读取 PDF417 条形码 C# – 完整的分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}