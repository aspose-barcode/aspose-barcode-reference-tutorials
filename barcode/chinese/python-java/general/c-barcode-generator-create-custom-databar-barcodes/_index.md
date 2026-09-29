---
category: general
date: 2026-08-19
description: C# 条码生成器教程展示了如何生成 DataBar Expanded Stacked 条码、定制条码尺寸以及配置行和列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: zh
lastmod: 2026-08-19
og_description: C# 条形码生成器教程教您如何生成 DataBar 条码、定制尺寸以及配置行列以实现精确输出。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: C# 条码生成器 – 定制 DataBar 条码的分步指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: C# 条码生成器：创建自定义 DataBar 条码
url: /zh/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 条形码生成器：创建自定义 DataBar 条码

如果您需要一个 **c# barcode generator** 能够生成 DataBar Expanded Stacked 符号，本指南将详细演示如何使用自定义行列生成条码图像。您将学习配置 databar 参数、调整条码尺寸，并将结果保存为 PNG 文件。

以编程方式生成条码可以省去手动设计步骤，并确保跨平台输出的一致性。在本教程中，您将：

* 安装并引用 Aspose.BarCode for .NET 库（或任何兼容的包）。
* 为 DataBar Expanded Stacked 符号创建条码生成器。
* **如何生成条码** 图像并设置特定的列和行。
* 通过控制 DataBar 行列 **自定义条码尺寸**。
* **配置 databar 参数**，如文本、格式和图像质量。

## 前置条件

* 已安装 .NET 6.0 SDK 或更高版本。
* C# 开发环境（Visual Studio、VS Code、Rider 等）。
* NuGet 包 `Aspose.BarCode`（或提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的等效库）。

使用 .NET CLI 添加包：

```bash
dotnet add package Aspose.BarCode
```

## 使用 C# 条形码生成器创建 DataBar 条码

以下章节将逐步演示每一步。主要聚焦于 **c# barcode generator** API，其他提供相似属性的条码库也可采用相同模式。

### 步骤 1：使用示例文本初始化条码生成器

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*为什么要这一步？*  
`BarcodeGenerator` 是所有条码创建任务的入口。传入 `EncodeTypes.DatabarExpandedStacked` 枚举告诉库使用哪种符号体系，而文本参数则成为符号中编码的可读值。

### 步骤 2：设置列数（使用默认行数）

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*为什么要这一步？*  
DataBar Expanded Stacked 符号由堆叠的线性元素组成。调整 `Columns` 属性会改变水平密度，使您在不增加整体高度的情况下容纳更长的数据字符串。这直接 **自定义条码尺寸**。

### 步骤 3：保存使用四列的条码图像

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*您将看到：*  
保存的 `DatabarCols4.png` 图像显示了一个比默认更宽的 DataBar 条码，因为它包含了四列。您可以使用任意图像查看器打开文件以验证输出。

### 步骤 4：为新配置重新初始化生成器

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*为什么要重新初始化？*  
在保持之前的列设置的同时更改 `Rows` 属性可能会产生意外组合。使用全新实例可确保只有预期的参数（`Rows`）影响下一张图像。

### 步骤 5：设置行数（使用默认列数）

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*为什么要这一步？*  
`Rows` 属性控制垂直堆叠。增加行数会使条码更高，当水平空间受限而垂直空间充足时，这非常有用。这是另一种 **自定义条码尺寸** 的方式。

### 步骤 6：保存使用三行的条码图像

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*结果：*  
`DatabarRows3.png` 展示了一个更高的条码，包含三行堆叠，演示了 **配置 databar 参数** 如何影响视觉外观。

## 完整可运行示例

下面是一个完整的程序，您可以复制、粘贴并运行。它包含所有引用、错误处理以及注释，便于理解。

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**预期输出**

运行程序后会生成两个 PNG 文件：

* `DatabarCols4.png` – 具有四列的宽条 DataBar 条码。
* `DatabarRows3.png` – 具有三行的高条 DataBar 条码。

打开图像即可确认条码尺寸与配置的参数相匹配。

## 常见问题与边缘情况处理

| Question | Answer |
|----------|--------|
| *What if I need both custom rows **and** columns?* | Set `Rows` **and** `Columns` on the same `BarcodeGenerator` instance before calling `Save`. The library combines both values to produce a grid of the requested size. |
| *Can I change the image format?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` to suit your workflow. |
| *What happens when the text is longer than the symbol can hold?* | The generator throws an `ArgumentException`. Shorten the text or increase `Columns`/`Rows` to provide more capacity. |
| *Is there a way to set DPI or image resolution?* | Use `generator.Parameters.ImageResolution` to specify the desired DPI before saving. This further **customizes barcode size** for high‑resolution printing. |
| *Does the library support other DataBar variants?* | Yes. Replace `EncodeTypes.DatabarExpandedStacked` with `DatabarExpanded`, `DatabarLimited`, etc., while keeping the same parameter structure. |

## 稳定生成条码的技巧

* **专业提示：** 在投入生产前，务必使用扫描仪或移动应用验证生成的图像。  
* **注意事项：** 空的或不存在的输出目录会导致 `Save` 抛出异常。必要时请编程创建文件夹。  
* **性能说明：** 在循环生成大量条码时，复用同一个 `BarcodeGenerator` 实例并仅修改 `Rows` 或 `Columns` 可以减少对象创建开销。

## 结论

现在您已经掌握了如何使用 **c# barcode generator** 来 **创建 databar 条码** 图像、**自定义条码尺寸**，以及 **配置 databar 参数**（如行列）。通过调整这些设置，您可以将条码适配到任何布局需求，同时保持扫描可靠性。

接下来，您可以探索诸如 **如何生成条码 PDF**、在报表中嵌入条码，或切换到其他符号体系（QR、Code‑128 等）的相关主题。尝试不同的 `Rows`、`Columns` 和图像分辨率，以找到最适合您具体使用场景的配置。

---


## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，帮助您在项目中进一步使用 API 功能并探索替代实现方式。每个资源均提供完整的可运行代码示例和逐步说明。

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}