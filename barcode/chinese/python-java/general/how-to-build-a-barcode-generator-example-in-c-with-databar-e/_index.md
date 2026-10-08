---
category: general
date: 2026-09-19
description: 使用 C# 的条形码生成器示例，展示如何使用 Aspose.BarCode 生成列和行布局的条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: zh
lastmod: 2026-09-19
og_description: 条形码生成器示例演示了如何使用 Aspose.BarCode 在 C# 中通过列和行布局生成条形码。
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: 条形码生成器示例 – 在 C# 中创建 DataBar 扩展堆叠条码
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 DataBar Expanded Stacked 构建条形码生成器示例
url: /zh/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成示例 – 在 C# 中创建 DataBar Expanded Stacked 条码

如果您需要一个 **条形码生成示例** 能在 .NET 项目中运行，本指南将详细演示如何使用 Aspose.BarCode 库在 C# 中生成条码。您将看到如何为列布局和行布局分别配置 DataBar Expanded Stacked 条码，并获得可直接运行的代码生成 PNG 图像。

本教程涵盖从安装 NuGet 包到保存最终图像的全部步骤，您可以直接将代码复制到自己的解决方案中，无需额外查找。

## 您将学到

* 如何在 C# 项目中安装并引用 Aspose.BarCode。  
* 如何创建一个 **条形码生成示例** 来编码长数据字符串。  
* 如何在同一种条码类型上设置 4 列布局和 3 行布局。  
* 如何将生成的图像保存为 PNG 文件。  

文章结束时，您将拥有两个可直接使用的 PNG 文件：`ExpandedStackedCols4.png`（四列）和 `ExpandedStackedRows3.png`（三行）。

## 前置条件

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7.2）。  
* Visual Studio 2022、VS Code 或任意您喜欢的 C# IDE。  
* 能够访问互联网以下载 **Aspose.BarCode** NuGet 包。  

不需要额外的外部服务。

## 第一步：安装 Aspose.BarCode NuGet 包

在项目文件夹的终端中运行：

```bash
dotnet add package Aspose.BarCode
```

该命令会将最新稳定版的 Aspose.BarCode 添加到项目文件中。包恢复完成后，您即可在 C# 源文件中引用其命名空间。

## 第二步：添加所需的 using 指令

创建一个新的 C# 控制台应用程序（或在现有项目中添加代码），并在文件顶部加入以下 `using` 语句：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

这些指令让您能够访问 **条形码生成示例** 中使用的 `BarcodeGenerator` 类和 `EncodeTypes` 枚举。

## 第三步：创建一个带 4 列布局的条形码生成示例

示例的第一部分构建一个使用四列排列的 DataBar Expanded Stacked 条码。下面的代码严格遵循原始片段的步骤，同时添加了说明每行代码作用的注释。

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**工作原理说明**

* `EncodeTypes.DatabarExpandedStacked` 告诉 Aspose.BarCode 生成 DataBar Expanded Stacked 符号，适用于零售场景。  
* 将 `DataBar.Columns` 设置为 `4` 强制生成器将符号分为四个垂直段，以提升在窄标签上的可读性。  
* `Save` 将条码写入磁盘；`BarCodeImageFormat.Png` 参数确保图像无损质量。

运行此代码块后，会在应用程序的工作目录生成 `ExpandedStackedCols4.png`。该文件包含高分辨率条码，可被任何标准 DataBar 读取器扫描。

## 第四步：为不同布局重新初始化生成器

为了演示基于行的布局，需要一个全新的 `BarcodeGenerator` 实例。重新初始化可确保之前的列设置不会影响新的配置。

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## 第五步：配置条码使用 3 行布局

DataBar API 同样支持行排列。设置 `Rows` 属性即可定义符号包含多少水平切片。

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**为何选择行而非列**

当标签高度受限而宽度充足时，使用行布局更为合适。三行布局在垂直方向压缩条码，同时保留所需的数据量。

## 完整源文件

下面是一个完整的、可自行编译运行的 `Program.cs`，其中包含列示例和行示例，单次执行即可生成两个 PNG 文件。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### 预期输出

运行程序后，控制台会显示两条确认文件创建的消息：

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

两个 PNG 文件均展示了编码字符串 `"Long data string"` 的 DataBar Expanded Stacked 条码。使用标准条码扫描器扫描任意图像均会返回原始数据。

## 常见问题与边缘情况

| 问题 | 答案 |
|----------|--------|
| **可以更改图像格式吗？** | 可以。将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Tiff`，根据需求选择。 |
| **如果数据字符串更短怎么办？** | DataBar 格式会自动调整符号大小，无需修改布局设置。 |
| **如何设置条码尺寸（宽度/高度）？** | 在调用 `Save` 之前使用 `generator.Parameters.Image.Width` 和 `generator.Parameters.Image.Height`。 |
| **能否添加可读的文字说明？** | 设置 `generator.Parameters.Barcode.CodeText` 并启用 `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`。 |
| **支持哪些 .NET 版本？** | Aspose.BarCode 支持 .NET Standard 2.0、.NET 5/6 以及 .NET Framework 4.6.1 以上。 |

针对这些变体的处理，使得 **条形码生成示例** 足够稳健，可用于生产环境。

## 专业技巧

* **仅在布局保持不变时复用生成器对象。** 如步骤 4‑5 所示，为每种布局创建新实例，可防止属性意外继承。  
* 如需确保符合 ISO/GS1 标准，可使用 `generator.Validate()` 对生成的条码进行验证。  
* **批量处理：** 将列和行逻辑封装在循环中，遍历一组布局配置，可在需要大量变体时减少代码重复。

## 结论

本 **条形码生成示例** 演示了如何使用 **生成条码 C#** 代码生成 4 列和 3 行的 DataBar Expanded Stacked 条码。您现在拥有完整的可运行程序、关键属性（`Columns`、`Rows`）的理解，以及扩展方案的实用技巧。

接下来，可进一步探索 **自定义条码颜色**、**在 PDF 文档中嵌入条码** 或 **使用 Aspose.BarCode 生成 QR 码** 等相关主题。所有这些内容均基于本指南中介绍的 API 原则。

欢迎尝试不同的数据字符串、图像格式和布局组合。祝编码愉快！

## 接下来您可以学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方式。

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}