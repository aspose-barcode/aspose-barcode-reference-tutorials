---
title: 使用 Aspose.BarCode for .NET 掌握 Aztec 符号模式
linktitle: 阿兹特克符号模式示例
second_title: Aspose.BarCode .NET API
description: 探索 Aspose.BarCode for .NET 中的 Aztec 符号模式，并了解如何轻松生成通用条形码。在这个综合教程中亲身体验自动、全范围、紧凑和符文模式。
type: docs
weight: 14
url: /zh/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---
如果您希望将强大的条形码生成功能合并到您的 .NET 应用程序中，Aspose.BarCode for .NET 是一个绝佳的解决方案。在本教程中，我们将深入研究 Aztec 符号模式，并使用 Aspose.BarCode for .NET 探索其各种选项。我们将介绍先决条件、导入命名空间，并将每个示例分解为多个步骤来指导您完成整个过程。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

- .NET 开发的实用知识。
- Visual Studio 安装在您的计算机上。
-  .NET 的 Aspose.BarCode 副本。你可以下载它[这里](https://releases.aspose.com/barcode/net/).

现在您已准备就绪，让我们深入研究 Aztec 符号模式示例。

## 导入命名空间

首先，您需要导入必要的命名空间才能使用 Aspose.BarCode for .NET。打开 Visual Studio 项目并在代码文件顶部添加以下 using 语句：

```csharp
using Aspose.BarCode.Generation;
```

命名空间就位后，您现在可以开始使用 Aspose.BarCode for .NET。

## 第 1 步：设置条码生成器

首先使用 Aztec 编码类型初始化条形码生成器并提供代码文本。操作方法如下：

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

在这一步中，我们设置了生成器并提供了用于编码的代码文本。

## 步骤 2：将符号模式设置为自动

现在，让我们将 Aztec 符号模式设置为“自动”并将条形码图像保存为 PNG 文件。您可以这样做：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

此步骤确保自动确定 Aztec 符号模式，并保存生成的条形码图像。

## 步骤 3：将符号模式设置为 FullRange

如果要将 Aztec 符号模式指定为“FullRange”，可以使用以下代码来执行此操作：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

这将创建具有 FullRange Aztec 符号模式的条形码。

## 步骤 4：将符号模式设置为紧凑

要创建将 Aztec 符号模式设置为“紧凑”的条形码，请使用以下代码：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

此步骤配置要使用紧凑 Aztec 符号模式生成的条形码。

## 第5步：将符号模式设置为符文

最后，如果您想使用“符文”阿兹特克符号模式，您可以通过如下设置来实现：

```csharp
gen.CodeText = "123"; //如果需要，更改代码文本
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

此步骤将代码文本更改为“123”并生成具有 Rune Aztec 符号模式的条形码。

## 结论

在本教程中，我们探索了 Aspose.BarCode for .NET 中的 Aztec 符号模式。我们介绍了设置条形码生成器、将 Aztec 符号模式配置为自动、全范围、紧凑和符文，以及保存生成的条形码图像。有了这些知识，您现在可以轻松地将多功能条形码生成集成到您的 .NET 应用程序中。

如果您有任何疑问或需要进一步帮助，请随时联系 Aspose.BarCode 社区[支持论坛](https://forum.aspose.com/c/barcode/13).

## 常见问题解答

### Q1：Aztec Symbol Mode 在条码生成中的用途是什么？

A1：Aztec 符号模式允许您指定 Aztec 条形码的编码方法，为条形码生成提供灵活性。

### Q2：我可以在 Aspose.BarCode for .NET 中更改 Aztec 条形码的代码文本吗？

A2: 是的，您在生成 Aztec 条码时可以根据您的具体要求轻松更改代码文本。

### Q3：Aspose.BarCode for .NET 有免费试用版吗？

A3：是的，您可以下载 Aspose.BarCode for .NET 的免费试用版[这里](https://releases.aspose.com/).

### Q4：在哪里可以找到 Aspose.BarCode for .NET 的完整文档？

 A4：您可以参考Aspose.BarCode for .NET的完整文档[这里](https://reference.aspose.com/barcode/net/).

### Q5：如何获得 Aspose.BarCode for .NET 的临时许可证？

 A5：您可以通过访问获取 Aspose.BarCode for .NET 的临时许可证[这个链接](https://purchase.aspose.com/temporary-license/).