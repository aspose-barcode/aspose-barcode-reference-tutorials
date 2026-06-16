---
date: 2026-05-19
description: 了解如何使用 Aspose.BarCode for .NET 创建 Aztec 条码，定制 aspect ratios，encode bytes
  or text，以及 master symbol modes。
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec 条码编码
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 创建 Aztec 条码
url: /zh/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aztec 条形码编码

您准备好深入了解 Aztec 条形码编码的世界，并学习如何使用 Aspose.BarCode for .NET **创建 Aztec 条形码** 图像了吗？该库让您能够完全控制尺寸、错误纠正和数据表示，使其非常适合从移动票务到库存跟踪的各种场景。

## 快速回答
- **支持 Aztec 条形码的库是什么？** Aspose.BarCode for .NET  
- **我可以更改宽高比吗？** 是的，可通过 `AspectRatio` 属性  
- **可以进行字节级编码吗？** 完全可以 — 使用 `EncodeBytes` 方法  
- **有哪些错误纠正级别可用？** 级别 0 到 4（级别越高，冗余越多）  
- **生产环境需要许可证吗？** 是的，商业许可证可移除评估限制  

## 什么是 Aztec 条形码？
Aztec 条形码是一种二维矩阵码，能够编码最多 3,000 个数字或 2,300 个字母数字字符。它具有位于中心的定位图案，即使在低分辨率打印的情况下也能实现快速扫描。由于图案位于中心，代码可以从任何方向读取，这使其在移动和工业应用中具有极高的可靠性。

## 如何自定义 Aztec 条形码的宽高比？
`BarcodeGenerator` 是 Aspose.BarCode 中用于创建条形码的主要类。将在 `BarcodeGenerator` 对象上的 `AspectRatio` 属性设置为所需的宽高比例，然后生成图像。调整宽高比有助于在受限的 UI 空间或标签布局中适配条形码，而不牺牲扫描可靠性，同时还能满足品牌指南或特定打印机要求。

### 自定义宽高比的步骤
1. **创建一个 `BarcodeGenerator` 实例**，使用 `EncodeTypes.Aztec`。  
2. **分配您的数据**（文本、字节或数字字符串）。  
3. **设置 `AspectRatio`** — 例如，`1.5` 表示更宽的条。  
4. **使用 `Save` 或 `GetBarCodeImage` 生成图像**。  

## 如何将原始字节编码为 Aztec 条形码？
`EncodeBytes` 是一个接受字节数组并将其转换为 Aztec 矩阵的方法。将字节数组传递给 `BarcodeGenerator` 的 `EncodeBytes` 方法。API 会自动将二进制数据转换为紧凑的 Aztec 矩阵，保留每一位。这非常适合将加密负载、二进制标识符或压缩文件直接嵌入条形码中。

### 编码字节的步骤
1. **准备字节数组**（例如，`byte[] data = Encoding.UTF8.GetBytes("Hello")`）。  
2. **实例化 `BarcodeGenerator`**，使用 `EncodeTypes.Aztec`。  
3. **调用 `EncodeBytes(data)`** 以加载二进制内容。  
4. **使用 `Save` 或 `GetBarCodeImage` 渲染条形码**。  

## 如何将文本编码为 Aztec 条形码？
`CodeText` 是一个保存待编码纯文本数据的属性。使用 `BarcodeGenerator` 的 `CodeText` 属性提供纯文本数据。库会自动选择最佳的编码模式（数字、字母数字或字节）并应用相应的错误纠正级别。这使得嵌入 URL、产品 ID 或任何可读字符串变得轻松。

### 编码文本的步骤
1. **创建生成器**，使用 `EncodeTypes.Aztec`。  
2. **将 `CodeText` 设置为要编码的字符串**。  
3. **可选地调整 `ErrorLevel`** 以获得更高的容错性。  
4. **使用 `Save` 或 `GetBarCodeImage` 生成图像**。  

