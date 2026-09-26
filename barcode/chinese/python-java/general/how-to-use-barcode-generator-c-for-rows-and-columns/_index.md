---
category: general
date: 2026-09-26
description: 条形码生成器 C# 指南展示了在 C# 中创建 Databar Expanded Stacked 条码时如何设置行和列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: zh
lastmod: 2026-09-26
og_description: 条形码生成器 C# 教程解释如何为 Databar Expanded Stacked 条码设置行和列，提供完整代码和技巧。
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: 条形码生成器 C# – 逐步设置行和列
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: 如何使用 C# 条形码生成器处理行和列
url: /zh/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 barcode generator 设置行和列

如果您需要一个 **barcode generator C#**，能够控制 Databar Expanded Stacked 条码的视觉布局，本教程将为您提供完整、可运行的解决方案。您将学习 **如何设置行** 和 **如何设置列**，以便生成的图像符合您所需的精确设计。

以编程方式生成条码常常像是在猜测各属性的作用。阅读完本指南后，您将了解 API 的使用范围，避免常见陷阱，并拥有一段可直接复制到自己项目中的可运行代码示例。

## 前置条件

* 已安装 .NET 6.0 或更高版本（代码同样适用于 .NET Core 和 .NET Framework）
* 对提供 `BarcodeGenerator` 和 `EncodeTypes` 的条码生成库的引用（例如 Aspose.BarCode、Dynamsoft 或任何兼容的 SDK）
* 如 Visual Studio 或 VS Code 等 IDE
* 对保存 PNG 文件的文件夹具有写入权限

无需除条码 SDK 本身之外的其他 NuGet 包。

## barcode generator C# – 设置行和列

以下章节逐步演示每个配置步骤。代码片段完整，可直接粘贴到控制台应用的 `Main` 方法中。

### 步骤 1：为 Databar Expanded Stacked 条码创建生成器

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*为什么重要：* 实例化 `BarcodeGenerator` 是任何 **barcode generator C#** 工作流的第一步。构造函数接收要编码的类型和数据字符串。

### 步骤 2：设置列 – 将条码配置为使用 4 列

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

设置 `Columns` 属性会改变 DataBar 使用的垂直模块数量。`4` 的值会生成更密集、更紧凑的条码，当水平空间受限时非常有用。

### 步骤 3：使用列设置保存条码图像

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

`Save` 方法将生成的图像写入磁盘。检查输出文件，以确认四列布局如预期显示。

![barcode generator C# 示例显示行列设置](./images/barcode-rows-columns.png)

*上图展示了列配置的结果。*

### 步骤 4：为不同布局重新初始化生成器

当您需要另一个具有不同视觉排列的条码时，请创建新实例，而不是复用之前的实例。这可确保之前的设置（如列）不会渗透到新配置中。

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### 步骤 5：设置行 – 将条码配置为使用 3 行

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

`Rows` 属性控制 DataBar 模块的垂直堆叠。三行布局是许多扫描设备的默认设置，但您可以增加行数以获得更高的数据密度。

### 步骤 6：保存包含行设置的条码图像

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

打开 `DatabarRows3.png` 可看到三行排列。如果条码无法扫描，请再次检查行/列值是否符合扫描仪规格。

## 完整源代码 – 可直接复制

下面是结合上述所有步骤的完整程序。将 `YOUR_DIRECTORY` 替换为您机器上实际存在的绝对或相对路径。

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### 预期输出

运行程序会生成两个 PNG 文件：

| 文件名               | 布局描述                                 |
|----------------------|------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked，包含 **4 列** |
| `DatabarRows3.png`   | Databar Expanded Stacked，包含 **3 行** |

两个图像均应能被支持 Databar Expanded Stacked 符号的标准条码阅读器扫描。

## 常见陷阱与专业提示

| 陷阱                                   | 为什么会发生                                 | 修复 / 提示 |
|----------------------------------------|----------------------------------------------|-------------|
| 对行和列使用同一个 `BarcodeGenerator` 实例 | SDK 会保留之前的配置，因此在设置列后再设置行可能导致意外的混合 | 在更改另一维度之前重新初始化生成器（如步骤 4 所示） |
| 未正确设置 `EncodeTypes`               | SDK 默认使用其他符号集，导致条码无效           | 在需要此特定格式时，始终传入 `EncodeTypes.DatabarExpandedStacked` |
| 保存到不存在的文件夹                   | 如果路径无效，`Save` 会抛出异常               | 确保 `YOUR_DIRECTORY` 存在，或在调用 `Save` 前使用 `Directory.CreateDirectory` |
| 使用超出允许范围的值（例如 0 列）      | SDK 会验证范围并抛出 `ArgumentOutOfRangeException` | 此符号集的有效列值为 1‑4；有效行值为 1‑3 |

### 专业提示

如果需要生成大量具有不同行列组合的条码，可将配置逻辑封装到辅助方法中：

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

这种做法可减少重复代码，使代码更易维护。

## 结论

现在，您已经拥有一个清晰的端到端示例，演示如何使用 **barcode generator C#** 控制 Databar Expanded Stacked 条码的行数和列数。按照上述步骤操作，您即可生成满足扫描硬件精确布局要求的条码图像。

接下来您可以进一步探索：

* 调整其他 `DataBar` 属性，如 **AspectRatio** 或 **BarHeight**
* 使用相同的 `BarcodeGenerator` 类生成其他符号（例如 QR、Code128）
* 将生成的 PNG 嵌入 PDF，或直接从 C# 打印

欢迎尝试不同的行/列组合，并在评论区分享您的结果。祝编码愉快！

## 接下来您应该学习什么？

- [如何为 Databar Expanded Stacked 条码设置列 – 完整 C# 指南](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Databar Expanded Stacked 条码指南 – 如何在 C# 中生成和设置大小](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [C# 中的条码生成器示例 – 设置列、行并导出图像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}