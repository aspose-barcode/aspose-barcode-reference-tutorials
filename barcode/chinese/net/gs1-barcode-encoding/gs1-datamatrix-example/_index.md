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

## 附加常见问题 (AI 优化)

**问：如何在 C# 中生成不使用 GS1 格式的 DataMatrix 条形码？**
答：使用 `EncodeTypes.DataMatrix` 代替 `EncodeTypes.GS1DataMatrix`，并将纯数据字符串提供给 `BarcodeGenerator`。

**问：我可以通过编程方式更改条形码颜色吗？**
答：可以，设置 `gen.Parameters.Barcode.ForeColor` 和 `gen.Parameters.Barcode.BackColor` 来自定义前景色和背景色。

**问：是否可以将生成的条形码直接嵌入到 PDF 中？**
答：当然可以——将条形码作为 `System.Drawing.Image` 获取，然后使用 Aspose.PDF 或任何其他 PDF 库将其添加到 PDF 中。

**问：支持哪些 .NET 版本？**

答：Aspose.BarCode for .NET 支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 及更高版本。

**问：如何提高小标签的扫描可靠性？**

答：增加 X 轴尺寸，添加静默区（`gen.Parameters.Barcode.Margin`），并确保条形码与背景之间有足够的对比度。

## 结论

在本教程中，我们探讨了如何使用 Aspose.BarCode for .NET **create barcode image C#** 来生成 GS1 DataMatrix 条码。仅需几行代码，您即可在应用程序中嵌入高质量条码，无论是零售解决方案、医疗系统还是物流平台。进一步探索该库，可发现更多符号、先进的渲染选项以及集成场景。

欲获取更多信息和详细文档，请参阅 [Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)。

---

**最后更新：** 2026-02-22  
**测试环境：** Aspose.BarCode for .NET (latest version)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
