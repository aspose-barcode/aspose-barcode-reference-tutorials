---
category: general
date: 2026-07-18
description: 使用 C# 快速创建 PDF417 条码。学习如何生成条码、设置参数并保存图像文件——包括 AI 10 处理。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: zh
lastmod: 2026-07-18
og_description: 在 C# 中创建 PDF417 条码的完整教程。了解如何生成条码、调整设置以及保存图像，同时处理 AI 10。
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: 在 C# 中创建 PDF417 条码 – 快速、灵活、完整代码示例
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: 在 C# 中创建 PDF417 条码 – 完整的逐步指南
url: /zh/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 PDF417 条码 – 完整分步指南

是否曾需要**创建 pdf417 条码**却不确定该选用哪个库或哪些设置？你并不孤单——许多开发者在首次接触 GS1‑Micro‑PDF417 时都会遇到这种困惑。好消息是，只需几行 C# 代码，你就能生成格式完美的条码，微调外观，并直接将图像保存到磁盘。

在本教程中，我们将演示**如何生成条码**，使用 Aspose.BarCode 库，展示**如何设置参数**（如 X 维度和列数），并演示**如何保存图像**文件，分别对应 AI 10 和 AI 21 两种变体。完成后，你将拥有一段可在任何 .NET 项目中复用的代码片段。

## 前置条件

在开始之前，请确保你具备以下条件：

- .NET 6+ 或 .NET Framework 4.7.2（任意近期运行时均可）
- Visual Studio 2022 或你喜欢的 C# 编辑器
- **Aspose.BarCode for .NET** NuGet 包（`Install-Package Aspose.BarCode`）
- 一个可写入的文件夹，用于存放生成的 PNG 文件

就这些——无需额外工具，也不需要复杂配置。准备好了吗？让我们开始吧。

## 第一步：使用 GS1‑Micro 格式创建 PDF417 条码

首先我们**创建 pdf417 条码**对象并输入初始的 AI 数据。在 GS1‑Micro‑PDF417 中，AI 10（批次/批号）通常是起始点，所以我们会立即对其进行编码。

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **为什么重要：** `EncodeTypes.GS1MicroPdf417` 告诉库遵循 GS1‑Micro 规范，库会自动在 AI 前后加上方括号。如果省略此设置，生成的将是普通 PDF417，可能在零售环境中无法被扫描。

## 第二步：如何设置条码参数

现在我们已经拥有条码实例，需要对其视觉特性进行微调。这正是**如何设置参数**发挥作用的地方。我们将调整三个常用设置：

1. **X‑dimension** – 控制最小条宽（像素）
2. **Column count** – 影响整体形状；列数越少，条码越高
3. **IsLinked** – 启用可选的链接模块，将条码与数据字符串关联

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **专业提示：** 若目标是移动端扫描，可将 X‑dimension 调高至 3‑4 像素；较大的模块在低分辨率摄像头下更易被识别。

## 第三步：如何保存图像 – 第一个版本（AI 10）

配置好生成器后，终于可以**如何保存图像**了。`Save` 方法会按照指定的格式将条码写入文件。这里我们使用 PNG，因为它能在不产生压缩伪影的情况下保持边缘锐利。

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

此时，你应该在 `outputDir` 中看到名为 `GS1MicroPdf417_AI10.png` 的文件。使用任意图像查看器打开，你会看到一张干净、对比度高的 PDF417 条码，已准备好打印。

## 第四步：切换到另一种 AI（AI 21）并再次保存

通常你需要编码不同的应用标识符，例如 AI 21（序列号）。只需更改 `CodeText` 属性即可。这一步演示了**barcode ai 10** 与 **barcode ai 21** 的切换处理。

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **如果需要更多 AI 呢？** 只需在同一字符串中拼接，例如 `"(10)ABCD(21)12345(240)XYZ"`。库会自动解析方括号。

## 完整工作示例

将上述所有步骤组合在一起，下面是一段可直接复制到控制台应用的自包含程序：

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**预期输出：** 在 `C:\Barcodes\` 目录下会生成两个 PNG 文件——`GS1MicroPdf417_AI10.png` 和 `GS1MicroPdf417_AI21.png`。两者均为可扫描的 PDF417 条码，前者编码 AI 10，后者编码 AI 21。

## 常见陷阱及规避方法

- **文件夹权限缺失：** 若 `Save` 抛出 `UnauthorizedAccessException`，请确认路径存在且应用拥有写入权限。
- **AI 格式错误：** 忘记使用括号（如 `(10)`）会导致条码被当作普通数据处理，进而破坏 GS1 校验。
- **X‑dimension 过小：** 条宽小于 1 像素在图像缩放时可能消失。屏幕显示时请保持至少 2 像素。

## 后续步骤与相关主题

既然你已经掌握了**如何生成条码**、**如何设置参数**以及**如何保存图像**，可以进一步探索：

- 在条码下方添加**可读文本**（`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`）
- 将输出改为**PDF**而非 PNG（`BarCodeImageFormat.Pdf`）
- 将条码生成集成到**ASP.NET Core API**中，实现即时图像创建

上述每个主题都直接基于本指南奠定的基础。

---

### 快速回顾

- 使用 `BarcodeGenerator` 与 `EncodeTypes.GS1MicroPdf417` **创建 pdf417 条码**
- **如何设置参数**：X‑dimension、列数以及链接模块
- **如何保存图像**：以 PNG 格式保存 AI 10 与 AI 21 两个变体
- 通过更改 `CodeText` 实现 **barcode ai 10** 与 **barcode ai 21** 的切换

动手试一试，调节设置，你就拥有了可投入生产的强大条码引擎。还有疑问或想深入了解？在下方留言——祝编码愉快！


## 接下来该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助你在项目中进一步使用 API 功能并探索替代实现方式，每篇均提供完整可运行的代码示例和逐步解释。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}