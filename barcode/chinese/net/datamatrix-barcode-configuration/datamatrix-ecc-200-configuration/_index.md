---
date: 2026-08-02
description: 了解如何创建 DataMatrix 条码、生成 DataMatrix，并在 Aspose.BarCode for .NET 项目中探索高密度条码生成。
keywords:
- create datamatrix barcode
- high density barcode
- generate datamatrix barcode
- barcode generation asp.net
- temporary aspose license
lastmod: 2026-08-02
linktitle: DataMatrix ECC 200 配置
og_description: 使用 Aspose.BarCode for .NET 创建 DataMatrix 条码。本教程展示高密度条码生成、临时 Aspose
  许可证设置以及一步一步的 C# 代码。
og_image_alt: Guide showing C# code to create a DataMatrix barcode using Aspose.BarCode
og_title: 创建 DataMatrix 条码 – Aspose.BarCode .NET 指南
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  headline: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode, generate datamatrix, and explore
    high density barcode generation with Aspose.BarCode for .NET projects.
  name: How to create DataMatrix barcode (ECC 200) with Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is Aspose.BarCode''s core class that creates and renders
      barcodes. It accepts the symbology type and the text to encode. Replace `"Your
      Directory Path"` with the folder where you’d like the image saved.'
  - name: Set XDimension and ECC Type
    text: '`XDimension` defines the pixel size of each DataMatrix module, while `DataMatrixEcc`
      selects the error‑correction level. ECC 200 provides the highest correction
      capability for this symbology. Adjust the pixel value if you need larger or
      smaller modules; typical values are 4‑6 px for on‑screen displa'
  - name: Generate and Save the Barcode Image
    text: The `Save` method writes the barcode to a file. You can choose PNG, JPEG,
      or TIFF by passing the corresponding `BarCodeImageFormat` enum value. Switch
      `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff`
      if your workflow requires a different format.
  type: HowTo
