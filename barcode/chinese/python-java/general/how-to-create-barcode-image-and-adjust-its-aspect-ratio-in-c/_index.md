---
category: general
date: 2026-10-08
description: 学习如何在 C# 中创建条形码图像，并了解如何调整 DataBar 堆叠全向条码的宽高比。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust aspect ratio
- Aspose.BarCode C#
- DataBar stacked omni‑directional
- barcode X‑dimension
language: zh
lastmod: 2026-10-08
og_description: 使用 C# 创建条形码图像，并学习如何为 DataBar 堆叠全向条码调整纵横比，附完整代码示例。
og_image_alt: Result of create barcode image with aspect ratio 15 using Aspose.BarCode
og_title: 在 C# 中创建条形码图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  headline: How to create barcode image and adjust its aspect ratio in C#
  type: TechArticle
- description: Learn how to create barcode image in C# and discover how to adjust
    aspect ratio for DataBar stacked omni‑directional barcodes.
  name: How to create barcode image and adjust its aspect ratio in C#
  steps:
  - name: Expected output
    text: 'After running the program you will find two PNG files in the execution
      directory:'
  - name: What if I need a different X‑dimension?
    text: You can change `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` to
      any integer greater than zero. For very high‑resolution output (e.g., 300 dpi),
      a value of 3‑4 pixels often yields clearer results.
  - name: How do I choose the right aspect ratio?
    text: 'The optimal ratio depends on the scanning environment: * **Low‑profile
      labels** – use a smaller ratio (e.g., 10‑15) to keep the barcode compact. *
      **Large shipping containers** – a higher ratio (e.g., 25‑35) improves readability
      from a distance. * **Regulatory requirements** – some standards mandate'
  - name: Can I generate other barcode formats with the same code?
    text: Yes. Replace `EncodeTypes.DatabarStackedOmniDirectional` with any other
      `EncodeTypes` value (e.g., `EncodeTypes.Code128`). The rest of the code—X‑dimension,
      aspect ratio (if applicable), and saving—remains the same.
  - name: What if I need to create the image in a different format?
    text: '`BarCodeImageFormat` supports PNG, JPEG, BMP, GIF, and TIFF. Just change
      the second argument of `Save`, for example:'
  - name: Next steps
    text: '* Explore other symbologies such as **Code128** or **QR Code** by swapping
      the `EncodeTypes` value. * Combine the barcode generation with PDF creation
      (e.g., using Aspose.PDF) to embed barcodes directly into invoices. * Experiment
      with dynamic aspect‑ratio selection based on label size—this extends '
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中创建条形码图像并调整其宽高比
url: /zh/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建条形码图像并调整其宽高比

如果您需要以编程方式**创建条形码图像**，本指南提供了一个完整、可直接运行的解决方案。您将看到如何**调整宽高比**以适用于 DataBar 堆叠全方向条码，这在零售和物流应用中经常出现的需求。

在本教程中，您将学习如何：
* 为 DataBar 堆叠全方向符号初始化 Aspose.BarCode `BarcodeGenerator`。  
* 以像素为单位设置 X 维度（模块宽度）以控制条的粗细。  
* 应用两种不同的宽高比并将每个结果保存为 PNG 文件。  
* 验证输出并了解宽高比为何重要。

无需任何外部工具——只需 Aspose.BarCode for .NET 库和 .NET 6（或更高）开发环境。

## 使用 Aspose.BarCode 创建条形码图像

第一步是使用所需的符号和数据字符串实例化生成器。`EncodeTypes.DatabarStackedOmniDirectional` 枚举告诉 Aspose.BarCode 生成 DataBar 堆叠全方向条码，这在 GS1‑128 应用中被广泛使用。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a BarcodeGenerator for DataBar stacked omni‑directional.
        // The data string "(01)12345678901231" follows the GS1 Application Identifier format.
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**为什么这很重要：** `BarcodeGenerator` 对象是所有条形码创建任务的入口。提前指定符号和原始数据，可确保生成的图像符合 GS1 标准。

## 设置 X 维度（模块宽度）

X 维度定义了最窄条（模块）的宽度。更大的 X 维度会产生更粗的条码，这对低分辨率打印机很有帮助。

