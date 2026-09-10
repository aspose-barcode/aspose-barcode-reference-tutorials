---
category: general
date: 2026-07-24
description: Barcode Generator C# 教程，展示如何生成条形码图像、设置列、设置行，并仅用几行代码创建 Databar 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: zh
lastmod: 2026-07-24
og_description: Barcode Generator C# 教程将带您逐步生成条形码图像、配置列和行，并使用清晰的代码示例创建 Databar 条码。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: 条码生成器 C# – 快速构建 DataBar 堆叠条码
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 条形码生成器 C# – 创建 DataBar 扩展堆叠图像
url: /zh/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成器 C# – DataBar Expanded Stacked 完整指南

有没有想过如何使用 **barcode generator c#** 在几秒钟内生成清晰、可扫描的图像？也许你曾盯着一个空白项目，不确定列或行该放在哪里，或者如何真正 *generate barcode image* 文件而不头疼。好吧，你来对地方了。在本教程中，我们将创建一个小型控制台应用程序，生成一个 DataBar Expanded Stacked 条形码，调整其布局，并将结果保存为 PNG——全部使用 **barcode generator c#** 库。

我们将覆盖你需要了解的所有内容：安装包、配置列和行（是的，我们会回答 *how to set columns* 和 *how to set rows*），以及最终如何 **create databar barcode** 对象，您可以将其嵌入发票、票据或任何需要机器可读标签的地方。无需外部文档；只需复制粘贴、运行，你会看到文件夹中出现两个 PNG 文件。

## 你需要的环境

- .NET 6.0 SDK 或更高版本（代码在 .NET Core、.NET Framework 和 .NET 5+ 上均可运行）
- 一个全新的控制台项目（`dotnet new console`）——如果你更喜欢 UI，也可以使用 Visual Studio。
- Aspose.BarCode for .NET NuGet 包（为 **barcode generator c#** 提供动力的库）。使用以下方式安装：

```bash
dotnet add package Aspose.BarCode
```

就这样。包恢复后即可开始。

## 条形码生成器 C# – 项目设置

首先，让我们引入必要的命名空间，并创建一个帮助方法，以保持主程序的整洁。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### 为什么这种结构有效

- **关注点分离** – 每个帮助方法专注于单一配置（列或行）。这使代码更易于阅读和复用。
- **显式参数** – 我们将 `columns` 或 `rows` 作为参数传入，这样你可以在不修改方法体的情况下调用相同的方法并传入任意值。
- **即时反馈** – `Console.WriteLine` 会告诉你文件保存的位置，在终端运行程序时非常方便。

## 如何为 DataBar Expanded Stacked 设置列

`DataBar.Columns` 属性是决定条形码包含多少垂直切片的调节器。默认值为 `4`，但根据你编码的数据量或扫描仪的要求，可能需要 `2` 或 `6`。下面是一个快速代码片段，专门演示列设置逻辑：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**专业提示：** 增加列数会使条形码的整体宽度按比例增长。如果你计划将图像嵌入 PDF 或网页，请确保容器能够容纳额外的宽度，否则扫描仪可能会读取错误。

## 如何为 DataBar Expanded Stacked 设置行

行的工作方式相同，但它们影响条形码的高度。默认行数为 `3`。如果标签的垂直空间有限，你可以将其降至 `2`。相反，更多的行数可以在低分辨率打印机上提升可读性。

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**注意：** 将行数设置为低于编码数据所需的最小值会在运行时抛出异常。库会抛出带有明确信息的 `ArgumentException`，因此你会立即知道配置无效。

## 生成条形码图像 – 保存为 PNG

上述两个帮助方法都以调用 `Save` 结束。`BarCodeImageFormat.Png` 枚举指示 Aspose.BarCode 输出无损的 PNG 文件，这在大多数扫描场景中是理想的，因为它保留了清晰的边缘。如果你更喜欢其他格式（网页用 JPEG，旧系统用 BMP），只需替换枚举值——无需其他代码更改。

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

生成的 PNG 如下（想象图像；下面的 alt 文本描述它）：

> **生成图像的 Alt 文本：** *DataBar Expanded Stacked 条形码，左侧 4 列，右侧 3 行，以高对比度的黑色渲染在透明背景上。*

## 创建 DataBar 条形码 – 完整工作示例

将所有内容整合在一起，下面是一个紧凑的版本，你可以直接放入 `Program.cs`。它演示了列和行的配置，并快速检查保存后文件是否存在。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### 预期输出

运行程序（`dotnet run`）时，你应该看到类似以下的控制台输出：

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

在任意图像查看器中打开这两个 PNG 文件；你会注意到左侧文件有四个垂直模块（列），而右侧文件有三行模块（行）。两者都可以被任何标准的 DataBar 读取器完美扫描。

## 常见陷阱及避免方法

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | 列设置为 0 或大于 8（库上限为 8）。 | 使用 **1** 到 **8** 之间的值。 |
| 条形码在 PDF 中模糊 | PNG 以默认 DPI（96）保存后被缩放。 | 在保存前使用 `generator.Parameters.ImageResolution = 300;`。 |
| 仅更改行配置时扫描仪失败 | 行已更改但列保持默认，导致与数据长度不匹配。 | 同时调整行 **和** 列，或通过省略手动设置让库自动尺寸。 |

## 下一步

现在你已经了解如何 **generate barcode image**、**set columns**、**set rows**，以及使用 **barcode generator c#** **create databar barcode**，你可以：

- 使用 `Aspose.PDF` 或 `iTextSharp` 将 PNG 嵌入 PDF。
- 如果需要更小的占用空间，切换到 `EncodeTypes.DatabarLimited`。
- 尝试颜色（`generator.Parameters.Barcode.ForeColor = Color.Blue`）。
- 在同一项目中添加 QR 码或其他符号——Aspose.BarCode 支持超过 150 种类型。

如果遇到任何问题，请在下方留言或查阅官方 Aspose.BarCode 文档（API 参考非常完整，包含数十个实时代码示例）。祝编码愉快，愿你的扫描仪永不失误！

## 接下来应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本教程展示的技术。每个资源都包含完整的可运行代码示例和逐步解释，帮助你掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [创建 DotCode 条形码图像 – 行与列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [创建条形码图像 c# – 配置 Codablock F 行与列](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [生成条形码图像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}