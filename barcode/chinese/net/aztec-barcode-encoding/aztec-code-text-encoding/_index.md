---
date: 2026-01-02
description: 学习如何使用 Aspose.BarCode for .NET 创建 Aztec 条码并识别它。本指南涵盖在 .NET 应用中对 Aztec
  条码的编码、保存和读取。
linktitle: Aztec Code Text Encoding
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 创建 Aztec 码
url: /zh/net/aztec-barcode-encoding/aztec-code-text-encoding/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 进行 Aztec Code 文本编码

## 介绍

准备好深入探索使用 Aspose.BarCode for .NET **创建 Aztec 码** 的精彩世界了吗？在本完整指南中，我们将手把手教您 **创建 Aztec 码**、对自定义文本进行编码、保存图像并再次读取。阅读完本教程，您不仅能掌握技术步骤，还能了解为何这种格式是现代应用中紧凑数据存储的理想选择。让我们开始吧！

## 快速答案
- **本教程教什么？** 如何在 .NET 中创建、保存并识别带文本编码的 Aztec 码。  
- **需要哪个库？** Aspose.BarCode for .NET。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境需商业许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **实现需要多长时间？** 基础示例约 10‑15 分钟即可完成。

## 什么是 Aztec Code？
Aztec Code 是一种二维条码，可在紧凑的方形图案中存储大量数据。与 QR 码不同，它不需要周围的“安静区”，因此非常适合空间受限的设计。

## 为什么使用 Aspose.BarCode for .NET 来创建 Aztec Code？
- **完整控制** 编码选项（字符集、纠错级别、尺寸）。  
- **强大识别** 引擎，可从图像、流或摄像头读取 Aztec 码。  
- **跨平台** 支持 .NET Framework、.NET Core 和 .NET 5/6。  
- **无需外部依赖** —— 所有功能均在托管代码中运行。

## 前置条件

在开始这段激动人心的旅程之前，您需要准备以下前置条件：

1. Aspose.BarCode for .NET：确保已安装此强大库。文档请参阅 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/)。  
2. Visual Studio：请在系统上安装 Visual Studio，以创建和运行 .NET 应用。  
3. C# 基础知识：熟悉 C# 编程会更有帮助，尽管我们会提供详细说明，确保所有人都能跟上。

现在我们已经介绍完前置条件，接下来进入 Aztec Code 文本编码的具体步骤。

## 导入命名空间

首先，需要在 C# 应用的 `.cs` 文件顶部导入使用 Aspose.BarCode for .NET 所必需的命名空间。添加以下代码：

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## 使用 Aspose.BarCode for .NET 创建 Aztec Code 的步骤

### 步骤 1：定义目录路径

设置保存生成的 Aztec Code 图像的路径。将 `"Your Directory Path"` 替换为您希望的目录路径。

```csharp
string path = "Your Directory Path";
```

### 步骤 2：初始化 Aztec Code 生成器

创建 `BarcodeGenerator` 实例，将 `EncodeTypes` 设置为 Aztec，并指定要编码的文本。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Aspose常に先を行く");
```

### 步骤 3：设置条码参数

配置条码参数。本示例中，我们将像素单位的 XDimension 设置，并将代码文本编码设为 UTF‑8。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.Aztec.CodeTextEncoding = Encoding.UTF8;
```

### 步骤 4：保存 Aztec Code 图像

将生成的 Aztec Code 图像保存到指定目录。

```csharp
gen.Save($"{path}AztecCodeTextEncoding.png", BarCodeImageFormat.Png);
```

### 步骤 5：识别 Aztec Code

尝试识别刚刚创建的 Aztec Code。我们使用 `BarCodeReader` 完成此操作。

```csharp
BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.Aztec);
foreach (BarCodeResult result in read.ReadBarCodes())
    Console.WriteLine("AztecCodeTextEncoding:" + result.GetCodeText(Encoding.UTF8));
```

## 常见陷阱与技巧

- **文件路径问题** —— 确保 `path` 变量以适合您操作系统的目录分隔符（`\` 或 `/`）结尾。  
- **编码不匹配** —— 始终将 `CodeTextEncoding` 设置为与源文本字符集相同，否则可能出现乱码。  
- **许可证异常** —— 未使用有效许可证时，生成的图像可能会带有水印。  

## 常见问答

### Q1：什么是 Aztec Code？

A1：Aztec Code 是一种二维条码格式，可编码多种数据类型，包括文本、URL 等。

### Q2：为什么要使用 Aspose.BarCode for .NET？

A2：Aspose.BarCode for .NET 是一款强大的库，简化了在 .NET 应用中创建和识别条码的过程，为您节省时间和精力。

### Q3：我可以使用 Aspose.BarCode for .NET 自定义 Aztec Code 的外观吗？

A3：可以，您可以自定义 Aztec Code 的大小、颜色以及编码选项等多个方面，以满足需求。

### Q4：Aspose.BarCode for .NET 有免费试用吗？

A4：有，您可以访问 [here](https://releases.aspose.com/) 进行免费试用。

### Q5：在哪里可以获取 Aspose.BarCode for .NET 的支持或提问？

A5：您可以加入 Aspose.BarCode for .NET 社区，在支持论坛 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) 提问并分享经验。

### Q6：我可以从流而不是文件读取 Aztec Code 吗？

A6：完全可以。`BarCodeReader` 同样接受 `Stream` 对象，支持从内存、网络或数据库 BLOB 中读取。

### Q7：如何更改 Aztec Code 的纠错级别？

A7：使用 `gen.Parameters.Barcode.Aztec.ErrorCorrection` 设置所需级别（例如 `ErrorCorrectionLevel.L`、`M`、`Q`、`H`）。

## 结论

在本教程中，我们深入探讨了使用 Aspose.BarCode for .NET 进行 **Aztec Code 文本编码** 的精彩内容。我们覆盖了前置条件、导入必要的命名空间，并逐步演示了 **创建 Aztec Code**、自定义外观、保存为图像以及再次识别的完整流程。现在，您已经具备将 Aztec Code 集成到 .NET 应用中的坚实基础，可用于库存追踪、数据安全传输等各种场景。

欢迎访问 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 获取更多深入信息和高级功能。祝编码愉快！

---

**最后更新：** 2026-01-02  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}