---
date: 2026-01-15
description: 学习如何在使用 Aspose.BarCode for .NET 的 DataMatrix 编码模式（C40）时保存 PNG 文件——一步一步的条码教程。
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode 将 DataMatrix C40 保存为 PNG
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix 主编码模式 (C40) 与 Aspose.BarCode for .NET

## Introduction

如果您正在寻找一份关于在生成 DataMatrix 条码时 **how to save png** 文件的清晰实用指南，您来对地方了。无论您是在构建库存系统、运单标签生成器，还是任何需要紧凑高密度条码的解决方案，掌握 C40 编码模式都能为您提供尺寸效率和可靠的数据表示。在本教程中，我们将使用 Aspose.BarCode for .NET，逐步演示 **step by step barcode** 的创建过程，从前置条件到最终的 PNG 输出。

## Quick Answers
- **What does “how to save png” refer to?** Saving the generated barcode as a PNG image file.  
- **Which encoding mode is covered?** DataMatrix C40 encoding.  
- **Do I need a license?** A free trial works for testing; a license is required for production.  
- **Can I run this on .NET Core?** Yes, Aspose.BarCode supports .NET Framework and .NET Core.  
- **What file format is produced?** PNG (Portable Network Graphics) image.

## How to Save PNG with DataMatrix C40 Encoding
将条码保存为 PNG 是在完成生成器配置后的最后一步。`Save` 方法接受文件路径、期望的文件名以及图像格式（`BarCodeImageFormat.Png`），从而确保条码以无损格式存储，能够在浏览器、打印机和移动设备上正常使用。

## What is DataMatrix Encoding Mode (C40)?
C40 是一种针对字母数字数据的高效字符集，能够在更小的 DataMatrix 符号中容纳更多信息。当需要编码包含字母、数字以及有限特殊字符的文本时，C40 特别有用。

## Why Use Aspose.BarCode for .NET?
- **Full control** over barcode dimensions, error correction, and encoding modes.  
- **Zero‑dependency** generation – no external services required.  
- **Cross‑platform** support for .NET Framework, .NET Core, and .NET 5/6+.  

## Prerequisites

在深入代码之前，请确保您具备以下条件：

1. **.NET Development Environment** – Visual Studio、Rider 或任何支持 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 通过 NuGet 或官方安装程序安装。详情请参阅 [documentation](https://reference.aspose.com/barcode/net/)。  
3. **Basic C# knowledge** – 您应熟悉命名空间、类以及 using 语句。  
4. **Write‑access folder** – 您机器上用于保存 PNG 的目录。

## Importing Necessary Namespaces

在 C# 源文件的顶部添加所需的命名空间，以便访问条码生成类：

```csharp
using Aspose.BarCode.Generation;
```

## Step-by-Step Barcode Generation

下面是一个 **step by step barcode** 演练。每一步都以通俗的语言说明，原始代码块保持不变，便于复制粘贴。

### Step 1: Define the Directory Path
设置 PNG 图像将要存放的文件夹。将占位符替换为您机器上的实际路径。

```csharp
string path = "Your Directory Path";
```

### Step 2: Set Up Barcode Generation
创建 `BarcodeGenerator` 实例，指定 `EncodeTypes.DataMatrix`，并提供要编码的数据。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Step 3: Customize Barcode
配置 X‑dimension（模块的像素宽度），并将编码模式切换为 C40。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Step 4: Save the Barcode Image
最后，将生成的条码保存为 PNG 文件。这就是使用 Aspose.BarCode **how to save png** 的具体答案。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

运行程序后，您将在指定的文件夹中找到 `DataMatrixEncodeModeC40.png`，可用于报表、标签或网页。

## Common Issues & Tips

- **Invalid Path** – 确保目录存在且您拥有写入权限；否则 `gen.Save` 将抛出异常。  
- **Incorrect Encoding Mode** – 如果需要编码超出 C40 集合的字符，请切换到 `DataMatrixEncodeMode.Auto` 或其他合适的模式。  
- **Image Size** – 调整 `XDimension.Pixels` 可在不影响可读性的前提下增大或缩小条码整体尺寸。

## Frequently Asked Questions

**Q: What is DataMatrix Encoding Mode (C40)?**  
A: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols, ideal for text that includes letters, numbers, and a limited set of special characters.

**Q: Where can I find the Aspose.BarCode for .NET documentation?**  
A: You can find the documentation [here](https://reference.aspose.com/barcode/net/). It provides detailed guidance on all barcode types and encoding options.

**Q: Is Aspose.BarCode for .NET compatible with all .NET versions?**  
A: Yes, the library supports a wide range of .NET versions, from .NET Framework 4.5+ to .NET 6 and later.

**Q: Can I try Aspose.BarCode for .NET before purchasing?**  
A: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting [this link](https://releases.aspose.com/). It allows you to test the library’s features and capabilities.

**Q: Where can I get support for Aspose.BarCode for .NET?**  
A: You can find a supportive community and access support for Aspose.BarCode for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Conclusion

通过遵循本 **step by step barcode** 指南，您现在已经掌握了使用 Aspose.BarCode for .NET 生成 DataMatrix C40 编码并 **how to save png** 文件的完整流程。此方法让您对条码的外观、尺寸和数据表示拥有完全控制，轻松将高质量条码集成到任何 .NET 应用程序中。

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}