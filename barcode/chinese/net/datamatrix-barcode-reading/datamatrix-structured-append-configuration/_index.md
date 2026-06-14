---
date: 2026-06-14
description: 了解如何在 .NET 中使用 Aspose.BarCode 读取 DataMatrix 并生成结构化附加条码，该库快速且可靠。
keywords:
- how to read datamatrix
- DataMatrix structured append
- Aspose.BarCode .NET
linktitle: DataMatrix 结构化附加配置
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET.
    question: What library handles DataMatrix structured append?
  - answer: Up to 16 DataMatrix symbols.
    question: How many symbols can a single structured append sequence contain?
  - answer: A free trial works for development and testing.
    question: Do I need a license for development?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: Yes, you can decode from a byte array or stream.
    question: Can I read the barcode without an image file?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 读取 DataMatrix 附加
url: /zh/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix 结构化追加配置（使用 Aspose.BarCode for .NET）

如果您是一名开发者，想要在 .NET 应用程序中 **如何读取 datamatrix**，Aspose.BarCode for .NET 是您的首选方案。在本分步指南中，我们将演示如何生成和解码跨多个符号的 DataMatrix 条码。完成本教程后，您将能够熟练创建、配置并读取使用 Aspose.BarCode for .NET 的 DataMatrix 结构化追加条码。

## 快速答案
- **哪个库处理 DataMatrix 结构化追加？** Aspose.BarCode for .NET。
- **单个结构化追加序列最多可以包含多少个符号？** 最多 16 个 DataMatrix 符号。
- **开发时需要许可证吗？** 免费试用版可用于开发和测试。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **可以不使用图像文件读取条码吗？** 可以，从字节数组或流中解码。

## 什么是读取 datamatrix？
**读取 datamatrix** 指的是解码 DataMatrix 符号的过程，并在适用时将结构化追加序列的各片段拼接起来，以恢复原始数据负载。Aspose.BarCode 提供内置支持，自动处理符号顺序和数据拼接。

## 为什么使用 Aspose.BarCode 进行 DataMatrix 结构化追加？
Aspose.BarCode 支持 **30 多种条码符号**，并且能够在典型服务器硬件上在 **200 ms** 内解码最高 **10,000 × 10,000 px** 的图像。该库还提供 **零依赖部署**，无需额外的本机 DLL，且可在 Windows、Linux、macOS 的 .NET 运行时上运行。

## 前置条件

在开始教程之前，您需要：

1. Aspose.BarCode for .NET 库 – 从 [here](https://releases.aspose.com/barcode/net/) 下载。
2. 您也可以在 [here](https://releases.aspose.com/) 浏览其他 Aspose 产品。
3. 一个 .NET 开发环境，例如 Visual Studio 2022 或带有 C# 扩展的 Visual Studio Code。

现在，让我们开始构建并读取 DataMatrix 结构化追加条码。

## 导入命名空间

第一步是导入提供条码 API 的命名空间。

`BarCodeWriter` 类是 Aspose.BarCode 用于创建条码的入口，而 `BarCodeReader` 负责解码。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

导入所需命名空间后，接下来生成结构化追加条码。

## 如何读取 DataMatrix 结构化追加条码？

将生成的图像（或流）加载到 `BarCodeReader`，启用 `ReadStructuredAppend` 选项，然后调用 `ReadBarcode`。读取器会自动返回合并后的数据，并公开诸如 `StructuredAppendFileId`、`StructuredAppendTotalCount`、`StructuredAppendSegmentId` 等序列细节。合并结果以单个字符串返回，您也可以通过读取器的 `StructuredAppendSegmentId` 属性获取各片段标识，以便自定义处理。

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

在此步骤中，我们使用读取器提取条码 ID、总计数和文件 ID，以确认结构化追加配置已被正确解释。

## 步骤 1：设置 DataMatrix 结构化追加配置

要创建 DataMatrix 结构化追加条码，需要设置其配置，包括目录路径、条码 ID、条码数量以及文件 ID。

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

在此步骤中，我们已使用所需参数配置了 DataMatrix 条码。

## 常见问题及解决方案

- **片段顺序错误：** 确保 `StructuredAppendSegmentId` 值从 0 开始且顺序连续；否则读取器无法正确重组数据。
- **总计数不匹配：** 所有符号的 `StructuredAppendTotalCount` 必须相同；不匹配会导致读取器将序列视为不完整。
- **图像质量：** 低分辨率图像可能导致解码失败。渲染条码为位图时建议至少 **300 dpi**。

## 常见问答

### Q1: 什么是 DataMatrix 结构化追加，为什么要使用它？

A1: DataMatrix 结构化追加是一项功能，允许将大量数据拆分为多个较小的条码。当单个条码空间受限或需要高效组织数据时，这非常有用。它常用于物流、医疗和制造业。

### Q2: 我可以在开源项目中使用 Aspose.BarCode for .NET 吗？

A2: 可以，Aspose.BarCode for .NET 提供免费试用版，可在开源项目中使用。试用版可在 [here](https://releases.aspose.com/) 获取。

### Q3: 是否有社区支持可用于 Aspose.BarCode for .NET？

A3: 有，您可以在 Aspose.BarCode 论坛 [here](https://forum.aspose.com/c/barcode/13) 寻求社区支持并与其他用户交流。

### Q4: 如何获取 Aspose.BarCode for .NET 的临时许可证？

A4: 若需用于评估或测试的临时许可证，可从 [here](https://purchase.aspose.com/temporary-license/) 获取。

### Q5: Aspose.BarCode for .NET 是否支持其他条码类型？

A5: 支持，Aspose.BarCode for .NET 支持广泛的条码类型，包括 QR 码、Code 128、EAN‑13 等。完整文档请参阅 [here](https://reference.aspose.com/barcode/net/)，了解所有受支持的条码类型列表。

---

**最后更新：** 2026-06-14  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.BarCode for .NET 的 DataMatrix 读取器编程](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条码](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [使用 Aspose.BarCode for .NET 的 DataMatrix 宏配置](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}