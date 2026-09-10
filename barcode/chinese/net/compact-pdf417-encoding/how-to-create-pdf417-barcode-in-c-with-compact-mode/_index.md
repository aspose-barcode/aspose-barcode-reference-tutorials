---
category: general
date: 2026-09-10
description: 快速在 C# 中创建 PDF417 条形码。了解如何启用紧凑模式、设置列数，并使用 BarcodeGenerator 生成 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: zh
lastmod: 2026-09-10
og_description: 在 C# 中通过启用紧凑模式、设置列数并保存为 PNG 来创建 PDF417 条码。请遵循完整的分步指南。
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: 在 C# 中创建 PDF417 条码 – 紧凑模式教程
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中使用紧凑模式创建 PDF417 条码
url: /zh/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用紧凑模式创建 PDF417 条码

如果您需要在 .NET 应用程序中**创建 PDF417 条码**，本指南将准确展示如何操作。您将看到如何**启用紧凑模式**、设置列数，并使用 BarcodeGenerator C# 库将结果保存为 PNG 图像。

生成条码是库存跟踪、票务系统和移动扫描应用的常见需求。通过本教程，您将拥有一个自包含、可运行的示例，生成可用于生产的紧凑 PDF417 条码。

## 前置条件

* .NET 6.0 或更高版本已安装（代码同样适用于 .NET Framework 4.7+）
* 最近版本的 **BarcodeGenerator** 库（例如，Aspose.BarCode for .NET）
* IDE 或编辑器，例如 Visual Studio 2022 或 VS Code
* 对将保存 PNG 的文件夹具有写入权限

除条码库本身外，无需其他 NuGet 包。

## 步骤 1：创建 PDF417 条码生成器

第一步是实例化一个 `BarcodeGenerator` 对象，使用 `EncodeTypes.Pdf417` 枚举并传入要编码的文本。该对象驱动整个生成过程。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*为什么这很重要*：`EncodeTypes.Pdf417` 值告诉库使用 PDF417 符号，而第二个参数提供负载。您可以将 `"Compact mode"` 替换为任何需要编码的字母数字字符串。

## 步骤 2：设置 X 维度（模块宽度）

X 维度控制条码中每个微小方块（模块）的宽度。较小的值会产生更紧凑的图像，在空间受限时非常有用。

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 像素的值在可读性和紧凑性之间取得了良好平衡，适用于大多数基于屏幕的扫描器。

## 步骤 3：定义列数

PDF417 可以在行列网格中排列数据。调整列数会改变条码的宽高比。

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

将 **how to set columns** 设置为 `3` 可得到短而宽的条码，适合贴在标签上。您可以根据数据量和目标扫描器尝试 `1` 到 `30` 之间的值。

## 步骤 4：启用紧凑模式

紧凑模式会移除不必要的填充行，使条码在不失去数据完整性的前提下更小。这是实现 **compact PDF417** 的关键步骤。

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

当 `Truncate` 为 `true` 时，库会自动计算存储数据所需的最少行数，这就是最终图像看起来“紧凑”的原因。

## 步骤 5：将生成的条码保存为 PNG 图像

最后，将条码写入文件。PNG 能保留可靠扫描所需的清晰边缘。

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

将 `YOUR_DIRECTORY` 替换为应用程序可写入的绝对或相对路径。执行后，您将在该目录下找到包含条码的 `CompactPdf417.png` 文件。

### 完整源代码

将所有步骤组合在一起，即可得到一个可直接运行的程序：

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

运行此程序会在可执行文件所在的同一文件夹生成 `CompactPdf417.png`。使用任意查看器打开图像；您应该会看到一条密集、高对比度的 PDF417 条码，已准备好进行扫描。

## 在其他场景中如何启用紧凑模式

* **批量生成** – 在创建大量条码时，在生成器上一次性设置 `Truncate`，并在每个新负载中重复使用。
* **不同的图像格式** – 同样的 `Save` 方法可与 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp` 配合使用，以获得不同的文件类型。
* **动态列数** – 如果编码字符串的长度变化，可根据字符串长度和扫描器分辨率计算最佳列数。

## 针对特定使用场景设置列数

* **标签打印** – 使用较低的列数（例如 `2`‑`5`），使条码足够短以适配窄标签。
* **移动扫描** – 较高的列数（`10`‑`15`）会产生更高的条码，便于手机摄像头对焦。
* **纠错权衡** – 更多列数会减少行数，这可能影响条码内置的纠错能力。请使用目标扫描器进行测试，以找到最佳平衡点。

## 常见陷阱与专业提示

| 问题 | 为什么会发生 | 解决方案 |
|-------|----------------|-----|
| 条码无法读取 | X 维度太低（例如 `1` 像素） | 将 `XDimension.Pixels` 提高到至少 `2` |
| 图像太大 | 对于短负载列数设置过高 | 减少 `Pdf417.Columns` 或启用 `Truncate` |
| PNG 文件为空 | 输出文件夹不存在或没有写入权限 | 确保目录存在并且进程拥有写入权限 |
| 扫描仪报告“数据损坏” | 使用大量列时未启用 Truncate | 启用 `Truncate` 或降低列数 |

## 验证结果

您可以使用任何 PDF417 扫描应用程序（市面上有许多免费 Android/iOS 应用）来验证条码。将在应用中打开 `CompactPdf417.png`，确认解码文本与原始负载（“Compact mode”）一致。如果文本不符，请再次检查 `Truncate` 标志和列设置。

## 下一步

* **与 ASP.NET Core 集成** – 直接从控制器操作返回 PNG，而不是保存到磁盘。
* **添加可读文本** – 使用 `barcodeGenerator.Parameters.Barcode.CodeTextParameters` 在条码下方显示编码字符串。
* **探索其他符号** – 同一 `BarcodeGenerator` 类支持 QR、Code128、DataMatrix 等。切换 `EncodeTypes` 进行尝试。

---

### 结论

您现在已经掌握了在 C# 中**创建 PDF417 条码**的方式，同时**启用紧凑模式**、控制**how to set columns**，并使用**barcode generator C#** API **生成条码**，满足实际尺寸限制。将这些步骤应用于任何需要紧凑、高密度条码的 .NET 项目，并根据需要将该模式扩展到其他条码格式。祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [在 C# 中创建 PDF417 条码 – 完整分步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [如何在 PDF417 条码中设置错误级别 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [如何在 C# 中保存条码 – 生成 PDF417 条码](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}