## 如何使用不同的错误纠正级别生成 Aztec 条形码？
`ErrorLevel` 是一个控制向条形码添加冗余数据量的属性。在渲染之前调整 `ErrorLevel` 属性（0‑4）。级别越高，冗余数据越多，即使符号损坏高达 30 % 时也能读取条形码。这在工业标签或户外标识等恶劣环境中至关重要。

### 设置错误纠正的步骤
1. **实例化用于 Aztec 的 `BarcodeGenerator`**。  
2. **分配您的数据**（文本或字节）。  
3. **设置 `ErrorLevel`** — 例如，`generator.Parameters.Barcode.Aztec.ErrorLevel = 3`。  
4. **使用您首选的输出格式渲染条形码**。  

## 不同的 Aztec 符号模式有哪些，如何使用它们？
`SymbolMode` 是一个决定生成的 Aztec 码矩阵大小和数据容量的设置。库提供四种模式：**Auto**、**FullRange**、**Compact** 和 **Rune**。

- **Auto** – 生成器选择可能的最小尺寸。  
- **FullRange** – 为非常大的数据集提供最大矩阵尺寸。  
- **Compact** – 创建更小、更密集的符号，适合空间受限的情况。  
- **Rune** – 用于编码 Unicode 符文的专用模式。

通过 `Generator.Parameters.Barcode.Aztec.SymbolMode` 选择模式。每种模式在尺寸、可读性和数据容量之间取得平衡，使您能够根据应用约束定制条形码。

## Aztec 条形码编码教程
以下是针对上述各主题的专门逐步指南。点击任意链接即可查看完整代码示例、前置条件和最佳实践提示。

### [自定义 Aztec 条形码宽高比](./aztec-aspect-ratio-customization/)
了解如何使用 Aspose.BarCode for .NET 自定义 Aztec 条形码的宽高比。为您的 .NET 应用程序创建独特且灵活的条形码。

### [Aztec 字节编码](./aztec-bytes-encoding/)
了解如何使用 Aspose.BarCode for .NET 执行 Aztec 字节编码。包括逐步指南、前置条件和代码示例。

### [Aztec 代码文本编码](./aztec-code-text-encoding/)
探索使用 Aspose.BarCode for .NET 进行 Aztec 代码文本编码的强大功能。学习如何在 .NET 应用程序中创建和识别 Aztec 码。

### [生成 Aztec 错误条形码](./aztec-error-level-example/)
了解如何使用 Aspose.BarCode for .NET 通过不同错误级别生成 Aztec 错误条形码。提供条形码创建的全面指南。

### [掌握 Aztec 符号模式](./aztec-symbol-mode-example/)
在 Aspose.BarCode for .NET 中探索 Aztec 符号模式，学习如何轻松生成多功能条形码。在本综合教程中实操 Auto、FullRange、Compact 和 Rune 模式。

## 常见问题

**Q: Aspose.BarCode 对 Aztec 编码支持哪些 .NET 版本？**  
A: 库支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 及更高版本。

**Q: 我可以创建用于打印的高分辨率 Aztec 条形码吗？**  
A: 是的 — 在保存图像之前设置 `Resolution` 属性（例如 300 dpi），即可获得适合打印的质量。

**Q: Aztec 条形码可以容纳多大的数据负载？**  
A: 最多可容纳 3,000 个数字或 2,300 个字母数字字符，或在 Compact 模式下约 1,800 字节的原始数据。

**Q: 能读取已旋转的 Aztec 条形码吗？**  
A: 完全可以 — Aspose.BarCode 的解码器会在读取时自动检测方向并进行校正。

**Q: 开发和测试是否需要许可证？**  
A: 提供免费评估许可证用于测试；生产部署需要商业许可证。

---

**最后更新：** 2026-05-19  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [如何使用 Aspose.BarCode for .NET 生成具有自定义宽高比的 Aztec 条形码](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [使用 barcode generator .net 进行 Aztec 字节编码](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [如何在 .NET 中创建具有错误纠正的 Aztec 条形码](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}