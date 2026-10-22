---
category: general
date: 2026-10-21
description: 使用 BarcodeGenerator 在 C# 中生成 Databar Expanded Stacked 条码图像。按照本分步指南创建条码图像、定制行列并导出
  PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: zh
lastmod: 2026-10-21
og_description: 使用本教程在 C# 中生成 databar 扩展堆叠条形码。了解如何使用 BarcodeGenerator、设置行列并保存 PNG
  图像。
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: 在 C# 中生成 DataBar 扩展堆叠条码 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中生成 DataBar Expanded Stacked 条码
url: /zh/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成 Databar Expanded Stacked 条形码

如果您需要在 C# 中生成 **databar expanded stacked** 条形码，本指南将向您展示如何操作。databar expanded stacked 符号非常适合在紧凑的形式中编码大量数据，您只需几行代码即可创建图像。您还将学习如何以不同格式 **生成条形码图像** 文件，并自定义行或列以适应您的扫描环境。

本教程涵盖了开始生成 databar 条形码所需的全部内容：安装必需的库、准备输出文件夹、使用自定义行或列创建条形码，以及将结果保存为 PNG 文件。完成后，您将能够以编程方式 **创建 databar 条形码** 图像，并将代码适配到其他图像格式或运行时场景。

## 前提条件

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Core 3.1 和 .NET Framework 4.7+）
* 如 Visual Studio 2022、Visual Studio Code 或 Rider 等开发环境
* 能够访问互联网以安装 **Barcode Generator C#** NuGet 包（Aspose.BarCode for .NET）

> **专业提示：** 如果您使用 CI/CD 流水线，请在项目文件中添加 NuGet 包引用，以确保构建可复现。

## 安装 Barcode Generator C# 库

示例使用 Aspose.BarCode 库，该库提供 `BarcodeGenerator` 类和 `EncodeTypes.DatabarExpandedStacked` 枚举。

```bash
dotnet add package Aspose.BarCode
```

该命令会将最新的稳定版本添加到您的项目中。安装完成后，您可以在 C# 文件中导入相应的命名空间：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## 准备输出文件夹

可靠的文件路径可以防止库在写入图像时出现运行时错误。以下代码会在目录不存在时创建它：

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **为何重要：** 尝试保存到不存在的目录会抛出 `IOException`。提前创建文件夹可以让代码在本地开发和生产环境中都更加稳健。

## 生成 databar expanded stacked 条形码图像

### 基础条形码生成

生成 **databar expanded stacked** 图像的最简方法是使用所需的 `EncodeTypes` 值和纯文本负载实例化 `BarcodeGenerator`。

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

运行此代码片段后，会在 *Barcodes* 文件夹中生成 `DatabarBasic.png`。该图像包含默认布局（4 列 × 4 行）的标准 databar expanded stacked 符号。

### 自定义列 – 创建 4 列的 databar 条形码

您可以通过 `Parameters.Barcode.DataBar.Columns` 属性控制列数。下面的示例在保持默认行数的情况下创建了 **4 列** 的条形码。

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

生成的文件 **DatabarCols4.png** 如下所示：

![带有4列的Databar扩展堆叠条形码](databar_cols4.png "带有4列的Databar扩展堆叠条形码 – 使用C#生成")

*图片 alt 文本 (og_image_alt):* **使用 C# 生成的示例 Databar 扩展堆叠条形码图像** – 这满足了 SEO 对图片 alt 文本的要求。

### 自定义行 – 创建 3 行的 databar 条形码

同样，您可以通过 `Parameters.Barcode.DataBar.Rows` 调整行数。下面的代码生成了 **3 行** 且列数保持默认（4 列）的条形码。

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

文件 **DatabarRows3.png** 包含一个在垂直方向上稍微更短的 databar expanded stacked 符号，这在空间受限的标签上非常有用。

### 导出为其他格式

如果需要不同的图像类型（例如 JPEG、BMP 或 SVG），请将 `BarCodeImageFormat.Png` 替换为相应的枚举值：

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

该库还支持 SVG 等矢量格式，非常适合高分辨率打印。

## 高级场景

### 保存到内存流

有时您希望直接将条形码嵌入到 Web 响应或 PDF 中，而不触及文件系统。可以使用 `MemoryStream`：

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### 处理无效输入

`BarcodeGenerator` 会根据所选符号验证负载。如果数据包含禁止字符，将抛出 `ArgumentException`。请将生成代码放在 try‑catch 块中，以提供友好的错误提示：

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### 缩放条形码图像

通过设置 `Parameters.Image.Width` 和 `Parameters.Image.Height`，您可以在不改变编码数据的前提下更改图像尺寸：

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

当条形码必须满足扫描仪的特定 DPI 要求时，缩放非常有用。

## 完整工作示例

下面是一个完整的、可直接运行的控制台应用程序，演示了本文讨论的所有步骤：

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**预期输出**


## 接下来您应该学习什么？

以下教程涵盖了与本指南紧密相关的主题，构建在本教程展示的技术之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何为 Databar Expanded Stacked 条形码设置列 – 完整 C# 指南](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [如何在 C# 中使用 DataBar Expanded Stacked 构建条形码生成器示例](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked 条形码指南 – 如何在 C# 中生成和调整大小](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}