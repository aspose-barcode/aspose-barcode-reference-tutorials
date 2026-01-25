---
date: 2026-01-25
description: 了解如何使用 Aspose.BarCode for .NET 通过字节模式编码 DataMatrix 来创建条形码 PNG 文件。请遵循本条形码生成指南，以便轻松实现。
linktitle: DataMatrix Encoding Mode (Bytes)
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 创建条码 PNG – DataMatrix 字节
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建条形码 PNG – 使用 Aspose.BarCode for .NET 的字节模式 DataMatrix 编码

在本教程中，您将学习 **如何使用 Aspose.BarCode for .NET 创建条将完整演示 **DataMatrix 条形码生成 DataMatrix 条形码。

## 快速回答
免费商业许可证。  
- **可以读取生成的条形码吗？** 可以，库自带的 BarCodeReader 能 **读取 DataMatrix 条形码** 数据。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 使用 Aspose.BarCode for .NET 创建条形码 PNG 的步骤
下面提供从前置条件到逐步代码演示的全部内容，帮助您 **生成 PNG 条形码**、设置显示文本，并使用内置读取器验证结果。

## 前置条件

在开始编码之前，您需要准备以下条件：

1. **Aspose.BarCode for .NET**：首先必须安装 Aspose.BarCode for .NET 库，可从 [here](https://releases.aspose.com/barcode/net/) 下载。  
2. **开发环境**：确保已搭建好开发环境，如 Visual Studio 或其他您喜欢的 IDE。  
3. **C# 基础**：本教程假设您具备基本的 C# 编程知识。

满足上述前置条件后，即可使用 Bytes 模式在 DataMatrix 格式中进行数据编码。

## 导入命名空间

使用 Aspose.BarCode for .NET 前，需要在 C# 代码中导入相应的命名空间。将以下代码添加到文件顶部：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

接下来，我们将把 DataMatrix Bytes 模式的编码过程拆分为多个步骤进行说明。

## 步骤 1：初始化 BarcodeGenerator

创建一个 BarcodeGenerator 对象，指定 EncodeType 为 DataMatrix，并传入要编码的数据。您可以将 `"Your Directory Path"` 替换为实际的保存条形码图像的路径。

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## 步骤 2：将 DataMatrix 编码模式设为 Bytes

使用以下代码将 DataMatrix 编码模式设置为 Bytes：

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

## 步骤 3：设置显示文本

您可以为条形码设置显示文本。本例中，我们将其设为 “Bytes mode”。

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

## 步骤 4：保存条形码图像

将生成的条形码图像保存到指定路径。本例中保存为 “DataMatrixEncodeModeBytes.png”。

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

## 步骤 5：尝试识别

现在，使用 BarCodeReader 对已编码的 DataMatrix 条形码进行识别。

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

## 步骤 6：遍历并显示结果

遍历识别结果并显示编码后的数据。

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

通过以上步骤，您已成功 **使用 Aspose.BarCode for .NET 在 DataMatrix Bytes 模式下创建条形码 PNG**。该强大库简化了条形码的生成与识别，是开发者不可或缺的工具。

现在，您可以轻松将条形码的编码与解码功能集成到 .NET 应用程序中，尽情发挥 Aspose.BarCode 的优势。

## 结论

本教程展示了如何使用 Aspose.BarCode for .NET **在 DataMatrix 格式的 Bytes 模式下创建条形码 PNG** 文件。按照这些简明步骤，您即可为应用程序添加强大的条形码生成与识别能力。如遇问题，Aspose.BarCode 社区随时为您提供帮助。

如有任何疑问或遇到问题，请前往 [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13) 寻求帮助。

## 常见问题

### Q1: 什么是 DataMatrix 编码模式？

A1: DataMatrix 编码模式是一种将数据编码为二维条形码的方式，提供多种编码选项，其中 Bytes 模式适用于二进制数据的编码。

### Q2: 如何获取 Aspose.BarCode for .NET 的免费试用？

A2: 您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

### Q3: 哪里可以找到 Aspose.BarCode for .NET 的文档？

A3: 文档可在 [here](https://reference.aspose.com/barcode/net/) 查看。

### Q4: Aspose.BarCode for .NET 可以用于商业项目吗？

A4: 可以，您可以在 [here](https://purchase.aspose.com/buy) 购买商业许可证。

### Q5: 是否可以获取 Aspose.BarCode for .NET 的临时许可证？

A5: 可以，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 获取。

## Frequently Asked Questions

**Q: 创建条形码后，如何 **读取 DataMatrix 条形码**？**  
A: 如步骤 5 与步骤 6 所示，使用 `BarCodeReader` 并将 `DecodeType.DataMatrix` 作为参数即可。

**Q: 能否更改生成 PNG 的尺寸？**  
A: 可以，在调用 `Save` 之前调整 `gen.Parameters.Barcode.XDimension.Pixels` 或设置 `ImageWidth`、`ImageHeight` 参数。

**Q: 如果想编码文本而不是字节，该怎么办？**  
A: 将编码模式切换为 `DataMatrixEncodeMode.Text`，并提供要编码的字符串。

**Q: 如何隐藏条形码上的可读文本？**  
A: 设置 `gen.Parameters.Barcode.CodeTextParameters.ShowCodeText = false` 即可隐藏显示文本。

**Q: Aspose.BarCode 是否支持 .NET Core？**  
A: 完全支持——库兼容 .-01-25  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}