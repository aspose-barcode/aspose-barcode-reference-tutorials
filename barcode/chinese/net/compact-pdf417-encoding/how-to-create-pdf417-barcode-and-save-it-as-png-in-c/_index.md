---
category: general
date: 2026-10-05
description: 学习如何在 C# 中创建 PDF417 条码，并通过一步步代码生成条码 PNG，同时提供最佳实践技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: zh
lastmod: 2026-10-05
og_description: 在 C# 中创建 PDF417 条码并即时生成条码 PNG。遵循本完整教程，获取可投入生产的解决方案。
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: 在 C# 中创建 PDF417 条码 – 生成 PNG 的完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: 如何在 C# 中创建 PDF417 条形码并保存为 PNG
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 PDF417 条码并保存为 PNG

如果您需要在 .NET 应用程序中**创建 PDF417 条码**，本指南将准确展示如何操作。您将获得一个可直接使用的 C# 代码片段，用于生成高质量的**条码 PNG**文件，并且您将了解影响输出的每个设置。

生成条码是票务系统、库存跟踪和安全文档编码的常见需求。通过本教程，您可以用完整的可运行示例回答“**如何生成 PDF417**”的问题。

## 前置条件

* 安装了 .NET 6.0 SDK 或更高版本  
* 开发环境，例如 Visual Studio 2022 或 VS Code  
* **Aspose.BarCode for .NET** NuGet 包（或任何支持 PDF417 的兼容库）  

您可以使用以下命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

下面的代码使用 Aspose API，因为它提供对 PDF417 参数的细粒度控制，并且开箱即支持 PNG 导出。

## 步骤 1：设置项目并导入命名空间

创建一个新的控制台项目并导入所需的命名空间：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation` 命名空间包含 `BarcodeGenerator` 类，这是**创建 PDF417 条码**图像的入口点。

## 步骤 2：使用所需文本创建 PDF417 条码

使用 `EncodeTypes.Pdf417` 枚举实例化生成器，并传入您想要编码的数据。示例使用包含特殊字符的字符串，以演示 Unicode 处理：

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

生成器现在持有一个条码对象，您可以在渲染之前进行配置。

## 步骤 3：配置视觉参数

对条码进行微调可以提升可读性并减小图像尺寸。最常调整的设置是 **X‑dimension**、**columns** 和 **compact mode**。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** 控制每个模块的宽度；`2` 像素的值可产生紧凑且可读的条码。  
* **Columns** 决定代码使用的数据显示列数。列数更少会使条码更窄但更高。  
* **Truncate** 启用 PDF417 规范定义的“紧凑”模式，去除不必要的填充行。

如果您的使用场景需要更高的抗损坏能力，可以尝试调整 `Rows` 和 `ErrorCorrectionLevel`。

## 步骤 4：将条码保存为 PNG 图像

最后，将条码导出为 PNG 文件。PNG 能保留锐利的边缘并支持透明度，非常适合网页和打印场景。

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

运行程序后会在指定目录生成 `CompactPdf417.png`。图像如下所示：

![使用 C# 创建的紧凑型 PDF417 条码](compact-pdf417.png "使用 C# 创建的紧凑型 PDF417 条码示例")

*上述 alt 文本包含主要关键词，满足 SEO 与可访问性要求。*

## 完整、可运行的示例

将所有部分组合在一起，下面是一个可自行复制、粘贴并运行的完整程序：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### 预期输出

打开 `CompactPdf417.png` 时，您应该看到一个垂直的高密度条码，编码的字符串为 *Åspóse.Barcóde©*。使用任何 PDF417 读取器扫描该图像都会返回原始文本。

## 为什么这些设置很重要

* **X‑dimension** 影响物理尺寸和扫描速度。较小的模块提升数据密度，但可能需要更高分辨率的扫描仪。  
* **Columns** 影响宽高比。对于移动收据，较低的列数可使条码足够窄，以适配窄纸。  
* **Truncate** 减少行数，节省墨水和空间且不牺牲数据完整性，因为 PDF417 已包含错误纠正码字。

了解这些参数后，您可以根据目标介质的限制（无论是标签打印机、网页还是移动应用）定制条码。

## 常见变体和边缘情况

### 生成其他图像格式

如果您更喜欢 JPEG 或 BMP，请更改 `BarCodeImageFormat` 枚举：

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG 会压缩图像，但可能产生影响小尺寸扫描的伪影。

### 调整错误纠正

对于恶劣环境（例如户外标识），请提高错误纠正级别：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

更高的级别会增加冗余，使条码更大但更稳健。

### 编码二进制数据

PDF417 可以编码二进制负载。传入 `byte[]` 而不是字符串：

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

库会自动切换到二进制模式。

### 处理超长字符串

当数据超过默认容量时，生成器会自动创建额外的行。您可以限制行数以避免图像过大：

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

如果内容仍然放不下，考虑将其拆分为多个条码。

## 专业技巧

* 如果需要使用相同设置创建大量条码，请**缓存生成器**。复用对象可避免重复分配内部资源。  
* 如果打印需要特定 DPI，请在 `ImageOptions` 上**设置 `Resolution`**：

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* 使用 `BarCodeReader` 以编程方式**验证输出**，确保生成的 PNG 在交付给用户之前能够被解码。

## 结论

现在，您已经了解如何在 C# 中**创建 PDF417 条码**并**生成条码 PNG**文件，能够全面控制尺寸、列数和紧凑模式。完整示例展示了标准做法，解释了每个设置的重要性，并涵盖了错误纠正、替代格式和二进制数据等变体。请使用上述技巧将解决方案适配到您的具体工作流，无论是构建票务系统、物流标签生成器，还是安全文档编码器。

---

**后续步骤**

* 使用相同的 `BarcodeGenerator` 类探索其他二维符号（DataMatrix、QR）。  
* 将条码创建集成到 ASP.NET Core API 中，以按需提供 PNG。  
* 将条码图像与 PDF 生成库结合，直接嵌入报告中。

祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中创建 pdf417 条码 – 步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中生成微型 pdf417 条码 – 步骤指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中使用紧凑模式创建 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}