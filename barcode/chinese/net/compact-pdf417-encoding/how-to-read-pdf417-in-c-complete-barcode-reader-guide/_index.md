---
category: general
date: 2026-08-09
description: 如何在 C# 中使用 BarCodeReader 读取 PDF417。学习读取条形码 PNG 文件、处理多个条形码并提取扩展元数据。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: zh
lastmod: 2026-08-09
og_description: 如何在 C# 中使用 Aspose.BarCode 读取 PDF417。本教程展示了如何读取条形码 PNG 文件、在同一图像中处理多个条形码以及检索扩展的
  PDF417 元数据。
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: 如何在 C# 中读取 PDF417 – 条形码阅读器教程
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中读取 PDF417 – 完整条码阅读器指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 – 完整条码读取指南

如果您需要在 .NET 应用程序中**读取 PDF417**，本指南为您提供一个即开即用的解决方案。您将看到如何读取条码 PNG、在同一图像中处理多个条码，以及提取许多扫描仪隐藏的扩展 PDF417 字段。

在物流、票务和文档管理中，读取 PDF417 条码非常常见。通过本教程，您可以解码 Macro PDF417 图像，显示所有结果，并在自己的业务逻辑中使用额外信息（文件 ID、段计数、时间戳等）。

## Prerequisites

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
- Visual Studio 2022 或任何 C# IDE
- **Aspose.BarCode for .NET**（免费试用或授权的 NuGet 包）
- 包含 Macro PDF417 条码的 PNG 图像（示例文件名为 `ExtPDF417Meta.png`）

> **技巧提示:** 使用 NuGet 控制台安装库：  
> `dotnet add package Aspose.BarCode`

## 使用 BarCodeReader 在 C# 中读取 PDF417

该解决方案的核心是 `BarCodeReader` 类。它接受图像路径和一个 `DecodeType` 枚举，用于指示引擎要查找的符号类型。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
}
```

### 为什么这样有效

- **`DecodeType.MacroPdf417`** 告诉读取器查找 Macro PDF417 变体，该变体存储您在第 4 步中看到的额外字段。
- `using` 块会自动释放读取器，释放文件句柄。
- `ReadBarCodes()` 返回**所有**匹配请求类型的条码，即使图像中只有一个，也满足*读取多个条码*的需求。

运行程序后会打印类似以下的输出：

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## 使用 C# 条码读取器读取多个条码

如果图像包含多个 Macro PDF417 符号（例如，包含一批票据的扫描页），相同的 `foreach` 循环会处理每一个。无需额外代码；读取器会在内部聚合结果。

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### 常见陷阱

- **图像格式：** 读取器支持 PNG、JPEG、BMP 和 TIFF。如果使用它无法解码的格式，将得到空集合。这也是教程强调*读取条码 PNG*的原因。
- **分辨率：** 低分辨率图像（< 300 dpi）可能导致段缺失。尽可能进行放大或请求更高质量的扫描。
- **宏标志：** 忘记使用 `DecodeType.MacroPdf417` 会将引擎限制为普通 PDF417 并丢弃扩展数据。当需要*读取条码扩展*字段时，请始终指定宏类型。

## 读取条码 PNG 文件 – 最佳实践

使用 PNG 文件相对简单，因为该格式保留无损像素数据。以下是快速检查清单：

1. 在创建读取器之前验证文件是否存在。  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. 仅在需要预处理（旋转、裁剪）时使用 `Image.FromFile`。`BarCodeReader` 可以直接打开文件，从而避免额外的内存分配。
3. 如果 PNG 包含透明度，读取器仍然可以工作，因为条码渲染在不透明像素上。

## 访问扩展 PDF417 元数据

`Extended.Pdf417` 对象公开了 PDF417 规范定义的所有可选字段。您可以将这些字段映射到领域模型、存储到数据库或用于验证。

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

填充模型：



## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条码](/barcode/english/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode 创建条码 – 紧凑型 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [读取 DataMatrix 条码 C# – 生成 DataMatrix 模式（自动）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}