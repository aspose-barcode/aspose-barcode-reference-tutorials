---
category: general
date: 2026-09-23
description: C# 条形码生成器教程展示了如何使用 Aspose.BarCode 库生成具有自定义宽高比的条形码图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: zh
lastmod: 2026-09-23
og_description: C# 条形码生成器指南将手把手教您如何使用 Aspose.BarCode 生成条形码图像、调整宽高比并导出 PNG 文件。
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: 使用 C# 条码生成器创建高质量条码
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: 如何使用 C# 条码生成器生成 DataBar 条码
url: /zh/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条形码生成器生成 DataBar 条码

如果您需要一个 **c# barcode generator** 能生成 DataBar stacked Omni‑Directional 符号，本指南提供完整、可直接运行的解决方案。您将看到如何生成条形码图像、控制 X‑dimension，以及在不离开 IDE 的情况下更改宽高比。

生成条形码是库存系统、运输标签和销售点应用的常见需求。完成本教程后，您可以创建任意宽高比的 PNG 文件，并了解如何将代码适配到其他条码类型。

## 前置条件

在开始之前，请确保您已具备：

* 已安装 .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或您喜欢的任何 C# 编辑器）  
* 对 **Aspose.BarCode** 的 NuGet 引用 —— 为 `BarcodeGenerator` 类提供支持的库  

您无需额外的图形库；Aspose.BarCode 在内部处理图像编码。

## 第 1 步：安装 Aspose.BarCode NuGet 包

在项目文件夹的终端中运行：

```bash
dotnet add package Aspose.BarCode
```

该命令会将最新的稳定版库添加到项目文件中，使 `BarcodeGenerator` 类可供使用。

## 第 2 步：定义输出文件夹

选择一个用于保存生成的 PNG 文件的文件夹。使用绝对路径或相对路径均可，但相对路径更有利于项目的可移植性。

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

以编程方式创建目录可以避免在文件夹不存在时出现运行时错误。

## 第 3 步：使用示例数据实例化 C# 条形码生成器

`BarcodeGenerator` 构造函数需要两个参数：条码类型和数据字符串。对于 DataBar stacked Omni‑Directional 符号，使用 `EncodeTypes.DatabarStackedOmniDirectional`。

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

数据字符串遵循 GS1 应用标识符格式。`EncodeTypes` 枚举包含超过 150 种条码标准；通过更改枚举值即可切换到其他类型。

## 第 4 步：设置条码的 X‑dimension（像素大小）

X‑dimension 控制最窄条的宽度。像素值为 2 时，可生成清晰的高分辨率图像，适用于大多数屏幕。

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

调整 X‑dimension 是可选的，但它可以让您细致控制条码的视觉密度。

## 第 5 步：生成宽高比为 15 的条码并保存为 PNG

`AspectRatio` 属性属于 `DataBar` 子对象。修改该值会在保持编码数据不变的前提下，垂直拉伸或压缩条码。

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save` 方法会将条码写入指定的文件路径。`BarCodeImageFormat.Png` 枚举确保无损压缩。

![c# 条形码生成器输出示例](generated_barcode_example.png)

*图片：宽高比为 15 的条码生成示例。*

## 第 6 步：将宽高比改为 30 并生成第二张图像

复用同一个 `BarcodeGenerator` 实例可避免重新分配对象。只需更新 `AspectRatio` 并再次调用 `Save`。

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

现在您拥有两张仅在垂直比例上不同的 PNG 文件。当需要相同数据用于不同标签尺寸时，这种技巧非常有用。

## 常见变体和边缘情况

### 切换到其他条码类型

如果需要 QR 码、Code 128 或 PDF417，只需在构造函数中替换枚举值：

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

其他配置步骤（X‑dimension、保存）保持不变。

### 处理不支持的字符

`BarcodeGenerator` 会根据所选符号体系验证输入字符串。提供非法字符会抛出 `ArgumentException`。请使用 try‑catch 块捕获异常并提供友好的错误提示：

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### 导出为其他图像格式

Aspose.BarCode 支持 BMP、JPEG、TIFF 和 SVG。相应地更改 `Save` 的第二个参数：

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### 打印用的高分辨率输出

在高 DPI 打印机上打印时，可增加 X‑dimension 并可选地设置 `Resolution` 属性：

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

这些设置会生成更大的文件，但在实体介质上保持边缘清晰。

## 预期输出

运行完整程序后，会在 `GeneratedBarcodes/` 目录下生成以下文件：

* `DatabarAspectRatio15.png` – 标准高度的 DataBar 条码  
* `DatabarAspectRatio30.png` – 垂直拉伸的版本  

两张图像包含相同的 GS1 编码数据，您可以使用任意条码扫描应用进行验证。

## 完整源代码

将下面的代码复制到新建的控制台项目（`dotnet new console`）中并运行。程序会在控制台输出状态信息，并将 PNG 文件写入磁盘。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

运行程序后，控制台输出类似于：

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## 结论

您现在拥有一个 **c# barcode generator**，能够创建 DataBar stacked Omni‑Directional 符号、调整 X‑dimension，并以自定义宽高比导出 PNG 文件。同样的模式适用于 Aspose.BarCode 支持的任何其他条码符号体系，便于在库存、运输或销售点解决方案中集成条码生成。

如果想进一步探索，可尝试：

* 生成 QR 码或 PDF417 符号（`how to generate barcode` 用于移动应用）  
* 导出为 SVG 以实现可伸缩的网页图形  
* 使用 Aspose.PDF 将生成的图像直接嵌入 PDF 发票  

尝试不同的 `AspectRatio` 值、X‑dimension 大小和输出格式，以匹配精确的需求。

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，每篇资源都提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 生成自定义宽高比的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 调整 Codablock F 条码的宽高比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 生成并调整一维 DataBar 条码的高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}