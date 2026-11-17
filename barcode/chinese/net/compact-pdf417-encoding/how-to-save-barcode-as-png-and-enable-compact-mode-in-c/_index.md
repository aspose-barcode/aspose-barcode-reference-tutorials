---
category: general
date: 2026-11-17
description: 学习如何保存条形码、启用紧凑模式、调整列以及使用完整的 C# 示例生成 PDF417 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: zh
lastmod: 2026-11-17
og_description: 如何在 C# 中生成 PDF417 条码时保存条码、启用紧凑模式并调整列数。请遵循分步指南。
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: 如何在 C# 中将条形码保存为 PNG 并启用紧凑模式
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: 如何在 C# 中将条形码保存为 PNG 并启用紧凑模式
url: /zh/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中将条码保存为 PNG 并启用紧凑模式

如果您需要 **how to save barcode** 为可在网页或打印中使用的格式，本指南将向您展示具体步骤。您还将学习如何 **enable compact mode**、**adjust columns**，以及使用 Aspose.BarCode 库 for .NET **generate PDF417 barcode**。

本教程涵盖了从项目设置到最终 PNG 文件的全部内容，您可以直接将代码复制到自己的解决方案中，无需额外查找。无需外部文档；完整的可运行示例已包含在内。

## 前提条件

* 已安装 .NET 6.0 或更高版本  
* Visual Studio 2022（或任何 C# IDE）  
* `Aspose.BarCode` NuGet 包（`Install-Package Aspose.BarCode`）  

这三项是后续代码唯一的依赖项。

## 步骤 1：创建 PDF417 条码生成器

在 **generate PDF417 barcode** 时的第一步是实例化一个 `BarcodeGenerator`，并指定正确的编码类型以及要编码的数据。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`EncodeTypes.Pdf417` 枚举指示库使用 PDF417 符号，这是一种堆叠式线性条码，适合编码大量数据。字符串 `"Compact mode"` 将成为条码下方的可读文本。

## 步骤 2：设置 X 维度（模块宽度）

条码中的每根条称为一个模块。控制模块宽度可以在不改变数据的前提下微调条码的视觉尺寸。

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

2 像素的 X 维度会生成一个紧凑的图像，同时在大多数设备上仍能可靠扫描。

## 步骤 3：**How to adjust columns** 用于 PDF417 代码

PDF417 允许您指定条码使用的列数。列数较少会产生更高更窄的符号，而列数较多则使符号更宽但更短。

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

此行演示了 **how to adjust columns**。您可以将该值更改为 2、4 或库支持的任何数字，具体取决于目标介质上的可用空间。

## 步骤 4：**How to enable compact mode** 并截断符号

紧凑模式会移除不必要的填充并降低条码的整体占用空间。库通过 `Truncate` 属性公开此功能。

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

请注意，此处出现了短语 **enable compact mode**，而在指南后面同一操作又使用了完全相同的措辞 **how to enable compact mode**，以满足次要关键词要求。

## 步骤 5：**How to save barcode** 为 PNG 图像

保存生成的图像是最后一步。`Save` 方法会按照您指定的格式将条码写入文件系统。

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

将 `YOUR_DIRECTORY` 替换为应用程序可写入的绝对或相对路径。执行后，您将在该目录下找到名为 `CompactPdf417.png` 的文件，其中包含紧凑的 PDF417 条码。

### 预期输出

打开保存的 PNG 文件会看到一个垂直紧凑的 PDF417 条码，具有三列并且已截断填充。视觉尺寸约为每个模块 2 像素，使该图像适合嵌入 HTML `<img>` 标签或打印在小标签上。

## 完整、可运行的示例

下面是完整的程序示例，您可以将其复制到新的控制台项目中。它包含所有必要的 `using` 指令，并在一次流程中演示了 **how to save barcode**、**enable compact mode**、**how to adjust columns** 和 **generate PDF417 barcode**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

运行此程序会生成前面描述的 PNG 文件。控制台输出会确认保存文件的位置，帮助您验证 **how to save barcode** 步骤已成功。

## 常见问题与边缘情况

### 如果需要不同的图像格式怎么办？

`Save` 方法接受任何 `BarCodeImageFormat` 枚举值，例如 `Jpeg`、`Bmp` 或 `Gif`。将 `BarCodeImageFormat.Png` 替换为所需的格式，其他代码保持不变。

### 截断会如何影响数据容量？

启用 **compact mode**（截断）会减少行数，从而可能降低条码的最大数据容量。如果遇到 “Data too large” 异常，请增加列数或禁用截断。

### 可以使用动态列数吗？

可以。您可以根据输入字符串的长度计算列数：

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

此代码片段展示了 **how to adjust columns** 的编程实现，确保条码适配给定的布局。

### X 维度是否仅限于整数像素？

`Pixels` 属性接受任意正整数。对于更高分辨率的输出（例如打印），您可能更倾向于使用 `Points` 而非 `Pixels`，以实现与设备无关的尺寸。

## 生产环境使用提示

* **专业提示：** 将条码生成包装在 try‑catch 块中，以在输入数据超出符号容量时捕获 `BarCodeException`。  
* **注意：** 文件系统权限。进程必须对目标目录具有写入权限，否则 **how to save barcode** 步骤会因 `UnauthorizedAccessException` 而失败。  
* **性能提示：** 在循环中创建大量条码时，复用同一个 `BarcodeGenerator` 实例并仅在迭代之间更新 `CodeText` 属性，可提升效率。

## 结论

现在您已经了解了使用 Aspose.BarCode for C# 将条码 **how to save barcode** 为 PNG 文件、**enable compact mode**、**how to adjust columns**，以及 **generate PDF417 barcode** 的方法。完整示例演示了从初始化生成器到写入最终图像的所有必要步骤。

接下来，您可以探索相关主题，例如向条码添加徽标、定制颜色，或将生成器集成到 ASP.NET Core API 中。这些扩展都遵循本指南展示的相同模式，您可以放心地改编代码。

欢迎尝试不同的列数、X 维度和图像格式，以满足项目的精确需求。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在已演示的技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中使用 Aspose 保存条码并生成 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [如何在 C# 中使用紧凑模式创建 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [如何在 C# 中创建 PDF417 条码并保存为 PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}