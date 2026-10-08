---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 创建 2d 矩阵条码——一步步指南，生成带扩展代码文本的 DotCode 条码。
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode 扩展代码文本配置
og_description: 学习使用 Aspose.BarCode for .NET 创建 2d 矩阵条码。本指南逐步演示如何生成带扩展代码文本的 DotCode
  条码。
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: 使用 Aspose.BarCode for .NET 创建 2d 矩阵条码
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: 如何使用 Aspose.BarCode for .NET 创建 2d 矩阵条码
url: /zh/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 创建 2d 矩阵条码

## 介绍

在条码生成和管理领域，Aspose.BarCode for .NET 脱颖而出，作为一种多功能解决方案，支持 **50+ 输入和输出格式**，并且能够在不将整个文件加载到内存中的情况下处理数百页的文档。无论您需要用于产品追踪、库存控制或数据丰富的应用的条码，创建诸如 DotCode 的 **2d 矩阵条码** 并使用扩展码文本，可在紧凑的方形符号中嵌入文本和二进制负载。本教程将逐步引导您构建该扩展码文本并渲染最终图像。

## 快速答案

- **创建 dotcode 扩展码文本 是什么意思？** 它意味着构建一个包含 FNC1、ECICodetext、纯文本和符号分隔符的单一扩展负载的 DotCode 条码。  
- **需要哪个库？** Aspose.BarCode for .NET。  
- **我需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7+。  
- **实现需要多长时间？** 基本示例大约需要 10‑15 分钟。

## 如何创建 dotcode 扩展码文本

加载项目，设置目录，构建扩展码文本并生成图像——全部代码不超过十几行。以下直接答案概括了整个过程：

使用 `EncodeTypes.DotCode` 加载 `BarcodeGenerator`，使用 `DotCodeExtendedCodetextBuilder` 构建扩展码文本（添加 FNC1、ECICodetext、纯文本和 FNC3 分隔符），然后调用 `Save` 将 PNG 文件写入磁盘。此序列在一次调用中创建完全符合规范的 2d 矩阵条码。

## 什么是 dotcode 扩展码文本？

**dotcode 扩展码文本** 是一个复合字符串，将多个数据段——如 FNC1 标识符、ECICodetext、纯文本和 FNC3 分隔符——组合成 DotCode 可解码的单一负载。它能够在单个 2d 矩阵条码中编码多语言文本、二进制块和结构化数据，非常适用于供应链、医疗保健和物联网场景。

## 为什么在此任务中使用 Aspose.BarCode？

Aspose.BarCode 在典型服务器硬件上可 **每秒处理高达 500 页**，并支持 **30 多种条码符号**，包括 DotCode。其 `GetExtendedCodetext` API 确保控制字符的正确放置，消除手动字符串拼接错误，确保符合 ISO/IEC 24724。除此之外，它还提供内置纠错和自动静区处理，减少手动调优的需求。

## 前提条件

- **Aspose.BarCode for .NET** – 从 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 下载。  
- .NET 开发环境（推荐使用 Visual Studio 2022 或更高版本）。  
- 可选：用于评估的临时许可证文件。

## 导入命名空间

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

这些命名空间公开了示例所需的 `BarcodeGenerator` 类和 `DotCodeExtendedCodetextBuilder` 辅助类。

```csharp
using Aspose.BarCode.Generation;
```

现在我们已经完成前提条件，让我们将生成 DotCode 扩展码文本的过程拆解为一步一步的指南。

## 步骤 1：定义目录路径

指定生成的 PNG 将保存的位置。使用应用程序有写入权限的绝对路径或相对路径。

```csharp
string path = "Your Directory Path";
```

将 `"Your Directory Path"` 替换为系统上的实际路径。

## 步骤 2：创建 dotcode 扩展码文本

`DotCodeExtendedCodetextBuilder` 类将各个段组合成单一的扩展码文本字符串。

要创建 DotCode 扩展码文本，请按照以下子步骤操作：

### 2.1 添加 fnc1 格式标识符

FNC1 格式标识符标记新数据字段的开始。它是 GS1 兼容的 DotCode 符号所必需的。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 添加 ecicodetext

ECICodetext 对特殊字符和国际文本进行编码。在本例中，我们使用 UTF‑8 编码 `"犬Right狗"`。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 添加纯文本码

您也可以向 DotCode 扩展码文本添加纯文本。在此，我们添加 `"Plain text"`。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 添加 fnc3 符号分隔符

FNC3 符号分隔符将代码的不同部分分开，提高扫描器的可读性。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 添加 fnc3 读取器初始化

此步骤添加 FNC3 读取器初始化信息，告诉扫描器如何解释后续数据。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 生成码文本

现在通过在 `textBuilder` 对象上调用 `GetExtendedCodetext` 方法来生成 DotCode 扩展码文本。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 步骤 3：生成 dotcode 图像

从扩展码文本渲染条码图像。

#### 3.1 初始化条码生成器

`BarcodeGenerator` 类是 Aspose.BarCode 用于创建任何条码的核心对象。您使用所需的符号（`EncodeTypes.DotCode`）和刚构建的扩展码文本实例化它。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

最后，调用 `Save` 将 PNG 文件写入磁盘。该图像可用于嵌入报告、移动应用或打印标签。

## 常见问题及解决方案

- **编码错误** – 添加多语言文本时请使用 `ECIEncodings.UTF8`；否则字符可能出现乱码。  
- **文件访问错误** – 确认应用程序对目标目录具有写入权限。  
- **缺少静区** – 如果扫描器需要符号周围的额外空白，请设置 `gen.Parameters.Barcode.Margin`。

## 常见问答

**Q: 我可以在移动应用中使用生成的条码吗？**  
A: 可以。生成器产生的 PNG 图像可以嵌入 iOS、Android 或任何跨平台移动应用中。

**Q: 如果需要编码二进制数据而不是文本怎么办？**  
A: 使用 `AddECICodetext` 方法并指定相应的 `ECIEncodings`（例如 `ECIEncodings.Base64`）来嵌入二进制负载。

**Q: 如何在不影响可读性的情况下更改条码尺寸？**  
A: 调整 `XDimension.Pixels` 属性；更高的值增大模块尺寸，较低的值使条码更紧凑。

**Q: 有办法在条码周围添加静区吗？**  
A: 有。设置 `gen.Parameters.Barcode.Margin` 以像素定义所需的静区。

**Q: 该库支持 .NET 8 吗？**  
A: 最新的 Aspose.BarCode 版本兼容 .NET 8，只需引用相应的 NuGet 包版本。

如果您需要进一步指导或有任何疑问，请随时访问 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 或在 [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13) 与社区交流。

---

**最后更新:** 2026-09-28  
**测试环境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose

## 相关教程

- [使用 Aspose.BarCode 在 .NET 中创建 DotCode 条码（自动模式）](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/net/datamatrix-barcode-configuration/)
- [使用 Aspose.BarCode for .NET 创建 Aztec 条码](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}