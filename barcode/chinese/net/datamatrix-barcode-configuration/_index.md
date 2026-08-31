---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码，定制宽高比、ECC 模式以及 DataMatrix
  C40 编码，以实现高效的条码创建。
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix 条码配置
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 生成 DataMatrix 条码 – Aspose.BarCode 专业指南
url: /zh/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成 DataMatrix 条码 – Aspose.BarCode 专业指南

欢迎来到我们关于使用 Aspose.BarCode for .NET **生成 DataMatrix 条码** 的完整教程系列。无论您是经验丰富的开发者，正在微调条码输出，还是渴望了解基础的新手，本指南将带您逐步完成每一步——从基本配置到高级编码技术——帮助您在任何 .NET 应用程序中生成可靠、可扫描的条码。

## 快速答案
- **主要目的是什么？** 以编程方式创建和自定义 DataMatrix 条码。  
- **使用哪个库？** Aspose.BarCode for .NET。  
- **需要许可证吗？** 提供免费试用；生产环境需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **可以自定义宽高比吗？** 可以——请参阅 “如何自定义 DataMatrix 宽高比” 部分。

## 什么是生成 DataMatrix 条码？
DataMatrix 条码是一种由黑白单元格组成的二维矩阵，可存储多达 2 300 个字母数字字符。使用 Aspose.BarCode，您可以直接从 .NET 代码 **生成 DataMatrix 条码** 图像、PDF 或 SVG，控制尺寸、纠错级别和编码模式，以满足任何行业标准。

## 为什么使用 Aspose.BarCode 生成 DataMatrix？
Aspose.BarCode 能以最高 **600 dpi** 渲染 DataMatrix 符号，且不会出现像素化，确保在高分辨率打印机上扫描清晰。它支持 **所有 50 多种 ECC 和宏模式**——包括 ECC 000‑140、ECC 200 和 Macro 05/06——让您可以为数据大小选择最佳的纠错级别。API 提供 **ASCII、C40、Text、X12 和 Bytes** 编码选项，使数据打包更高效。集成仅需一个 NuGet 包，无需外部本机库。

## 如何自定义 DataMatrix 宽高比
`BarCodeGenerator` 的 `AspectRatio` 属性控制生成的 DataMatrix 符号的宽高比例。`BarCodeGenerator` 是 Aspose.BarCode 中用于创建条码图像的主要类。

**直接答案：** 在调用 `GenerateBarCodeImage()` 之前，将 `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2`（或介于 0.5 到 2.0 之间的任意值）进行设置。库会自动重新计算模块大小，以在满足所请求比例的同时保持扫描可靠性。

### 步骤说明
1. **实例化** 使用 `EncodeTypes.DataMatrix` 的 `BarCodeGenerator`。  
2. **调整** `AspectRatio` 为所需的值。  
3. **生成** 图像，并使用扫描仪或 Aspose 内置读取器进行验证。

## 如何生成 DataMatrix ECC 000‑140 条码
ECC 000‑140 适用于需要紧凑符号的短数据字符串，提供高达 140 个纠错码字。`DataMatrixEccMode.Ecc000140` 为 DataMatrix 选择 ECC 000‑140 纠错方案。

**直接答案：** 在渲染之前使用 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140`。这会将编码器切换到 ECC 000‑140 算法，为给定数据生成尽可能小的矩阵，同时仍提供强大的纠错能力。

### 实用技巧
在编码少于 20 个字符的数字数据时，ECC 000‑140 通常会产生 10 × 10 的矩阵，从而节省宝贵的标签空间。

## 如何生成 DataMatrix ECC 200 条码
ECC 200 是最广泛采用的 DataMatrix 模式，支持多达 2 335 个字母数字字符，并提供卓越的纠错能力。`DataMatrixEccMode.Ecc200` 为 DataMatrix 选择 ECC 200 纠错方案。

**直接答案：** 将 `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` 并通过 `CodeText` 提供负载。库随后会自动选择最佳矩阵大小。

### 何时优先选择 ECC 200
对于较长的字符串、混合类型数据，或需要最高抗损伤能力的情况，请使用 ECC 200——符号中最多可恢复 **30 %** 的损坏。

## 如何精通 DataMatrix 的 ASCII 编码
ASCII 模式使用每字符一个字节进行编码，是纯文本最省空间的方式。`DataMatrixEncodeMode.Ascii` 告诉生成器对 DataMatrix 符号使用 ASCII 编码。

**直接答案：** 将 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` 并将 `CodeText` 设置为您的 ASCII 字符串。引擎在没有额外开销的情况下打包数据，为纯 ASCII 内容生成尽可能小的矩阵。

### 示例场景
仓库 SKU 由大写字母和数字组成（例如 “AB1234”），非常适合 ASCII 模式，通常会产生 12 × 12 的矩阵。

## 如何生成 DataMatrix 自动模式
自动模式让 Aspose.BarCode 分析输入并自动选择最有效的编码（ASCII、C40、Text、X12 或 Bytes）。`DataMatrixEncodeMode.Auto` 启用此自动选择功能。

**直接答案：** 将 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`。库会评估负载，选择最佳模式，并在一步完成条码渲染。

### 好处
自动模式降低开发工作量，并确保混合类型数据生成最小的符号，提高扫描速度。

## 如何使用 DataMatrix 编码模式（Bytes）
Bytes 模式专为二进制数据设计，如加密负载或压缩文件。`DataMatrixEncodeMode.Bytes` 指示生成器将每个字节视为原始数据。

**直接答案：** 使用 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` 并将 Base64 编码的字符串作为 `CodeText` 提供。编码器将每个字节视为原始数据，保留精确的二进制表示。

### 使用案例
将 128 位 GUID 或小型加密令牌直接嵌入 DataMatrix 符号中。

