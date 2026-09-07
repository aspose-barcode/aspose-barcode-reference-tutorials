---
category: general
date: 2026-09-07
description: 学习如何使用 BarCodeReader 在 C# 中解码 PDF417 条码。本分步指南还解释了如何高效读取 PDF417 数据。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: zh
lastmod: 2026-09-07
og_description: 如何使用 BarCodeReader 在 C# 中解码 PDF417 条码。请跟随本教程学习如何读取 PDF417 数据并提取 MacroPdf417
  字段。
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: 如何在 C# 中解码 PDF417 条形码 – 完整指南
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: 如何使用 BarCodeReader 在 C# 中解码 PDF417 条形码
url: /zh/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarCodeReader 解码 PDF417 条码

如果您需要在 .NET 应用程序中 **解码 PDF417** 条码，本指南将带您完整了解整个过程。您还将发现 **如何读取 PDF417** 数据，例如 MacroPdf417 文件和段标识符，只需几行 C# 代码。

在处理交通票证、驾驶执照或运输标签时，解码 PDF417 是常见需求。完成本教程后，您将拥有一个可运行的控制台程序，能够打印出 GroupDocs.Barcode SDK 所提供的每个 MacroPdf417 字段。

## 前提条件

* .NET 6.0 SDK 或更高版本（代码可在 .NET Core 和 .NET Framework 上编译）
* Visual Studio 2022 或任何支持 C# 的 IDE
* **GroupDocs.Barcode** NuGet 包（`GroupDocs.Barcode` ≥ 23.3）
* 包含 Macro PDF417 条码的图像文件（例如 `ExtPDF417Meta.png`）

> **专业提示:** 通过 CLI 安装包：  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## 如何在 C# 中解码 PDF417 条码

以下章节将把解决方案拆分为逻辑步骤。每一步都包含所需的完整代码以及简短的原因说明。

### 步骤 1：准备项目并导入命名空间

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*为什么？*  
`GroupDocs.Barcode` 提供 `BarCodeReader` 类，而 `GroupDocs.Barcode.Common` 包含进行 PDF417 解码所需的 `DecodeType` 枚举。

### 步骤 2：定义图像路径

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*为什么？*  
读取器支持 .NET 所支持的任何图像格式（`.png`、`.jpg`、`.bmp`）。提供正确的路径可确保 SDK 能找到文件。

### 步骤 3：初始化条码读取器以解码 MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*为什么？*  
`DecodeType.MacroPdf417` 告诉 SDK 查找扩展的 Macro PDF417 格式，该格式携带额外的元数据，如文件和段 ID。使用 `using` 语句可确保及时释放非托管资源。

### 步骤 4：读取图像中找到的所有条码

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*为什么？*  
一张图像可能包含多个条码。`ReadBarCodes()` 方法返回一个集合，便于您逐个处理。

### 步骤 5：检索并显示 Macro PDF417 特定数据

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*为什么？*  
`Extended.Pdf417` 对象公开了规范中定义的所有 Macro PDF417 字段。打印这些字段可让您验证解码操作是否成功，并获取后续处理所需的数据。

### 完整可运行示例

将上述代码片段组合成一个 `Program.cs` 文件：

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**预期的控制台输出**（数值会根据条码内容不同而有所差异）：

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

如果图像不包含 Macro PDF417 条码，`ReadBarCodes()` 集合将为空，且不会打印任何内容。

## 常见变体和边缘情况

| Situation | How to adapt the code |
|-----------|----------------------|
| **Standard (non‑macro) PDF417** | 将 `DecodeType.MacroPdf417` 更改为 `DecodeType.Pdf417`。`Extended.Pdf417` 对象将为 `null`，因此需防止空引用。 |
| **Multiple images** | 将读取器初始化包装在 `foreach (var path in imagePaths)` 循环中。 |
| **Large images** | 设置 `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` 以限制内存使用。 |
| **Performance‑critical batch** | 复用单个 `BarCodeReader` 实例，使用 `reader.SetImage(path)` 而不是为每个文件创建新对象。 |

## 故障排查清单

* **无输出:** 验证 `imagePath` 指向有效文件且图像实际包含 PDF417 条码。 |
* **`Extended.Pdf417` 为 null:** 您可能使用了 `DecodeType.Pdf417` 而不是 `MacroPdf417`。 |
* **异常 `FileNotFoundException`:** 确保工作目录与路径匹配，或使用绝对路径。 |
* **置信度低:** 提高图像质量或调整 `reader.Options.Quality` 设置。

## 结论

您现在已经了解如何在 C# 中 **解码 PDF417** 条码以及 **读取 PDF417** 元数据，如 Macro 文件 ID、段 ID 和时间戳。完整示例演示了如何初始化 `BarCodeReader`、选择正确的解码类型、遍历结果并提取所有可用的 MacroPdf417 字段。

从这里您可以：

* 将提取的数据集成到物流或票据验证系统中。
* 扩展控制台应用，将结果写入数据库或 JSON 文件。
* 通过切换 `DecodeType` 枚举，探索 GroupDocs.Barcode 支持的其他条码格式（QR、DataMatrix、Code128 等）。

祝编码愉快，欢迎尝试不同的图像和条码设置，以掌握 .NET 项目中的 PDF417 解码！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中读取 PDF417 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [如何在 C# 中读取 PDF417 – 完整条码读取器示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何生成 PDF417 条码 – 完整编程指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}