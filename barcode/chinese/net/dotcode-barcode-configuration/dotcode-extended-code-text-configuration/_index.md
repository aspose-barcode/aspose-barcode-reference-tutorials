---
date: 2026-01-27
description: 学习如何使用 Aspose.BarCode for .NET 创建 DotCode 扩展代码文本——一步步生成带有扩展代码文本的 DotCode
  条码指南。
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 创建 DotCode 扩展码文本
url: /zh/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 创建 DotCode 扩展代码文本

## 介绍

在条码生成和管理领域，Aspose.BarCode for .NET 以其多功能和高效性脱颖而出。无论您需要为产品、库存或其他任何应用生成条码，Aspose.BarCode for .NET 都能满足需求。在本综合教程中，我们将 **创建 DotCode 扩展代码文本**，并探讨为何此功能在现代数据丰富的环境中至关重要。DotCode 是一种二维矩阵条码，能够编码文本和二进制数据，是各行业的有价值工具。

## 快速回答
- **“创建 DotCode 扩展代码文本” 是什么意思？** 这意味着构建一个包含 FNC1、ECICodetext、普通文本和符号分隔符的单一扩展负载的 DotCode 条码。  
- **需要哪个库？** Aspose.BarCode for .NET。  
- **需要许可证吗？** 临时许可证可用于评估；生产环境需要正式许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7+。  
- **实现需要多长时间？** 基本示例约 10‑15 分钟。

## 如何创建 DotCode 扩展代码文本

下面提供一个简洁的逐步演练，展示如何构建扩展代码文本并渲染条码图像。

## 先决条件

在深入逐步指南之前，您需要准备以下前置条件：

1. Aspose.BarCode for .NET：确保已安装 Aspose.BarCode for .NET 库并准备就绪。若未安装，可从 [Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/) 下载。

2. 开发环境：建议在系统上安装 Visual Studio 等可用的 .NET 开发环境。

有了这些前置条件，即可继续生成 DotCode 扩展代码文本。

## 导入命名空间

首先，需要在 .NET 项目中导入必要的命名空间，以访问 Aspose.BarCode 库提供的功能。操作如下：

```csharp
using Aspose.BarCode.Generation;
```

现在我们已经完成前置工作，下面将把生成 DotCode 扩展代码文本的过程拆解为逐步指南。

## 步骤 1：定义目录路径

此步骤需要指定保存生成的 DotCode 扩展代码文本图像的目录路径。

```csharp
string path = "Your Directory Path";
```

将 `"Your Directory Path"` 替换为您系统中的实际路径。

## 步骤 2：创建 DotCode 扩展代码文本

要创建 DotCode 扩展代码文本，请按以下子步骤操作：

### 2.1 添加 FNC1 格式标识符

FNC1 格式标识符用于指示新数据字段的开始，是 DotCode 扩展代码文本的关键部分。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 添加 ECICodetext

ECICodetext 用于编码特殊字符和国际文本。本示例中，我们使用 UTF‑8 编码对 `"犬Right狗"` 进行编码。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 添加普通代码文本

您也可以向 DotCode 扩展代码文本中添加普通文本。本例中添加了 `"Plain text"`。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 添加 FNC3 符号分隔符

FNC3 符号分隔符用于分隔代码的不同部分。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 添加 FNC3 读取器初始化

此步骤添加 FNC3 读取器初始化信息。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 生成代码文本

现在，通过调用 `textBuilder` 对象的 `GetExtendedCodetext` 方法生成 DotCode 扩展代码文本。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 步骤 3：生成 DotCode 图像

要将 DotCode 扩展代码文本生成为图像，请按以下子步骤操作：

#### 4.1 初始化条码生成器

使用适当的参数初始化 `BarcodeGenerator`。本例中使用 `EncodeTypes.DotCode` 和生成的代码文本。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

就这样！您已成功使用 Aspose.BarCode for .NET 生成 DotCode 扩展代码文本。

## 结论

Aspose.BarCode for .NET 是简化条码生成的强大工具。本教程重点介绍了 **创建 DotCode 扩展代码文本**，该功能在需要多语言和特殊字符编码的各行业中尤为重要。按照上述步骤，您即可轻松为特定需求创建 DotCode 扩展代码文本。

如需进一步指导或有任何疑问，请访问 [Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/) 或在 [Aspose.BarCode 支持论坛](https://forum.aspose.com/c/barcode/13) 与社区交流。

## 常见问题

### Q1: DotCode 用途是什么？

A1: DotCode 用于编码文本和二进制数据，常用于医疗、物流等行业的追踪和数据编码。

### Q2: 我可以自定义 DotCode 条码的外观吗？

A2: 可以，Aspose.BarCode for .NET 提供了自定义 DotCode 条码外观的选项，包括尺寸和编码模式。

### Q3: Aspose.BarCode for .NET 是否兼容各种 .NET 框架？

A3: 兼容，Aspose.BarCode for .NET 支持广泛的 .NET 框架，确保灵活性和易于集成。

### Q4: 如何获取 Aspose.BarCode for .NET 的临时许可证？

A4: 您可以从 [Aspose 的网站](https://purchase.aspose.com/temporary-license/) 获取临时许可证，用于评估和测试。

### Q5: Aspose.BarCode for .NET 适合企业级条码生成吗？

A5: 绝对适合，Aspose.BarCode for .NET 旨在满足小规模和企业级条码生成需求，具备可扩展性和可靠性。

## Frequently Asked Questions

**Q: 我可以在移动应用中使用生成的条码吗？**  
A: 可以。生成的 PNG 图像可嵌入 iOS、Android 或任何跨平台移动应用。

**Q: 如果需要编码二进制数据而不是文本怎么办？**  
A: 使用 `AddECICodetext` 方法并指定相应的 `ECIEncodings`（例如 `ECIEncodings.Base64`）来嵌入二进制负载。

**Q: 如何在不影响可读性的前提下改变条码尺寸？**  
A: 调整 `XDimension.Pixels` 属性；数值越高模块越大，数值越低条码越紧凑。

**Q: 能否在条码周围添加空白区（quiet zone）？**  
A: 可以。设置 `gen.Parameters.Barcode.Margin` 以像素为单位定义所需的空白区。

**Q: 库是否支持 .NET 8？**  
A: 最新的 Aspose.BarCode 版本兼容 .NET 8，只需引用相应的 NuGet 包版本。

---

**最后更新：** 2026-01-27  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}