---
category: general
date: 2026-07-27
description: 使用 Aspose.BarCode 创建全方向条形码图像。了解如何使用 Aspose 生成条形码、调整宽高比并保存为 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: zh
lastmod: 2026-07-27
og_description: 使用 Aspose 创建全向条形码图像。按照本指南使用 Aspose 生成条形码，调整宽高比，并导出 PNG。
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: 使用 Aspose 创建全向条码图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: 使用 Aspose 创建全向条形码图像 – 完整指南
url: /zh/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose 创建全向条形码图像 – 完整指南

是否曾经需要**创建全向条形码图像**但不确定该选哪个库？你并非唯一。在许多物流和零售项目中，DataBar Stacked Omnidirectional 格式是实现紧凑、高密度编码的关键。

好消息是？使用 **Aspose.BarCode**，你可以用几行代码生成该条形码，调整其宽高比，并直接将 PNG 保存到磁盘。下面你将看到如何**使用 Aspose 生成条形码**，每个设置为何重要，以及在更改宽高比时需要注意的事项。

---

## 本教程涵盖内容

我们将完整演示整个生命周期：

1. 设置输出文件夹。
2. 实例化 DataBar Stacked Omnidirectional 生成器。
3. 配置像素尺寸和宽高比。
4. 将条形码保存为 PNG 文件。
5. 为其他格式和边缘情况扩展示例。

完成后，你将拥有一个可直接运行的 C# 控制台应用程序，能够生成两张不同的条形码图像。无需外部工具，仅靠纯 Aspose 代码。

**先决条件**

- .NET 6.0 SDK 或更高（代码同样适用于 .NET Framework 4.7.2）。
- Aspose.BarCode for .NET NuGet 包（`Install-Package Aspose.BarCode`）。
- 磁盘上一个可写入图像的文件夹。

如果你已经具备上述条件，下面开始吧。

---

## 第一步：准备输出文件夹

首先——告诉程序 PNG 文件要保存到哪里。硬编码路径适用于演示，但在生产环境中通常会从配置读取。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*为什么重要：* `Directory.CreateDirectory` 是幂等的；如果文件夹已存在不会抛异常，从而省去 try‑catch 代码块。

---

## 第二步：创建 DataBar Stacked Omnidirectional 生成器

现在我们使用特定的编码类型和示例数据实例化生成器。字符串 `"(01)12345678901231"` 符合 GS1 应用标识符语法，表示 14 位 GTIN。

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*说明：* `EncodeTypes.DatabarStackedOmniDirectional` 告诉 Aspose 使用全向变体，该变体可从任意方向读取——非常适合可能被旋转的小标签。

---

## 第三步：设置通用条形码参数

在渲染之前，我们先定义最小元素尺寸（X‑Dimension）。**2 像素**的值能够在保持图像清晰的同时避免文件体积膨胀。

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*小贴士：* 如果需要更高的打印分辨率，可将其提升至 3 或 4。只需记住，较大的 X‑Dimension 会等比例增加宽度和高度。

---

## 第四步：使用宽高比 15 生成并保存

DataBar 系列允许你调整 **宽高比**，该比例控制高度与宽度的关系。宽高比 **15** 是全向条形码的常用默认值。

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*你将看到：* 一个相对较高的条形码，仍能轻松放入 2 × 1 cm 标签。PNG 格式保持无损质量，适合后续处理或打印。

---

## 第五步：将宽高比改为 30 再次保存

想要更矮的条形码？只需修改 `AspectRatio` 属性并再次调用 `Save`。无需重新创建生成器。

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*为什么复用同一个生成器？* Aspose 对象轻量，修改属性后重新保存比构造新实例更快，并且可以保证相同的编码设置（如 X‑Dimension）保持一致。

---

## 完整可运行示例

将所有代码整合在一起，下面是可以直接复制粘贴到新控制台项目中的完整自包含程序。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**预期输出**

运行程序后会在 `Barcodes` 子文件夹中生成：

- `DatabarAspectRatio15.png` – 较高的经典外观。
- `DatabarAspectRatio30.png` – 更平的宽标签适配。

两张图像编码相同的 GTIN 数据；唯一的区别是视觉比例。

---

## 扩展示例（边缘情况与变体）

### 1. 不同的图像格式

Aspose 除 PNG 外还支持 BMP、JPEG、TIFF 和 SVG。只需替换枚举值：

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG 为矢量格式，可在不失真情况下任意缩放——非常适合响应式 Web 应用。

### 2. 自定义颜色

如果需要在深色背景上显示白色条形码，可设置 `ForeColor` 与 `BackColor`：

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. 处理无效的宽高比

Aspose 会验证范围（通常为 5‑50）。若传入超出范围的值，会抛出 `ArgumentException`。将保存调用包装在 try‑catch 中，以提供友好提示：

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. 批量生成

当拥有 GTIN 列表时，可遍历列表，更新 `CodeText`，并使用唯一文件名保存每个文件。生成器对象可以复用，从而保持低内存占用。

---

## 常见陷阱与专业技巧

- **务必在保存前设置 `XDimension`**；默认值 (0.33 mm) 在低分辨率显示器上会导致模糊。
- **宽高比指的是高度与宽度的比值**，而不是相反。数值越大，条形码在垂直方向上越*短*。
- **文件路径**：使用 `Path.Combine` 可避免平台特定的分隔符问题——尤其是代码运行在 Linux 容器时。
- **授权**：Aspose.BarCode 为商业产品。试用模式下图像会出现水印。请尽早注册授权，以免在生产环境中出现意外。

---

## 结论

现在，你已经掌握了使用 Aspose **创建全向条形码图像**、调整宽高比并导出 PNG 文件的全部技巧，代码行数不足 30 行。本教程一步步演示了每个设置的意义，并介绍了不同格式、颜色以及批量处理等扩展方式。

准备好迎接下一个挑战了吗？尝试生成 QR 码、将条形码嵌入 PDF，或在 ASP.NET Core API 中集成输出。相同的**使用 Aspose 生成条形码**原理适用于所有条形码类型，今天学到的内容可以直接复用。

有问题或想分享自己的改进？在下方留言——祝编码愉快！


## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在项目中进一步掌握 API 功能并探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}