```csharp
        // 2️⃣ Define the X‑dimension in pixels.
        // A value of 2 pixels provides a good balance between readability and file size.
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么这很重要：** 调整 X 维度是视觉调优过程的一部分。它不影响编码数据，但会影响不同设备的扫描可靠性。

## 如何调整宽高比 – 第一个版本（15）

宽高比控制 DataBar 条码的高宽关系。`DataBar.AspectRatio` 属性接受整数值；数值越大，条码越高。

```csharp
        // 3️⃣ Set the aspect ratio to 15 and save the first image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**为什么这很重要：** 宽高比 15 是零售扫描器的常见默认值。生成的 PNG（`DatabarAspectRatio15.png`）将呈现更高的外观，有助于手持设备的扫描成功率。

## 如何调整宽高比 – 第二个版本（30）

对于特定标签格式，您可能需要更高的条码。只需在再次调用 `Save` 之前为宽高比赋予新的整数值即可。

```csharp
        // 4️⃣ Change the aspect ratio to 30 and save a second image.
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**为什么这很重要：** 通过演示**如何调整宽高比**，您可以在不重新创建生成器的情况下，从同一数据源生成多个条码图像。这降低了内存使用并加快了批处理速度。

### 预期输出

运行程序后，您将在执行目录中找到两个 PNG 文件：

| 文件名                     | 宽高比 | 视觉描述 |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | 标准高度，适用于大多数销售点扫描器。 |
| `DatabarAspectRatio30.png`    | 30           | 更高的条形，适用于大标签或低分辨率打印机。 |

两个图像都包含相同的编码 GTIN `(01)12345678901231`，但视觉比例会根据您设置的宽高比而不同。

## 常见问题与边缘情况处理

### 如果需要不同的 X 维度怎么办？

您可以将 `barcodeGenerator.Parameters.Barcode.XDimension.Pixels` 更改为任何大于零的整数。对于超高分辨率输出（例如 300 dpi），3‑4 像素的值通常能产生更清晰的效果。

### 如何选择合适的宽高比？

最佳比例取决于扫描环境：
* **低剖面标签** – 使用较小的比例（例如 10‑15），以保持条码紧凑。  
* **大型运输容器** – 使用较高的比例（例如 25‑35），可提升远距离可读性。  
* **法规要求** – 某些标准规定了最小高度；请查阅 GS1 规范获取具体数值。

### 能否使用相同的代码生成其他条形码格式？

可以。将 `EncodeTypes.DatabarStackedOmniDirectional` 替换为任意其他 `EncodeTypes` 值（例如 `EncodeTypes.Code128`）。其余代码——X 维度、宽高比（如适用）以及保存——保持不变。

### 如果需要以不同格式创建图像怎么办？

`BarCodeImageFormat` 支持 PNG、JPEG、BMP、GIF 和 TIFF。只需更改 `Save` 的第二个参数，例如：

```csharp
barcodeGenerator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

## 专业提示：在批处理时复用生成器

当您必须使用相同的视觉设置创建数十个条码时，只需实例化一次生成器，仅更新 `CodeText` 属性，并重复调用 `Save`。这可避免反复分配内部缓冲区的开销。

```csharp
// Example of batch creation
string[] gtins = { "(01)12345678901231", "(01)98765432109876", "(01)55555555555555" };
foreach (var gtin in gtins)
{
    barcodeGenerator.CodeText = gtin;
    barcodeGenerator.Save($"Barcode_{gtin.Substring(4, 6)}.png", BarCodeImageFormat.Png);
}
```

## 结论

您现在已经了解如何使用 Aspose.BarCode 在 C# 中**创建条形码图像**，以及如何精准**调整 DataBar 堆叠全方向符号的宽高比**。通过控制 X 维度和宽高比，您可以生成满足任何扫描或布局需求的条码，同时保持实现简洁且易于维护。

### 下一步

* 通过切换 `EncodeTypes` 值，探索其他符号，如 **Code128** 或 **QR Code**。  
* 将条码生成与 PDF 创建相结合（例如使用 Aspose.PDF），直接将条码嵌入发票中。  
* 基于标签尺寸尝试动态宽高比选择——这将**如何调整宽高比**的模式扩展为完整的标签设计引擎。

欢迎自行改编示例、分享成果，或在评论中提出后续问题。祝编码愉快！

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方案。每个资源都包含完整的可运行代码示例和逐步解释。

- [如何在 C# 中使用 Aspose.Barcode 创建堆叠式 DataBar 条码](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [如何在 C# 中使用 Aspose.Barcode 创建条形码图像](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [如何使用 Aspose.BarCode for .NET 调整条码大小 – Codablock F 宽高比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}