---
category: general
date: 2026-07-21
description: 如何在 C# 中使用简洁的条码读取器示例读取 PDF417 条码。快速学习使用逐步代码从图像读取条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: zh
lastmod: 2026-07-21
og_description: 如何在 C# 中读取 PDF417 条码并提供实用示例。了解如何从图像读取条码并立即集成 C# 条码读取器示例。
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: 如何在 C# 中读取 PDF417 – 完整条码阅读器教程
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中读取 PDF417 – 完整条形码读取示例
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 – 完整条码读取示例

是否曾经想过 **如何在 .NET 项目中读取 PDF417** 而不必在无尽的文档中搜索？你并不是唯一的。无论是扫描驾驶执照、登机牌，还是自定义库存标签，可靠地提取这些数据都是现实需求。  

在本指南中，我们将逐步演示一个 **c# 条码读取示例**，从单个图像文件中提取所有 Macro PDF417 元数据。完成后，你将拥有一个可直接运行的控制台应用程序，能够 **从图像读取条码** 并打印出所有可能需要的扩展字段。

## 你需要的条件

- .NET 6.0 SDK 或更高版本（也可以针对 .NET Framework 4.7+——代码同样适用）
- Visual Studio 2022、VS Code 或任何你喜欢的 C# 编辑器
- **Aspose.BarCode for .NET** NuGet 包（`BarCodeReader` 类来自该库）
- 包含 Macro PDF417 条码的图像文件（演示中我们使用 `ExtPDF417Meta.png`）

> **专业提示：** 如果你手头没有 PDF417 示例，Aspose 在其 GitHub 仓库中提供了几张测试图像——只需下载一张并放入项目文件夹即可。

## 步骤 1：安装条码库

在项目文件夹打开终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该包会添加我们后面需要的 `BarCodeReader`、`DecodeType` 和 `Extended` 属性。无需额外配置；库对大多数图像格式（PNG、JPEG、BMP 等）开箱即用。

## 步骤 2：创建最小化控制台应用

如果尚未创建，请新建一个控制台项目：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

用下面的代码替换生成的 `Program.cs`。请注意，每个部分都有注释，即使你是条码处理新手也能跟随逻辑。

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### 为什么这样可行

- **`DecodeType.MacroPdf417`** 告诉读取器期待扩展的 Macro PDF417 格式，该格式携带额外的元数据（文件 ID、段计数、时间戳等）。
- **`Extended.Pdf417`** 对象仅在 Macro PDF417 条码时填充，因此在调用 `ReadBarCodes()` 后访问这些属性是安全的。
- 使用 **`using`** 块可确保文件句柄被释放，防止 Windows 上的文件锁定问题。

## 步骤 3：运行应用程序

编译并执行：

```bash
dotnet run
```

如果图像包含有效的 Macro PDF417 条码，你应该会看到类似以下的输出：

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

如果没有任何输出，请再次确认图像路径是否正确，以及条码是否确实为 Macro PDF417 变体。普通的 PDF417（没有宏扩展）仍会被解码，但 `Extended` 属性将为空。

## 处理边缘情况

### 单图像中多个条码

有时一次扫描会包含多个 PDF417 段（比如跨多个符号编码的多页文档）。`foreach` 循环已经枚举了 *所有* 检测到的条码，因此无需额外逻辑——只需收集这些段并在需要时重新组装即可。

### 缺少扩展数据

并非所有 PDF417 都携带宏信息。在这种情况下，`result.Extended.Pdf417` 会被实例化，但其字段会是默认值（零、空字符串或 `false`）。你可以这样进行防护：

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### 性能提示

- **批量处理：** 如果有一个图像文件夹，可在循环中创建 `BarCodeReader` 并使用 `barcodeReader.SetImage(imagePath)` 重用同一实例，从而降低分配开销。
- **并行化：** 对于大批量任务，可考虑对文件列表使用 `Parallel.ForEach`，但需记住 Aspose 读取器仅在每个线程使用各自的 `BarCodeReader` 实例时才是线程安全的。

## 完整源码列表（可直接复制粘贴）

下面是完整的程序代码，可直接放入 `Program.cs`。除图像外无需其他文件。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## 小结：如何快速在 C# 中读取 PDF417

- 通过 NuGet 安装 **Aspose.BarCode**。
- 使用 `DecodeType.MacroPdf417` 将 `BarCodeReader` 指向你的图像。
- 遍历 `ReadBarCodes()`，获取基本字段和扩展字段。
- 优雅地处理缺失的宏数据，并考虑对批量扫描进行性能优化。

## 后续步骤与相关主题

- 使用其他格式（QR、DataMatrix）**从图像读取条码**——只需更换 `DecodeType` 枚举。
- 如需编程生成条码，可使用 `BarCodeGenerator` **编码 PDF417**。
- 探索 **纠错级别** 以及它们对扫描可靠性的影响。
- 将此逻辑集成到 ASP.NET Core API 中，以将条码读取功能作为 Web 服务公开。

随意尝试：更换图像、玩转 `DecodeType` 标志，或将宏数据写入数据库。核心模式保持不变，现在你的工具箱中已有一个可靠的 **c# 条码读取示例**。

祝编码愉快，愿你的扫描始终清晰！

## 接下来你应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助你掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条码](/barcode/english/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode 创建紧凑型 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 为 Code 16K 条码创建安静区](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}