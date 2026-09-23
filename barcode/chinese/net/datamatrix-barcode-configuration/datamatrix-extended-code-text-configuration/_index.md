---
date: 2026-09-23
description: 了解如何在 .NET 中使用 Aspose.BarCode 生成带有扩展代码文本的 DataMatrix 条形码，适用于库存和物流应用。
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix 扩展代码文本配置
og_description: 如何在 .NET 中使用 Aspose.BarCode 生成带有扩展代码文本的 DataMatrix 条形码。遵循快速的分步指南，适用于库存和物流解决方案。
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: 如何在 .NET 中使用 Aspose.BarCode 创建 DataMatrix 代码文本
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: 如何在 .NET 中使用 Aspose.BarCode 创建 DataMatrix 代码文本
url: /zh/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中使用 Aspose.BarCode 创建 DataMatrix 条码文本

将条码集成到现代 .NET 应用程序中已不再是小众任务——它是库存、物流和移动扫描解决方案的核心需求。在本指南中，您将**学习如何使用 Aspose.BarCode** 配置带有扩展代码文本的 DataMatrix 条码，生成图像并以编程方式进行验证。您将了解为何此方法非常适合用于库存条码的创建，以及它如何适配 .NET Core 或 .NET 6 项目。

## 快速答案
- **需要的库是什么？** Aspose.BarCode for .NET  
- **条码类型是哪种？** DataMatrix with extended code text  
- **可以使用 .NET Core / .NET 6 吗？** 是的，API 跨平台  
- **测试是否需要许可证？** 免费试用可用于开发；生产环境需要许可证  
- **实现需要多长时间？** 基本示例大约 10‑15 分钟  

## Aspose.BarCode for .NET 是什么？

Aspose.BarCode for .NET 是一款商业库，使开发者能够生成和识别超过 30 种条码符号，包括 DataMatrix、QR 和 Code 128，并且能够在不依赖外部组件的情况下生成最高 10,000 × 10,000 像素的图像。它支持 .NET Framework 4.5+、.NET Core 3.1+ 和 .NET 5/6/7。

## 为什么使用 DataMatrix 扩展代码文本？

DataMatrix 扩展代码文本允许在单个符号中嵌入多种编码方案——UTF‑8、C40、Text、X12——从而在一个紧凑的方形中容纳多达 **3116 个代码字**（约 155 KB 数据）。此功能非常适合多语言产品标签、医疗设备追踪以及需要将字母数字 ID 与二进制负载相结合的智能包装。

## 前置条件

1. **Aspose.BarCode for .NET** – 从官方网站下载 **[Aspose.BarCode .NET 下载页面](https://releases.aspose.com/barcode/net/)**。  
2. **.NET 开发环境** – Visual Studio、Rider 或带有 .NET SDK 的 VS Code。  
3. **基本的 C# 知识** – 您应熟悉类、命名空间以及 `using` 指令。

## 导入命名空间

在 C# 文件的顶部添加所需的命名空间，以便编译器知道条码类所在的位置。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

这些命名空间让您能够访问条码生成和识别的功能。

## 如何配置 DataMatrix 扩展代码文本？

加载构建器，添加所需的段，并让 Aspose.BarCode 自动处理 ECI 标记。以下直接回答段落为您提供具体步骤：创建 `DataMatrixExtCodetextBuilder`，添加 Unicode、C40、纯文本和 Text 模式段，然后获取用于生成器的组合字符串。

### 步骤 1：定义输出文件夹

指定生成的条码图像保存位置。将占位符替换为您机器上的有效路径。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：构建扩展代码文本

`DataMatrixExtCodetextBuilder` 是一个帮助类，根据 DataMatrix 规范组装扩展代码文本。它会自动插入所需的 ECI（扩展通道解释）标记。

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

此示例展示了如何在单个 DataMatrix 符号中结合 Unicode 字符、C40 编码、纯文本和 Text 模式。

### 步骤 3：生成最终的代码文本字符串

在配置完所有部分后，获取 Aspose.BarCode 将嵌入条码的组合字符串。

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### 步骤 4：创建 DataMatrix 条码

`BarcodeGenerator` 是生成条码图像的核心类。使用 `EncodeTypes.DataMatrix` 和扩展代码文本实例化它，然后设置视觉参数，如 X‑dimension、图像格式以及可选的人类可读文本。

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

上述代码 **creates barcode aspose .net** 使用所需的扩展代码文本，并将其保存为 PNG 文件。

### 步骤 5：通过读取回验证条码

`BarCodeReader` 验证生成的符号能够正确解码，这对于自动化测试流水线和质量保证至关重要。

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

如果一切设置正确，控制台将输出您之前构建的完整扩展代码文本。

## 常见问题及故障排除

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 条码无法读取 | X‑dimension 太低 | 增加 `XDimension.Pixels`（例如，4 → 6） |
| 字符乱码 | ECI 编码错误 | 确保 `ECIEncodings.UTF8` 与字符集匹配 |
| 文件未保存 | 路径无效 | 使用绝对路径或确保文件夹存在 |
| 许可证异常 | 试用期已过 | 应用临时或正式许可证（参见 FAQ） |

## 常见问答

### Q1：Aspose.BarCode for .NET 是什么？

A1: Aspose.BarCode for .NET 是一款强大的库，使开发者能够生成和识别多种条码符号，包括 DataMatrix、QR、Code128 等。

### Q2：在哪里可以找到 Aspose.BarCode for .NET 的文档？

A2: 您可以访问完整的 API 参考 **[Aspose.BarCode .NET API 参考](https://reference.aspose.com/barcode/net/)**。

### Q3：Aspose.BarCode for .NET 是否提供免费试用？

A3: 是的，免费试用版可从 **[Aspose.BarCode 免费试用下载](https://releases.aspose.com/)** 下载。

### Q4：如何获取用于测试的临时许可证？

A4: 临时许可证用于评估，可在 **[Aspose 临时许可证申请页面](https://purchase.aspose.com/temporary-license/)** 申请。

### Q5：在哪里可以获得 Aspose.BarCode for .NET 的支持或提问？

A5: 官方 Aspose.BarCode 论坛是获取帮助的最佳场所：**[Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)**。

**最后更新：** 2026-09-23  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/net/datamatrix-barcode-configuration/)
- [使用 Aspose.BarCode for .NET (C#) 在 ASCII 模式下生成 DataMatrix 条码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [使用 Aspose.BarCode for .NET 生成带文本编码的 Aztec 条码](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}