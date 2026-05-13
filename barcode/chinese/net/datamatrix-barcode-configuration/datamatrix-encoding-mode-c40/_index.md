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

## 简介

如果您正在寻找一份关于在生成 DataMatrix 条码时 **how to save png** 文件的清晰实用指南，您来对地方了。无论您是在构建库存系统、运单标签生成器，还是任何需要紧凑高密度条码的解决方案，掌握 C40 编码模式都能为您提供尺寸效率和可靠的数据表示。在本教程中，我们将使用 Aspose.BarCode for .NET，逐步演示 **step by step barcode** 的创建过程，从前置条件到最终的 PNG 输出。

## 快速解答

- **“如何保存 PNG”指的是什么？** 将生成的条形码保存为 PNG 图像文件。
- **支持哪种编码模式？** DataMatrix C40 编码。
- **需要许可证吗？** 免费试用版可用于测试；生产环境需要许可证。
- **可以在 .NET Core 上运行吗？** 可以，Aspose.BarCode 支持 .NET Framework 和 .NET Core。
- **生成的文件格式是什么？** PNG（便携式网络图形）图像。

## 如何使用 DataMatrix C40 编码保存 PNG
将条码保存为 PNG 是在完成生成器配置后的最后一步。`Save` 方法接受文件路径、期望的文件名以及图像格式（`BarCodeImageFormat.Png`），从而确保条码以无损格式存储，能够在浏览器、打印机和移动设备上正常使用。

## 什么是 DataMatrix 编码模式 (C40)？
C40 是一种针对字母数字数据的高效字符集，能够在更小的 DataMatrix 符号中容纳更多信息。当需要编码包含字母、数字以及有限特殊字符的文本时，C40 特别有用。

## 为什么选择 Aspose.BarCode for .NET？

- **完全控制** 条形码尺寸、纠错和编码模式。
- **零依赖**生成 – 无需外部服务。 - **跨平台**支持 .NET Framework、.NET Core 和 .NET 5/6+。

## 先决条件

在深入代码之前，请确保您具备以下条件：

1. **.NET Development Environment** – Visual Studio、Rider 或任何支持 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 通过 NuGet 或官方安装程序安装。详情请参阅 [documentation](https://reference.aspose.com/barcode/net/)。  
3. **Basic C# knowledge** – 您应熟悉命名空间、类以及 using 语句。  
4. **Write‑access folder** – 您机器上用于保存 PNG 的目录。

## 导入必要的命名空间

在 C# 源文件的顶部添加所需的命名空间，以便访问条码生成类：

```csharp
using Aspose.BarCode.Generation;
```

## 条形码生成分步指南

下面是一个 **step by step barcode** 演练。每一步都以通俗的语言说明，原始代码块保持不变，便于复制粘贴。

### 步骤 1：定义目录路径
设置 PNG 图像将要存放的文件夹。将占位符替换为您机器上的实际路径。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：设置条形码生成
创建 `BarcodeGenerator` 实例，指定 `EncodeTypes.DataMatrix`，并提供要编码的数据。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 步骤 3：自定义条形码
配置 X‑dimension（模块的像素宽度），并将编码模式切换为 C40。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 步骤 4：保存条形码图像
最后，将生成的条码保存为 PNG 文件。这就是使用 Aspose.BarCode **how to save png** 的具体答案。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

运行程序后，您将在指定的文件夹中找到 `DataMatrixEncodeModeC40.png`，可用于报表、标签或网页。

## 常见问题及提示

- **Invalid Path** – 确保目录存在且您拥有写入权限；否则 `gen.Save` 将抛出异常。  
- **Incorrect Encoding Mode** – 如果需要编码超出 C40 集合的字符，请切换到 `DataMatrixEncodeMode.Auto` 或其他合适的模式。  
- **Image Size** – 调整 `XDimension.Pixels` 可在不影响可读性的前提下增大或缩小条码整体尺寸。

## 常见问题解答

**问：什么是 DataMatrix 编码模式 (C40)？** 

答：C40 是一种紧凑的字母数字编码方案，适用于 DataMatrix 符号，非常适合包含字母、数字和少量特殊字符的文本。

**问：在哪里可以找到 Aspose.BarCode for .NET 的文档？** 

答：您可以在[此处](https://reference.aspose.com/barcode/net/)找到文档。它提供了所有条形码类型和编码选项的详细指南。

**问：Aspose.BarCode for .NET 是否兼容所有 .NET 版本？** 

答：是的，该库支持从 .NET Framework 4.5+ 到 .NET 6 及更高版本的各种 .NET 版本。

**问：购买前我可以试用 Aspose.BarCode for .NET 吗？** 

答：可以，您可以访问[此链接](https://releases.aspose.com/)免费试用 Aspose.BarCode for .NET。试用版允许您测试该库的功能和特性。

**问：我可以在哪里获得 Aspose.BarCode for .NET 的支持？** 

答：您可以在[Aspose 论坛](https://forum.aspose.com/c/barcode/13)找到支持社区并获得 Aspose.BarCode for .NET 的支持。

## 总结

通过遵循本 **step by step barcode** 指南，您现在已经掌握了使用 Aspose.BarCode for .NET 生成 DataMatrix C40 编码并 **how to save png** 文件的完整流程。此方法让您对条码的外观、尺寸和数据表示拥有完全控制，轻松将高质量条码集成到任何 .NET 应用程序中。

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}