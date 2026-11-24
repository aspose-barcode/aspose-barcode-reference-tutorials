---
category: general
date: 2026-11-23
description: 学习如何在 C# 中使用 BarCodeReader 从图像读取条形码，包括 Macro PDF417 解码，提供完整的代码示例和清晰的说明。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: zh
lastmod: 2026-11-23
og_description: 如何在 C# 中使用 BarCodeReader 从图像读取条形码。请按照本分步指南，使用可直接运行的代码解码 Macro PDF417
  及其他格式。
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: 如何在 C# 中使用 BarCodeReader – 快速从图像读取条形码
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: 如何在 C# 中使用 BarCodeReader 读取图像中的条形码
url: /zh/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarCodeReader 读取图像中的条形码

如果您需要 **how to use BarCodeReader** 来快速扫描条形码，本指南将为您提供确切的步骤。无论您是在构建销售点系统还是自动化文档采集，您都将学习如何在 C# 项目中仅用几行代码读取图像中的条形码。

在本教程中，您将看到一个完整且可运行的示例，解码 Macro PDF417 条形码，提取其扩展属性，并将有用的信息打印到控制台。无需外部文档——您所需的一切都在这里。

## 前置条件

在开始之前，请确保您具备：

* 已安装 .NET 6.0（或更高）——代码面向最新的 LTS 版本。
* 已引用 **Aspose.BarCode**（或任何兼容）NuGet 包，以提供 `BarCodeReader`。
* 包含 Macro PDF417 条形码的图像文件（示例使用 `ExtPDF417Meta.png`）。

> **专业提示：** 如果您使用 Visual Studio，可通过 `dotnet add package Aspose.BarCode` 或 NuGet 包管理器 UI 添加该包。

## 第一步：创建 BarCodeReader 实例

在使用条形码库时，首先要实例化一个读取器，指向源图像并告诉 API 要查找的条形码类型。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*此步骤重要原因：*  
`BarCodeReader` 会打开图像，分配本机内存，并为指定的 `DecodeType` 准备解码算法。将类型限制为 `MacroPdf417` 可以降低 CPU 开销并提升检测准确性。

## 第二步：读取图像中找到的所有条形码

单张图像可能包含多个条形码，尤其是在处理宏编码数据时。`ReadBarCodes` 方法返回一个 `BarCodeResult` 对象的可枚举集合，每个对象代表一个检测到的代码。

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*此步骤重要原因：*  
遍历集合可确保捕获每一个实例，这对于批处理场景或文档中嵌入多个代码的情况至关重要。

## 第三步：访问扩展的 Macro PDF417 属性

Macro PDF417 存储了额外的元数据，如文件标识符、段号和总段数。这些值通过 `BarCodeResult` 的 `Extended.Pdf417` 属性公开。

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*此步骤重要原因：*  
扩展字段可帮助您重建多段文档或验证所有部分是否来自同一来源。跳过此步骤只能得到原始文本，失去宝贵的上下文信息。

## 第四步：输出最有用的信息

最后，将数据写入控制台（或任意日志记录器），以便验证读取操作。示例会打印代码类型、解码文本以及若干宏字段。

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**预期的控制台输出**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **注意：** 如果图像不包含 Macro PDF417 条形码，`ReadBarCodes()` 将返回空集合，循环体永远不会执行。生产代码中请始终检查结果是否为空。

## 在 C# 中从图像读取条形码 – 处理常见场景

### 1. 解码多种条形码格式

如果需要检测多种格式，可传入组合的 `DecodeType` 标志：

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. 处理大图像

大图像可能导致高内存占用。请在将图像传递给读取器之前先进行降采样：

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. 错误处理

将读取逻辑包装在 try‑catch 块中，以捕获解码失败：

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## 完整可运行示例

下面是完整的程序代码，您可以复制、粘贴并直接运行。它包含所有步骤、必要的 `using` 指令以及一个简单的错误处理框架。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**运行程序** 将打印每个检测到的 Macro PDF417 条形码及其扩展字段，或提示未找到条形码。

## 结论

现在您已经掌握了 **how to use BarCodeReader** 在 C# 应用中读取图像条形码的技巧，包括提取 Macro PDF417 元数据。该方案涵盖了初始化、遍历、扩展属性访问以及处理多种格式、大图像和错误的实用建议。

接下来，您可以探索：

* **读取 QR 码** – 将 `DecodeType.MacroPdf417` 替换为 `DecodeType.QR`。
* **将解码数据** 保存到数据库或 JSON 文件，以便后续处理。
* **与 ASP.NET Core 集成**，通过 Web API 接收上传的图像。

欢迎尝试不同的条形码类型和图像来源。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖了与本指南技术密切相关的主题，帮助您在自己的项目中进一步掌握 API 功能并探索替代实现方案，每篇资源均提供完整的可运行代码示例和逐步解释。

- [c# 条形码读取器教程 – 使用 GroupDocs.Barcode 步骤式读取 Macro PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [如何在 C# 中使用条形码生成器生成 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [从图像读取条形码 C# – 包含 Macro PDF417 的完整指南](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}