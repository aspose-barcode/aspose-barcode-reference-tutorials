---
date: 2026-06-29
description: 学习如何使用 Aspose.BarCode 创建带错误纠正的 aztec barcode .net。一步一步的指南，附有代码示例。
keywords:
- create aztec barcode .net
- aztec error correction
- aspose barcode .net
linktitle: Aztec 错误级别示例
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to create aztec barcode .net with error correction using
    Aspose.BarCode. Step‑by‑step guide with code examples.
  headline: How to create aztec barcode .net with error correction
  type: TechArticle
- questions:
  - answer: Error correction ensures the barcode remains readable even if part of
      it is damaged, scratched, or obscured. Higher levels add more redundancy, improving
      reliability.
    question: What is the purpose of error correction in Aztec barcodes?
  - answer: Yes. Besides X‑Dimension and error level, you can modify colors, margins,
      and even embed a logo using other Aspose.BarCode parameters.
    question: Can I customize the appearance of the generated Aztec barcodes?
  - answer: Absolutely. The same `BarcodeGenerator` class supports QR Code, DataMatrix,
      PDF417, Code128, and many more.
    question: Is Aspose.BarCode for .NET compatible with other barcode formats?
  - answer: A temporary license is available for evaluation. For production use, purchase
      a full license from [this link](https://purchase.aspose.com/buy).
    question: Do I need a license to use Aspose.BarCode for .NET?
  - answer: The comprehensive API reference is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find the official documentation?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用错误纠正创建 aztec barcode .net
url: /zh/net/aztec-barcode-encoding/aztec-error-level-example/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用错误纠正创建 aztec 条形码 .net

在本分步教程中，您将学习如何使用 Aspose.BarCode for .NET 库创建包含不同错误纠正级别的 **create aztec barcode .net** 图像。无论您是需要用于包装、票务或移动扫描的强大条形码，控制错误级别都能帮助您在数据容量和抗损坏性之间取得平衡。我们将逐一演示每个配置选项，向您展示所需的完整代码，并解释每个设置的意义。

## 快速答案
- **使用的库是什么？** Aspose.BarCode for .NET  
- **我可以设置自定义错误级别吗？** 是 – 任意整数，范围从 0 % 到 100 %  
- **推荐使用哪个 IDE？** Visual Studio（任何版本）或带 .NET 支持的 VS Code  
- **我需要许可证吗？** 临时许可证可用于评估；生产环境需要完整许可证  
- **支持的输出格式？** PNG、JPEG、BMP、GIF 等  

## 如何使用错误纠正创建 aztec 条形码 .net？

加载 `BarcodeGenerator`，选择 Aztec 符号，设置所需的错误纠正百分比，然后调用 `Save` —— 这就是生成条形码图像所需的全部操作。库会自动处理尺寸、编码和错误纠正数据，让您专注于提供待编码文本的业务逻辑。

## 什么是带错误纠正的 Aztec 条形码？

Aztec 条形码是一种紧凑的二维矩阵码，能够存储大量数据，错误纠正会添加冗余信息，使得即使符号的一部分受损或被遮挡，仍然可以读取。调整错误纠正级别可以在数据容量和抗损坏性之间进行权衡，使条形码适用于工业标签或移动票务扫描等恶劣环境。

## 为什么使用 Aspose.BarCode for .NET？

Aspose.BarCode 支持 **30 多种条形码标准**——包括 Aztec、QR、DataMatrix、PDF417 和 Code128，并且能够生成最高达 2000 × 2000 像素的图像而不出现性能下降。其流式 API 抽象了底层编码，兼容 .NET Framework、.NET Core 以及 .NET 5/6+，并提供丰富的自定义选项（颜色、边距、徽标），满足企业应用的需求。

## 前提条件

- 对 C# 和 .NET 生态系统的基本了解。  
- Visual Studio、Visual Studio Code 或任何兼容 C# 的 IDE。  
- Aspose.BarCode for .NET 库 – 从 [此链接](https://releases.aspose.com/barcode/net/) 下载。  
- (可选) 用于无障碍试用的临时许可证 – 在 [此处](https://purchase.aspose.com/temporary-license/) 获取。  

## 导入命名空间

要开始，请在项目中引入所需的 Aspose.BarCode 命名空间：

```csharp
using Aspose.BarCode.Generation;
```

## 步骤 1：设置条形码生成器

`BarcodeGenerator` 是 Aspose.BarCode 的核心类，用于创建和配置条形码图像。

创建 `BarcodeGenerator` 实例，指定 **Aztec** 类型，并提供要编码的数据。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecErrorLevelExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde© is a powerful library to generate & recognize 1D & 2D barcodes");
```

> **技巧提示：** 将 `"Your Directory Path"` 替换为您拥有写入权限的绝对或相对路径。

## 步骤 2：定义 X 维度

`XDimension` 属性定义生成的条形码中单个模块（像素）的大小。

X 维度控制条形码中最小模块（像素）的宽度。将其设置为 4 像素可得到清晰、可扫描的图像。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## 步骤 3：选择 Aztec 符号模式

`AztecSymbolMode` 决定库如何为 Aztec 条形码选择矩阵大小。

Aztec 支持多种符号模式。使用 `FullRange` 可让库根据您的数据和错误纠正设置自动选择最佳尺寸。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
```

## 步骤 4：设置错误纠正容量

`AztecErrorLevel` 设置添加用于错误纠正的冗余数据的百分比。

现在我们调整错误纠正级别。在本示例中，我们创建两个条形码——一个错误级别为 5 % 的普通条形码，另一个错误级别为 50 % 的强大条形码，以展示视觉差异。

```csharp
// Set error correction capacity to 5%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 5;
gen.Save($"{path}AztecErrorLevel5.png", BarCodeImageFormat.Png);

// Set error correction capacity to 50%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 50;
gen.Save($"{path}AztecErrorLevel50.png", BarCodeImageFormat.Png);
```

运行代码后将在指定文件夹生成两个 PNG 文件。50 % 版本包含更多冗余数据，使其对损坏更具容忍度，但符号会略大一些。

## 常见问题与解决方案

| 症状 | 可能原因 | 解决办法 |
|---------|--------------|-----|
| 条形码图像模糊 | 所选输出尺寸的 X‑Dimension 过低 | 增加 `XDimension.Pixels`（例如，设置为 6 或 8）。 |
| 保存操作抛出 *AccessDenied* | 路径无效或不可写 | 确认 `path` 变量指向您有写入权限的文件夹。 |
| 扫描仪无法读取代码 | 错误级别对于数据量来说过高 | 降低 `AztecErrorLevel` 或缩短编码文本。 |

## 常见问答

**问：在 Aztec 条形码中错误纠正的目的是什么？**  
答：错误纠正确保即使条形码的部分受损、划伤或被遮挡，仍然可以读取。更高的级别会添加更多冗余，提高可靠性。

**问：我可以自定义生成的 Aztec 条形码的外观吗？**  
答：可以。除了 X‑Dimension 和错误级别外，您还可以使用其他 Aspose.BarCode 参数修改颜色、边距，甚至嵌入徽标。

**问：Aspose.BarCode for .NET 是否兼容其他条形码格式？**  
答：当然。相同的 `BarcodeGenerator` 类支持 QR Code、DataMatrix、PDF417、Code128 等众多格式。

**问：使用 Aspose.BarCode for .NET 是否需要许可证？**  
答：可获取临时许可证用于评估。生产使用时，请从 [此链接](https://purchase.aspose.com/buy) 购买完整许可证。

**问：在哪里可以找到官方文档？**  
答：完整的 API 参考可在 [此处](https://reference.aspose.com/barcode/net/) 查看。

**问：生成的图像最大可以多大？**  
答：Aspose.BarCode 能生成最高 2000 × 2000 像素的图像，同时在典型工作负载下内存使用保持在 100 MB 以下。

**问：该库是线程安全的吗？**  
答：是的。只要每个线程使用各自的 `BarcodeGenerator` 实例，即可并发使用。

## 结论

现在，您已经了解如何使用 Aspose.BarCode for .NET 通过 **create aztec barcode .net** 创建具有自定义错误纠正级别的图像。通过调整 X‑Dimension、符号模式和错误级别，您可以生成满足应用程序精确可靠性和尺寸需求的条形码。欢迎尝试不同的数据字符串和错误百分比，观察条形码的适应情况。

如果遇到任何问题，社区活跃于 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)，官方文档提供了更深入的高级自定义指南。

---

**最后更新：** 2026-06-29  
**测试环境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

## 相关教程

- [使用 Aspose.BarCode for .NET 的 Aztec 代码文本编码](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义宽高比的 Aztec 条形码](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [精通 Aspose.BarCode for .NET 的 Aztec 符号模式](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}