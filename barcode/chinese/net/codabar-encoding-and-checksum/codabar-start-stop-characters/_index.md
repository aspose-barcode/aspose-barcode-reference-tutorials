---
date: 2026-05-24
description: 了解如何使用 Aspose.BarCode for .NET 创建带起始和结束字符的 Codabar 条码。面向开发者的逐步条码生成教程。
keywords:
- create codabar barcode
- codabar start stop characters
- aspose barcode example
- barcode generation .net core
linktitle: Codabar 起始/结束字符
schemas:
- author: Aspose
  dateModified: '2026-05-24'
  description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  headline: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for
    .NET
  type: TechArticle
- description: Learn how to create codabar barcode with start and stop characters
    using Aspose.BarCode for .NET. Step‑by‑step barcode generation tutorial for developers.
  name: Create Codabar Barcode with Start/Stop Characters in Aspose.BarCode for .NET
  steps:
  - name: Initialize the Barcode Generator
    text: '`BarcodeGenerator` is the core class that creates barcode images. It takes
      the symbology type and the data string as constructor arguments. > **Pro tip:**
      The dash (`-`) is one of the valid start/stop symbols for Codabar. You can also
      use `A`, `B`, `C`, or `D` depending on your application’s require'
  - name: Set the X‑Dimension (barcode element width)
    text: '`XDimension` controls the width of the narrowest bar. Larger values improve
      readability on low‑resolution printers, while smaller values conserve space
      on high‑density labels. > **Why it matters:** Adjusting `XDimension` helps you
      meet scanner specifications that often require a minimum bar width of'
  - name: Define Start and Stop Characters
    text: Codabar supports four start/stop symbols (A, B, C, D). Below are examples
      for each option. Choose the one that matches the specification of the system
      you’re integrating with.
  - name: Save the Generated Barcode Images (PNG)
    text: '`Save` writes the barcode to a file. Using `BarCodeImageFormat.Png` produces
      lossless PNG images that are ideal for web and print use cases. Each file now
      contains a **codabar barcode example** with the corresponding start/stop symbols.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library do I need?
  - answer: PNG (`BarCodeImageFormat.Png`)
    question: Which format can I save the barcode in?
  - answer: A free trial works for testing; a commercial license is required for production.
    question: Do I need a license for development?
  - answer: Yes – use `CodabarSymbol.A`, `B`, `C`, or `D`.
    question: Can I change the start/stop symbols?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: What .NET versions are supported?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 在 Aspose.BarCode for .NET 中创建带起始/结束字符的 Codabar 条码
url: /zh/net/codabar-encoding-and-checksum/codabar-start-stop-characters/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建带起始/停止字符的 Codabar 条形码（使用 Aspose.BarCode for .NET）

## 介绍

在本教程中，您将使用 Aspose.BarCode for .NET **创建包含显式起始/停止字符的 Codabar 条形码** 图像。无论您是构建零售库存系统、实验室样本跟踪器，还是医疗记录解决方案，Codabar 的数字符号依赖这些边界符号来确保可靠的扫描。接下来几分钟，我们将从环境设置到保存 PNG 文件全部讲解，让您能够立即开始生成 Codabar 条形码。

## 快速答疑
- **需要的库是什么？** Aspose.BarCode for .NET  
- **我可以将条形码保存为何种格式？** PNG (`BarCodeImageFormat.Png`)  
- **开发是否需要许可证？** 免费试用可用于测试；生产环境需要商业许可证。  
- **我可以更改起始/停止符号吗？** 可以 – 使用 `CodabarSymbol.A`、`B`、`C` 或 `D`。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。

## 什么是 Codabar，为什么起始/停止字符至关重要？

Codabar 是一种广泛用于图书馆、医疗保健和库存管理的数字条形码符号。起始和停止字符（A‑D 或短横线）定义条形码的边界，使扫描仪能够以 99.9 % 的读取准确率检测数据的起始和结束位置。

## 为什么使用 Aspose.BarCode for .NET？

Aspose.BarCode 支持 **30 多种条形码符号**，并且能够生成最高 **10,000 × 10,000 px** 的图像，而无需将整个文档加载到内存中。它可在 Windows、Linux 和 macOS 上运行，并兼容 .NET Framework、.NET Core 和 .NET 5+，为您在所有现代平台上提供灵活性。

## 前置条件

