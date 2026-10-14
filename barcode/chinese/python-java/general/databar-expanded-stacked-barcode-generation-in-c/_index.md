---
category: general
date: 2026-09-29
description: 学习如何在 C# 中创建 Databar Expanded Stacked 条码并生成条码图像。本分步指南展示了如何使用 BarcodeGenerator
  设置行和列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: zh
lastmod: 2026-09-29
og_description: 在 C# 中解释 Databar Expanded Stacked 条码生成。按照教程创建条码图像、设置行数，并使用 BarcodeGenerator
  保存 PNG 文件。
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: 在 C# 中生成 Databar Expanded Stacked 条码 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 在 C# 中生成 Databar Expanded Stacked 条码
url: /zh/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar Expanded Stacked 条形码生成（C#）

如果您需要在 C# 中生成 **Databar Expanded Stacked** 条形码，本指南将向您展示 **如何创建条形码** 图像并自定义行数和列数。您将了解 **如何设置行数**、如何设置列数，以及如何使用 Aspose.BarCode 的 `BarcodeGenerator` 类 **生成条形码图像** 文件。

在本教程中，您将：

* 安装所需的 NuGet 包。
* 为 Databar Expanded Stacked 符号初始化 `BarcodeGenerator`。
* 配置列数和行数。
* 保存生成的 PNG 文件。
* 了解常见的陷阱，如缺少许可证或图像路径错误。

唯一的前置条件是最近的 .NET SDK（≥ .NET 6）和 Visual Studio 2022 等 IDE。无需外部服务。

## 安装并配置 BarcodeGenerator C# 库

在编写任何代码之前，将 Aspose.BarCode 包添加到项目中：

```bash
dotnet add package Aspose.BarCode
```

如果您使用 Visual Studio，也可以通过 **NuGet 包管理器**（搜索 *Aspose.BarCode*）进行安装。包恢复完成后，即可开始编码。

> **专业提示：** 免费评估版会在生成的条形码上添加小水印。生产环境请获取许可证文件，并在创建任何条形码对象之前调用 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`。

## 生成 Databar Expanded Stacked 条形码图像

创建一个新的控制台应用程序（或将代码集成到任意 C# 项目），并添加以下 `using` 语句：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

现在编写完整程序。代码严格遵循原示例的步骤，并添加了解释性注释。

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### 每一步的重要性

* **步骤 1** 创建一个绑定到 *Databar Expanded Stacked* 符号的 `BarcodeGenerator`，这是实现 GS1 兼容零售扫描的前提。
* **步骤 2** 通过先调整列数间接演示 **如何设置行数**——这表明列和行的设置是独立的。
* **步骤 3** 保存图像，便于您验证列数对视觉效果的影响。
* **步骤 4** 重新初始化生成器，以防行配置继承了之前设置的列值，这是常见的混淆来源。
* **步骤 5** 明确展示 **如何设置行数**，这也是本次关键字的主要关注点。
* **步骤 6** 保存第二张图像，让您可以并排比较基于列和基于行的密度差异。

运行程序后，会在输出目录生成两个 PNG 文件：

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

使用图像查看器打开任意文件，确认条形码渲染正确。

## 常见变体和边缘情况

| 场景 | 需要更改的内容 | 原因 |
|----------|----------------|--------|
| **不同的数据负载** | 将 `BarcodeGenerator` 的第二个参数替换为您自己的字符串（例如 `"123456789012"`）。 | 条形码会编码提供的文本；请确保符合 Databar 的 GS1 规则。 |
| **其他图像格式** | 使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 | 选择与下游处理流水线匹配的格式。 |
| **更高分辨率** | 调用 `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);`，其中最后一个参数为 DPI。 | 在打印大标签时提升可读性。 |
| **许可证处理** | 在任何生成器创建之前添加 `License` 代码片段。 | 去除评估水印并解锁全部功能。 |

## 可靠生成条形码的技巧

* **验证输入字符串** – Databar Expanded Stacked 只接受最多 70 位的数字数据。提供非数字字符可能导致异常。
* **检查文件路径** – 使用 `Path.Combine(Environment.CurrentDirectory, "output.png")` 可避免硬编码目录在目标机器上不存在的情况。
* **释放对象** – `BarcodeGenerator` 实现了 `IDisposable`。如果在循环中生成大量条形码，请将其放在 `using` 块中，以及时释放本机资源。

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## 结论

您现在已经掌握了 **如何创建 Databar Expanded Stacked 条形码**，以及 **如何设置行数**（以及列数），使用 **barcode generator C#** API，并能够 **生成 PNG 格式的条形码图像**。通过遵循上述完整示例，您可以将 Databar 条形码集成到库存系统、销售点应用或任何需要高密度 GS1 条形码的 .NET 解决方案中。

**后续步骤**

* 试验其他符号，如 `EncodeTypes.DatabarExpanded` 或 `EncodeTypes.QR`。  
* 探索 `BarcodeReader` 类，以验证生成的图像是否可扫描。  
* 将条形码生成与 PDF 创建相结合（例如使用 `Aspose.PDF`），生成可打印标签。

祝编码愉快！


## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方式。每个资源都包含完整的可运行代码示例和逐步解释。

- [如何为 Databar Expanded Stacked 条形码设置列数 – 完整 C# 指南](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [如何在 C# 中使用 DataBar Stacked 更改条形码大小](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked：在 C# 中生成条形码图像](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}