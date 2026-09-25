---
category: general
date: 2026-08-22
description: 学习如何使用 Aspose.BarCode 在 C# 中生成 PDF417 条形码，设置条形码尺寸，调整列数，并启用紧凑模式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: zh
lastmod: 2026-08-22
og_description: 使用 Aspose.BarCode 在 C# 中生成 PDF417 条码。本指南展示如何设置条码尺寸、控制列数以及启用紧凑模式以获得更小的图像。
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: 在 C# 中生成 PDF417 条码 – 设置尺寸、列数和紧凑模式
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: 如何在 C# 中生成 PDF417 条码并设置条码尺寸
url: /zh/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成 PDF417 条码并设置条码尺寸

如果您需要在 .NET 应用程序中 **生成 PDF417 条码**，本指南将带您完成整个过程。您将看到如何使用 Aspose.BarCode **生成 PDF417**，调整 **设置条码尺寸**，并生成可嵌入报告或移动应用的紧凑 PNG。

创建条码不需要单独的图形编辑器。完成本教程后，您将拥有一个完整的 C# 方法，能够生成具有精确尺寸的 PDF417 图像，随时用于后续处理。

## 您将学习

* 安装并引用 Aspose.BarCode 库。
* 创建 PDF417 条码生成器并指定要编码的文本。
* **设置条码尺寸**，通过配置 X‑dimension 和列数。
* 启用紧凑（截断）模式以缩小符号。
* 将结果保存为 PNG 文件。
* 排查常见问题，例如代码不可读和图像过大。

### 前置条件

* .NET 6.0 或更高版本（该 API 也支持 .NET Framework 4.6+）。
* 具备 C# 和 Visual Studio（或任何 C# IDE）的基本使用经验。
* 有效的 Aspose.BarCode 许可证（免费评估版可用于测试）。

> **专业提示：** 如果您计划在循环中生成大量条码，请复用同一个 `BarcodeGenerator` 实例，仅更改 `CodeText` 属性。这可以减少内存分配。

## 使用 Aspose.BarCode 生成 PDF417 条码

第一步是实例化用于 PDF417 符号的 `BarcodeGenerator`。该对象是所有条码操作的入口。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*这点为何重要*：`EncodeTypes.Pdf417` 告诉库使用 PDF417 标准，它支持大容量数据和错误纠正。构造函数还接受要编码的数据，省去了后续单独设置 `CodeText` 的步骤。

## 设置条码尺寸和列数

PDF417 符号由行和列组成，每个小矩形模块。控制模块宽度（X‑dimension）和列数可以微调整体尺寸。

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*说明*：  
* **X‑dimension**（`Pixels`）决定每个模块的宽度。较小的值会生成更紧凑的条码，而较大的值在低分辨率扫描仪上提升可读性。  
* **Columns** 控制水平布局。列数少时条码更高，列数多时条码更宽。将这两个设置一起调整，以实现您需要的精确 **设置条码尺寸**。

## 启用紧凑模式以获得更小的条码

PDF417 包含一种 “紧凑”（或截断）模式，可去除不必要的填充并降低整体占用空间。这在屏幕空间受限时尤为有用。

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*为何启用截断？*  
当 `Truncate` 为 `true` 时，生成器会省略停止模式和一些在大多数扫描场景中不必需的错误纠正码字。生成的图像大约缩小 15‑20 %，且在典型使用情况下不影响数据完整性。

## 将条码保存为 PNG 图像

在配置尺寸和模式后，将条码写入磁盘。PNG 为无损格式，确保模块边缘保持清晰。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

文件 `CompactPdf417.png` 将包含一个清晰的 PDF417 符号，其尺寸与前面步骤中设置的相匹配。

### 预期输出

打开保存的 PNG 应显示一个垂直方向的 PDF417 条码，包含三列，每个模块宽度为 2 px，总尺寸约为 **120 × 240 px**（宽 × 高）。使用任何标准 PDF417 读取器扫描该图像会返回原始文本 “Sample text for PDF417”。

## 常见陷阱及避免方法

| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| 条码不可读 | X‑dimension 对扫描仪来说太小 | 将 `XDimension.Pixels` 增加到 3 或 4 |
| 图像宽度超出 UI | 列数设置过多 | 减少 `Pdf417.Columns` 或启用 `Truncate` |
| 异常 `ArgumentOutOfRangeException` | 列数为负或零 | 确保 `Columns` 为正整数（最小 1） |
| PNG 文件为空 | 输出路径不存在或没有写入权限 | 验证目录是否存在且应用具有写入权限 |

> **专业提示：** 在调用 `Save()` 之前使用 `barcodeGenerator.ValidateParameters()`，可提前捕获配置错误。

## 完整、可运行的示例

下面是一个独立的控制台程序，包含上述所有步骤。将其复制到新的 C# 项目中，恢复 Aspose.BarCode NuGet 包，然后运行即可看到结果。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**运行程序** 会在可执行文件的工作目录生成 `CompactPdf417.png`。使用移动应用（例如 “Barcode Scanner”）扫描该图像，以验证编码文本与源字符串匹配。

## 后续步骤及相关主题

* **提升错误纠正级别** – 为噪声较大的扫描环境调整 `Pdf417.ErrorLevel`。  
* **更改方向** – 如需水平布局，将 `Pdf417.Rotate` 设置为 `RotationAngle.Rotate90`。  
* **在 PDF 中嵌入条码** – 将 Aspose.PDF 与 Aspose.BarCode 结合，将图像直接放入文档。  
* **生成其他 2‑D 条码** – 同一 `BarcodeGenerator` 类支持 DataMatrix、QR 和 Aztec 码；只需将 `EncodeTypes.Pdf417` 替换为所需的符号。

通过掌握 **生成 PDF417 条码** 技巧，您可以在各种 .NET 应用中实现票务自动化、库存标签以及安全的数据传输。

## 结论

您现在已经了解如何在 C# 中 **生成 PDF417 条码**，精确 **设置条码尺寸**，配置列数，启用紧凑模式，并将结果保存为 PNG。将这些设置应用于任何 UI 限制或扫描需求，并根据需要将方法扩展到其他条码格式。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [如何生成 PDF417 条码 – 紧凑 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何创建条码 – 使用 Aspose.BarCode 的紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}