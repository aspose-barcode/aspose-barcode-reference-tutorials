---
category: general
date: 2026-08-15
description: Databar 扩展堆叠条形码在 C# 中的生成。了解如何生成条形码图像，为 DataBar 布局设置列和行。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: zh
lastmod: 2026-08-15
og_description: Databar 在 C# 中扩展了堆叠条形码生成。请按照本分步指南高效生成条形码图像、设置列和设置行。
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar 扩展堆叠 – 在 C# 中生成条码图像
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Databar 扩展堆叠：在 C# 中生成条码图像
url: /zh/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked：在 C# 中生成条码图像

如果您需要在 C# 中生成 **databar expanded stacked** 条码图像，本指南将向您展示如何使用自定义列和行布局 **生成条码** 图像。您将看到如何设置列、如何设置行，以及如何在不离开 IDE 的情况下保存生成的图像。

本教程包括：

* 为 **databar expanded stacked** 符号创建条码生成器。  
* 配置 4 列布局和 3 行布局。  
* 将每种配置保存为 PNG 文件。  
* 处理诸如列数无效等边缘情况的技巧。

无需外部文档；完整、可运行的示例已包含在内。

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="使用 C# 生成的 databar expanded stacked 条码" }

## Databar expanded stacked 条码生成步骤

### 1. 安装 Aspose.BarCode 库

代码使用 **Aspose.BarCode for .NET** 库，该库提供 `BarcodeGenerator` 类。使用以下命令通过 NuGet 安装包：

```bash
dotnet add package Aspose.BarCode
```

安装完包后，在文件顶部添加所需的命名空间：

```csharp
using Aspose.BarCode.Generation;
```

### 2. 为 **databar expanded stacked** 创建条码生成器

生成器是所有条码操作的入口点。您必须指定符号 (`EncodeTypes.DatabarExpandedStacked`) 和要编码的文本。

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*为什么重要：* `EncodeTypes` 枚举告诉库生成哪种条码格式。使用 **databar expanded stacked** 可确保生成的图像符合 GS1 DataBar 堆叠布局规范。

### 3. 如何设置 DataBar 的列

`Columns` 属性控制堆叠条码中出现多少个垂直模块。有效值为 2、3 或 4。设置列数会影响条码的宽度以及可存储的数据量。

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**提示：** 如果尝试分配超出允许范围的值，库会抛出 `ArgumentException`。在向用户公开列选择时，请始终验证输入。

### 4. 保存 4 列条码图像

保存图像会生成一个文件，您可以将其嵌入报告、发票或移动应用中。`Save` 方法接受文件路径和图像格式。

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

文件写入后，您可以使用任意图像查看器打开，以确认 **databar expanded stacked** 图案正确显示。

### 5. 如何设置 DataBar 的行

行数为堆叠布局添加第二维度，使得在不增加条码宽度的情况下编码更多数据。`Rows` 属性默认值为 1；对于扩展堆叠变体，您可以将其提升至最多 3 行。

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**为什么行数重要：** 增加行数可以在保持数据容量的同时降低整体宽度，这对于窄标签或移动屏幕空间尤为有用。

### 6. 保存 3 行条码图像

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

现在您拥有两个 PNG 文件——一个是 4 列布局，另一个是 3 行布局——均使用 **databar expanded stacked** 符号。

### 7. 完整的 C# 示例以生成条码图像

将所有步骤组合在一起即可得到一个可直接复制到控制台应用程序的自包含程序：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**预期输出**

运行程序后会打印：

```
4‑column barcode saved.
3‑row barcode saved.
```

并在 `YOUR_DIRECTORY` 中创建两个 PNG 文件。打开这些文件即可验证每张图像都显示了有效的 **databar expanded stacked** 条码。

## 常见陷阱与实用技巧

* **目录是否存在** – `Save` 不会自动创建缺失的文件夹。请确保 `YOUR_DIRECTORY` 已存在，或在保存前使用 `Directory.CreateDirectory` 创建。
* **列限制** – 除 2、3、4 之外的值会触发异常。使用简单的范围检查来防止用户输入错误：

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **行限制** – 扩展堆叠变体最多支持 3 行。将 `Rows` 设置为 0 或大于 3 的值同样会抛出异常。
* **图像格式** – `BarCodeImageFormat.Png` 提供无损质量，适合打印。仅在文件大小是主要考虑因素时才使用 `Jpeg`。

## 后续步骤

了解了如何使用自定义列和行配置 **生成条码** 图像后，您可以：

* 将生成器集成到 Web API 中，以按需提供条码图像。  
* 将条码与 PDF 生成库结合，嵌入发票中。  
* 使用相同的 `Parameters.Barcode.DataBar` 对象尝试其他 DataBar 变体（`DatabarExpanded`、`DatabarLimited`）。

如需更深入的自定义——例如更改条纹颜色、添加可读文本或叠加 QR 码——请参考 Aspose.BarCode 文档中 `BarcodeGenerator` 属性的说明。

---

通过本指南，您已经掌握了 **databar expanded stacked** 工作流，学会了 **如何设置列**、**如何设置行**，并生成了两张可直接用于生产的条码图像。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在自己的项目中进一步掌握 API 功能并探索替代实现方式，每个资源都包含完整的可运行代码示例和逐步解释。

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}