---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# 让您轻松添加宏数据并生成 PDF417 条形码。一步步学习如何添加宏元数据并创建
  PDF417 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: zh
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# 向您展示如何添加宏元数据并在几行代码中生成 PDF417 条形码。
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose 条形码生成器 C# – 添加宏并生成 PDF417 条码
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: 如何使用 Aspose 条形码生成器 C# 生成 MacroPdf417 条码
url: /zh/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose Barcode Generator C# 生成 MacroPdf417 条码

如果您需要在 C# 中创建 MacroPdf417 条码，**Aspose Barcode Generator C#** 提供了简洁的 API，能够同时处理条码图像和所需的宏元数据。本教程将一步步演示如何添加宏信息并生成 PDF417 条码图像。

您将学习如何配置视觉参数、嵌入文件 ID、时间戳等宏字段，并将结果保存为 PNG。无需外部工具——只需 Aspose.BarCode 库和 .NET 开发环境。

## 前置条件

在开始之前，请确保您具备：

* 已安装 .NET 6.0 或更高版本  
* Visual Studio 2022（或任意 C# IDE）  
* **Aspose.BarCode for .NET** 的授权或评估版  

该代码在 Windows、Linux 和 macOS 上均可运行，因为库是跨平台的。

## 步骤 1：安装 Aspose.BarCode NuGet 包

在 Visual Studio 中打开项目，然后在 **Package Manager Console** 中运行以下命令：

```powershell
Install-Package Aspose.BarCode
```

此操作会将 `Aspose.BarCode` 程序集及其依赖项添加到项目中。

## 步骤 2：创建条码生成器实例

第一行代码为 **MacroPdf417** 符号创建一个 `BarcodeGenerator` 对象，并提供要编码的文本。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*为什么重要*：`EncodeTypes.MacroPdf417` 值告诉库需要宏相关字段，后续步骤中我们将设置这些字段。

## 步骤 3：定义视觉外观

您可以控制每个模块（最小的黑白方块）的大小以及 PDF417 矩阵的列数。调整 `XDimension` 会影响整体图像分辨率。

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

增大 `Columns` 会降低条码高度，而更大的 `XDimension` 能在高 DPI 屏幕上呈现更清晰的图像。

## 步骤 4：添加宏元数据（如何添加宏）

MacroPdf417 需要若干额外字段来描述源文件及其分段。以下属性直接映射到 PDF417 宏规范：

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*这些字段的作用*：  
* `MacroPdf417FileID` 将所有分段关联起来，确保扫描器能够重新组装原始文档。  
* `MacroPdf417SegmentID` 与 `MacroPdf417SegmentsCount` 让解码器知道顺序和总段数。  
* `MacroPdf417FileSize` 与 `MacroPdf417Checksum` 提供完整性校验，对大数据传输尤为重要。

## 步骤 5：保存条码图像（如何生成 pdf417）

最后，将条码写入磁盘。`Save` 方法接受文件路径和图像格式。PNG 能在不产生压缩伪影的情况下保留条码的锐利边缘。

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

程序运行后，您将在输出文件夹中看到 **ExtPDF417Meta.png**。打开该图像即可看到一张干净的 MacroPdf417 条码，准备打印或嵌入 PDF。

### 预期输出

| 文件名               | 格式 | 大小（约）               |
|----------------------|------|--------------------------|
| ExtPDF417Meta.png    | PNG  | 300 × 150 px（随 `XDimension` 变化） |

使用支持 PDF417 的读取器（如 ZXing、Aspose.BarCode for .NET）扫描该图像，可得到原始文本 **“Åspóse.Barcóde©”** 以及所有宏字段。

## 常见问题及解决办法

| 问题                         | 产生原因                                 | 解决方案 |
|------------------------------|------------------------------------------|----------|
| **EncodeTypes 错误**         | 使用 `EncodeTypes.Pdf417` 而非 `EncodeTypes.MacroPdf417` 会禁用宏字段。 | 始终使用 `EncodeTypes.MacroPdf417` 实例化生成器。 |
| **缺少宏字段**               | 若未提供必需的宏字段，部分扫描器会忽略条码。 | 至少填充 `FileID`、`SegmentID`、`SegmentsCount` 与 `Terminator`。 |
| **XDimension 过小**          | 小于 1 像素的值在低分辨率显示器上会导致条码不可读。 | 对大多数屏幕和打印场景保持 `XDimension` ≥ 2 像素。 |
| **文件路径错误**             | 提供的相对路径不存在会抛出异常。 | 使用 `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` 或绝对路径。 |

## 完整源代码

以下是可直接复制到新控制台项目中的完整可运行示例。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

运行程序（`dotnet run`）。执行完毕后，控制台会打印成功信息，PNG 文件会出现在项目的输出文件夹中。

## 后续步骤

* **编码更大数据** – 增加 `Columns` 或通过 `Pdf417.Rows` 调整行数，以容纳更多字符。  
* **嵌入 PDF** – 使用 Aspose.PDF 将生成的 PNG 放入文档中。  
* **扫描验证** – 利用 `Aspose.BarCode.Reader` 解码条码并以编程方式确认宏字段。  

深入探索这些主题，可帮助您掌握 **如何生成带丰富宏信息的 PDF417** 条码，并为批量文档处理或安全数据交换等真实场景做好准备。

---

*祝编码愉快！如果本指南对您有帮助，请与团队分享或在 GitHub 上给 Aspose.BarCode 项目加星。*


## 接下来应该学习什么？

以下教程与本指南所示技术密切相关，帮助您进一步掌握 API 功能并探索项目中的其他实现方式。

- [如何使用 Aspose.BarCode 在 C# 中创建宏 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何使用条码生成器在 C# 中生成 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose 条码示例：在 C# 中生成 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}