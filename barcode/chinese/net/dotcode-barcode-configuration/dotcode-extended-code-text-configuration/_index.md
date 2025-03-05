---
title: 使用 Aspose.BarCode for .NET 进行 DotCode 扩展代码文本配置
linktitle: DotCode 扩展代码文本配置
second_title: Aspose.BarCode .NET API
description: 使用 Aspose.BarCode for .NET 轻松生成 DotCode 扩展代码文本配置。请按照我们的分步指南进行高效的条形码创建。
type: docs
weight: 13
url: /zh/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
---
## 介绍

在条形码生成和管理领域，Aspose.BarCode for .NET 是一种多功能且高效的解决方案。无论您需要为产品、库存还是任何其他应用程序生成条形码，Aspose.BarCode for .NET 都能满足您的需求。在这个综合教程中，我们将重点关注使用 Aspose.BarCode for .NET 生成 DotCode 扩展代码文本配置。 DotCode 是一种二维矩阵条形码，可以对文本和二进制数据进行编码，使其成为各个行业的宝贵工具。

## 先决条件

在我们深入研究分步指南之前，您需要满足一些先决条件才能有效地遵循：

1.  Aspose.BarCode for .NET：确保您已安装并准备好 Aspose.BarCode for .NET 库。如果没有，您可以从以下位置下载[Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/).

2. 开发环境：您的系统上应该安装一个可用的 .NET 开发环境，最好是 Visual Studio。

按顺序满足这些先决条件后，我们现在可以继续生成 DotCode 扩展代码文本配置。

## 导入命名空间

首先，您需要将必要的命名空间导入到 .NET 项目中，以从 Aspose.BarCode 库访问所需的功能。您可以按照以下方法执行此操作：


```csharp
using Aspose.BarCode.Generation;
```

现在我们已经满足了先决条件，让我们将生成 DotCode 扩展代码文本配置的过程分解为分步指南。



## 第 1 步：定义目录路径

在此步骤中，您需要指定要保存生成的DotCode扩展代码文本图像的目录路径。

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`与系统上的实际路径。

## 第2步：创建DotCode扩展代码文本

要创建 DotCode 扩展代码文本，请执行以下子步骤：

### 2.1 添加FNC1格式标识符

FNC1 格式标识符用于指示新数据字段的开始。它是 DotCode 扩展代码文本的重要组成部分。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 添加ECI代码文本

ECICodetext 是您可以对特殊字符和国际文本进行编码的地方。在此示例中，我们使用 UTF-8 编码对“犬右狗”进行编码。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 添加纯代码文本

您还可以将纯文本添加到 DotCode 扩展代码文本中。在这里，我们添加了“纯文本”。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 添加FNC3符号分隔符

FNC3 符号分隔符用于分隔代码的不同部分。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 添加FNC3读卡器初始化

此步骤添加 FNC3 Reader 初始化信息。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 生成代码文本

现在，通过调用生成 DotCode 扩展代码文本`GetExtendedCodetext`方法上的`textBuilder`目的。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 第3步：生成DotCode图像

要将 DotCode 扩展代码文本生成为图像，请执行以下子步骤：

#### 4.1 初始化条码生成器

初始化`BarcodeGenerator`具有适当的参数。在这种情况下，我们使用`EncodeTypes.DotCode`和生成的代码文本。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    //设置条形码的 X 尺寸（根据需要调整）。
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    //将 DotCode 编码模式设置为 ExtendedCodetext。
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    //保存生成的条形码图像。
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

就是这样！您已使用 Aspose.BarCode for .NET 成功生成了 DotCode 扩展代码文本。

## 结论

Aspose.BarCode for .NET 是一个功能强大的工具，可以简化条形码生成。在本教程中，我们重点关注生成 DotCode 扩展代码文本，这在各个行业中都至关重要，特别是在需要多语言和专门字符编码的情况下。通过执行上述步骤，您可以轻松创建满足您特定需求的 DotCode 扩展代码文本。

如果您需要进一步指导或有疑问，请随时访问[Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)或与社区互动[Aspose.BarCode 支持论坛](https://forum.aspose.com/c/barcode/13).

## 常见问题解答

### Q1：DotCode有什么用？

A1：DotCode 用于编码文本和二进制数据，通常应用于医疗保健和物流等行业，用于跟踪和数据编码目的。

### Q2：我可以自定义DotCode条码的外观吗？

A2：是的，Aspose.BarCode for .NET 提供了自定义 DotCode 条形码外观的选项，包括大小和编码模式。

### Q3：Aspose.BarCode for .NET 与各种.NET 框架兼容吗？

A3：是的，Aspose.BarCode for .NET 与广泛的 .NET 框架兼容，确保灵活性和易于集成。

### Q4：如何获得 Aspose.BarCode for .NET 的临时许可证？

 A4：您可以从以下地点获得临时许可证：[阿斯普斯的网站](https://purchase.aspose.com/temporary-license/)用于评估和测试目的。

### Q5：Aspose.BarCode for .NET适合企业级条码生成吗？

A5：当然，Aspose.BarCode for .NET 旨在满足小规模和企业级条码生成的需求，提供可扩展性和可靠性。