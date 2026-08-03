---
category: general
date: 2026-08-03
description: 在 C# 中创建条形码 PNG，并学习如何更改 DataBar 图像的宽高比。请参阅包含代码和技巧的完整示例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: zh
lastmod: 2026-08-03
og_description: 在 C# 中创建条形码 PNG，并了解如何更改 DataBar 条码的宽高比。本指南提供可直接运行的代码和实用技巧。
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: 在 C# 中创建条形码 PNG – 完整示例，带宽高比控制
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: 使用 C# 创建条形码 PNG – 步骤指南
url: /zh/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建条形码 PNG – 步骤指南

如果你需要在 C# 中**创建条形码 PNG**，本教程将一步步演示。你将生成一个堆叠全向 DataBar 条形码，将其保存为 PNG 文件，并学习**如何更改宽高比**以适应不同的扫描环境。

本指南涵盖了所有必需内容：所需的包、完整可运行的程序以及每个设置为何重要的解释。完成后，你将得到两个 PNG 文件——一个宽高比为 15，另一个为 30——可用于测试或生产环境。

## 前置条件

在开始之前，请确保你已经：

- 安装了 .NET 6.0 SDK 或更高版本
- 安装了 Visual Studio 2022（或任何 C# IDE）
- 在项目中引用了 **Aspose.BarCode**（提供 `BarcodeGenerator` 的库）的 NuGet 包
- 对将保存 PNG 文件的目录拥有写入权限

你可以使用以下命令添加 Aspose.BarCode 包：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：创建项目并导入命名空间

创建一个新的控制台应用程序，并导入生成条形码和文件 I/O 所需的命名空间。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**原因说明：** 导入 `Aspose.BarCode.Generation` 可让你使用 `BarcodeGenerator`。将代码放在 `Main` 方法内部，使示例自包含且易于运行。

## 第二步：为堆叠全向 DataBar 创建条形码生成器

实例化 `BarcodeGenerator`，使用 `EncodeTypes.DatabarStackedOmniDirectional` 类型并提供示例 GS1‑128 数据字符串。

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**原因说明：** 选用的编码类型会生成高密度 DataBar，能够被大多数现代扫描仪读取。数据字符串遵循 GS1 应用标识符 (01) 格式，常用于产品标识。

## 第三步：以像素为单位定义 X‑维度（模块宽度）

设置模块宽度，以控制条形码的整体尺寸，同时不影响可读性。

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**原因说明：** X‑维度设为 2 像素，可让条形码既不会对扫描仪太小，也不会对标签空间太大。

## 第四步：使用宽高比 15 保存第一张 PNG

调整 DataBar 的宽高比，然后将图像保存为 PNG 文件。

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**原因说明：** 宽高比决定堆叠 DataBar 的高宽关系。宽高比 15 是常见的默认值，能够在可读性和标签高度之间取得平衡。

## 第五步：将宽高比改为 30 并保存第二张 PNG

修改同一生成器实例以使用更大的宽高比，然后保存第二张图像。

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**原因说明：** 提高宽高比会在垂直方向上拉伸条形码，这可以在低分辨率设备或标签印在窄介质时提升扫描可靠性。

## 预期输出

运行程序后会生成两张 PNG 文件：

| 文件                               | 宽高比 | 大致尺寸（像素） |
|------------------------------------|--------|-----------------|
| `DatabarAspectRatio15.png`         | 15     | 200 × 300（宽 × 高） |
| `DatabarAspectRatio30.png`         | 30     | 200 × 600（宽 × 高） |

两张图像均包含清晰、可扫描的 DataBar 条形码，编码的 GS1 标识符为 `(01)12345678901231`。

## 常见问题与边缘情况

### 如何更改其他视觉属性？

你可以通过 `generator.Parameters.Barcode` 对象调整前景色、背景色或添加可读文本。例如：

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### 如果需要其他图像格式怎么办？

将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Gif` 即可。PNG 仍是无损条形码图像的最佳选择。

### 宽高比会影响扫描速度吗？

更高的宽高比会增加条形码的高度，这可以在对短堆叠符号处理不佳的设备上提升扫描可靠性。但极高的条形码可能无法适配小标签，需要在目标硬件上进行测试。

### 能否在循环中生成多个条形码？

可以。为每个数据字符串创建新的 `BarcodeGenerator` 实例，或在更新 `CodeText` 和 `DataBar.AspectRatio` 时复用同一实例。这种方式可减少对象分配开销。

## 专业技巧

- **复用生成器**：仅更改 `CodeText` 或 `AspectRatio` 而不重新实例化对象，可加速批量处理。
- **验证输出**：使用手持扫描仪或移动应用确认生成的 PNG 能正确读取后，再投入生产使用。
- **文件命名**：在文件名中加入宽高比（如示例所示），便于在测试期间跟踪不同变体。

## 结论

现在你已经掌握了在 C# 中**创建条形码 PNG**文件的完整流程，并且能够**精确更改堆叠全向 DataBar 符号的宽高比**。完整示例展示了初始化、X‑维度设置、宽高比调节以及图像保存——全部在一个可运行的程序中实现。

接下来，你可以探索其他条形码类型、尝试颜色自定义，或将生成器集成到更大的报表或库存系统中。祝编码愉快！

## 接下来你应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助你在已有技巧的基础上进一步深入。每篇资源都提供完整的可运行代码示例和逐步解释，帮助你掌握更多 API 功能并在项目中尝试不同实现方式。

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}