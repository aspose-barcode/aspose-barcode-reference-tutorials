---
category: general
date: 2026-09-07
description: 条码生成器 C# 教程，展示如何生成条码 PNG 文件并创建可自定义行列的 DataBar 条码
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: zh
lastmod: 2026-09-07
og_description: 条形码生成器 C# 教程：学习如何生成条形码 PNG 文件，并在几分钟内使用自定义行列创建 DataBar 条形码
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: 条形码生成器 C# – 创建 DataBar 条码和 PNG 图像
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: 如何使用 C# 条码生成器创建 DataBar 条码
url: /zh/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条码生成器创建 DataBar 条码

如果您需要 **C# 条码生成器** 来生成高质量的条码，本指南将向您展示如何 **生成条码 PNG** 文件并使用自定义行列创建 DataBar 条码。无论是构建零售库存系统还是票务平台，下面的步骤都能让您在单个自包含示例中生成 DataBar Expanded Stacked 条码。

在本教程中，您将学习：

* 如何实例化用于 DataBar Expanded Stacked 符号的 `BarcodeGenerator`。  
* 如何调整列和行设置以符合 ISO / GS1 规范。  
* 如何将输出保存为 PNG 图像，以便嵌入网页或打印标签。  

无需外部服务——只需 Aspose.BarCode for .NET 库（或任何遵循相同 API 的兼容库）。代码在 .NET 6+ 上运行，可在 Visual Studio、Rider 或任何支持 C# 的 IDE 中使用。

## 前置条件

在开始之前，请确保您拥有：

* 已安装 .NET 6 SDK 或更高版本。  
* 对 `Aspose.BarCode` NuGet 包的引用（或提供 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 的等效库）。  
* 对 C# 语法和项目结构的基本了解。  

您可以通过命令行添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 第 1 步：为 DataBar Expanded Stacked 初始化 C# 条码生成器

第一步是创建一个针对 **DataBar Expanded Stacked** 符号的 `BarcodeGenerator` 实例。该对象保存所有渲染参数，包括要编码的文本。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**为什么重要：** `EncodeTypes.DatabarExpandedStacked` 枚举值告诉库使用哪种条码标准。使用正确的枚举可确保生成的图像符合 GS1 DataBar 规范。

## 第 2 步：配置列数（使用默认行数）

DataBar Expanded Stacked 可以拆分为多个列。调整列数会改变视觉密度，并有助于在受限空间内容纳更长的数据字符串。

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**小贴士：** 默认列数为 1。将其设为 4 会创建四个堆叠列，适合较长的数字字符串，同时保持条码高度可控。

## 第 3 步：使用列设置生成条码 PNG

现在将条码保存为 PNG 图像。PNG 能保留扫描仪所需的清晰边缘，且在网页和打印介质上均表现良好。

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

文件 `DatabarCols4.png` 包含一个 **条码 PNG**，您可以直接在 HTML 中嵌入：

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## 第 4 步：为行配置创建单独的生成器实例

如果需要控制行数而非列数，请实例化一个新的 `BarcodeGenerator`。在更改维度后复用同一实例可能导致意外的布局问题，使用全新对象是最安全的做法。

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 第 5 步：设置行数（使用默认列数）

行数影响条码模块的垂直堆叠。增加行数会使条码更高，这在某些标签尺寸下可能是必需的。

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**为什么区分行与列：** 列在水平方向拆分条码，行则在垂直方向延伸。请选择最适合标签布局的方向。

## 第 6 步：使用行设置生成条码 PNG

最后，将行调整后的条码保存为 PNG 文件。

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

您现在拥有两个不同的 PNG 文件：

* `DatabarCols4.png` – 4 列，1 行。  
* `DatabarRows3.png` – 1 列，3 行。

两张图像均可直接用于应用程序、报表或打印标签。

## 如何在 C# 中使用自定义尺寸生成条码 PNG 文件

上述模式可复用于任何 DataBar 变体或库支持的其他符号。以下是一个紧凑的模板，您可以复制粘贴到工具类中：

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

像这样调用该方法：

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**需要注意的边界情况**

* **数据长度** – DataBar Expanded Stacked 最多可编码 74 位数字字符。超出此限制会抛出异常。请在调用生成器前验证输入长度。  
* **无效维度** – 对于该符号，库将列限制在 1‑4，行限制在 1‑3。提供超出范围的值会被忽略或导致错误。  
* **图像 DPI** – 如需更高分辨率以供打印，可在保存前设置 `generator.Parameters.ImageResolution`。

## 预期输出

打开 `DatabarCols4.png` 或 `DatabarRows3.png` 时，您应看到清晰、高对比度的 DataBar 条码。使用兼容 GS1 的扫描器扫描该图像，将返回原始文本 `"Databar Expanded Stacked long"`。

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Alt text: 使用 C# 条码生成器保存为 PNG 的 DataBar Expanded Stacked 条码示例*

## 结论

本教程演示了如何使用 **C# 条码生成器** 来 **创建 DataBar 条码** 并 **生成带有自定义行列设置的条码 PNG** 文件。通过六个步骤——初始化生成器、配置列或行、保存为 PNG——您即可获得可直接用于库存系统、票务或任何需要可靠条码渲染的场景的生产级图像。

接下来，您可以探索：

* 为 PNG 添加颜色或背景图像（仍然兼容大多数扫描器）。  
* 使用相同的 `BarcodeGenerator` API 生成其他符号，如 QR、Code 128 或 PDF417。  
* 将生成的 PNG 直接嵌入 ASP.NET Core MVC 视图或 Blazor 组件中。

欢迎尝试不同的数据字符串、尺寸和图像格式（例如 JPEG、BMP）。相同的模式适用于所有情况，使 **C# 条码生成器** 成为任何 .NET 开发者工具箱中的多功能工具。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在自己的项目中进一步掌握 API 功能并探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步说明。

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}