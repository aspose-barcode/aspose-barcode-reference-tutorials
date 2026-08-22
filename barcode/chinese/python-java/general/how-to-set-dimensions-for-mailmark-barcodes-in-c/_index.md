---
category: general
date: 2026-08-22
description: 学习如何在 C# 中设置 Mailmark 条形码的尺寸并将其保存为 PNG 图像。包括完整代码、解释和技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: zh
lastmod: 2026-08-22
og_description: 如何在 C# 中设置 Mailmark 条码的尺寸并导出为 PNG 文件。遵循完整示例，避免常见错误。
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: 在 C# 中设置 Mailmark 条码尺寸的分步指南
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: 如何在 C# 中设置 Mailmark 条码的尺寸
url: /zh/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中设置 Mailmark 条形码的尺寸

如果您需要在 C# 中**设置尺寸**Mailmark 条形码，本指南将展示具体步骤。您将看到如何配置 X‑dimension（模块宽度）和条码高度，然后将条形码保存为 PNG 图像，无需额外工具。

生成邮政条形码是构建邮件标签软件时的常规任务，但默认尺寸往往与打印机或布局要求不匹配。完成本教程后，您将能够精确控制条形码尺寸，并生成两种有效的 Mailmark 类型（C‑type 和 L‑type），即可直接打印。

**您将学到**

* 如何为 `BarcodeGenerator` 设置 X‑dimension（模块宽度）和条码高度。
* 如何使用 `BarCodeImageFormat` 将生成的条形码保存为 PNG 文件。
* 常见的陷阱，如无效的文件夹路径或不受支持的尺寸值。
* 在多个条形码之间复用相同配置的技巧。

## 前提条件

* .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.6+）。
* **Aspose.BarCode for .NET** NuGet 包（或任何提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的兼容库）。
* 基本的 C# 语法和文件 I/O 知识。

> **专业提示：** 使用 CLI 命令  
> `dotnet add package Aspose.BarCode` 安装包，以保持项目整洁。

## 第一步：定义输出文件夹

在创建任何条形码之前，必须决定 PNG 文件的写入位置。使用绝对路径可以避免在不同机器上出现意外。

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*为什么这很重要*：如果文件夹不存在，`Save` 会抛出 `IOException`。`Directory.CreateDirectory` 调用是幂等的——如果文件夹已经存在则不做任何操作。

## 第二步：创建 Mailmark C‑type 条形码并**设置尺寸**

Mailmark C‑type 编码一个 20 字符的字母数字字符串。初始化生成器后，您可以通过 `Parameters.Barcode` 对象**设置尺寸**。

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### 为什么选择这些数值？

* **X‑dimension** 控制最小条的宽度（即“模块”）。`4` 像素的值可产生大多数激光打印机易于读取的条形码，同时保持文件大小适中。
* **BarHeight** 决定条的垂直尺寸。`50` 像素是标准邮件标签的常用高度，若需更大格式可相应增大。

> **边缘情况：** 某些打印机要求最低条高为 30 px。将高度设置低于打印机的能力可能导致条形码不可读取。

## 第三步：创建 Mailmark L‑type 条形码并**设置尺寸**

L‑type 使用更长的数据字符串（最多 30 个字符）。相同的尺寸设置方法同样适用。

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### 复用配置

如果您需要生成许多尺寸相同的条形码，考虑将配置提取到辅助方法中：

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

调用 `ApplyStandardDimensions(mailmarkC)` 与 `ApplyStandardDimensions(mailmarkL)` 可减少重复代码，并使将来更改（例如切换到 5 像素模块）只需一行编辑。

## 第四步：验证生成的 PNG 文件

运行程序后，在任意图像查看器中打开这两个 PNG 文件。您应该看到两个不同的 Mailmark 条形码，每个模块宽度为 4 px，条高为 50 px。

*预期输出*

| 文件名                         | 大约尺寸 (px)            |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × 模块 × N 模块 |
| `PostalMailmarkLType.png`     | 4 px × 模块 × N 模块 |

确切宽度取决于编码的数据长度，但高度始终为 **50 px**，因为我们设置了 `BarHeight.Pixels`。

## 常见陷阱及避免方法

| 问题                                 | 症状                                          | 解决方案 |
|--------------------------------------|-----------------------------------------------|----------|
| 文件夹路径无效                       | `IOException: Could not find a part of the path` | 使用 `Path.Combine` 与 `Environment.SpecialFolder`，或验证路径字符串。 |
| X‑dimension 设置为 0 或负数          | 条形码显示为实心块                              | 确保 `XDimension.Pixels` 为正整数（最小 1）。 |
| 不支持的 `EncodeTypes.Mailmark`      | 在生成器构造时抛出 `ArgumentException`          | 确认使用的 Aspose.BarCode 库版本包含 Mailmark 支持。 |
| 使用错误的图像格式保存               | PNG 文件损坏                                    | 使用 `BarCodeImageFormat.Png`（如需其他格式可使用 `Jpeg`）。 |

## 扩展示例

* **不同尺寸** – 将 `XDimension.Pixels` 改为 3 可生成更紧凑的条形码，或将 `BarHeight.Pixels` 增加到 70 以适配更大标签。
* **批量生成** – 遍历数据字符串集合，在每次迭代中应用相同的尺寸设置。
* **其他图像格式** – 如工作流需要，可将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。

## 结论

您现在已经掌握了在 C# 中**设置 Mailmark 条形码尺寸**并导出为 PNG 文件的方法。通过配置 `XDimension.Pixels` 和 `BarHeight.Pixels`，即可控制 C‑type 与 L‑type 条形码的视觉大小，确保符合打印机规格和布局约束。

接下来，您可以尝试不同的尺寸值，将代码集成到更大的邮件标签系统中，或为批量邮件操作生成条形码。

---

*下一步*：探索 **BarcodeGenerator dimensions** 在 QR 码中的应用，或阅读 Aspose.BarCode 文档中关于 **setting DPI** 的章节，以实现高分辨率打印。如果需要将条形码嵌入 PDF，可将此方法与 **Aspose.PDF** 库结合，实现完整的端到端解决方案。

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每个资源都包含完整的可运行代码示例和逐步说明。

- [如何为 ITF-14 条形码自定义边框](/barcode/english/net/itf-14-barcode-customization/)
- [如何使用 Aspose.BarCode for .NET 配置 Patch Code 条形码](/barcode/english/net/patch-code-configuration/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码的逐步指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}