---
date: 2026-05-30
description: 了解如何使用 Aspose.BarCode for .NET 创建具有自定义 DataMatrix 长宽比的条形码 PNG。提供条形码生成和尺寸自定义的分步指南。
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: DataMatrix 长宽比自定义
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 创建条形码 PNG – DataMatrix 长宽比 – Aspose.BarCode
url: /zh/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 barcode PNG – DataMatrix 长宽比 – Aspose.BarCode

生成具有自定义 DataMatrix 长宽比的 **barcode PNG** 是一种常见需求，当您需要 **create barcode PNG** 文件以符合特定布局约束时。在本教程中，我们将逐步演示使用 Aspose.BarCode for .NET **create barcode PNG** 文件的确切步骤，解释为何需要调整长宽比，并展示如何为您的应用程序微调输出。

## 快速答案
- **“aspect ratio” 控制什么？** 它定义了 DataMatrix 模块的宽高比例。  
- **我可以输出 PNG、JPEG 或 SVG 吗？** 是的 – `Save` 方法支持 PNG、JPEG、BMP、GIF、TIFF、SVG 和 PDF。  
- **我需要为此功能购买许可证吗？** 免费试用可用于开发；生产环境需要完整许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.x、.NET Core 3.1+、.NET 5/6/7。  
- **有效的 aspect‑ratio 值有多少？** 任意正浮点数；常见值为 0.5 – 2.0。

## 什么是 DataMatrix 条码，为什么要调整其长宽比？
DataMatrix 条码是一种二维矩阵码，可在紧凑的方形中存储大量数据。调整 **aspect ratio** 可让您水平拉伸或压缩模块，这在需要将条码放入狭窄列或宽标签中且不影响扫描可靠性时非常有用。

## 为什么使用 Aspose.BarCode 来创建 barcode PNG？
Aspose.BarCode 支持 **7 种图像格式** — PNG、JPEG、BMP、GIF、TIFF、SVG 和 PDF — 并且能够在内存中处理 **50+ 种输入和输出格式**，在不加载整个文件的情况下处理数百页的文档。该库提供流畅的 API，允许您在一行代码中生成 DataMatrix 条码，确保像素级完美渲染并完全兼容 .NET。

## 前提条件

在我们开始自定义 DataMatrix 长宽比之前，请确保已具备以下前提条件：

1. **Visual Studio** – 任意近期版本均可。  
2. **Aspose.BarCode for .NET** – 在此下载 [此处](https://releases.aspose.com/barcode/net/)。  
3. 您也可以在 [此处](https://releases.aspose.com/) 浏览其他 Aspose 产品发布。  
4. **.NET Framework / .NET Core** – 您的项目必须针对受支持的版本。

## 导入命名空间

首先，您需要在 C# 项目中导入必要的命名空间：

`using Aspose.BarCode.Generation;` 导入包含条码生成类的命名空间。  

```csharp
using Aspose.BarCode.Generation;
```

> **技巧提示：** 将此 `using` 语句保留在文件顶部，以便随时可用 `BarcodeGenerator` 类。

## 如何使用自定义长宽比创建 barcode PNG？

加载 `BarcodeGenerator`，设置 DataMatrix 类型，调整 `AspectRatio` 属性，然后调用 `Save`。此单行模式会创建符合您指定比例的 barcode PNG，库会自动处理模块缩放和安静区。

`BarcodeGenerator` 根据指定的符号系统和数据创建条码图像。  

### 步骤 1：设置项目
在 Visual Studio 中创建一个新的控制台或 Windows Forms 项目，并添加对 Aspose.BarCode DLL 的引用。

### 步骤 2：初始化 Barcode Generator
使用 DataMatrix 符号系统和您想要编码的数据实例化它：

`BarcodeGenerator` 根据指定的符号系统和数据创建条码图像。  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 此行创建了一个准备生成包含示例文本的 DataMatrix 条码的生成器。

### 步骤 3：自定义长宽比并保存 PNG 文件
现在您可以更改 **aspect ratio** 并将每个版本保存为 PNG 图像：

`AspectRatio` 设置 DataMatrix 模块的宽高比例。  
`Save` 将生成的条码图像写入所选格式的文件。  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 第一次调用创建了一个正方形比例的条码（`AspectRatio = 1`）。  
- 第二次调用水平压缩条码（`AspectRatio = 0.5`），产生更宽的外观。

现在您拥有两个具有不同长宽比的 **barcode PNG** 文件，可用于报表、标签或 UI 元素。

## 常见问题与解决方案

| 问题 | 解决方案 |
|-------|----------|
| **生成的图像模糊** | 在保存之前增加 `Resolution` 参数 (`gen.Parameters.ImageResolution = 300`)。 |
| **条码无法扫描** | 确保长宽比保持在 0.5 – 2.0 范围内，并保持足够的安静区 (`gen.Parameters.Barcode.CodeTextParameters.Margin`)。 |
| **文件路径错误** | 使用 `Path.Combine` 构建输出路径并确认文件夹存在。 |

## 常见问题解答

**问：我可以使用 Aspose.BarCode for .NET 自定义其他条码类型的长宽比吗？**  
**答：** 是的，许多 2‑D 条码（例如 QR、PDF417）通过其特定参数对象支持 aspect‑ratio 调整。

**问：Aspose.BarCode for .NET 是否提供免费试用？**  
**答：** 是的，您可以在 [此处](https://releases.aspose.com/) 获取 Aspose.BarCode for .NET 的免费试用。

**问：在哪里可以购买 Aspose.BarCode for .NET 的许可证？**  
**答：** 您可以在 Aspose 网站的 [此处](https://purchase.aspose.com/buy) 购买许可证。

**问：Aspose.BarCode for .NET 是否兼容不同的 .NET Framework 版本？**  
**答：** 是的，它兼容 .NET Framework 4.x、.NET Core 3.1+ 以及最新的 .NET 版本。

**问：我可以使用 Aspose.BarCode for .NET 生成不同格式的条码吗？**  
**答：** 当然可以——PNG、JPEG、BMP、GIF、TIFF、SVG 和 PDF 都开箱即支持。

## 结论

使用 Aspose.BarCode for .NET 自定义 DataMatrix 条码的 **aspect ratio** 并 **创建 barcode PNG** 文件非常简便。按照上述步骤操作，您即可生成尺寸恰当、满足项目精确布局需求的条码。探索诸如 `Resolution`、`Margin`、`Color` 等额外参数以进一步定制输出，并在使用 Visual Studio 构建易于扫描的应用程序时考虑 `generate datamatrix barcode` 功能。

欲深入了解，请查阅官方 [文档](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 社区。

---

**最后更新：** 2026-05-30  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [生成 DataMatrix 条码 – Aspose.BarCode 专业指南](/barcode/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [掌握使用 Aspose.BarCode for .NET 的 ASCII 编码 DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}