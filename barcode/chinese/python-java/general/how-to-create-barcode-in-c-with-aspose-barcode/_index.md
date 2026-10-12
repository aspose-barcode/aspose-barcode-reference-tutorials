---
category: general
date: 2026-09-26
description: 学习如何使用 Aspose.BarCode 在 C# 中创建条形码。本分步指南包含条形码生成器示例，并展示如何调整条码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: zh
lastmod: 2026-09-26
og_description: 使用 Aspose.BarCode 在 C# 中创建条形码。请按照本指南生成条形码、调整条码高度并保存为 PNG 图像。
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: 使用 Aspose.BarCode 在 C# 中创建条形码 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何使用 Aspose.BarCode 在 C# 中创建条形码
url: /zh/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中创建条形码  

如果您需要快速 **create barcode c#** 项目，Aspose.BarCode 提供了一个流畅的 API 来处理繁重的工作。在本教程中，您将看到完整的 **barcode generator example**，学习 **how to adjust bar height**，并将结果导出为 PNG 文件。  

无论您是构建零售收银系统、生成库存标签，还是自动化运输标签，能够以编程方式更改条形码的视觉尺寸都是必不可少的。本指南假设您对 C# 有基本了解，并且拥有如 Visual Studio 2022 等开发环境。  

## 前提条件  

* .NET 6.0 SDK 或更高版本已安装。  
* Visual Studio 2022（或任何 C# IDE）。  
* 有效的 Aspose.BarCode 许可证（免费试用可用于学习）。  

您还需要将 Aspose.BarCode NuGet 包添加到项目中：

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** 如果您计划在循环中生成大量条形码，请复用同一个 `BarcodeGenerator` 实例，并仅修改变化的参数。这可以减少内存分配并提升性能。

## 如何使用 Aspose.BarCode 在 C# 中创建条形码  

以下章节将逐步演示 **barcode generator example** 的每一步。代码是自包含的；将其复制到新的控制台应用程序中并运行即可。  

### 步骤 1：导入所需的命名空间  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

这些命名空间让您能够访问 `BarcodeGenerator` 类和 `EncodeTypes` 枚举。  

### 步骤 2：初始化条形码生成器  

我们将生成一个 **Databar Omni‑Directional** 符号，用于编码 GTIN‑14 值。构造函数接受条码类型和原始数据字符串。

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 值告诉 Aspose.BarCode 使用哪种条码标准。数据字符串遵循 GS1 应用标识符格式，这在零售条码中很常见。  

### 步骤 3：设置通用条形码参数  

最常调整的两个视觉参数是：X‑dimension（窄条宽度）和整体条码高度。  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** 控制条码的密度，而 **BarHeight** 决定每根条的垂直尺寸。当您想为不同的打印介质 **change barcode height** 时，调整 **BarHeight** 正是您需要的。  

### 步骤 4：保存第一张图像（30 像素高度）  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` 方法将渲染的图像写入磁盘。文件名清晰地指示了使用的高度，这有助于比较不同的输出。  

### 步骤 5：将条码高度更改为 60 像素  

现在我们演示在运行时 **how to adjust bar height**。复用同一个 `generator` 实例；仅更改 `BarHeight` 属性。  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

由于生成器保留了所有其他设置（条码类型、数据、X‑dimension），两个 PNG 文件之间唯一的视觉差异是条的垂直尺寸。  

### 完整源代码  

将所有代码组合在一起即可得到一个简洁、可运行的程序：  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**预期输出**  

运行程序后，会在可执行文件的工作目录中生成两个 PNG 文件：  

* `DatabarBarHeight30Pixels.png` – 条码的条高为 30 像素。  
* `DatabarBarHeight60Pixels.png` – 相同的条码，但每根条的高度是前者的两倍。  

在任意查看器中打开这些图像；您会看到整体图案保持一致，而垂直尺寸发生变化，证明 **change barcode height** 操作成功。  

## 高级变体  

### 切换到其他条码类型  

如果您需要 QR 码而不是 Databar，只需替换 `EncodeTypes` 的值：  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

所有其他参数设置（X‑dimension、BarHeight）仍然适用，只要它们有意义。  

### 使用毫米单位的 `BarHeight`  

Aspose.BarCode 也支持物理单位。要设置 10 mm 的高度：  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

当您为需要精确尺寸的打印布局生成条码时，这非常方便。  

### 错误处理  

如果数据字符串不符合所选条码类型，`BarcodeGenerator` 会抛出 `ArgumentException`。请将生成逻辑放在 try‑catch 块中，以提供友好的提示信息：  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## 常见问题解答  

* **更改 BarHeight 会影响可扫描性吗？**  
  只要 X‑dimension 和整体安静区符合条码规范，条码仍然可扫描。增加高度只会使条更长；不会降低对比度。  

* **可以为单个条设置不同的高度吗？**  
  不能。`BarHeight` 属性对整个符号统一适用。若需可变高度的设计，需要在 Aspose.BarCode 范围之外实现自定义渲染。  

* **PNG 是打印的最佳格式吗？**  
  PNG 保留无损像素数据，适合屏幕显示。对于高分辨率打印任务，建议使用 `BarCodeImageFormat.Tiff` 或 `Pdf` 以保留矢量信息。  

## 结论  

现在，您已经了解如何使用 Aspose.BarCode **create barcode c#** 应用程序，看到完整的 **barcode generator example**，并掌握 **how to adjust bar height**，以满足不同布局需求。通过复用同一个生成器实例并仅修改 `BarHeight`，您可以高效地 **change barcode height**，而无需重新构建整个对象。  

接下来您可以探索：  

* 生成其他条码类型（`EncodeTypes.Code128`、`EncodeTypes.EAN13`）。  
* 导出为 SVG 或 PDF 以获得可缩放的图形。  
* 使用 Aspose.Words 或 Aspose.Cells 将条码直接嵌入 Word 或 Excel 文档。  

祝编码愉快，尽情享受 Aspose.BarCode 为您的 C# 条码项目带来的灵活性！  

## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。  

- [如何使用 Aspose.BarCode for .NET 为一维 Databar 生成并调整条码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)  
- [如何在 C# 中创建可调高度的条码 PNG 文件](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)  
- [如何在 C# 中生成条码 – 完整 Aspose.BarCode 指南](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}