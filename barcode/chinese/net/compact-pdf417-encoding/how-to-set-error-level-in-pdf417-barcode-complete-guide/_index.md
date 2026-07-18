---
category: general
date: 2026-07-18
description: 如何使用 Aspose.BarCode 设置 PDF417 条码的错误级别。学习在几分钟内生成带自定义文本的 PDF417 条码并微调错误纠正。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: zh
lastmod: 2026-07-18
og_description: 如何快速设置 PDF417 条码的错误级别。本教程将指导您生成带有自定义文本和不同错误纠正级别的 PDF417 条码。
og_image_alt: how to set error level in PDF417 barcode example
og_title: 如何在 PDF417 条码中设置错误级别 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: 如何在 PDF417 条码中设置错误级别——完整指南
url: /zh/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PDF417 条码中设置错误级别 – 完整指南

有没有想过在生成 PDF417 条码时**如何设置错误**？你并不孤单——大多数开发者在需要更强大的条码以在恶劣环境中扫描时都会遇到这个难题。好消息是？使用 Aspose.BarCode 调整错误纠正级别非常简单，同时你还会学习**如何生成 PDF417**并使用自定义文本。

在本教程中，我们将逐步演示，从创建带特殊字符的条码生成器到保存展示不同错误纠正级别的两个 PNG 文件。完成后，你将熟练掌握**生成 PDF417 条码**、调整其 X‑dimension、列数，以及最重要的**设置错误**级别，以满足你的使用场景。

## 前置条件

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework）
- 已安装 Aspose.BarCode for .NET（通过 NuGet 使用 `Install-Package Aspose.BarCode`）
- 磁盘上用于写入图像的文件夹（在示例中替换 `YOUR_DIRECTORY/`）
- 基本的 C# 知识——只要写过 `Console.WriteLine`，就可以开始了

> **专业提示：** 如果你的目标是移动端扫描，建议使用更高的错误级别（Level 5），以抵御污垢、划痕或低光条件。

## 步骤 1：使用自定义文本创建条码生成器

首先需要一个 `BarcodeGenerator` 实例，告诉它应生成**PDF417 条码**并携带你想要编码的确切文本。注意使用了带重音的字符和版权符号——这表明生成器能够开箱即用地处理 Unicode。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*为什么这很重要：* `EncodeTypes.Pdf417` 标志告诉 Aspose 你正在处理一种 2‑D 堆叠条码，而字符串参数则成为数据负载。如果跳过这一步，你最终会得到默认的 Code128 条码，而不是所需的高容量 PDF417。

## 步骤 2：微调视觉参数

PDF417 条码不仅是数据，还包含视觉图案。调整**X‑dimension**（最小条的宽度）和**列数**可以控制条码的实际尺寸和可读性。

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*为什么这很重要：* 较小的 X‑dimension 能产生更紧凑的图像，但在低分辨率扫描仪上可能难以读取。三列在大多数标签尺寸下提供了平衡的宽高比。

## 步骤 3：设置错误纠正级别为 2 并保存

错误纠正是 PDF417 **如何设置错误**的核心。`Pdf417ErrorLevel` 枚举范围从 `Level0`（无额外数据）到 `Level5`（最大冗余）。这里我们从 **Level 2** 开始，它在不显著增大图像的情况下提供适度的错误恢复能力。

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

运行此代码后，你将在文件夹中看到 `Pdf417ErrorLevel2.png`。打开它，你应该会看到一个干净的三列条码，仍然包含相当数量的冗余信息。

## 步骤 4：将错误纠正提升至 Level 5 并再次保存

有时需要条码在更激烈的损坏下仍能被读取——比如仓库地面上标签被擦伤的情况。切换到 **Level 5** 会在图像略微增大的代价下最大化错误纠正。

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

现在你拥有并排的两个 PNG 文件：一个具有中等错误纠正，另一个具有最大纠正。比较它们；Level 5 版本会有更多的暗模块，这正是算法为保护数据而添加的。

![如何在 PDF417 条码中设置错误级别示例](image.png)

*图片说明（alt 文本）：如何在 PDF417 条码中设置错误级别示例 – 显示两个具有不同错误纠正级别的 PNG 文件。*

## 预期输出

| 文件名                         | 错误级别   | 大约尺寸 (px) |
|-------------------------------|-----------|----------------|
| `Pdf417ErrorLevel2.png`       | Level 2   | 150 × 80       |
| `Pdf417ErrorLevel5.png`       | Level 5   | 180 × 95       |

两张图像均编码字符串 **“Åspóse.Barcóde©”**，可使用任何标准 PDF417 读取器（如 ZXing、Scandit）扫描。Level 5 图像可容忍约 30 % 的损坏，而 Level 2 可容忍约 15 %。

## 常见问题与边缘情况

### 如果我的文本包含换行符怎么办？

PDF417 会自动编码换行（`\n`）字符。只需在字符串中包含它们：

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### 我可以使用不同的图像格式吗？

完全可以。将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Svg`，根据下游工作流的需求选择。

### 更改 X‑dimension 会影响错误纠正吗？

间接会有影响。较大的 X‑dimension 会产生更大的模块，可能提升扫描可靠性，但**不会**改变逻辑错误纠正级别。请独立调整这两个参数以获得最佳效果。

### 如何在 Web API 中生成 PDF417 条码？

将相同代码封装在 ASP.NET Core 控制器中，并将 PNG 以 `FileResult` 的形式流回。核心逻辑保持不变，这意味着 **如何生成 PDF417** 在桌面和 Web 环境中保持一致。

## 回顾

我们已经介绍了 PDF417 条码的**如何设置错误**，演示了使用自定义 Unicode 文本**如何生成 PDF417**，并展示了如何微调 X‑dimension 和列数等视觉设置。通过将 `Pdf417ErrorLevel.Level2` 替换为 `Level5`，即可在图像大小与抗损坏能力之间进行权衡。

## 后续步骤

- 尝试使用包含 URL 或产品 ID 的**自定义文本条码**。
- 尝试不同的列数（`generator.Parameters.Barcode.Pdf417.Columns = 5`），观察形状的变化。
- 在同一文档中将 PDF417 与其他条码类型结合，实现多模态扫描解决方案。
- 深入阅读 Aspose 的[官方文档](https://docs.aspose.com/barcode/net/)，了解宏 PDF417 或紧凑模式等高级功能。

如果遇到任何问题，欢迎留言或分享你的扫描结果。祝条码制作愉快！

## 接下来你应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在自己的项目中进一步掌握 API 功能并探索替代实现方式。每个资源都提供完整的可运行代码示例和逐步解释。

- [如何使用 Aspose.BarCode 创建条码 – 紧凑型 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 .NET 中创建带错误纠正的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码（ECC 200）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}