## 如何精通 DataMatrix 编码模式（C40）
C40 模式压缩大写字母数字数据，与 ASCII 相比可实现高达 **40 %** 的尺寸缩减。`DataMatrixEncodeMode.C40` 启用此压缩算法。

**直接答案：** 将 `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` 并提供大写字符串（例如 “HELLO WORLD”）。引擎将三个字符打包成两个码字，缩小最终矩阵。

### 专业提示
当负载主要由大写字母、数字和空格组成时，C40 效果最佳。对于混合大小写，建议使用自动模式。

## 如何配置 DataMatrix 代码文本
`CodeText` 属性定义条码中存储的精确数据。它可以包含纯文本、数字字符串，甚至 XML 负载。`CodeText` 是 `BarCodeGenerator` 的主要字符串属性，用于保存条码负载。

**直接答案：** 在渲染之前将 `generator.Parameters.Barcode.CodeText = "YourDataHere"` 进行赋值。该属性接受任何 UTF‑8 字符串，长度上限取决于所选 ECC 模式的最大支持长度。

### 高级技巧
将 `CodeText` 与 `ExtendedDataMatrix` 结合使用，可在不增加可见矩阵尺寸的情况下嵌入额外元数据。

## 如何精通 DataMatrix 宏配置
宏模式（Macro 05 和 Macro 06）允许在主符号内部嵌入次级 DataMatrix 符号，便于链接外部数据源。`DataMatrixMacroMode.Macro05` 和 `DataMatrixMacroMode.Macro06` 启用这些宏功能。

**直接答案：** 使用 `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05`（或 `Macro06`）启用宏模式，并为次级负载设置 `MacroPdf417` 属性。生成器会创建一个复合符号，扫描仪可将其解释为两个关联的代码。

### 实际案例
在宏部分嵌入 URL，同时在主矩阵中保留产品标识符，实现无缝的网页到条码集成。

*使用 Aspose.BarCode for .NET 教程列表*

## DataMatrix 条码配置教程
### [自定义 DataMatrix 宽高比](./datamatrix-aspect-ratio-customization/)
了解如何使用 Aspose.BarCode for .NET 自定义 DataMatrix 条码宽高比。条码生成的逐步指南。
### [生成 DataMatrix ECC 000-140 条码](./datamatrix-ecc-000-140-configuration/)
使用 Aspose.BarCode for .NET 轻松创建 DataMatrix ECC 000-140 条码。提升库存管理等效率。
### [生成 DataMatrix ECC 200 条码](./datamatrix-ecc-200-configuration/)
学习如何使用 Aspose.BarCode for .NET 在 .NET 中生成 DataMatrix ECC 200 条码。通过高效条码创建简化运营。
### [精通 DataMatrix ASCII 编码](./datamatrix-encoding-mode-ascii/)
学习使用 Aspose.BarCode for .NET 在 ASCII 模式下创建 DataMatrix 条码。面向开发者的逐步指南。
### [生成 DataMatrix 自动模式](./datamatrix-encoding-mode-auto/)
学习如何使用 Aspose.BarCode for .NET 生成 DataMatrix 自动模式。本逐步指南涵盖从前置条件到读取条码的全部内容。
### [DataMatrix 编码模式（Bytes）](./datamatrix-encoding-mode-bytes/)
学习使用 Aspose.BarCode for .NET 在 Bytes 模式下对数据进行 DataMatrix 编码。遵循我们的逐步指南进行条码生成和识别。
### [精通 DataMatrix 编码模式（C40）](./datamatrix-encoding-mode-c40/)
使用 Aspose.BarCode for .NET 学习 DataMatrix 编码模式（C40）。高效创建自定义条码。探索逐步指南。
### [配置 DataMatrix 代码文本](./datamatrix-extended-code-text-configuration/)
学习使用 Aspose.BarCode for .NET 配置 DataMatrix 扩展代码文本。生成、识别并在 .NET 应用程序中集成条码。
### [精通 DataMatrix 宏配置](./datamatrix-macro-configuration/)
学习如何使用 Aspose.BarCode for .NET 配置 DataMatrix 宏条码。生成、定制并在 .NET 应用程序中识别 DataMatrix 条码。

## 常见问题

**Q: 我该如何决定使用哪种 ECC 模式？**  
**A:** 对于小数据集且纠错需求有限的情况选择 ECC 000‑140；对于更大数据和更高可靠性则使用 ECC 200。宏模式为链接添加了额外的数据层。

**Q: 我可以在 DataMatrix 条码中嵌入自定义文本吗？**  
**A:** 可以，将 `CodeText` 属性设置为自定义字符串，然后选择相应的编码模式（ASCII、C40 等）以控制尺寸。

**Q: 有办法自动选择最佳编码模式吗？**  
**A:** 将 `EncodeMode` 设置为 `Auto`；Aspose.BarCode 会评估负载并自动挑选最省空间的模式。

**Q: 大批量条码的性能考虑有哪些？**  
**A:** 重用单个 `BarCodeGenerator` 实例，启用多线程，并生成 PNG 图像以获得无损质量，或使用 JPEG 以获得更小的文件大小。处理 10 000 个符号通常在标准 8 核服务器上不到 30 秒完成。

**Q: Aspose.BarCode 是否支持 .NET Core 和 .NET 5/6？**  
**A:** 当然——该库完全兼容 .NET Framework、.NET Core 以及最新的 .NET 发行版，在所有平台上提供相同的功能集。

**最后更新：** 2026-06-09  
**已测试版本：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码（ECC 200）](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [精通 Aspose.BarCode for .NET 的 DataMatrix ASCII 编码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [创建条码 PNG – DataMatrix 宽高比 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}