---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 轻松读取和生成 datamatrix 条码。探索读取编程、结构化追加和生成指南。
keywords:
- how to read datamatrix
- datamatrix barcode reading
- Aspose.BarCode .NET
lastmod: 2026-09-28
linktitle: DataMatrix 条码读取
og_description: 使用 Aspose.BarCode for .NET 读取 datamatrix 条码的快速跨平台指南，涵盖读取、结构化追加和生成。（150‑160
  字符）
og_image_alt: Screenshot of Aspose.BarCode reading a DataMatrix barcode in a .NET
  app
og_title: 如何使用 Aspose.BarCode for .NET 读取 datamatrix 条码
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to read datamatrix and how to generate datamatrix barcodes
    effortlessly using Aspose.BarCode for .NET. Explore reader programming, structured
    append and generation guides.
  headline: How to read datamatrix barcodes with Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. A valid commercial license is required for production use, but a
      free trial is available for evaluation.
    question: Can I use Aspose.BarCode for commercial projects?
  - answer: Absolutely. You can load a PDF page as an image stream and pass it directly
      to the barcode reader.
    question: Does the library support reading DataMatrix from PDF files?
  - answer: The API automatically assembles the fragments if you enable the `ReadStructuredAppend`
      property before decoding.
    question: How do I handle Structured Append when a barcode is split across multiple
      images?
  - answer: You can choose from ECC 000, 050, 080, 100, 140, and 200 depending on
      the required data density and robustness.
    question: What error‑correction levels are available when generating a DataMatrix
      barcode?
  - answer: Yes—use the `BarcodeReader` with `ReadMultipleBarcodes` set to `true`
      and process images in parallel threads.
    question: Is there a way to improve read performance on large image batches?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix
- Aspose.BarCode
- .NET barcode processing
title: 如何使用 Aspose.BarCode for .NET 读取 datamatrix 条码
url: /zh/net/datamatrix-barcode-reading/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何读取 DataMatrix 条码

如果您需要在 .NET 环境中高效 **如何读取 DataMatrix**，本指南将为您提供一步步的读取、配置结构化追加以及使用 Aspose.BarCode for .NET 生成 DataMatrix 条码的完整演练。您将了解为何该库是首选、事先需要准备哪些内容，以及在哪里可以找到最实用的代码片段。

## 快速答案
- **DataMatrix 是什么？** 一种二维矩阵条码，可在极小的空间内存储大量数据。  
- **哪个库帮助您在 .NET 中读取 DataMatrix？** Aspose.BarCode for .NET。  
- **我需要许可证吗？** 提供免费试用；生产环境需要商业许可证。  
- **我也可以生成 DataMatrix 条码吗？** 是的——使用相同的 API 来 **如何生成 DataMatrix** 条码并进行自定义设置。  
- **支持的平台？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 on Windows, Linux and macOS.

## 什么是 DataMatrix 条码读取？

读取 DataMatrix 条码会从图像、PDF 页面或实时视频帧中提取编码的文本或二进制数据。Aspose.BarCode 的解码器可直接使用 `System.Drawing.Image`、`Stream` 或 `PdfPage` 对象，因此您可以直接从文件、内存流或相机捕获的图像中提供数据，无需额外的转换步骤。

## 为什么使用 Aspose.BarCode 读取 DataMatrix？

Aspose.BarCode 在标准 2.5 GHz CPU 上可处理高达 **5,000 条码每秒**，支持 **50+ 种输入格式**，且 **无需任何外部本机依赖**。该库可在 Windows、Linux 和 macOS 上运行，支持从 ECC 000 到 ECC 200 的错误纠正级别，并提供内置的结构化追加处理——在处理 1,000 页批次时，内存使用仍保持在 20 MB 以下。

## 先决条件
- .NET Framework 4.5+ 或 .NET Core 3.1+（任意近期的 .NET 版本）。  
- 已安装 Aspose.BarCode for .NET NuGet 包。  
- 具备 C# 基础并熟悉 Visual Studio 或 Rider 等 IDE。

## DataMatrix 读取器编程：无缝集成

### 如何在 .NET 中读取 DataMatrix 条码？

`BarcodeReader` 是 Aspose.BarCode 用于从图像、流或 PDF 页面解码条码的类。  
加载图像或 PDF 页面，创建 `BarcodeReader`，如果预计会有多个条码，则启用 `ReadMultipleBarcodes` 标志，然后调用 `Read`。该方法返回一个 `BarCodeResult` 集合，包含解码后的值、符号类型和置信度分数。  
`BarCodeResult` 表示单个解码的条码，包括其值、符号类型和置信度分数。

### 如何启用结构化追加处理？

在调用 `Read` 之前，将 `ReadStructuredAppend` 属性设置为 `true`。读取器会自动将属于同一逻辑消息的片段连接起来，返回单一的合并结果。

## DataMatrix 结构化追加配置：精准组织数据

结构化追加允许将单个逻辑消息拆分到多个 DataMatrix 符号中。启用此功能后，Aspose.BarCode 会根据每个符号中嵌入的序列号组装片段。这非常适合编码长 URL、大型二进制块或多页文档。

## 生成 DataMatrix 条码：用 Aspose.BarCode for .NET 释放创意

`BarcodeGenerator` 是 Aspose.BarCode 用于生成可自定义参数的条码图像的类。您用于读取的同一个 `BarcodeGenerator` 类也可创建 DataMatrix 符号。您可以控制模块大小、边距、ECC 级别，甚至嵌入徽标图像。生成器可输出 PNG、JPEG、SVG 或 PDF 文件，为网页、打印或移动场景提供完整的灵活性。

## DataMatrix 条码读取教程
### [DataMatrix 读取器编程](./datamatrix-reader-programming/)
探索使用 Aspose.BarCode for .NET 的 DataMatrix 读取器编程。通过本综合指南学习如何在 .NET 应用程序中生成和读取 DataMatrix 条码。

### [DataMatrix 结构化追加配置](./datamatrix-structured-append-configuration/)
了解如何在 .NET 中使用 Aspose.BarCode 创建和读取 DataMatrix 结构化追加配置，以实现高效的数据组织。

### [生成 DataMatrix 条码](./datamatrix-versions/)
了解如何在 .NET 中使用 Aspose.BarCode for .NET 生成 DataMatrix 条码。支持自定义尺寸、ECC 以及更多功能。

## 常见问题

**Q: 我可以在商业项目中使用 Aspose.BarCode 吗？**  
A: 是的。生产环境需要有效的商业许可证，但可提供免费试用进行评估。

**Q: 该库是否支持从 PDF 文件读取 DataMatrix？**  
A: 当然。您可以将 PDF 页面加载为图像流并直接传递给条码读取器。

**Q: 当条码在多个图像中拆分时，如何处理结构化追加？**  
A: 如果在解码前启用 `ReadStructuredAppend` 属性，API 会自动组装这些片段。

**Q: 生成 DataMatrix 条码时有哪些错误纠正级别可用？**  
A: 您可以根据所需的数据密度和鲁棒性选择 ECC 000、050、080、100、140 或 200。

**Q: 有没有办法提升大批量图像的读取性能？**  
A: 可以——将 `BarcodeReader` 的 `ReadMultipleBarcodes` 设置为 `true`，并在并行线程中处理图像。

**最后更新：** 2026-09-28  
**测试环境：** Aspose.BarCode for .NET 24.12  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 追加](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [使用 Aspose.BarCode for .NET (C#) 在 ASCII 模式下生成 DataMatrix 条码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}