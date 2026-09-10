---
category: general
date: 2026-07-15
description: 快速使用 Aspose.BarCode 在 C# 中创建全方向条码——学习如何生成可调节条高和 X 维度的 C# 条码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: zh
lastmod: 2026-07-15
og_description: 使用 Aspose.BarCode 在 C# 中创建全方向条形码。掌握通过调节 XDimension 和 BarHeight 来生成完美条形码的技巧。
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: 在 C# 中创建全向条码 – 完整编程演练
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: 在 C# 中创建全向条形码 – 步骤指南
url: /zh/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建全向条形码 – Step‑by‑Step Guide

是否曾想过如何生成符合 GS1 DataBar Omni‑Directional 符号的 C# 条形码？你并不孤单。在本教程中，我们将 **创建全向条形码** 图像，从零开始，调整 X‑dimension，并玩转条码高度——全部使用 Aspose.BarCode 库。

我们将通过一个真实场景来演示：你需要为零售标签制作紧凑的高密度条形码，并希望完全控制其视觉尺寸。完成后，你将得到两个 PNG 文件——一个条码高度为 30 px，另一个为 60 px——可直接用于任何打印工作流。

## Prerequisites

- 已在机器上安装 .NET 6（或任意近期的 .NET 运行时）。  
- Visual Studio 2022 或 VS Code——你喜欢的 IDE 都可以。  
- 免费的 Aspose.BarCode for .NET NuGet 包（`Aspose.BarCode`）。

除此之外无需其他依赖。如果你从未使用过 NuGet，只需打开 Package Manager Console 并运行：

```powershell
Install-Package Aspose.BarCode
```

## create omni-directional barcode – Understanding the Basics

**GS1 DataBar Omni‑Directional** 符号旨在任意方向扫描，非常适合货架边缘标签。当你调用 `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)` 时，库会完成繁重的工作：对数据进行编码，应用符号规则，并生成栅格图像。

> **专业提示：** 始终将原始数据包装在相应的应用标识符（AI）格式中，例如 `"(01)12345678901231"` 用于 GTIN‑14。这告诉扫描器这些数字的含义。

## Step 1 – Set Up the Barcode Generator (how to generate barcode c#)

首先创建生成器对象。这是使用 Aspose **how to generate barcode c#** 的基石。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 枚举值告诉引擎使用哪种符号。第二个参数是已经包装好的 GTIN AI 原始数据字符串。

## Step 2 – Adjust the X‑Dimension (barcode XDimension)

**barcode XDimension** 控制最小条的宽度。2 px 的数值在可读性和紧凑性之间取得了良好平衡，适用于大多数标签打印机。

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

如果需要更细或更粗的外观，只需更改该数值。记住：X‑dimension 是基本单位，所有其他条宽都是它的倍数。

## Step 3 – Create the First Image with a 30 px Bar Height (barcode BarHeight)

现在将 **barcode BarHeight** 设置为 30 px 并保存图像。这会生成一个适合标准标签的适中尺寸条码。

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` 方法会将 PNG 文件写入磁盘。如果你更喜欢 JPEG 输出，可以将 `BarCodeImageFormat.Jpeg` 替换进去。

## Step 4 – Increase Bar Height to 60 px for Larger Labels (barcode BarHeight)

有时需要更大的条码——比如放在离扫描器较远的货架标签上。我们将高度翻倍。

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

注意我们 **不需要** 重新创建生成器，只需调整参数并复用同一个对象。这可以节省内存并保持代码整洁。

## Step 5 – Save the Second Image (how to generate barcode c#)

最后，保存第二个 PNG。现在你拥有两份仅在条码高度上不同的文件。

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Expected output

- `DatabarBarHeight30Pixels.png` – 高度为 30 px 的全向条形码。  
- `DatabarBarHeight60Pixels.png` – 同样的数据，但条码高度为 60 px。

在任意图像查看器中打开文件，你会看到符合 GS1 DataBar Omni‑Directional 规范的清晰可扫描条纹。

## Common Questions & Edge Cases

### What if I need a different X‑dimension?

只需在调用 `Save` 前赋予新值即可。对于超高密度打印，你可以降至 1 px，但请先用扫描器进行测试——有些设备对小于 2 px 的条宽支持不佳。

### Can I add human‑readable text below the barcode?

可以。将 `barcodeGenerator.Parameters.Barcode.CodeText` 设置为字符串，并可选地将 `barcodeGenerator.Parameters.Barcode.CodeLocation` 调整为 `BarCodeTextLocation.Below`。这在零售环境中非常实用，因为需要显示可读的 GTIN 数字。

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Is PNG the best format for printing?

PNG 为无损格式，能够保留条码扫描器所需的锐利边缘。如果下游系统需要其他格式（TIFF、BMP），只需更改 `BarCodeImageFormat` 枚举即可。

## Full Working Example (create omni-directional barcode)

下面是完整的、可直接运行的示例程序。复制粘贴到新的控制台项目中，按 **F5** 运行。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

运行程序，检查输出文件夹，你将看到如前所述的两个 PNG 文件。

## Recap

我们展示了 **how to generate barcode C#** 代码，使用 Aspose.BarCode **create omni-directional barcode**。通过调整 **barcode XDimension** 和 **barcode BarHeight**，你可以细粒度地控制视觉尺寸，而不牺牲扫描可靠性。

## What’s Next?

- 试验其他 **GS1 DataBar Omni-Directional** 设置，如 `Color` 或 `Margin`。  
- 使用 `Graphics` 将多个条码组合到同一画布上，实现复杂标签设计。  
- 将生成器集成到 Web API 中，让你的电商平台能够按需生成条码。

有想法想分享吗？留下评论，让我们继续交流。祝编码愉快！


## What Should You Learn Next?


以下教程涵盖与本指南技术紧密相关的主题，帮助你在项目中进一步掌握 API 功能并探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}