---
category: general
date: 2026-09-16
description: 了解如何在 C# 中使用 BarcodeGenerator 设置条码列，并为 DataBar Expanded Stacked 条码设置条码行。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: zh
lastmod: 2026-09-16
og_description: 快速在 C# 中设置条码列。本指南展示如何使用 BarcodeGenerator 配置列、行和图像格式。
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: 在 C# 中设置条形码的列和行 – 完整的 BarcodeGenerator 指南
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# BarcodeGenerator 设置条形码的列和行
url: /zh/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# BarcodeGenerator 设置条形码的列和行

如果您需要在 C# 应用程序中设置条形码的列数，本教程将展示所需的完整步骤。您将看到如何为 DataBar Expanded Stacked 条码配置列和行，然后将结果保存为 PNG 图像。

以编程方式生成条形码可以免去手动设计的工作，并确保在报表、发票和产品标签之间保持一致性。下面的示例涵盖了完整的工作流，从安装库到生成两张图像——一张使用自定义列数，另一张使用自定义行数。

## 前置条件

在开始之前，请确保您具备以下条件：

* 已安装 .NET 6.0 或更高版本。  
* 已引用 **Aspose.BarCode for .NET** NuGet 包。使用以下命令安装：

```bash
dotnet add package Aspose.BarCode
```

* 对将保存生成的 PNG 文件的文件夹具有写入权限。

这些要求确保代码能够成功编译并运行，无需额外配置。

## 如何在 C# 中设置条形码列数

第一步是为 **DataBar Expanded Stacked** 符号创建 `BarcodeGenerator` 实例，并指定所需的列数。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**工作原理说明：**  
`EncodeTypes.DatabarExpandedStacked` 告诉库使用哪种符号进行渲染。设置 `Parameters.Barcode.DataBar.Columns` 会改变内部模块布局，直接影响条形码的视觉宽度。`Save` 方法会按照指定的 `BarCodeImageFormat` 将图像写入磁盘。

### 预期结果
在任意图像查看器中打开 `C:\Barcodes\DatabarCols4.png`。您应该会看到一个比默认更宽的 DataBar Expanded Stacked 条码，因为它使用了四列。

## 如何在 C# 中设置条形码行数

在保存了基于列的图像后，您可能希望通过调整行数来改变条码的高度。该过程与列的配置类似，只是使用 `Rows` 属性。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**工作原理说明：**  
重新实例化生成器可确保之前的列设置不会影响行配置。修改 `Parameters.Barcode.DataBar.Rows` 会改变条码的高度，当行数超过默认值时，生成的图像会更高。

### 预期结果
打开 `C:\Barcodes\DatabarRows3.png`。条码将显得更高，反映出三行的配置。

## 完整的端到端示例

下面是一个一次性创建两张图像的完整程序。将代码放在同一个文件中，可演示如何在不重启应用的情况下在列和行配置之间切换。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

运行程序后会生成两个 PNG 文件：

* **DatabarCols4.png** – 具有四列的条码。  
* **DatabarRows3.png** – 具有三行的条码。

两个文件均使用 **barcode image format** PNG，能够保持锐利的边缘并支持无损压缩——非常适合打印和数字显示。

## 常见问题与技巧

| Question | Answer |
|----------|--------|
| *Can I use JPEG instead of PNG?* | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is smaller but introduces compression artifacts, which may affect scanner reliability. |
| *What is the maximum number of columns or rows?* | The library validates the values against the DataBar specification. Values outside the allowed range throw an `ArgumentException`. Check the Aspose.BarCode documentation for the exact limits. |
| *Do I need to dispose the `BarcodeGenerator`?* | The class implements `IDisposable`. Wrap the generator in a `using` block if you create many instances in a loop to free unmanaged resources promptly. |
| *How do I change the barcode size without altering columns/rows?* | Use `barcodeGenerator.Parameters.Image.Width` and `Height` to scale the output image while keeping the module layout unchanged. |

**专业提示：** 当为高分辨率打印生成条码时，建议增加输出图像的尺寸（`Width`/`Height`），而不是增加列或行数。此做法可在保持符号定义的标准模块大小的同时，提供更清晰的图像。

## 结论

现在，您已经掌握了如何使用 **BarcodeGenerator** 类在 C# 中设置条形码的列和行。本文介绍了生成器的初始化、列/行计数的配置、以 PNG 格式保存条码以及常见的变体（如更改图像格式和资源释放）。

接下来，您可以进一步探索 **自定义条码颜色**、**添加可读文本**、以及 **将条码嵌入 PDF 文档** 等相关主题。这些扩展都基于本文展示的相同配置模式，帮助您在任何 .NET 应用中构建功能完整的条码解决方案。

## 接下来应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，均提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中尝试不同实现方式。

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}