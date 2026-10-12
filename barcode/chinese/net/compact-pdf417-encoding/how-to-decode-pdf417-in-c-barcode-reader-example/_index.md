---
category: general
date: 2026-09-26
description: 学习如何在 C# 中解码 PDF417，提供一步一步的条形码读取示例。本指南展示如何使用 Aspose.BarCode 在 C# 中读取条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: zh
lastmod: 2026-09-26
og_description: 如何快速在 C# 中解码 PDF417。请参考此条形码读取示例，使用 Aspose.BarCode 在 C# 中读取条形码图像并提取宏详细信息。
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: 如何在 C# 中解码 PDF417 – 完整条码阅读器指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中解码 PDF417 – 条形码读取示例
url: /zh/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中解码 PDF417 – 条码读取示例

如果你需要在 .NET 应用程序中 **如何解码 PDF417**，本教程提供了完整、可直接运行的解决方案。你将看到如何使用 Aspose.BarCode 库在 C# 中读取条码图像、获取扩展的 PDF417 宏信息，并显示每个相关字段。

解码 PDF417 不仅限于纯文本；该格式还能携带文件分段数据、时间戳和校验和。本指南将逐步演示每一步，解释代码为何如此组织，并指出实现 C# 条码读取示例时可能遇到的常见陷阱。

## 前置条件

在开始之前，请确保你拥有：

* 已安装 .NET 6.0（或更高）SDK  
* Visual Studio 2022（或任意支持 C# 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 包（`Aspose.BarCode`）  
* 一个示例宏 PDF417 图像（例如 `ExtPDF417Meta.png`）

这些要求确保代码能够编译并在无需额外配置的情况下运行。

## 第一步：安装 Aspose.BarCode NuGet 包

任何 **read barcode image C#** 项目的第一步都是添加条码库。打开解决方案文件夹中的终端并运行：

```bash
dotnet add package Aspose.BarCode
```

该包提供 `BarCodeReader`、`DecodeType` 以及用于访问宏数据的 `Extended` 属性。只需安装一次，即可在整个项目中使用这些类。

## 第二步：为宏 PDF417 图像创建条码读取器

现在可以使用图像路径实例化 `BarCodeReader`，并指定 `DecodeType.MacroPdf417`。这会告诉库查找包含宏信息的扩展 PDF417 格式。

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**为什么重要：**  
`DecodeType.MacroPdf417` 会激活宏专用解析器。如果省略此参数，读取器只会返回纯文本负载，而忽略你可能需要用于文件重建的宏字段。

## 第三步：读取图像中找到的所有条码

单张图像可能包含多个 PDF417 符号，尤其是当数据被分段时。遍历 `ReadBarCodes()` 可确保捕获每个分段。

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**为何使用循环：**  
PDF417 宏数据通常出现在多个分段中。处理每个 `BarCodeResult` 可确保收集完整的宏字段集合，例如 `MacroPdf417FileID` 和 `MacroPdf417SegmentsCount`。

## 第四步：获取并显示基本条码数据

`BarCodeResult` 对象包含类型和解码后的文本。显示这些值有助于在深入宏细节之前验证读取器是否正确识别了符号。

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**提示：**如果 `CodeText` 为空，可能是图像损坏或解码模式不正确。请再次检查初始化时使用的 `DecodeType`。

## 第五步：提取扩展的 PDF417 宏信息

宏数据位于 `barcodeResult.Extended.Pdf417` 下。每个属性对应 PDF417 规范中定义的字段。

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**各字段含义**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | 将所有属于同一逻辑文件的分段进行分组的标识符。 |
| `MacroPdf417SegmentID` | 当前分段的索引（从 1 开始）。 |
| `MacroPdf417SegmentsCount` | 重建原始文件所需的总分段数。 |
| `MacroPdf417FileName` | 嵌入宏中的可选文件名。 |
| `MacroPdf417Checksum` | 用于完整性校验的 CRC‑16 校验和。 |
| `MacroPdf417FileSize` | 重建后文件的预期大小（字节）。 |
| `MacroPdf417TimeStamp` | 宏生成的日期时间。 |
| `MacroPdf417Addressee` | 可选的收件人标识符。 |
| `MacroPdf417Sender` | 可选的发送者标识符。 |
| `MacroPdf417Terminator` | 结束标志；在最后一个分段上应为 `true`。 |

了解这些字段后，你就可以重建原始文件、验证数据完整性，并实现自定义业务逻辑（例如拒绝过期文档）。

## 第六步：处理多个分段并重建原始文件（进阶）

当 `MacroPdf417SegmentsCount` 大于 1 时，需要收集每个分段、按 `MacroPdf417SegmentID` 排序，并将 `CodeText` 值拼接起来。下面是简洁的实现示例：

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**为何重要：**  
如果不进行排序和拼接，解码后的数据将不完整或出现乱码。该代码片段还通过检查分段计数展示了防御性编程的做法。

## 第七步：加入错误处理与最佳实践

一个面向生产的 **c# barcode reader example** 应当预见 IO 错误、不支持的格式以及损坏的图像。

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**最佳实践清单**

* 在创建 `BarCodeReader` 前验证图像路径。  
* 使用 `using` 语句确保非托管资源得到释放。  
* 记录宏字段以便审计——尤其是 `MacroPdf417Checksum` 和 `MacroPdf417TimeStamp`。  
* 处理大文件时，考虑将拼接后的负载流式写入磁盘，而不是全部保存在内存中。

## 预期输出

将完整程序针对有效的 `ExtPDF417Meta.png` 运行后，输出类似如下：

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

如果三个分段全部存在，重建块将在验证信息后打印完整负载。

## 结论

现在，你已经掌握了 **如何在 C# 中解码 PDF417**，并拥有一个可靠的条码读取示例。教程涵盖了 Aspose.BarCode 的安装、为宏 PDF417 初始化 `BarCodeReader`、遍历多个条码、提取宏字段、重建分段数据以及实现错误处理。

接下来，你可以：

* 将读取器集成到接受上传图像的 Web API 中。  
* 将宏元数据存入数据库以便审计。  
* 通过更换 `DecodeType` 将解决方案扩展到其他 2‑D 条码（如...

## 接下来你应该学习什么？

以下教程与本指南紧密相关，帮助你进一步掌握 API 功能并探索在项目中实现的其他方式。每个资源都包含完整的可运行代码示例和逐步解释。

- [如何在 C# 中读取 PDF417 – 完整条码读取示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何使用 Aspose 创建 PDF417 条码 – 完整步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [在 C# 中读取 PDF417 条码 – 条码读取示例](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}