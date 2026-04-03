---
date: 2026-02-22
description: 学习如何使用 Aspose.BarCode for .NET 在 C# 中创建条形码图像，并快速高效地生成 GS1 DataMatrix
  条码。
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: 创建条码图像 C# – GS1 DataMatrix 示例
url: /zh/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix 示例

如果您正在寻找在 .NET 应用程序中 **create barcode image C#** 的可靠方法，Aspose.BarCode for .NET 让过程变得简单。这个强大的库支持广泛的符号集，包括 GS1 DataMatrix，并提供简洁的 API，让您专注于业务逻辑，而不是低层条码细节。在接下来的几分钟里，我们将通过一个完整的动手示例，展示如何生成 GS1 DataMatrix 条码、定制其外观并将其保存为图像文件。

## 快速答案
- **示例生成了什么？** 一个包含示例产品数据的 GS1 DataMatrix 条码。  
- **使用了哪个库？** Aspose.BarCode for .NET。  
- **我可以更改输出格式吗？** 可以，您可以保存为 PNG、JPEG、BMP 等。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **代码兼容 .NET Core 吗？** 完全兼容——相同的 API 在 .NET Framework 和 .NET Core/5/6 上都可使用。

## GS1 DataMatrix 条码是什么？
GS1 DataMatrix 是一种二维条码，用于编码产品级信息（例如 GTIN、序列号以及其他应用标识符）。它在零售、医疗保健和物流领域被广泛使用，以实现紧凑的高密度数据存储。

## 为什么使用 Aspose.BarCode 来 create barcode image C#？
- **Full‑featured API** – 支持 GS1 标准、错误纠正和尺寸控制。  
- **No external dependencies** – 纯 .NET 库，易于集成。  
- **Cross‑platform** – 可在 Windows、Linux 和 macOS 上运行。  
- **Extensive documentation** – 包含本示例等案例，帮助您快速上手。

## 先决条件

在深入教程之前，请确保您已具备以下先决条件：

1. **Aspose.BarCode for .NET** – 您需要安装 Aspose.BarCode for .NET。如果尚未安装，可在此处[下载](https://releases.aspose.com/barcode/net/)。  
2. **Development Environment** – 您应在系统上配置好 .NET 开发环境（Visual Studio、VS Code 或其他您偏好的 IDE）。

现在您已准备好先决条件，让我们开始生成 GS1 DataMatrix 条码。

## 导入命名空间

首先，导入使用 Aspose.BarCode for .NET 所需的命名空间。这些命名空间为您提供条码生成的功能。

```csharp
using Aspose.BarCode;
using System;
```

## 如何 create barcode image C# – 步骤指南

### 步骤 1：设置条码生成器

要开始，创建一个 `BarcodeGenerator` 实例并指定 **GS1 DataMatrix** 符号以及要编码的数据。在本示例中，我们编码字符串 **"(01)12345678901231(21)ASPOSE(30)9876"**，该字符串遵循 GS1 应用标识符格式。

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*技巧提示：* 用您自己的 GS1 标识符替换示例数据，以适应您的产品目录。

### 步骤 2：自定义条码属性

您可以使用 `Parameters` 对象定制条码的外观。这里我们将 X‑dimension（最小模块的大小）设置为 8 像素，并定义矩阵尺寸为 36 列 × 12 行。根据扫描需求调整这些数值。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*为什么调整 X‑dimension？* 较大的 X‑dimension 能让低分辨率设备更容易扫描条码，而较小的值则可减小图像尺寸。

### 步骤 3：保存条码图像

最后，将生成的条码保存到磁盘。示例使用 PNG 格式，但您也可以选择 JPEG、GIF、BMP 等 Aspose.BarCode 支持的格式。

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

运行代码后，您将在指定文件夹中看到 **Gs1DataMatrixExample.png**，可用于标签、包装或数字应用。

## 常见使用场景

- **Retail product labeling** – 编码 GTIN、批号和有效期。  
- **Pharmaceutical tracking** – 使用符合 GS1 标准的数据满足监管要求。  
- **Warehouse logistics** – 紧凑存储位置信息和库存数据。

## 故障排除与技巧

- **Incorrect data format** – 确保您的字符串遵循 GS1 应用标识符语法，否则条码可能无法被扫描。  
- **Image size issues** – 若生成的图像模糊，请增大 `XDimension.Pixels` 的值。  
- **License errors** – 试用许可证可用于评估，但生产部署必须使用正式许可证。

## 常见问题

### GS1 DataMatrix 是什么？
GS1 DataMatrix 是一种用于编码与产品及其识别相关数据的二维条码符号，特别在零售和医疗保健行业中广泛使用。

### Aspose.BarCode for .NET 适用于其他条码类型吗？
是的，Aspose.BarCode for .NET 支持多种条码类型，能够满足不同应用场景的需求。

### 我可以生成除 PNG 之外的其他图像格式的条码吗？
可以，Aspose.BarCode for .NET 允许您将生成的条码保存为 JPEG、GIF、BMP 等多种图像格式，除了 PNG 之外。

### 使用 Aspose.BarCode for .NET 是否需要许可证？
是的，商业使用 Aspose.BarCode for .NET 必须拥有有效许可证。您可以在 [Aspose 网站](https://purchase.aspose.com/buy) 获取许可证。

### 在哪里可以获得 Aspose.BarCode for .NET 的支持？
您可以在 [Aspose.BarCode for .NET 论坛](https://forum.aspose.com/c/barcode/13) 中寻找答案并获取支持。

## 附加常见问题 (AI 优化)

**Q: How do I generate a DataMatrix barcode in C# without GS1 formatting?**  
A: Use `EncodeTypes.DataMatrix` instead of `EncodeTypes.GS1DataMatrix` and provide the plain data string to the `BarcodeGenerator`.

**Q: Can I change the barcode colors programmatically?**  
A: Yes, set `gen.Parameters.Barcode.ForeColor` and `gen.Parameters.Barcode.BackColor` to customize foreground and background colors.

**Q: Is it possible to embed the generated barcode directly into a PDF?**  
A: Absolutely – retrieve the barcode as a `System.Drawing.Image` and add it to a PDF using Aspose.PDF or any other PDF library.

**Q: What .NET versions are supported?**  
A: Aspose.BarCode for .NET supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6, and later.

**Q: How can I improve scanning reliability for small labels?**  
A: Increase the X‑dimension, add quiet zones (`gen.Parameters.Barcode.Margin`), and ensure sufficient contrast between the barcode and background.

## 结论

在本教程中，我们探讨了如何使用 Aspose.BarCode for .NET **create barcode image C#** 来生成 GS1 DataMatrix 条码。仅需几行代码，您即可在应用程序中嵌入高质量条码，无论是零售解决方案、医疗系统还是物流平台。进一步探索该库，可发现更多符号、先进的渲染选项以及集成场景。

欲获取更多信息和详细文档，请参阅 [Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-22  
**测试环境：** Aspose.BarCode for .NET (latest version)  
**作者：** Aspose