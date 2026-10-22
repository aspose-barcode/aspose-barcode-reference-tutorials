---
category: general
date: 2026-10-21
description: 如何在 C# 中使用条码读取器从图像读取 PDF417 条码。请按照此逐步 C# 条码读取器示例进行操作，以实现可靠的解码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: zh
lastmod: 2026-10-21
og_description: 如何在 C# 中读取 PDF417 条码，提供完整的条码阅读器示例。学习解码 Macro PDF417 图像并访问所有扩展字段。
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: 如何在 C# 中读取 PDF417 条码 – 详细指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中读取 PDF417 条码 – 完整的条码阅读器指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 条码 – 完整条码读取指南

如果您需要在 .NET 应用程序中 **how to read PDF417 barcode**，本指南为您提供一个可直接运行的解决方案。您将看到如何使用流行的条码库 **read barcode from image C#**，并在无需额外工具的情况下获取所有 Macro PDF417 属性。

本教程涵盖了 **C# barcode reader example** 所需的全部内容：项目设置、代码讲解以及处理边缘情况的技巧。完成后，您可以将代码粘贴到控制台项目中，立即开始解码 PDF417 图像。

## 您需要的条件

在开始之前，请确认以下先决条件：

| 先决条件 | 原因 |
|--------------|--------|
| .NET 6.0 SDK 或更高版本 | 为 C# 控制台应用提供运行时 |
| Visual Studio 2022（或任何 C# IDE） | 启用轻松的项目创建和调试 |
| Aspose.BarCode for .NET（NuGet 包） | 提供 `BarCodeReader` 和 `DecodeType` 类 |
| 一个 Macro PDF417 图像文件（例如 `MacroPdf417.png`） | 作为解码的输入文件 |

您可以使用 dotnet CLI 安装该库：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中从图像读取 PDF417 条码

读取条码的核心工作流包括三个步骤：

1. 初始化特定 `DecodeType` 的 `BarCodeReader`。
2. 遍历返回的 `BarCodeResult` 集合。
3. 访问基本和扩展的 PDF417 字段。

下面是完整的可运行代码。将其保存为控制台项目中的 `Program.cs`。

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### 各步骤说明

* **Step 1 – Initialise the reader**  
  `BarCodeReader` 构造函数接收图像文件路径和一个 `DecodeType`。`DecodeType.MacroPdf417` 告诉库查找 Macro PDF417 符号，这些符号包含比普通 PDF417 条码更多的元数据。

* **Step 2 – ReadBarCodes()**  
  此方法返回一个 `IEnumerable<BarCodeResult>`，如果图像中包含多个条码，则可能包含多个结果。`foreach` 循环确保每个检测到的符号都被处理。

* **Step 3 – Basic information**  
  `CodeTypeName` 标识条码格式（例如 “MacroPDF417”）。`CodeText` 保存符号中编码的原始数据字符串。

* **Step 4 – Extended fields**  
  Macro PDF417 在 `barcodeResult.Extended.Pdf417` 下添加了一组扩展属性。这些字段公开文件级数据，如 `FileID`、`SegmentID` 和 `FileName`。直接访问它们可以重建多段文档或验证完整性。

#### 预期的控制台输出

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

确切的数值取决于您 `MacroPdf417.png` 中编码的内容。如果图像仅包含一个段，`SegmentsCount` 将为 1，`SegmentID` 将为 0。

## 设置 C# 条码读取器环境

可靠的 **C# barcode reader example** 依赖于干净的项目配置：

1. **Create a new console project**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Add the Aspose.BarCode package**（如前所示）。
3. **Copy the image file** 到项目文件夹，或使用绝对路径引用它。
4. **Build and run**  
   ```bash
   dotnet run
   ```

如果构建因缺少引用错误而失败，请确认 `using Aspose.BarCode;` 语句与已安装的包版本匹配。该库的 API 在 .NET 6 和 .NET 8 之间保持稳定，您可以在不更改代码的情况下升级运行时。

## 解码 Macro PDF417 条码

当您调用 `ReadBarCodes()` 时，库在内部执行以下操作：

* **图像预处理** – 将位图转换为二进制矩阵，校正旋转和噪声。
* **模式检测** – 扫描 PDF417 的起止模式并提取模块宽度。
* **错误校正** – 使用 Reed‑Solomon 码恢复受损的代码字。
* **Macro 提取** – 解析扩展的 PDF417 段头并填充 `Extended.Pdf417` 对象。

了解此流水线有助于您决定何时微调解码器选项。例如，如果图像对比度低，可以启用 `BarCodeReader` 的 `ReadQuality` 属性（后续版本提供），以提升检测率。

## 解释扩展的 PDF417 字段

这些扩展字段直接对应于 Macro PDF417 规范：

| 字段 | 含义 |
|-------|---------|
| `MacroPdf417FileID` | 整个文件在所有段中的唯一标识符 |
| `MacroPdf417SegmentID` | 当前段的零基索引 |
| `MacroPdf417SegmentsCount` | 构成文件的段总数 |
| `MacroPdf417FileName` | 编码时存储的原始文件名 |
| `MacroPdf417Checksum` | 用于完整性验证的 16 位校验和 |
| `MacroPdf417FileSize` | 原始文件的字节大小 |
| `MacroPdf417TimeStamp` | 生成条码时的 UTC 时间戳 |
| `MacroPdf417Addressee` | 文档的预期收件人 |
| `MacroPdf417Sender` | 文档的发送者 |
| `MacroPdf417Terminator` | 标记最后一段的文字字符串 “END” |

您可以使用这些值来重建多段 PDF，验证没有段缺失，或记录合规审计信息。

## 常见问题及故障排除

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| 没有输出 | 图像路径不正确或不受支持的格式 | 使用绝对路径并确保文件是 Aspose.BarCode 支持的 PNG/JPEG |
| `CodeType` 显示 “PDF417” 而非 “MacroPDF417” | 图像包含普通 PDF417 符号，而非宏变体 | 验证源条码是否使用 Macro PDF417 扩展进行编码 |
| 某些字段为空 | 条码在生成时未包含这些宏字段 | 使用完整宏负载进行编码，或在代码中处理空值 |
| 解码器抛出 `ArgumentException` | 指定了错误的 `DecodeType` | 如果只需要标准 PDF417 数据，将 `DecodeType.MacroPdf417` 改为 `DecodeType.Pdf417` |

**Pro tip:** 如果预期会遇到非宏条码，请在访问字段时加入空检查。`Extended.Pdf417` 对象在数据缺失时会返回默认值（例如数值字段返回 `0`）。

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## 完整工作示例回顾

把所有内容组合在一起，最终程序由 using 指令、`Main` 方法以及前面展示的四步循环构成。无需额外的配置文件。编译并运行项目，即可在控制台看到包含所有 Macro PDF417 属性的输出。

## 结论

您现在已经掌握了使用简洁的 **C# barcode reader example** 在 C# 中 **how to read PDF417 barcode** 的方法。指南带您完成了环境搭建、代码实现以及每个扩展 Macro PDF417 字段的解释。凭借此基础，您可以将条码扫描集成到库存系统、文档管理工作流或移动后端中。

### Next


## 接下来您应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步提升。每个资源都包含完整的可运行代码示例和逐步解释，助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何在 C# 中读取 PDF417 – 完整条码读取指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [如何在 C# 中使用条码读取示例解码 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [如何在 C# 中使用 Macro PDF417 选项创建 PDF417 条码图像](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}