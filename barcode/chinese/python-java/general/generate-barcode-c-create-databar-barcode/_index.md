---
category: general
date: 2026-07-21
description: 使用 Aspose.BarCode 快速生成 C# 条形码。学习创建 DataBar 条形码、定制条形码尺寸，并在几步内导出条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: zh
lastmod: 2026-07-21
og_description: 使用 Aspose.BarCode 在 C# 中生成条形码。创建 DataBar 条码，自定义其尺寸，并即时导出图像。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: 生成条形码 C# – 使用自定义尺寸构建 DataBar 条码
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: 生成条码 C# – 创建 DataBar 条码
url: /zh/python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成条形码 C# – 创建 DataBar 条形码

想要 **生成条形码 C#** 而不必在海量文档中翻找吗？你来对地方了。在本指南中，我们将一步步演示如何创建 **DataBar 条形码**、调整其尺寸，最后 **导出条形码图像**——只需几行 C# 代码。

想象一下，你需要一个可以贴在小货架标签上的紧凑产品标签。DataBar Expanded Stacked 符号正好满足需求，使用 Aspose.BarCode 你可以精确控制使用多少列或行。准备好了吗？让我们开始吧。

## 你将实现的目标

- **从头创建 DataBar 条形码**（“expanded stacked” 变体）。  
- **通过直接设置列或行** 来自定义条形码尺寸。  
- **在不重新生成生成器的情况下** 动态更改条形码尺寸。  
- **将条形码图像导出** 为 PNG（或 Aspose 支持的任何格式）。  

无需外部服务，无需繁琐配置——只要干净、可运行的 C# 代码。

## 前置条件

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）。  
- 有效的 Aspose.BarCode for .NET 许可证（或使用试用模式）。  
- 任意 IDE——Visual Studio、Rider 或 VS Code 都可以。  

如果还未安装 NuGet 包，请运行：

```bash
dotnet add package Aspose.BarCode
```

就这么简单——没有其他依赖。

## 第一步：设置条形码生成器（如何 **生成条形码 C#**）

首先，需要创建一个指向 **DataBar Expanded Stacked** 符号的 `BarcodeGenerator` 实例。该对象是后续生成图像的引擎。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*为什么重要*：`EncodeTypes.DatabarExpandedStacked` 枚举告诉 Aspose 我们需要堆叠版本，适合狭窄空间。我们传入的文本会成为编码值；你可以替换为任何应用需要的数字字符串。

## 第二步：**自定义条形码尺寸** – 设置列数

DataBar 条形码允许通过指定 **列** *或* **行** 来影响视觉密度。我们先从列数开始。行数会自动计算，以保持条形码有效。

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*专业提示*：列数影响条形码的宽度。列越多 → 条形码越宽，在低分辨率打印机上可以提升扫描可靠性。

## 第三步：使用列设置 **导出条形码图像**

现在将图像写入磁盘。你可以选择 PNG、JPEG、BMP，甚至 SVG。这里使用 PNG 以获得清晰、无损的输出。

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **预期结果** – 打开 `DatabarCols4.png`，你会看到一个整齐堆叠、包含四列的 DataBar。它看起来像一堆密集的垂直条，非常适合小标签。

## 第四步：**更改条形码尺寸** – 设置行数

有时你需要更高的条形码而不是更宽的。切换到行控制，Aspose 会自动重新计算列数。

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*为什么切换？* 行数影响条形码的高度。行越多 → 符号越高，当你有垂直空间但宽度受限时非常有用。

## 第五步：使用行设置 **导出条形码图像**

保存第二种变体。文件名已反映出此更改；你也可以保留两个图像进行对比。

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **结果** – `DatabarRows3.png` 现在显示相同数据的更高版本，仍然可以完美扫描。

## 完整工作示例

把所有步骤整合在一起，下面是一个可以直接复制粘贴并立即运行的控制台应用程序：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

运行程序后，打开这两个 PNG 文件。你已经 **生成条形码 C#**、**自定义条形码尺寸**、**更改条形码尺寸**，并 **导出条形码图像**——全部在一分钟内完成。

## 常见问题与边缘情况

- **如果我需要其他图像格式怎么办？**  
  将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp`、`Gif` 或 `Svg`。API 会自动完成转换。

- **我可以同时更改行和列吗？**  
  技术上可以同时设置，但 Aspose 会优先使用你最后修改的属性。为了得到有效的 DataBar，建议只设置 *一个* 维度，让库自动计算另一个。

- **如何应用前景色/背景色？**  
  使用 `barcodeGen.Parameters.Barcode.ForegroundColor` 和 `BackgroundColor`。示例：  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **编码数据有尺寸限制吗？**  
  DataBar Expanded Stacked 支持最多 74 位数字字符（或 30 位字母数字字符）。超出范围会抛出异常。

## 后续步骤

既然已经掌握了 **创建 databar 条形码** 的基础，接下来可以考虑：

- 在条形码下方添加 **文本注释**（`barcodeGen.Parameters.CaptionAbove.Text`）。  
- 使用 Aspose.PDF 将 PNG 直接嵌入 PDF。  
- 通过遍历 CSV 中的产品 ID 批量生成条形码。

这些主题都基于同一个 `BarcodeGenerator` 对象，无需重新开始。

---

**结论**：现在你已经了解如何 **生成条形码 C#**、**自定义条形码尺寸**、**更改条形码尺寸**，以及 **导出条形码图像**，全部使用 Aspose.BarCode。尝试不同的列/行值、切换图像格式，并将代码集成到你的库存或 POS 系统中。祝编码愉快！


## 接下来你应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助你进一步掌握 API 功能并在项目中探索替代实现方式。每篇资源都提供完整的可运行代码示例和逐步解释。

- [生成条形码图像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [使用 Aspose.BarCode for .NET 生成自定义宽高比的 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [生成 DataMatrix 条形码 – Aspose.BarCode 专业指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}