---
date: 2026-08-17
description: 了解如何使用 Aspose.BarCode for .NET 创建带宏字符的 DataMatrix 条码，并探索在应用程序中使用 DataMatrix
  的方法。
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: DataMatrix 宏配置
og_description: 了解如何使用 Aspose.BarCode for .NET 创建带宏字符的 DataMatrix 条码。本指南提供逐步代码示例、定制选项以及验证技巧，帮助实现可靠的条码生成。
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: 使用 Aspose.BarCode 创建带宏字符的 DataMatrix 条码
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: 如何在 .NET 中使用宏字符创建 DataMatrix 条码
url: /zh/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中使用宏字符创建 DataMatrix 条码

## 介绍

生成包含宏字符的 **DataMatrix 条码** 可以将额外的参考信息压缩到一个小方形符号中。在本教程中，您将学习如何使用 Aspose.BarCode for .NET **创建带宏字符的 DataMatrix 条码**，自定义尺寸和错误纠正，并即时验证结果。完成后，您即可在产品标签、文档或医疗设备中嵌入支持宏的条码。

## 快速答案
- **主要库是什么？** Aspose.BarCode for .NET  
- **我可以创建带宏字符的 DataMatrix 条码吗？** 可以 – 设置 `MacroCharacters` 属性。  
- **生产环境需要许可证吗？** 需要有效的 Aspose 许可证才能用于生产。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **是否提供免费试用？** 当然 – 可从官方 Aspose 网站下载。

## 前置条件

在进行宏配置之前，请确保具备以下条件：

1. **Visual Studio** – 任意近期版本均可。  
2. **Aspose.BarCode for .NET** – 从 [the download link](https://releases.aspose.com/barcode/net/) 下载。  
3. **基本的 .NET 知识** – 熟悉 C# 和 .NET 生态系统。

## 导入命名空间

我们首先引入生成和识别条码所需的命名空间。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## 什么是带宏字符的 “生成 DataMatrix 条码”？

`MacroCharacters` 使 DataMatrix 条码能够包含宏符号，以引用额外的数据。使用 Macro05、Macro06 等宏字符，单个条码即可指向更大的数据集或一系列相关条码，这在物流、制造和文档追踪等需要紧凑编码链接信息的场景中非常有价值。

## 为什么使用 Aspose.BarCode 生成 DataMatrix 条码？

Aspose.BarCode 为您提供对 DataMatrix 大小、错误纠正级别和宏设置的精确控制，支持超过 30 种条码符号，并能在不将整幅图像加载到内存的情况下处理高达 10 MB 的文件。其跨平台 .NET 实现兼容 .NET Framework、.NET Core 和 .NET 5/6，并内置识别功能，可即时验证条码。

## 步骤指南

### 步骤 1：设置项目

在 Visual Studio 中创建一个新的控制台应用程序（或任意 .NET 项目）。将从下载获得的 Aspose.BarCode DLL 添加为引用。

### 步骤 2：DataMatrix 宏配置

本教程的核心 – 在此我们实际 **创建带宏字符的 DataMatrix 条码**。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **专业提示：** 将 `"ASPOSE"` 替换为您需要编码的任意字符串。宏字符 (`Macro05`) 告诉扫描仪此条码是宏序列的一部分。

### 步骤 3：自定义错误纠正的条码参数

保存之前，您可以微调以下设置：

- **XDimension** – 控制每个模块（像素）的大小。  
- **Margin**、**ErrorCorrection** 和 **EncodingMode** – 均可通过 `gen.Parameters.Barcode.DataMatrix` 访问。

### 步骤 4：保存条码

上面的代码片段会将图像保存为 `DataMatrixMacro.png` 到您指定的文件夹。PNG 为无损格式，适合后续处理。

### 步骤 5：识别条码

`BarCodeReader` 是 Aspose.BarCode 用于从图像解码条码的类。使用 `BarCodeReader` 我们立即读取生成的图像，以确认宏字符和数据是否正确。这种往返验证在自动化测试中尤为便利。

## 如何在实际场景中使用 DataMatrix？

您可以将带宏字符的 DataMatrix 条码应用于产品标签，将序列号链接到中心数据库；用于文档追踪，通过嵌入对数字记录的引用；以及用于医疗设备标签，在微小的可扫描符号中存储患者或设备数据。这些用例可减少手工录入并提升可追溯性。

## 常见问题与解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 条码未被识别 | `XDimension` 不正确或图像分辨率太低 | 将 `XDimension.Pixels` 增加到 4‑6 并保存为 PNG 或 TIFF |
| 宏字符被忽略 | 读取器不支持宏模式 | 使用明确支持 DataMatrix 宏的扫描仪/读取器（例如更新的 ZXing 版本） |
| 路径未找到 | `path` 变量无效 | 确保目录存在或使用 `Path.Combine` 与 `Environment.CurrentDirectory` |

## 常见问题

**问：Aspose.BarCode for .NET 是什么？**  
答：Aspose.BarCode for .NET 是一个强大的库，允许 .NET 开发者生成和识别各种格式的条码，包括 DataMatrix、QR 等。

**问：为什么要使用 DataMatrix 条码？**  
答：DataMatrix 条码体积小、可靠性高，且可存储大量数据，非常适合制造、物流和医疗领域。

**问：在哪里可以找到 Aspose.BarCode for .NET 的文档？**  
答：您可以在 [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 查看文档。

**问：是否提供 Aspose.BarCode for .NET 的免费试用？**  
答：是的，您可以从 [the free trial link](https://releases.aspose.com/) 下载免费试用版。

**问：在哪里可以获得 Aspose.BarCode for .NET 的支持？**  
答：如果有任何问题或需要帮助，可访问 Aspose.BarCode for .NET 论坛 [the support forum](https://forum.aspose.com/c/barcode/13)。

---

**最后更新：** 2026-08-17  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [创建条码 Aspose .NET - 配置 DataMatrix 代码文本](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码（ECC 200）](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [DataMatrix 结构化追加配置（使用 Aspose.BarCode for .NET）](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}