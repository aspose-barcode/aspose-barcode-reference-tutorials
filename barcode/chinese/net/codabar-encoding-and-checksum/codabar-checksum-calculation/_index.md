---
date: 2026-06-29
description: 了解如何使用 Aspose.BarCode for .NET 生成带校验码的 Codabar 条形码。逐步指南，涵盖 Mod10 和 Mod16
  校验模式。
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Codabar 校验码计算
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 生成带校验码的 Codabar 条形码 (Aspose.BarCode .NET)
url: /zh/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成带校验和的 Codabar 条形码 (Aspose.BarCode .NET)

Codabar 是一种广泛采用的线性条形码符号，应用于物流、图书馆和医疗保健。**生成带校验和的 Codabar 条形码** 能显著提升数据完整性，捕获转录错误，防止问题发生。在本教程中，您将学习如何在使用 Aspose.BarCode for .NET *生成 Codabar 条形码* 时添加校验和，并看到 Mod10 和 Mod16 两种校验和模式的实际效果。

## 快速解答
- **添加校验和 对于 Codabar 意味着什么？** 它会添加一个错误检测位，用于验证编码的数据。  
- **支持哪些校验和模式？** Mod10（标准）和 Mod16（更高精度）。  
- **使用此功能是否需要许可证？** 是的——在生产环境中需要有效的 Aspose.BarCode for .NET 许可证。  
- **兼容哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **生成的图像保存在哪里？** 保存到您在 `path` 变量中指定的文件夹。

## 如何生成带校验和的 Codabar 条形码？

加载您的数据，启用校验和，选择 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16`，然后调用 `Save`。Aspose.BarCode 会自动完成计算并附加校验和位，因此您只需一次方法调用即可获得可直接扫描的图像。保存时还可以指定输出文件夹、文件名和图像格式（例如 PNG）。

## 为什么要为 Codabar 条形码添加校验和？

添加校验和可将单字符错误降低 **最高 99.9%**，并捕获大多数换位错误，这对血库等行业至关重要，因为单个数字错误可能导致严重后果。它还满足许多物流标准的合规要求。

## 前置条件

1. **Aspose.BarCode for .NET** – 从 [here](https://releases.aspose.com/barcode/net/) 下载最新版本。  
2. **C# 开发环境** – Visual Studio、VS Code 或任何支持 .NET 的 IDE。

现在所有准备工作已完成，让我们逐步演示实现过程。

## 导入命名空间

`BarcodeGenerator` 类位于 `Aspose.BarCode.Generation` 命名空间。请在文件顶部导入它：

`using Aspose.BarCode.Generation;`

## 什么是 BarcodeGenerator 类？

`BarcodeGenerator` 类是 Aspose.BarCode 的核心对象，用于创建、配置和渲染条形码图像。它封装了所有条形码特定的设置，如符号类型、文本、尺寸和校验和选项，使您能够通过一次 `Save` 调用生成图像。通过修改其 `Parameters` 属性，您可以自定义外观、编码模式以及任何受支持条形码类型的错误检测功能。

## 步骤 1：初始化条形码生成器

创建 `BarcodeGenerator` 实例，指定 Codabar 符号，并提供要编码的数据。将 `"Your Directory Path"` 替换为实际希望保存图像的文件夹路径。

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## 步骤 2：生成 **不带** 校验和的 Codabar 条形码

如果旧系统只需要普通条形码，请将校验和选项设置为 `Default`。这将禁用额外的校验位。

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## 步骤 3：生成带 **Mod10** 校验和的 Codabar 条形码

启用校验和并选择 Mod10 算法，这是 Codabar 最常用的模式。

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## 步骤 4：生成带 **Mod16** 校验和的 Codabar 条形码

在需要更高错误检测的场景下，切换到 Mod16。只需对单个属性赋值即可完成更改。

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

通过这四个简单步骤，您已经学习了 **如何生成带校验和的 Codabar 条形码**，以及如何使用 Aspose.BarCode for .NET 在 Mod10 和 Mod16 模式之间切换。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| 生成的图像为空 | `path` 指向不存在的文件夹 | 确保目录存在，或在保存前调用 `Directory.CreateDirectory(path)` |
| 未应用校验和 | `IsChecksumEnabled` 保持为 `Default` | 在保存前将 `IsChecksumEnabled = EnableChecksum.Yes` 设置为启用 |
| 校验和模式错误 | 使用了错误的枚举值 | 根据需要使用 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16` |

## 常见问题

**Q: 我可以在图书馆图书条形码中使用 Mod16 校验和吗？**  
A: 当然可以。Mod16 提供更强的错误检测，对于图书馆等高吞吐量环境非常有益。

**Q: 启用校验和会影响扫描速度吗？**  
A: 额外的数字几乎不增加处理时间；大多数扫描仪都能在不明显延迟的情况下处理。

**Q: 如何在程序中验证校验和？**  
A: 生成条形码后，使用相同的 `CodabarChecksumMode` 重新计算校验和，并将其与编码字符串的最后一个字符进行比较。

**Q: 能否自定义校验和数字的外观？**  
A: 可以。使用 `BarcodeGenerator` 的外观设置（例如 `BarHeight`、`ForeColor`）来设置整个条形码的样式，包括校验和数字。

**Q: 如果需要在循环中生成多个条形码怎么办？**  
A: 实例化一个 `BarcodeGenerator`，在每次迭代中更新 `CodeText` 属性，并使用唯一的文件名调用 `Save`。

如果遇到任何问题，Aspose.BarCode 社区可在 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 提供帮助。

---

**最后更新：** 2026-06-29  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## 相关教程

- [在 Aspose.BarCode for .NET 中生成带起止字符的 Codabar 条形码](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Aspose.BarCode for .NET 的综合教程和示例](/barcode/net/)
- [生成 DataMatrix 条形码 – Aspose.BarCode 专业指南](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}