---
category: general
date: 2026-09-10
description: 学习如何使用简洁的 C# 条码读取示例，从图像中解码条码，仅需几行代码即可读取 Macro PDF417 编码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: zh
lastmod: 2026-09-10
og_description: 使用简短的 C# 条码读取器示例从图像解码条码。按照分步指南即时读取 Macro PDF417 数据。
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: 使用 C# 条码读取器示例从图像解码条码
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: 使用 C# 条码读取器示例从图像解码条码
url: /zh/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 条码读取器示例从图像解码条码

如果您需要**从图像解码条码**，本指南将准确展示如何在 C# 中实现。使用简洁的**C# 条码读取器示例**，您只需几行代码即可读取 Macro PDF417 数据。

您将看到一个完整且可运行的程序，了解每个部分为何重要，并学习防止常见陷阱的技巧。无需外部文档——所有所需内容都在此处。

## 您将学习

- 为条码解码设置所需的 NuGet 包。  
- 编写一个**C# 条码读取器示例**，打开图像文件并提取所有条码。  
- 访问扩展的 Macro PDF417 字段，例如文件 ID。  
- 验证输出并将代码适配到其他条码类型。

### 前置条件

- .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Core 3.1 和 .NET Framework 4.7+）。  
- 对 C# 控制台应用程序有基本了解。  
- 包含 Macro PDF417 条码的图像文件（例如 `MacroPdf417.png`）。  

## 步骤 1：安装条码库

示例使用 **Aspose.BarCode for .NET**，这是一款广泛使用的库，支持 Macro PDF417 解码。

```bash
dotnet add package Aspose.BarCode
```

> **为什么选择此库？**  
> 它提供了一个 `BarCodeReader` 类，能够处理多种格式，具有高精度，并返回 Macro PDF417 代码的扩展信息——且无需额外配置。

## 步骤 2：创建 C# 条码读取器示例

创建一个新的控制台项目，并用下面的代码替换生成的 `Program.cs`。示例遵循以下三个明确的操作：

1. **初始化** 针对目标图像的 `BarCodeReader`。  
2. **遍历** 每个检测到的条码。  
3. **打印** 标准的以及扩展的 Macro PDF417 数据。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### 各部分说明

- **`BarCodeReader` 构造函数** – 第一个参数是图像路径；第二个参数指示库专门查找 Macro PDF417 代码。相较于扫描所有可能的格式，这种聚焦解码提升了性能。  
- **`ReadBarCodes()`** – 返回图像中检测到的所有条码的可枚举集合，使您能够在单个文件中处理多个代码。  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 保存额外的元数据（文件 ID、段计数等）。示例检查是否为 null，以避免在图像包含非 Macro 条码时出现 `NullReferenceException`。  

## 步骤 3：运行程序并验证输出

构建并运行控制台应用程序：

```bash
dotnet run
```

您应该会看到类似以下的输出：

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

如果图像不包含 Macro PDF417 条码，程序仍会列出其他检测到的格式，但扩展字段将被省略。

## 专业技巧：在不大量修改代码的情况下解码其他条码类型

要为不同的格式**从图像解码条码**，只需更改 `DecodeType` 枚举值：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

您也可以传入 `DecodeType.AllSupportedTypes`，让库检测其支持的所有条码。

## 常见陷阱及避免方法

| 症状 | 原因 | 解决办法 |
|------|------|----------|
| 完全没有输出 | 图像路径错误或文件格式不受支持 | 验证路径，确保文件是受支持的图像格式（PNG、JPEG、BMP） |
| Macro PDF417 的 `result.Extended` 为 null | 条码不是 Macro PDF417 变体 | 确认源图像确实包含 Macro PDF417 代码 |
| 异常 `System.IO.FileNotFoundException` | 运行时缺少 NuGet 包 | 运行 `dotnet restore` 并确保 `Aspose.BarCode.dll` 已复制到输出文件夹 |

## 完整源码列表，快速复制粘贴

下面是完整的程序，可直接复制到 `Program.cs` 中。无需其他文件。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## 后续步骤

- **探索其他扩展字段**，如 `MacroPdf417SegmentID` 或 `MacroPdf417FileSize`，以构建完整文档重建工作流。  
- **将读取器集成到 Web API**，使客户端能够上传图像并即时获取解码数据。  
- **进行性能基准测试**，通过解码大批量图像；`BarCodeReader` 在新版 Aspose 中支持异步处理。

---

通过遵循此 **C# 条码读取器示例**，您现在拥有一种可靠的方式来**从图像解码条码**并提取丰富的 Macro PDF417 信息。尝试不同的 `DecodeType` 值，将此逻辑与文件监视器结合，或嵌入移动后端——您的条码处理能力已准备好扩展。

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中读取 PDF417 – 完整条码读取器示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [使用文本生成条码 – 完整 PDF417 Macro 指南](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [如何使用 Aspose 创建 PDF417 条码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}