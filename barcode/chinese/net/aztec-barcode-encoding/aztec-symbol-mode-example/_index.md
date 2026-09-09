---
date: 2026-05-24
description: 学习如何使用 Aspose.BarCode for .NET 创建 Aztec 条码 .NET，涵盖 Auto、FullRange、Compact
  和 Rune 符号模式，并提供一步一步的指导。
keywords:
- create aztec barcode .net
- aztec symbol mode
- aspose barcode .net
linktitle: Aztec 符号模式示例
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create aztec barcode .net using Aspose.BarCode for .NET,
    covering Auto, FullRange, Compact, and Rune symbol modes with step‑by‑step guidance.
  headline: Create Aztec Barcode .NET with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Aztec Symbol Mode determines how the library packs data into layers, affecting
      size, capacity, and readability.
    question: What is the purpose of Aztec Symbol Mode in barcode generation?
  - answer: Yes, simply assign a new string to the `CodeText` property before calling
      `Save`.
    question: Can I change the code text for Aztec barcodes in Aspose.BarCode for
      .NET?
  - answer: Yes, you can download a free trial version of Aspose.BarCode for .NET
      [here](https://releases.aspose.com/).
    question: Is there a free trial version of Aspose.BarCode for .NET available?
  - answer: You can refer to the complete documentation for Aspose.BarCode for .NET
      [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the full documentation for Aspose.BarCode for .NET?
  - answer: You can acquire a temporary license for Aspose.BarCode for .NET by visiting
      [this link](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 在 .NET 中创建 Aztec 条码
url: /zh/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握 Aztec 符号模式与 Aspose.BarCode for .NET

如果您希望快速可靠地 **create aztec barcode .net**，Aspose.BarCode for .NET 为您提供一个功能完整的 API，支持 .NET Framework、.NET Core 和 .NET 5/6+。在本教程中，我们将探讨四种 Aztec 符号模式——Auto、FullRange、Compact 和 Rune——并向您展示如何在它们之间切换并将结果保存为图像。完成后，您只需几行代码即可在任何 .NET 应用程序中嵌入 Aztec 条码。

## 快速答案
- **什么库在 .NET 中生成 Aztec 条码？** Aspose.BarCode for .NET.  
- **Aztec 支持多少种符号模式？** 四种：Auto、FullRange、Compact 和 Rune。  
- **开发是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 和 .NET 6+。  
- **我可以输出 PNG、JPEG 或 SVG 吗？** 可以——支持任何标准图像格式。

## 什么是 create aztec barcode .net？
`create aztec barcode .net` 指在 .NET 环境中使用 Aspose.BarCode API 生成 Aztec 二维条码的过程。该 API 自动处理编码、符号模式选择和图像渲染，使开发人员能够在不处理错误纠正计算或像素操作等底层细节的情况下生成高质量条码。

## 为什么使用 Aspose.BarCode 来生成 Aztec 条码？
Aspose.BarCode 支持 **30+ 条码符号**，并且能够在不将整个文件加载到内存中的情况下渲染高达 **10,000 × 10,000 px** 的图像。它在普通服务器上可在 **2 秒** 内处理 500 页文档，因而非常适合高吞吐量的企业场景。

## 前提条件

在开始之前，请确保您已具备以下前提条件：

- 具备 .NET 开发的基本知识。  
- 在机器上安装了 Visual Studio。  
- 拥有 Aspose.BarCode for .NET 的副本。您可以在[此处](https://releases.aspose.com/barcode/net/)下载。您也可以在[此处](https://releases.aspose.com/)探索其他 Aspose 产品。

既然您已准备就绪，让我们深入了解 Aztec 符号模式示例。

## 导入命名空间

首先，您需要导入使用 Aspose.BarCode for .NET 所必需的命名空间。打开 Visual Studio 项目，在代码文件顶部添加以下 using 语句：

```csharp
using Aspose.BarCode.Generation;
```

有了这些命名空间，您现在可以开始使用 Aspose.BarCode for .NET。

## 如何为 Aztec 条码设置 Barcode Generator？

`BarcodeGenerator` 类是根据所选符号和配置选项创建条码图像的核心组件。它提供了一个简易的 API，用于指定条码类型、要编码的数据以及各种渲染参数，然后将结果保存为图像文件。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

在此步骤中，我们已经设置了生成器并提供了用于编码的代码文本。

## 如何将 Aztec 符号模式设置为 Auto？

`AztecSymbolMode` 枚举定义了 Aztec 条码的四种可能符号模式，**Auto** 选项让库自动选择在保留所有数据和错误纠正要求的前提下最紧凑的尺寸。此模式适用于大多数希望获得最小条码且无需手动调节的场景。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

此步骤确保 Aztec 符号模式自动确定，并保存生成的条码图像。

## 如何强制使用 FullRange 符号模式？

当您需要最大的数据容量时，可以选择 `AztecSymbolMode` 枚举的 **FullRange** 值。此模式禁用自动尺寸缩减，使条码能够存储完整字符范围并实现最高的信息密度，适用于大数据集。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

这将创建一个使用 FullRange Aztec 符号模式的条码。

## 如何生成 Compact Aztec 条码？

`AztecSymbolMode` 枚举的 **Compact** 值通过减少矩阵使用的层数来生成更小的条码。这产生更节省空间的图像，适用于显示面积受限的应用，如移动屏幕或小标签。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

此步骤将条码配置为使用 Compact Aztec 符号模式生成。

## 如何创建 Rune Aztec 条码？

**Rune** 模式是 Aztec 符号的专用变体，使用自定义字符集对数字数据进行编码，提供独特的视觉风格，同时保留与其他模式相同的错误纠正强度。当您需要强调数字信息的条码时，它非常有用。

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

此步骤将代码文本更改为 "123" 并生成使用 Rune Aztec 符号模式的条码。

## 常见问题及解决方案

- **图像未保存** – 确保输出文件夹存在且应用程序具有写入权限。  
- **意外的符号尺寸** – 验证代码中未在其他位置覆盖 `EncodeMode`。  
- **许可证异常** – 试用版会添加水印；使用有效许可证即可去除。

## 常见问答

**Q: Aztec 符号模式在条码生成中的作用是什么？**  
A: Aztec 符号模式决定库如何将数据打包到层中，影响尺寸、容量和可读性。

**Q: 我可以在 Aspose.BarCode for .NET 中更改 Aztec 条码的代码文本吗？**  
A: 可以，只需在调用 `Save` 之前为 `CodeText` 属性赋予新的字符串。

**Q: 是否有 Aspose.BarCode for .NET 的免费试用版？**  
A: 有，您可以在[此处](https://releases.aspose.com/)下载 Aspose.BarCode for .NET 的免费试用版。

**Q: 在哪里可以找到 Aspose.BarCode for .NET 的完整文档？**  
A: 您可以在[此处](https://reference.aspose.com/barcode/net/)查阅 Aspose.BarCode for .NET 的完整文档。

**Q: 如何获取 Aspose.BarCode for .NET 的临时许可证？**  
A: 您可以通过访问[此链接](https://purchase.aspose.com/temporary-license/)获取 Aspose.BarCode for .NET 的临时许可证。

## 结论

在本教程中，我们探讨了如何使用 Aspose.BarCode **create aztec barcode .net**，涵盖了 Auto、FullRange、Compact 和 Rune 符号模式。现在，您已经具备了将多功能 Aztec 条码嵌入任何 .NET 应用程序的坚实基础，无论其运行在桌面、Web 服务器还是云服务上。

如果您有任何问题或需要进一步帮助，请随时在 Aspose.BarCode 社区的[支持论坛](https://forum.aspose.com/c/barcode/13)上联系。

---

**最后更新：** 2026-05-24  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [使用 Aspose.BarCode for .NET 的 Aztec 文本编码](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [使用 barcode generator .net 的 Aztec 字节编码](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [如何在 .NET 中创建带错误纠正的 Aztec 条码](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}