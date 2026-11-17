---
category: general
date: 2026-11-17
description: 学习如何在 C# 中创建 PDF417 条码——使用 C# 条码生成器从字符串生成条码的完整指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: zh
lastmod: 2026-11-17
og_description: 快速在 C# 中创建 PDF417 条形码。本教程展示如何使用 C# 条形码生成器从字符串生成条形码，并附带完整源代码。
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: 在 C# 中创建 PDF417 条码——分步指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: 如何使用条形码生成器在 C# 中创建 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用条码生成器创建 PDF417 条码

如果您需要在 .NET 应用程序中**创建 PDF417 条码**，本指南将准确展示如何操作。您将学习如何**从普通字符串生成条码**、配置符号大小，并将结果保存为 PNG 文件——全部使用可靠的 C# 条码生成器。

以编程方式生成条码可以消除手动步骤并保证一致的质量。在本教程中，我们将从项目设置一直覆盖到最终图像，帮助您今天就能将条码创建集成到任何 C# 解决方案中。

## 前提条件

* .NET 6.0 SDK 或更高版本（代码兼容 .NET Core 和 .NET Framework）
* Visual Studio 2022（或任何支持 C# 的 IDE）
* **Aspose.BarCode for .NET** 的许可证或免费试用版——示例中使用的库
* 对 C# 语法的基本了解

无需额外的包；NuGet 包 `Aspose.BarCode` 已包含您所需的所有类。

## 第一步 – 设置 C# 条码生成器

在**创建 PDF417 条码**时，首先要实例化一个 `BarcodeGenerator` 对象。该对象代表**c# 条码生成器**，负责编码、渲染和保存。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*为什么重要*：`EncodeTypes.Pdf417` 枚举指示库使用 PDF417 符号，这与身份证件和运输标签使用的标准相同。字符串 `"(01)12345678901234"` 是一个**从字符串生成条码**的示例，同时演示了如何**创建 GS1 条码**数据。

## 第二步 – 配置 X 维度（模块宽度）

X 维度控制最小条（模块）的宽度。屏幕渲染的常用值为 2 像素。

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

显式设置 X 维度可防止生成器使用默认值，从而避免生成对某些扫描仪来说过小的条码。

## 第三步 – 定义列数

PDF417 允许您调整列数，这会影响条码的形状和数据容量。对于紧凑标签，四列效果良好。

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

如果需要更高的条码，可增加列数；库会自动计算所需的行数。

## 第四步 – 将条码保存为图像

最后，将条码导出为 PNG 文件。PNG 能保持清晰的边缘并支持透明度。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

运行程序后会生成 `output/Gs1Pdf417.png`。在任意图像查看器中打开该文件，您将看到一个干净的 **PDF417 条码**，其中编码了您提供的 GS1 数据。

### 预期输出

![显示 GTIN (01)12345678901234 的生成的 PDF417 条码](/images/pdf417-sample.png){: .center-image alt="使用 C# 条码生成器创建的 PDF417 条码"}

*上图展示了完整代码示例的结果。该条码可被任何兼容 PDF417 的阅读器扫描。*

## 其他选项和常见变体

### 更改图像格式

如果您更喜欢 JPEG 或 BMP，只需将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。其余代码保持不变。

### 调整错误纠正级别

PDF417 支持 0‑8 的错误纠正级别。更高的级别会增加冗余度，但也会使条码变大。

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### 生成其他 GS1 条码

相同的 `BarcodeGenerator` 可以为其他符号生成**创建 GS1 条码**，例如 `EncodeTypes.Gs1DataMatrix` 或 `EncodeTypes.Gs1Qr`。只需更换枚举值：

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### 处理空或 null 数据

在**从字符串生成条码**时，务必验证输入：

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

这可以防止运行时异常，并确保条码符合 GS1 格式规则。

## 完整、可运行的示例

下面是完整的程序，您可以复制粘贴到新的控制台项目中。它包含所有必要的 `using` 指令、文件夹创建以及错误处理。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**运行程序**（`dotnet run`），您将在 *output* 文件夹中找到 `Gs1Pdf417.png`。使用任何 PDF417 阅读器扫描，以验证 GTIN `(01)12345678901234` 已正确编码。

## 常见问题

**问：我可以在 .NET Framework 4.6 上使用此代码吗？**  
**答**：可以。Aspose.BarCode 库面向 .NET Standard 2.0，兼容 .NET Framework 4.6 及更高版本。

**问：如果需要更高分辨率的图像怎么办？**  
**答**：在保存之前设置 `Resolution` 属性：

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**问：如果没有 GS1 应用标识符，条码仍然有效吗？**  
**答**：它将是标准的 PDF417 条码，但不会被识别为符合 GS1 的符号。需要**创建 GS1 条码**合规时，请包含 `(01)` 前缀。

## 结论

现在您已经了解如何使用强大的 **c# 条码生成器** 在 C# 中**创建 PDF417 条码**。本教程涵盖了：

* 使用 GS1 数据实例化 `BarcodeGenerator`  
* 配置 X 维度和列数  
* 将结果保存为 PNG 图像  
* 通过错误纠正、不同格式和输入验证扩展解决方案  

有了这套基础，您可以直接从字符串生成任意 PDF417 或 GS1 条码，将其嵌入报告，或发送至打印机。探索 Aspose.BarCode API，可添加颜色、边距，或将多个条码合并为单个图像。

**下一步**：尝试为 DataMatrix 生成**创建 GS1 条码**，实验动态列计算，或将生成器集成到 ASP.NET Core Web 服务中，以按需返回条码图像。

祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方法。

- [如何在 C# 中生成 PDF417 条码 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [如何在 C# 中创建微型 PDF417 条码并生成 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [如何在 C# 中使用 Aspose.BarCode 创建宏 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}