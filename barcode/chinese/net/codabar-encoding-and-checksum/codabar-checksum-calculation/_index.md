---
date: 2026-01-04
description: 了解如何在使用 Aspose.BarCode for .NET 生成 Codabar 条码时添加校验和。一步步指南，涵盖 Mod10 和
  Mod16 校验和模式。
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 为 Codabar 条码添加校验和
url: /zh/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 为 Codabar 条码添加校验和

Codabar 是一种被广泛采用的线性条码符号，尤其在物流、图书馆和医疗保健领域。为 Codabar 条码添加校验和可以显著提升数据完整性，在错误发生之前就检测出转录错误。在本教程中，您将学习 **如何在使用 Aspose.BarCode for .NET 生成 Codabar 条码时添加校验和**，并看到 Mod10 与 Mod16 两种校验模式的实际效果。

## 快速答案
- **“添加校验和” 对 Codabar 意味着什么？** 它会启用用于验证编码数据的错误检测数字。
- **支持哪些校验和模式？** Mod10（常用）和 Mod16（用于更高精度的场景）。
- **使用此功能是否需要许可证？** 是的，生产环境下需要有效的 Aspose.BarCode for .NET 许可证。
- **兼容哪些 .NET 版本？** 该库支持 .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。
- **生成的图像保存在哪里？** 保存到您在 `path` 变量中指定的文件夹。

## “如何在 Codabar 中添加校验和” 是什么？
添加校验和意味着配置条码生成器，根据您提供的数据计算并附加一个（或多个）额外数字。扫描器会验证这些额外信息，从而降低误读的可能性。

## 为什么要生成带校验和的 Codabar 条码？
- **可靠性提升：** 检测单字符错误和大多数换位错误。
- **合规性：** 某些行业（例如血库）要求使用带校验和的条码。
- **灵活性：** Aspose.BarCode 只需更改一个属性，即可在 Mod10 与 Mod16 之间切换。

## 前置条件

在开始之前，请确保您具备以下条件：

1. **Aspose.BarCode for .NET** – 从 [here](https://releases.aspose.com/barcode/net/) 下载最新版本。  
2. **C# 开发环境** – Visual Studio、VS Code 或任何支持 .NET 开发的 IDE。

准备工作完成后，让我们一步步实现。

## 导入命名空间

在 C# 文件顶部添加所需的命名空间，以便访问条码生成类：

```csharp
using Aspose.BarCode.Generation;
```

## 步骤 1：初始化条码生成器

创建 `BarcodeGenerator` 实例，指定 Codabar 符号并提供要编码的数据。记得将 `"Your Directory Path"` 替换为实际的图像保存文件夹路径。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## 步骤 2：生成 **不带** 校验和的 Codabar 条码

如果需要普通条码（不带校验和），将校验和选项设为 `Default`。这对不期待校验和数字的旧系统很有用。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## 步骤 3：生成带 **Mod10** 校验和的 Codabar 条码

启用校验和并选择 Mod10 算法。这是 Codabar 最常用的校验模式。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## 步骤 4：生成带 **Mod16** 校验和的 Codabar 条码

对于需要更高错误检测能力的应用，切换到 Mod16。代码改动极小——只需更新 `CodabarChecksumMode`。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

通过上述四个简单步骤，您已经学习了 **如何为 Codabar 条码添加校验和**，并掌握了在 Aspose.BarCode for .NET 中在 Mod10 与 Mod16 模式之间切换的方法。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 生成的图像为空 | `path` 指向不存在的文件夹 | 确保目录存在，或在保存前使用 `Directory.CreateDirectory(path)` |
| 未应用校验和 | `IsChecksumEnabled` 仍为 `Default` | 在保存前设置 `IsChecksumEnabled = EnableChecksum.Yes` |
| 校验和模式错误 | 使用了错误的枚举值 | 根据需要使用 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16` |

## 结论

本指南介绍了 **如何在使用 Aspose.BarCode for .NET 生成 Codabar 条码时添加校验和**，演示了 Mod10 与 Mod16 两种校验模式，并阐明了带校验和条码对数据完整性的重要性。欢迎尝试不同的数据字符串，探索 Aspose 提供的丰富条码自定义选项。

如果遇到任何困难，Aspose.BarCode 社区将在 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 为您提供帮助。

## 常见问答

**Q: 可以在图书馆的图书条码中使用 Mod16 校验和吗？**  
A: 当然可以。Mod16 提供更强的错误检测，适用于图书馆等高吞吐量环境。

**Q: 启用校验和会影响扫描速度吗？**  
A: 额外的数字几乎不增加处理时间，大多数扫描器都能在不明显延迟的情况下处理。

**Q: 如何在代码中验证校验和？**  
A: 生成条码后，使用相同的 `CodabarChecksumMode` 重新计算校验和，并将其与编码字符串的最后一个字符进行比较。

**Q: 可以自定义校验和数字的外观吗？**  
A: 可以。使用 `BarcodeGenerator` 的外观设置（如 `BarHeight`、`ForeColor`）来样式化整个条码，包括校验和数字。

**Q: 如果需要在循环中生成多个条码怎么办？**  
A: 实例化一个 `BarcodeGenerator`，在每次迭代中更新 `CodeText` 属性，并使用唯一的文件名调用 `Save`。

---

**最后更新：** 2026-01-04  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}