1. **环境设置** – 确保拥有可用的 .NET 开发环境。如需指导，请参阅[文档](https://reference.aspose.com/barcode/net/)。  
2. **Aspose.BarCode for .NET 库** – 从官方[来源](https://releases.aspose.com/barcode/net/)下载并安装该库。  
3. **基础 .NET 知识** – 熟悉 C# 以及 Visual Studio、Rider 或 VS Code 等 IDE。  
4. **IDE** – Visual Studio、Rider 或 Visual Studio Code 都可以。

现在我们已经介绍完前置条件，下面深入实际代码。

## 如何生成带起始/停止字符的 Codabar 条形码？

加载 `BarcodeGenerator`，将编码类型设置为 **Codabar**，并传入已包含所需起始/停止符号的数据字符串（例如 “-12345-”）。随后配置 X‑Dimension，可选地选择不同的起始/停止符号，最后将图像保存为 PNG。此端到端流程仅需几行 C# 代码即可创建可直接使用的条形码。

### 导入命名空间

`BarcodeGenerator` 及相关类型位于 `Aspose.BarCode.Generation` 命名空间中。

```csharp
using Aspose.BarCode.Generation;
```

### 步骤 1：初始化条形码生成器

`BarcodeGenerator` 是创建条形码图像的核心类。它在构造函数中接受符号类型和数据字符串作为参数。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarStartStop:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

> **小贴士：** 短横线（`-`）是 Codabar 的有效起始/停止符号之一。您也可以根据应用需求使用 `A`、`B`、`C` 或 `D`。

### 步骤 2：设置 X‑Dimension（条码元素宽度）

`XDimension` 控制最窄条的宽度。较大的数值可提升低分辨率打印机的可读性，而较小的数值则在高密度标签上节省空间。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **重要性说明：** 调整 `XDimension` 有助于满足扫描仪规范，通常要求最小条宽为 0.25 mm。

### 步骤 3：定义起始和停止字符

Codabar 支持四种起始/停止符号（A、B、C、D）。以下是每种选项的示例。请选择与您集成系统规范相匹配的符号。

#### 设置起始 A 和停止 A

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.A;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.A;
```

#### 设置起始 B 和停止 B

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.B;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.B;
```

#### 设置起始 C 和停止 C

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.C;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.C;
```

#### 设置起始 D 和停止 D

```csharp
gen.Parameters.Barcode.Codabar.CodabarStartSymbol = CodabarSymbol.D;
gen.Parameters.Barcode.Codabar.CodabarStopSymbol = CodabarSymbol.D;
```

您可以为每个需要生成的符号重复配置；下面的示例将保存四个独立的图像——每对起始/停止符号对应一个图像。

### 步骤 4：保存生成的条形码图像（PNG）

`Save` 将条形码写入文件。使用 `BarCodeImageFormat.Png` 可生成无损 PNG 图像，适用于网页和打印场景。

```csharp
gen.Save($"{path}CodabarStartAStopA.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartBStopB.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartCStopC.png", BarCodeImageFormat.Png);
gen.Save($"{path}CodabarStartDStopD.png", BarCodeImageFormat.Png);
```

每个文件现在都包含一个带有相应起始/停止符号的 **Codabar 条形码示例**。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决方案 |
|------|----------|----------|
| 条形码出现失真 | 所选打印机分辨率下 X‑Dimension 设置过低 | 增加 `XDimension.Pixels`（例如，设为 3 或 4） |
| 扫描仪无法读取起始/停止符号 | 目标系统使用了错误的起始/停止符号 | 核实所需符号（A‑D），并相应设置 |
| PNG 文件为空或损坏 | 输出路径无效或写入权限不足 | 确保 `path` 指向已存在的文件夹且应用具有写入权限 |

## 常见问答

**Q1：什么是 Codabar，起始和停止字符为何重要？**  
A：Codabar 是一种用于库存、图书馆和医疗保健的数字条形码符号。起始/停止字符定义条形码的边界，确保扫描仪知道数据的起始和结束位置。

**Q2：我可以使用 Aspose.BarCode for .NET 定制 Codabar 条形码的外观吗？**  
A：可以。除了 X‑Dimension，您还可以更改颜色、添加边距，并使用相同的 API 导出为 PDF 或 SVG。

**Q3：Codabar 条形码在数据编码方面有哪些限制？**  
A：Codabar 主要支持数字数据（0‑9）以及有限的特殊字符。不适用于完整的字母数字字符串。

**Q4：Aspose.BarCode for .NET 是否适用于商业使用，如何获取许可证？**  
A：是的，已具备生产就绪性。可在 [Aspose 的购买页面](https://purchase.aspose.com/buy) 购买许可证。

**Q5：我可以在哪里寻求帮助或讨论 Aspose.BarCode for .NET 相关问题？**  
A：加入 [Aspose.BarCode for .NET 支持论坛](https://forum.aspose.com/c/barcode/13) 社区，可获得 Aspose 工程师和其他开发者的帮助。

**最后更新：** 2026-05-24  
**测试版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [Codabar 起始/停止字符和校验和](/barcode/net/codabar-encoding-and-checksum/)
- [如何使用 Aspose.BarCode for .NET 为 Codabar 条形码添加校验和](/barcode/net/codabar-encoding-and-checksum/codabar-checksum-calculation/)
- [Aspose.BarCode for .NET 的综合教程和示例](/barcode/net/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}