- questions:
  - answer: Yes, the same API works in .NET Core, .NET 5, and .NET 6 projects.
    question: Can I use this code in a .NET Core console application?
  - answer: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` in the
      `Save` call.
    question: How do I change the output format to JPEG?
  - answer: Yes – generate the image first, then add it to a PDF using Aspose.PDF
      or any PDF library.
    question: Is it possible to embed the barcode directly into a PDF?
  - answer: DataMatrix supports UTF‑8; simply pass the Unicode string to the generator
      as shown.
    question: What if I need to encode Unicode characters?
  - answer: Absolutely – place the generation code inside a loop and change the data/value
      for each iteration.
    question: Does the library support batch generation of multiple barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- .NET barcode generation
- C# barcode tutorial
title: 如何使用 Aspose.BarCode for .NET 创建 DataMatrix 条码（ECC 200）
url: /zh/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 创建 DataMatrix 条码（ECC 200）

## 介绍

在本指南中，您将使用 Aspose.BarCode for .NET **创建 DataMatrix 条码**（ECC 200）。无论是构建库存跟踪器、销售点系统，还是自动化文档工作流，高密度条码都能在极小的空间内存储大量数据。我们将逐步演示每个配置步骤，解释每个设置为何重要，并提供可直接运行的 C# 代码片段。

## 快速答案
- **哪个库是 .NET 中 DataMatrix 的最佳选择？** Aspose.BarCode for .NET  
- **ECC 200 提供哪种 ECC 级别？** 高密度错误纠正，提供稳健的扫描。  
- **运行示例是否需要许可证？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **可以输出 PNG、JPEG 或 TIFF 吗？** 可以——`Save` 方法支持多种图像格式。

## 什么是 DataMatrix ECC 200？

DataMatrix ECC 200 是一种高密度二维条码，可在紧凑的方形或矩形图案中存储最多 2,335 个字母数字字符或 1,556 字节的二进制数据。它使用 Reed‑Solomon 错误纠正来恢复丢失或损坏的模块，因而非常适合航空部件标记、药品标签和物流等对可靠性要求极高的场景。

## 为什么使用 Aspose 条码生成？

Aspose.BarCode 支持 **30 多种符号系统**，能够在不将整个文件加载到内存的情况下渲染高达 10,000 × 10,000 像素的图像，并在 Windows、Linux 和 macOS 上提供确定性的输出。其 API 让您可以控制每一个渲染参数，是 **ASP.NET 条码生成** 场景中最灵活的选择。

## 前置条件

1. **开发环境** – 已安装相应 .NET 框架的 Visual Studio。  
2. **Aspose.BarCode for .NET** – 从官网下载安装，[此处](https://releases.aspose.com/barcode/net/)。  
3. **许可证** – 从[此处](https://purchase.aspose.com/temporary-license/)获取用于测试的临时许可证。  
4. **C# 基础** – 熟悉 C# 语法和项目结构。

现在我们已经掌握了基础，接下来进入 DataMatrix ECC 200 的配置。

## 导入命名空间

`Aspose.BarCode.Generation` 命名空间包含创建条码所需的所有类。请在文件顶部导入：

```csharp
using Aspose.BarCode.Generation;
```

## 如何一步步创建 DataMatrix 条码（ECC 200）

要生成 DataMatrix ECC 200 条码，只需加载要编码的数据，在 `BarcodeGenerator` 上配置少量关键参数，然后调用 `Save` 将图像写入文件。此三步流程处理编码、错误纠正和输出格式选择，使您能够以最少的代码将条码创建集成到任何 .NET 应用程序中。

### 步骤 1：初始化条码生成器

`BarcodeGenerator` 是 Aspose.BarCode 的核心类，用于创建和渲染条码。它接受符号类型和要编码的文本。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

将 `"Your Directory Path"` 替换为您希望保存图像的文件夹路径。

### 步骤 2：设置 XDimension 和 ECC 类型

`XDimension` 定义每个 DataMatrix 模块的像素大小，`DataMatrixEcc` 选择错误纠正级别。ECC 200 为此符号提供最高的纠正能力。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

如果需要更大或更小的模块，请调整像素值；常见的取值为屏幕显示时 4‑6 px，打印标签时 8‑10 px。

### 步骤 3：生成并保存条码图像

`Save` 方法将条码写入文件。通过传入相应的 `BarCodeImageFormat` 枚举值，您可以选择 PNG、JPEG 或 TIFF。

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

如果工作流需要不同的格式，请将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Tiff`。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|------|----------|----------|
| 条码显示模糊 | XDimension 设置过低 | 将 `XDimension.Pixels` 提升至 6‑8 |
| 移动端扫描失败 | ECC 级别错误 | 确保 `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| 文件未创建 | 路径字符串无效 | 使用绝对路径或确保文件夹已存在 |

## 常见问答

**Q: 我可以在 .NET Core 控制台应用程序中使用这段代码吗？**  
**A:** 可以，相同的 API 在 .NET Core、.NET 5 和 .NET 6 项目中均可使用。

**Q: 如何将输出格式改为 JPEG？**  
**A:** 在 `Save` 调用中将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Jpeg`。

**Q: 能否直接将条码嵌入 PDF 中？**  
**A:** 可以——先生成图像，然后使用 Aspose.PDF 或其他 PDF 库将其添加到 PDF 中。

**Q: 如果需要编码 Unicode 字符怎么办？**  
**A:** DataMatrix 支持 UTF‑8，只需按示例将 Unicode 字符串传递给生成器即可。

**Q: 库是否支持批量生成多个条码？**  
**A:** 完全支持——将生成代码放入循环中，并为每次迭代更改数据/值。

## 结论

我们已经覆盖了使用 Aspose.BarCode for .NET **创建 DataMatrix 条码**（ECC 200）的全部要点：从前置条件和命名空间导入，到配置 X‑dimension、选择 ECC 级别，再到以所需格式保存图像。您可以尝试使用诸如边距、背景色和旋转等额外属性，进一步微调输出以满足特定需求。

如果遇到任何困难，社区随时在 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 为您提供帮助。祝编码愉快！

---

**Last Updated:** 2026-08-02  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix ECC 000-140 条码](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-000-140-configuration/)
- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条码](/barcode/net/datamatrix-barcode-reading/)
- [创建条码 PNG – DataMatrix 长宽比自定义 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}