---
category: general
date: 2026-10-02
description: 学习如何在 C# 条码生成器中设置列和行以创建 DataBar 条码。一步一步的指南，附完整代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: zh
lastmod: 2026-10-02
og_description: C# 条码生成器指南 – 学习如何设置列和行以创建 DataBar 条码，并提供完整代码示例。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: C# 条码生成器：设置 DataBar 条码的列和行
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: 如何使用 C# 条码生成器创建具有自定义列和行的 DataBar 条码
url: /zh/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条码生成器创建具有自定义列和行的 DataBar 条码

如果您需要一个 **c# barcode generator** 能够生成具有精确列和行配置的 DataBar 条码，本教程将准确展示操作方法。您将了解为何调整列和行很重要，并获得一个完整、可直接运行的示例，创建 4 列和 3 行的 DataBar Expanded Stacked 条码。

在接下来的章节中，我们将介绍：

* 使用 Aspose.BarCode for .NET 库的前提条件。
* 如何在 DataBar 条码上设置列（`how to set columns`）和行（`how to set rows`）。
* 一个完整的 C# 控制台程序，您可以复制、编译并执行。
* 预期的输出文件以及故障排除提示。

通过本指南，您将能够 **create databar barcode** 图像，以满足您的布局需求。

## 前提条件

在开始之前，请确保您具备以下条件：

| 要求 | 原因 |
|------|------|
| .NET 6.0 SDK or later | 为 C# 代码提供运行时环境。 |
| Visual Studio 2022 (or any IDE that supports .NET) | 使项目创建和调试更为简便。 |
| Aspose.BarCode for .NET NuGet package | 提供示例中使用的 `BarcodeGenerator` 类。 |
| Write permission to a folder for the output PNG files | 生成器将条码图像写入磁盘。 |

使用以下命令安装 Aspose.BarCode 包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：创建基本的 DataBar Expanded Stacked 条码

第一步是实例化一个 **c# barcode generator**，使用 `EncodeTypes.DatabarExpandedStacked` 格式。该格式是一种二维 DataBar 条码，最多可编码 74 个数字字符。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

构造函数接受两个参数：

* `EncodeTypes.DatabarExpandedStacked` – 告诉库使用哪种符号体系。
* `"Databar Expanded Stacked long"` – 将被编码的文本。

## 步骤 2：如何设置列

列影响 DataBar 条码的水平密度。增加列数会使条码更宽，从而在低分辨率打印机上提升扫描可靠性。

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**为什么是 4 列？**  
四列在大多数零售应用中在尺寸和可读性之间提供了良好的平衡。您可以尝试 1 到 8 的值；库会自动调整模块宽度。

## 步骤 3：保存列配置的条码

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

图像以 PNG 文件保存，能够保持条码扫描仪所需的清晰边缘。

## 步骤 4：为行配置创建单独的生成器

行配置的工作方式相同，但影响垂直密度。为避免列和行设置混合，我们创建一个新的生成器实例。

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 步骤 5：如何设置行

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**何时使用更多行？**  
增加行数会使条码更高，当水平打印空间受限而垂直空间充足时（例如，产品标签高度大于宽度），这会很有用。

## 步骤 6：保存行配置的条码

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

两个 PNG 文件（`DatabarCols4.png` 和 `DatabarRows3.png`）将出现在 `C:\Barcodes` 文件夹中。

## 完整、可运行的示例

下面是一个独立的控制台应用程序，包含上述所有步骤。将代码复制到新的 .NET 控制台项目中并运行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### 代码功能说明

| 部分 | 目的 |
|------|------|
| **命名空间导入** | 引入 `Aspose.BarCode` 和 `Aspose.BarCode.Generation`。 |
| **输出目录** | 集中路径，以便在移动文件夹时只需编辑一行代码。 |
| **列生成器** | 演示在 `c# barcode generator` 上 **how to set columns**。 |
| **行生成器** | 演示在 `c# barcode generator` 上 **how to set rows**。 |
| **保存调用** | 将 PNG 文件写入磁盘，使其可用于扫描或报告中。 |
| **控制台输出** | 提供即时反馈，对开发过程有帮助。 |

## 预期输出

运行程序后，您应该会看到两个 PNG 文件：

* **DatabarCols4.png** – 显示四列的更宽条码。  
* **DatabarRows3.png** – 显示三行的更高条码。

两个图像均包含文本 *“Databar Expanded Stacked long”*，使用 DataBar Expanded Stacked 符号体系编码。您可以在任何图像查看器中打开它们，或将其送入条码扫描仪以验证可读性。

## 常见陷阱及避免方法

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **File‑access exception** | 输出文件夹不存在或您没有写入权限。 | 手动创建文件夹或以提升的权限运行程序。 |
| **Incorrect column/row values** | 库仅接受列值 1‑8 和行值 1‑4。 | 在赋值前验证数值，例如 `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`。 |
| **Barcode not scanning** | 生成的图像对扫描仪的分辨率来说太小。 | 使用 `generator.Parameters.Image.Height` 或 `...Width` 增加 `ImageHeight` 或 `ImageWidth`。 |
| **Text truncation** | 编码的文本超出所选 DataBar 变体的最大长度。 | 使用更短的字符串，或如果需要更大容量则切换到 `EncodeTypes.DatabarExpanded`。 |

## 专业提示

* **Cache the generator** – 如果需要使用相同的列/行设置创建大量条码，请复用同一个 `BarcodeGenerator` 实例，仅更改 `CodeText` 属性。  
* **Batch processing** – 对产品标识集合进行循环，在循环中设置 `generator.CodeText`，并在每次迭代时使用唯一的文件名调用 `Save`。  
* **Performance** – 对于高吞吐场景，禁用抗锯齿 (`generator.Parameters.Image.AntiAlias = false`) 可加快图像生成速度，而不影响扫描质量。  

## 后续步骤

既然您已经了解如何使用 **c# barcode generator** **how to set columns** 和 **how to set rows**，您可能想进一步探索：

* **在条码下方添加可读文本** (`generator.Parameters.Barcode.CodeTextLocation`)。  
* **更改颜色** (`generator.Parameters.Image.ForegroundColor` 和 `BackgroundColor`)。  
* **生成其他 DataBar 变体**，如 `DatabarLimited` 或 `DatabarExpanded`。  
* **在 PDF 报告中嵌入条码**，使用 Aspose.PDF。  

这些主题都基于此处的基础，帮助您创建更丰富、可投入生产的条码解决方案。

---

*祝编码愉快！如果遇到任何问题，欢迎留言或查阅 Aspose.BarCode 文档获取更深入的 API 细节。*

## 接下来应该学习什么？

以下教程涵盖与本指南紧密相关的主题，构建在此处演示的技术之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [如何使用 C# BarcodeGenerator 设置条码列和行](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [C# 条码生成器示例 – 设置列、行并导出图像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [如何使用 C# 条码生成器创建 DataBar 条码](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}