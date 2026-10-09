---
category: general
date: 2026-09-29
description: 如何使用 C# 设置 GS1 DataBar Omni‑Directional 条码的宽度以及更改高度。请按照一步一步的指南，查看完整代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: zh
lastmod: 2026-09-29
og_description: 如何在 C# 中设置 GS1 DataBar Omni‑Directional 条码的宽度以及更改高度。了解确切的 API 调用并查看完整的可运行示例。
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: 如何设置 GS1 DataBar 条码的宽度 – C# 指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: 如何在 C# 中为 GS1 DataBar Omni‑Directional 条码设置宽度并调整高度
url: /zh/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中设置 GS1 DataBar Omni‑Directional 条码的宽度并调整高度

在需要为扫描设备提供精确尺寸时，设置 GS1 DataBar Omni‑Directional 条码的宽度是常见任务。在本教程中，您还将学习 **how to change height**，使条码完美适配您的布局。指南将带您完整了解整个过程，从项目设置到可直接运行的代码示例。

我们将覆盖：

* 所需的 NuGet 包和 .NET 版本。
* 为什么 X‑dimension（模块宽度）对条码可读性至关重要。
* 用于 **how to set width** 和 **how to change height** 的精确 API 调用。
* 边缘情况处理，如最小模块宽度和高分辨率渲染。
* 一个完整的复制粘贴示例，可生成两张不同条码高度的 PNG 文件。

## Prerequisites

在开始之前，请确保您具备：

| 要求 | 原因 |
|------------|--------|
| .NET 6.0 SDK 或更高版本 | 示例使用现代 C# 特性，可在 Windows、Linux 或 macOS 上运行。 |
| Visual Studio 2022（或任何 C# IDE） | 为 Aspose.Barcode API 提供 IntelliSense。 |
| **Aspose.Barcode for .NET** NuGet 包 | 包含 `BarcodeGenerator`、`EncodeTypes` 以及图像格式支持。使用 `dotnet add package Aspose.Barcode` 安装。 |
| 对将保存 PNG 文件的文件夹拥有写入权限 | 生成器会将输出图像写入磁盘。 |

## How to set width of the barcode

**how to set width** 步骤通过配置条码参数的 `XDimension` 属性来完成。`XDimension` 表示模块宽度（最小的条或空白），单位可以是像素、点或毫米。正确设置可确保条码符合扫描仪规格。

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Why the X‑dimension matters

* **Scanner tolerance** – 大多数扫描仪要求最小模块宽度；数值过小会导致读取错误。  
* **Print resolution** – 在 300 dpi 打印时，2 px 模块约等于 0.17 mm，属于 GS1 DataBar 推荐范围。  
* **Image size** – 较大的 X‑dimension 会增加条码整体宽度，可能影响布局约束。

### Tips for reliable width settings

* **Never set XDimension below 1 px** – 库会将数值限制在最低值，但生成的条码可能无法读取。  
* **Match the target DPI** – 若渲染为高分辨率格式（如 600 dpi 的 TIFF），请相应提升 XDimension。  
* **Test with a real scanner** – 调整宽度后，请在实际读取设备上验证条码。

## How to change height of the barcode

在确定宽度后，可通过 `BarHeight` 属性控制垂直尺寸。以下代码演示了 **how to change height**，将高度从 30 px 改为 60 px，并保存为两张独立图片。

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Understanding bar height

* **Visual balance** – 较高的条形提升低对比度背景下的可读性，但会增加图像的垂直占用。  
* **Regulatory limits** – 某些标准（如零售标签）规定了最大条形高度，请据此调整。  
* **Aspect ratio** – 改变高度不会影响模块宽度，可独立微调两者。

### Edge‑case handling for height adjustments

| 情况 | 推荐做法 |
|-----------|----------------------|
| Height < 10 px | 增加至至少 10 px；过短的条形可能被扫描仪忽略。 |
| Very tall bars (≥ 100 px) | 确认输出介质（纸张、标签）能够容纳额外空间。 |
| Need proportional scaling | 计算 `BarHeight = XDimension * desiredRatio` 以保持视觉一致性。 |

## Full, runnable example

下面是完整程序，结合了 **how to set width** 与 **how to change height** 步骤。将代码复制到新建的控制台项目中，恢复 Aspose.Barcode NuGet 包后运行。`bin/Debug/net6.0` 文件夹中将出现两个 PNG 文件。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Expected output**

运行程序后会生成两张 PNG 文件：

* `DatabarBarHeight30Pixels.png` – 条码高度 30 px，模块宽度 2 px。  
* `DatabarBarHeight60Pixels.png` – 同一条码的垂直尺寸加倍。

在任意查看器中打开任意图片，您将看到一个干净的 GS1 DataBar Omni‑Directional 符号，已准备好进行扫描。

## Common questions answered

| Question | Answer |
|----------|--------|
| *Can I use millimetres instead of pixels?* | 可以。设置 `generator.Parameters.Barcode.XDimension.Millimeters` 与 `BarHeight.Millimeters`。库会根据图像 DPI 将其转换为设备像素。 |
| *What if I need a different barcode type?* | 将 `EncodeTypes.DatabarOmniDirectional` 替换为其他 `EncodeTypes` 值（例如 `EncodeTypes.QR`）。宽度和高度属性的使用方式相同。 |
| *Is there a way to generate SVG instead of PNG?* | 在 `Save` 调用中使用 `BarCodeImageFormat.Svg`。宽度/高度设置仍然适用。 |
| *Do I need to call `generator.Dispose()`?* | `BarcodeGenerator` 实现了 `IDisposable`。在控制台应用中可以使用 `using` 块包装，但对于短暂示例来说可选。 |

## Conclusion

您现在已经掌握了使用 Aspose.Barcode API 在 C# 中 **how to set width** GS1 DataBar Omni‑Directional 条码以及 **how to change height** 的方法。完整示例展示了创建生成器、配置 `XDimension` 与 `BarHeight`，并保存不同垂直尺寸的 PNG 文件的全过程。

接下来您可以：

* 尝试其他 `EncodeTypes`（如 QR、Code128）。  
* 渲染为 TIFF 等高分辨率格式以用于打印。  
* 将生成器集成到返回条码的 Web API 中，实现即时生成。

祝编码愉快，愿您的条码始终清晰可扫！

## What Should You Learn Next?

以下教程涵盖与本指南紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}