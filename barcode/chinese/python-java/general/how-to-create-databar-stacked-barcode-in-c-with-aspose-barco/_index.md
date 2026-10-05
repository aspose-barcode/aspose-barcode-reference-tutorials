---
category: general
date: 2026-09-13
description: 使用 Aspose.Barcode 在 C# 中快速创建 DataBar 堆叠条码——学习设置列、行并保存图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: zh
lastmod: 2026-09-13
og_description: 使用 Aspose.Barcode 在 C# 中创建堆叠式 DataBar 条码。本指南展示如何配置列、行以及导出 PNG 图像。
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: 在 C# 中创建 Databar 堆叠条码 – 完整分步指南
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: 如何在 C# 中使用 Aspose.Barcode 创建堆叠式 DataBar 条码
url: /zh/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.Barcode 创建堆叠式 DataBar 条码

如果您需要在 .NET 应用程序中**创建堆叠式 DataBar 条码**，本指南提供了完整的、可直接运行的解决方案。您将看到如何配置列数、调整行数，并将结果保存为 PNG 文件——全部使用 Aspose.Barcode for .NET 库。

只要了解三步工作流：实例化生成器、设置所需尺寸、将图像写入磁盘，生成**Databar Expanded Stacked** 条码就不再是谜。以下章节将逐步带您完成每一步，解释设置的意义，并展示您可以即时验证的最终输出。

## 先决条件

- **Visual Studio 2022**（或任何 C# IDE），已安装 .NET 6+。
- **Aspose.Barcode for .NET** NuGet 包（`Install-Package Aspose.Barcode`）。
- 对保存 PNG 文件的文件夹拥有写入权限。

不需要其他依赖。

## 步骤 1：设置项目并添加 Aspose.Barcode

1. 创建一个新的控制台应用程序项目：

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. 添加 Aspose.Barcode 包：

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. 打开 **Program.cs** 并添加所需的 `using` 语句：

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

这些步骤确保 **C# 条码生成器** 类可在您的代码中使用。

## 步骤 2：为堆叠式 DataBar 条码创建生成器

您需要的第一个对象是为 **Databar Expanded Stacked** 符号配置的 `BarcodeGenerator`。该对象是所有条码相关操作的入口。

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**为什么这很重要：**  
`EncodeTypes.DatabarExpandedStacked` 告诉 Aspose.Barcode 使用 DataBar 系列的堆叠版本，适用于高度受限的空间，如收据。第二个参数提供条码中编码的数据；您可以将其替换为符合 DataBar 标准的任意数字或字母数字字符串。

## 步骤 3：配置条码列并保存图像

堆叠式 DataBar 可以使用可配置的 **列** 数量进行显示。默认是三列，但对于较长的数据字符串可能需要四列。在保存之前调整 `Columns` 属性。

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**说明：**  
- `Parameters.Barcode.DataBar.Columns` 直接影响条码的水平分段。更多列会生成更宽的图像，但高度保持不变。  
- `Save` 将条码写入 PNG 文件。通过传入不同的 `BarCodeImageFormat` 值，还支持其他格式（JPEG、BMP、SVG）。

## 步骤 4：创建另一个生成器并配置条码行

有时扫描环境需要更高的条码，您可以通过增加 **行** 数来实现。下面的代码片段创建了第二个生成器实例，设置三行，并保存结果。

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**为什么使用单独的实例？**  
在同一个 `BarcodeGenerator` 上在保存调用后更改 `Rows` 也可以工作，但创建全新的实例可以使每个配置相互独立，代码更易阅读——尤其是在后续扩展教程以涵盖更多变体（例如不同的数据字符串或纠错级别）时。

## 步骤 5：验证生成的条码

打开刚才创建的两个 PNG 文件。您应该看到：

- **DatabarCols4.png** – 由四个垂直列组成的更宽条码。  
- **DatabarRows3.png** – 由三行水平组成的更高条码。

两个图像编码相同的文本（`"Databar Expanded Stacked long"`），但视觉结构不同。使用任何标准 DataBar 扫描仪或支持 DataBar 的移动应用扫描，以确认它们能够正确解码。

## 常见陷阱与专业提示

| 问题 | 原因 | 避免方法 |
|------|------|----------|
| **文件夹路径不正确** | 如果目录不存在，`Save` 会抛出 `DirectoryNotFoundException`。 | 在调用 `Save` 之前使用 `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` 创建目录。 |
| **列/行数量过多** | DataBar 规范将列数限制为 4，行数限制为 3。 | 请遵守允许范围；否则 Aspose.Barcode 将抛出 `ArgumentOutOfRangeException`。 |
| **条码不可读** | 低图像分辨率会导致条码模糊。 | 如果需要更高质量（例如 300 dpi），可通过 `barcodeGenerator.Parameters.ImageResolution` 提高 DPI。 |
| **数据格式错误** | 在某些模式下，DataBar 仅接受最多 13 位的数字字符串。 | 在将输入字符串传递给生成器之前进行验证。 |

## 扩展示例

现在您已经能够使用自定义列和行**创建堆叠式 DataBar 条码**，您可能想进一步探索：

- **更改前景/背景颜色**（`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`）。  
- **添加安静区**（`barcodeGenerator.Parameters.Barcode.Qz = 2;`）。  
- **导出为 SVG** 以实现分辨率无关的渲染（`BarCodeImageFormat.Svg`）。

所有这些选项均记录在 [Aspose.Barcode for .NET API reference](https://docs.aspose.com/barcode/net/) 中。

## 完整源代码

下面是完整的可运行程序，包含上述所有步骤。将其复制到您的 `Program.cs` 中，将 `YOUR_DIRECTORY` 替换为实际路径，然后运行 `dotnet run`。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

运行程序后会生成两个 PNG 文件，演示 **条码列** 和 **条码行** 如何影响 **Databar Expanded Stacked** 符号的视觉布局。

## 结论

您现在已经了解如何使用 Aspose.Barcode for .NET 在 C# 中**创建堆叠式 DataBar 条码**。通过调整 `Columns` 和 `Rows` 属性，您可以生成适应各种空间限制且保持数据完整性的条码。示例涵盖了从项目设置到故障排除的全部内容，为更高级的条码场景奠定了坚实基础。

**下一步：**  
- 尝试不同的数据字符串，观察列/行限制对可读性的影响。  
- 将此代码与 Web API 结合，实现按需生成条码。  
- 使用相同的 `BarcodeGenerator` 模式探索其他符号（例如 QR、Code128）。

祝编码愉快，愿您的扫描始终成功！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在本指南演示的技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [Barcode Generator C# – Create DataBar Expanded Stacked Images](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}