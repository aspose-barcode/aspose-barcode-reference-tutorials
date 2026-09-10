---
date: 2026-05-30
description: 了解如何在字节模式下生成 DataMatrix 条码以及使用 Aspose.BarCode for .NET 读取 DataMatrix
  条码——一步一步的条码指南。
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: DataMatrix 编码模式（字节）
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 在字节模式下生成 DataMatrix 条码
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 在字节模式下生成 DataMatrix 条码

在本教程中，您将学习如何使用字节编码模式**生成 DataMatrix 条码**，然后使用 Aspose.BarCode for .NET **读取 DataMatrix 条码**。无论您是构建仓库管理系统还是移动票务应用，下面的逐步条码指南将向您展示如何配置条码生成器设置、生成高质量图像并再次解码——只需几行 C# 代码。

## 快速答案
- **我可以在 .NET 中生成 DataMatrix 条码吗？** 是的，使用 `BarcodeGenerator` 与 `EncodeTypes.DataMatrix` 并设置 `DataMatrixEncodeMode.Bytes`。
- **哪个方法读取条码？** `BarCodeReader` 读取图像并返回编码的文本。
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用。
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **我可以编码多少字节？** 单个 DataMatrix 符号最多可编码 1,555 字节。

## 什么是生成 DataMatrix 条码？
**生成 DataMatrix 条码** 是指创建一种二维方形条码，可存储二进制数据。Aspose.BarCode 将符号渲染为 PNG、JPG 或 SVG 图像，任何扫描仪都可以解码。它广泛用于库存跟踪、文档管理和身份验证，因为它提供高数据密度和错误纠正能力，即使在低质量打印时也可靠。

## 为什么使用字节编码模式？
字节模式允许您嵌入原始二进制数据（最多 1,555 字节），无需转换为文本，非常适合序列号、GUID 或加密负载。Aspose.BarCode 支持 **30+ 条码符号**，并且能够在不将整个文件加载到内存中的情况下处理 **数百页文档**，确保在高吞吐场景下的快速性能。

## 前提条件

在我们深入编码过程之前，您需要准备以下前提条件：

1. Aspose.BarCode for .NET：要开始使用，您必须安装 Aspose.BarCode for .NET 库。您可以从 [here](https://releases.aspose.com/barcode/net/) 下载。您也可以在 [here](https://releases.aspose.com/) 找到其他 Aspose 产品。
2. 开发环境：确保已设置开发环境，包括 Visual Studio 或您选择的其他 IDE。
3. C# 基础知识：本教程假设您具备 C# 编程的基本了解。

如需帮助，请访问 [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13)。

有了这些前提条件，您即可开始使用字节模式对 DataMatrix 格式进行数据编码。

## 导入命名空间

要使用 Aspose.BarCode for .NET，请在 C# 文件顶部导入所需的命名空间：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

现在环境已准备就绪，让我们逐步演示**生成 DataMatrix 条码**并随后读取的确切步骤。

## 如何在字节模式下生成 DataMatrix 条码？

加载 `BarcodeGenerator`，将编码模式设置为 Bytes，配置可选的显示文本，保存图像，最后使用 `BarCodeReader` 验证结果——全部六个简洁步骤。此方法确保生成符合 ISO/IEC 16022 标准的可靠条码。

### 步骤 1：初始化 BarcodeGenerator

`BarcodeGenerator` 是用于为给定符号和数据生成条码图像的主要类。

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### 步骤 2：将 DataMatrix 编码模式设置为 Bytes

`DataMatrixEncodeMode.Bytes` 告诉生成器将输入视为原始二进制字节而不是文本。

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### 步骤 3：设置显示文本

`CodeText` 属性设置条码符号下方显示的可读文本。

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### 步骤 4：保存条码图像

`Save` 方法将生成的条码写入指定格式的图像文件。

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### 步骤 5：尝试识别

`BarCodeReader` 读取条码图像并提取编码数据。

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### 步骤 6：遍历并显示结果

遍历 `reader.ReadBarCodes()` 以访问每个检测到的条码及其 `CodeText`。

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

通过这些步骤，您已成功在字节模式下**生成 DataMatrix 条码**并使用 Aspose.BarCode for .NET 验证。该库抽象了底层编码细节，使您能够专注于业务逻辑，而无需关注条码数学。

## 常见问题及解决方案

- **编码数据被截断** – 确保字节数组不超过 1,555 字节；否则库会自动切换到更大的符号尺寸或抛出异常。
- **图像模糊** – 在调用 `Save` 前通过设置 `generator.Parameters.ImageResolution` 将图像保存为更高分辨率（例如 300 dpi）。
- **读取器返回 null** – 验证图像路径是否正确且文件未损坏；还要确认 `BarCodeReader` 使用 `DecodeType.DataMatrix` 实例化。

## 常见问答

**Q: 什么是 DataMatrix 编码模式？**  
A: DataMatrix 编码模式定义了输入数据如何转换为二维图案；字节模式直接存储原始二进制字节。

**Q: 如何获取 Aspose.BarCode for .NET 的免费试用？**  
A: 您可以从 [here](https://releases.aspose.com/) 获取 Aspose.BarCode for .NET 的免费试用。

**Q: 在哪里可以找到 Aspose.BarCode for .NET 的文档？**  
A: Aspose.BarCode for .NET 的文档可在 [here](https://reference.aspose.com/barcode/net/) 获取。

**Q: Aspose.BarCode for .NET 适合商业使用吗？**  
A: 是的，Aspose.BarCode for .NET 适用于商业使用。您可以从 [here](https://purchase.aspose.com/buy) 购买许可证。

**Q: 我可以为 Aspose.BarCode for .NET 使用临时许可证吗？**  
A: 可以，您可以从 [here](https://purchase.aspose.com/temporary-license/) 获取 Aspose.BarCode for .NET 的临时许可证。

---

**最后更新：** 2026-05-30  
**测试版本：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.BarCode for .NET 的 ASCII 编码 Master DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [读取 DataMatrix 条码 C# – 生成 DataMatrix 模式（自动）](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}