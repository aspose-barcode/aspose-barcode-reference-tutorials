---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode 通过 C40 编码生成 DataMatrix 条形码并保存为 PNG – .NET Core
  条形码生成的完整指南。
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix 编码模式 (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode 通过 C40 生成 DataMatrix PNG
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 的主 DataMatrix 编码模式 (C40)

## 介绍

在本教程中，您将学习 **如何生成 datamatrix** 条码并使用 C40 编码模式将其保存为 PNG 文件，使用 Aspose.BarCode for .NET。无论您是在构建库存系统、运单标签生成器，还是任何需要紧凑高密度符号的解决方案，掌握 C40 都能在不牺牲可读性的前提下提供更小的符号。我们将逐步演示每一步——从环境设置到生成最终 PNG——以便您立即将代码集成到项目中。

## 快速答案
- **“how to generate datamatrix” 是指什么？** 以编程方式创建 DataMatrix 条码图像。  
- **覆盖了哪种编码模式？** DataMatrix C40，一种高效的字母数字方案。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **我可以在 .NET Core 上运行吗？** 可以，Aspose.BarCode 完全支持 .NET Core、.NET 5、.NET 6 及更高版本。  
- **生成的文件格式是什么？** PNG – 一种无损、适合网页的图像格式。

## 如何使用 C40 编码生成 DataMatrix

加载数据，配置生成器，然后调用 `Save` ——这就是三个简洁步骤的完整工作流。`BarcodeGenerator` 类负责符号创建，而 `BarCodeImageFormat.Png` 枚举指示 Aspose.BarCode 将结果写入 PNG 文件。`Save` 将生成的条码图像写入指定的文件路径并使用所选格式。这段直接回答的段落在我们深入每行代码之前，为您提供端到端的解决方案。

## 什么是 DataMatrix 编码模式 (C40)？

`DataMatrixEncodeMode` 是一个枚举，用于指定 Aspose.BarCode 应该为 DataMatrix 符号使用哪种编码方案。`DataMatrixEncodeMode.C40` 选项选择 C40 字母数字编码，它将字母、数字以及有限的标点符号压缩到更少的模块中，从而在保持典型库存文本可读性的同时减小整体符号尺寸。这种高效方案在需要以紧凑形式编码字母数字数据时尤为理想。

## 为什么使用 Aspose.BarCode for .NET？

Aspose.BarCode 提供 **30+ 可配置参数** 用于尺寸、纠错级别和编码模式，并支持 **50+ 图像和条码格式**。该库可在 **.NET Framework 4.5+、.NET Core 2.0+、.NET 5/6+** 上运行，提供零依赖的生成能力，适用于服务器、桌面和移动设备。

## 前提条件

在深入代码之前，请确保您具备以下条件：

1. **.NET 开发环境** – Visual Studio、Rider 或任何支持 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 通过 NuGet 或官方安装程序安装。详情请参阅[文档](https://reference.aspose.com/barcode/net/)。  
3. **基本的 C# 知识** – 你应熟悉命名空间、类和 using 语句。  
4. **写入权限文件夹** – 机器上用于保存 PNG 的目录。

## 导入必要的命名空间

`BarcodeGenerator` 类是创建任何条码的入口点。请在 C# 源文件顶部添加所需的命名空间，以便访问生成 API：

```csharp
using Aspose.BarCode.Generation;
```

## 步骤式条码生成

下面是一个 **step‑by‑step barcode** 演练。每一步都用通俗语言解释，原始占位符保持不变，便于复制粘贴。

### 步骤 1：定义目录路径
设置将存储 PNG 图像的文件夹。将占位符替换为您机器上的实际路径。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：设置条码生成
创建 `BarcodeGenerator` 实例，指定 `EncodeTypes.DataMatrix`，并提供要编码的数据。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 步骤 3：自定义条码
配置 X‑dimension（模块的像素宽度），并将编码模式切换为 C40。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 步骤 4：保存条码图像
最后，将生成的条码保存为 PNG 文件。这就是 **如何保存 png** 的具体答案，使用 Aspose.BarCode。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

运行程序后，您将在指定的文件夹中找到 `DataMatrixEncodeModeC40.png`，可用于报表、标签或网页。

## 常见问题与技巧

- **无效路径** – 确保目录存在且具有写入权限；否则 `gen.Save` 会抛出异常。  
- **编码模式错误** – 如果需要编码 C40 集合之外的字符，请切换到 `DataMatrixEncodeMode.Auto` 或其他合适的模式。  
- **图像大小** – 调整 `XDimension.Pixels` 可在不影响可读性的前提下增大或减小条码整体尺寸。

## 常见问题解答

**问：什么是 DataMatrix 编码模式 (C40)？**  
答：C40 是一种紧凑的字母数字编码方案，适用于包含字母、数字以及有限特殊字符的文本。

**问：在哪里可以找到 Aspose.BarCode for .NET 文档？**  
答：您可以在[此处](https://reference.aspose.com/barcode/net/)找到文档。它提供了所有条码类型和编码选项的详细指南。

**问：Aspose.BarCode for .NET 是否兼容所有 .NET 版本？**  
答：是的，库支持广泛的 .NET 版本，从 .NET Framework 4.5+ 到 .NET 6 及更高版本。

**问：我可以在购买前试用 Aspose.BarCode for .NET 吗？**  
答：可以，您可以通过访问[此链接](https://releases.aspose.com/)获取 Aspose.BarCode for .NET 的免费试用版，以测试库的功能和特性。

**问：在哪里可以获得 Aspose.BarCode for .NET 的支持？**  
答：您可以在[Aspose 论坛](https://forum.aspose.com/c/barcode/13)找到支持社区并获取 Aspose.BarCode for .NET 的帮助。

## 结论

通过遵循本 **step‑by‑step barcode** 指南，您现在已经完全掌握 **如何生成 datamatrix** 条码并使用 C40 编码模式将其保存为 PNG 文件，使用 Aspose.BarCode for .NET。此方法让您对条码的外观、尺寸和数据表示拥有完整控制，轻松将高质量条码嵌入任何 .NET 应用程序。

---

**最后更新：** 2026-06-09  
**测试版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.BarCode for .NET 的字节方式 DataMatrix 编码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [使用 Aspose.BarCode for .NET 的 ASCII 主 DataMatrix 编码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}