---
category: general
date: 2026-10-15
description: 在 C# 中创建条形码 PNG，使用紧凑的 PDF417 示例——了解如何设置列、调整尺寸并生成图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: zh
lastmod: 2026-10-15
og_description: 使用紧凑的 PDF417 示例在 C# 中创建条形码 PNG。本指南展示如何设置列、调整尺寸并保存图像。
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: 在 C# 中创建条形码 PNG – 完整编程教程
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: 如何在 C# 中创建条形码 PNG – 逐步指南
url: /zh/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建条形码 PNG – 步骤指南

如果您需要从 C# 代码 **创建条形码 PNG** 文件，本教程将在几行代码内展示完整的解决方案。您将看到如何设置列、调整模块大小，并将紧凑的 PDF417 条形码保存为 PNG 图像——全部通过一个简洁易懂的示例实现。

以编程方式生成条形码可以省去使用图形编辑器的手动步骤，并且可以直接将条形码嵌入发票、票据或库存标签中。在接下来的章节中，我们将覆盖关于 **如何创建条形码** 图像的全部必要知识，解释每个配置为何重要，以及如何针对不同使用场景调整代码。

## 前提条件

* .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
* 对支持 PDF417 的条形码库的引用，例如 **Aspose.BarCode for .NET** 或 **IronBarcode**。示例使用 Aspose.BarCode，您可以通过 NuGet 安装：

```bash
dotnet add package Aspose.BarCode
```

* 具备 C# 语法和 Visual Studio（或您偏好的任何 IDE）的基本熟悉度。

> **专业提示：** 如果您更倾向于免费方案，开源的 **ZXing.Net** 库同样支持 PDF417，但属性名称略有不同。这里展示的概念保持不变。

## 如何在 C# 中创建条形码 PNG（主要步骤）

解决方案的核心是一个配置为 PDF417 编码的 `BarcodeGenerator` 对象。以下章节将逐行解析代码，说明 **如何设置列**，并展示这些设置为何会影响最终 PNG 的尺寸。

### 步骤 1：使用所需文本初始化条形码生成器

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*为什么重要*：`EncodeTypes.Pdf417` 枚举指示库生成二维堆叠条形码。构造函数还接受您要编码的数据，因此无需单独调用 `SetData`。

### 步骤 2：以像素设置模块（X）尺寸

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X 维度** 控制条形码的视觉密度。较小的数值会产生更紧凑的图像，适用于需要在移动屏幕或受限打印空间中使用紧凑 PNG 的情况。

### 步骤 3：定义 PDF417 条形码的列数

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

此行演示了 **如何设置列**。PDF417 可以自动选择最佳列数，但显式设置可提供可预测的宽度，尤其是在将 PNG 嵌入固定尺寸布局时。

### 步骤 4：通过截断条形码启用紧凑布局

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

当 `Truncate` 为 true 时，库会移除不含数据的尾部行，从而在不丢失信息的前提下降低图像的整体高度。

### 步骤 5：将条形码图像保存为 PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save` 方法将条形码以您指定的格式写入磁盘。PNG 为无损格式，非常适合需要精确边缘检测的扫描应用。

### 完整、可运行的示例

将所有内容组合在一起，以下是一个可自行复制、粘贴并运行的完整程序：

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**预期输出** – 运行程序后，您将在执行文件夹中找到 `CompactPdf417.png`。该图像包含一个三列的 PDF417 条形码，足够紧凑，可适配标准的 2 × 2 cm 标签，同时保持完全可扫描。

![Create barcode PNG example](placeholder.png){alt="使用 C# 创建条形码 PNG 示例"}

## 如何为不同数据大小设置列（次要关键词）

列数会影响条形码的宽度和可读性：

| 列数 | 大约宽度 (px) | 典型使用场景 |
|--------|-------------------|------------------|
| 1‑2    | 窄且高      | 小标签、类似 RFID 的打印 |
| 3‑5    | 均衡          | 通用标签 |
| 6‑9    | 宽且短       | 大型海报或包装 |

如果您的数据字符串变长，库可能会自动增加行数以保持条形码在列限制范围内。然而，强行将列数设得过低会导致条形码高度过大，可能无法适配收据打印机。请根据输出介质的物理约束调整列数。

## 如何以其他格式创建条形码图像（次要关键词）

虽然 PNG 是网页和移动端最常用的格式，但您可能需要以 JPEG、BMP 或 SVG 等格式 **创建条形码** 图像，以满足特定工作流的需求：

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

* **PNG** – 无损，适合扫描仪。
* **JPEG** – 文件体积更小，在可接受轻微压缩伪影的情况下使用。
* **SVG** – 适用于高分辨率打印或 UI 缩放。

## C# 条形码示例：错误处理与边缘情况

一个健壮的 **c# 条形码示例** 应该预见运行时问题：

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*为什么要使用 `try/catch` 包裹？* 文本中的无效字符、不支持的尺寸或写入权限问题都会抛出异常。优雅地处理这些异常可防止应用在批处理期间崩溃。

## 扩展示例：添加徽标或背景

许多实际场景需要在条形码上叠加徽标或添加彩色背景。Aspose.BarCode API 允许您将条形码与位图结合：

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

此技术在保持 **创建条形码 PNG** 工作流不变的同时，丰富了最终图像的视觉品牌效果。

## 总结

在本指南中，我们演示了如何使用紧凑的 PDF417 配置在 C# 中 **创建条形码 PNG** 文件。您学到了：

* 初始化 `BarcodeGenerator` 所需的完整代码。
* **如何设置列** 以及列数为何对尺寸和可读性重要。
* 如何调整 X 维度并启用截断以获得更紧凑的 PNG。
* 将图像保存为 PNG、JPEG 或 SVG 的方法。
* 生产就绪的 **c# 条形码示例** 的错误处理模式。
* 可选的扩展，如徽标叠加和背景自定义。

您现在拥有一个可直接运行的代码片段，可将其集成到发票生成器、票务系统或库存管理工具中。尝试不同的列值、模块大小或条形码类型（例如 QR、Code128），观察图像的变化。

## 后续步骤

* 探索其他编码类型（`EncodeTypes.QR`、`EncodeTypes.Code128`），以覆盖更多使用场景。
* 将条形码生成与 PDF 创建库（如 **iTextSharp**）结合，将 PNG 直接嵌入文档。
* 研究动态尺寸：根据输入字符串长度和目标标签尺寸计算最佳列数。

祝编码愉快，尽情享受在 C# 中以编程方式生成清晰条形码 PNG 的简便性！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中创建 PDF417 条形码并保存为 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [如何在 C# 中创建 PDF417 条形码并设置其尺寸](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [如何在 C# 中使用紧凑模式创建 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}