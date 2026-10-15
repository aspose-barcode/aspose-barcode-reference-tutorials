---
category: general
date: 2026-10-12
description: 如何在 C# 中使用 Aspose.BarCode 设置条形码高度并生成 DataBar 条码。请按照一步一步的指南查看完整代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: zh
lastmod: 2026-10-12
og_description: 如何在 C# 中设置条形码高度并使用 Aspose.BarCode 生成 DataBar 条码。了解完整代码、每一步的意义以及如何更改条形码高度。
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: 如何在 C# 中设置条码高度并生成 DataBar 条码
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何设置条码高度，在 C# 中生成 DataBar 条码
url: /zh/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何设置条形码高度，在 C# 中生成 DataBar 条形码

如果您需要 **如何设置条形码** 的尺寸（以编程方式），本指南将展示完整步骤。您将学习如何生成 DataBar Omni‑directional 条形码、调整其高度，并将两个版本保存为 PNG 文件。

在收据、产品标签或移动屏幕中集成条形码时，改变条形码的条高是常见需求。下面的示例使用 Aspose.BarCode 库，该库支持完整的 GS1 DataBar 符号系列。

## 您将实现的目标

完成本教程后，您将能够：

* **如何设置条形码** 高度，以生成 DataBar Omni‑directional 条形码  
* **生成条形码 c#** 代码，创建两个不同高度的图像  
* 理解 **如何创建 databar** 符号以及条高为何重要  
* 在不重新创建生成器的情况下应用 **更改条形码高度** 的逻辑  

无需任何外部工具，只需 Aspose.BarCode NuGet 包和 .NET 6+ 运行时。

## 前置条件

* 已安装 .NET 6 SDK 或更高版本  
* Visual Studio 2022（或任意 C# 编辑器）  
* Aspose.BarCode for .NET – 通过 `dotnet add package Aspose.BarCode` 安装  

> **专业提示：** 如果没有商业授权密钥，可使用 Aspose 的免费试用许可证；API 的使用方式完全相同。

## 第一步：安装 Aspose.BarCode 包

在项目文件夹的终端中运行：

```bash
dotnet add package Aspose.BarCode
```

该包会添加 `Aspose.BarCode` 命名空间，其中包含我们将用于 **生成条形码 c#** 图像的 `BarcodeGenerator` 类。

## 第二步：创建 DataBar 条形码生成器

设置 **如何设置条形码** 参数的第一步是实例化 `BarcodeGenerator`，并指定所需的符号类型和数据字符串。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*原因说明：* `EncodeTypes.DatabarOmniDirectional` 生成一种紧凑的全向 DataBar，可从任意角度扫描——非常适合小标签。

## 第三步：设置通用条形码参数（包括初始条高）

现在我们在保存第一张图像之前，回答 **如何设置条形码** 的 X‑dimension 和条高。

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension 控制每根条的整体宽度；2 像素的设置在大多数屏幕上能够产生清晰、可读的图像。后续的 **更改条形码高度** 步骤将复用同一个生成器，从而节省时间和内存。

## 第四步：保存第一张条形码图像（30 像素高）

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

文件 `DatabarHeight30.png` 现在包含一张条高为 30 像素的 DataBar 条形码。

## 第五步：仅将条高改为 60 像素

为了演示 **更改条形码高度**，我们只修改 `BarHeight` 属性。其他设置保持不变，这是从单一生成器生成多种尺寸的最高效方式。

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## 第六步：保存第二张条形码图像（60 像素高）

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

现在您拥有两张 PNG 文件，条高不同但数据和 X‑dimension 完全相同。

## 完整、可运行的示例

下面是完整的程序代码，您可以直接复制粘贴到新建的控制台应用程序（`dotnet new console`）中并立即运行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### 预期输出

运行程序后，会在可执行文件的工作目录生成两个文件：

* `DatabarHeight30.png` – 条高为 30 像素的 DataBar 条形码。  
* `DatabarHeight60.png` – 同一条形码，但每根条的高度是前者的两倍。

两张图像均可在任意图像查看器中打开，或直接嵌入 PDF、HTML 页面或打印标签中。

## 为什么调整条高很重要

* **扫描可靠性：** 某些扫描器在低分辨率介质上对非常短的条形不友好，增加条高可提升检测率。  
* **设计约束：** 移动应用可能需要紧凑的条形码（30 px），而打印收据可能需要更大的条码（60 px）。  
* **合规要求：** 某些行业规定 GS1 DataBar 符号必须满足最低条高。

通过复用同一个 `BarcodeGenerator` 实例，您可以避免重复解析数据字符串的开销，这在高吞吐量环境中尤为有益。

## 常见变体和边缘情况

| 场景 | 推荐的调整 |
|-----------|-------------------|
| 需要不同的 X‑dimension | 在第一次 `Save` 之前更改 `XDimension.Pixels`。 |
| 想使用其他符号（例如 DataBar Stacked） | 在构造 `BarcodeGenerator` 时使用 `EncodeTypes.DatabarStacked`。 |
| 必须将条形码嵌入 PDF | 使用 `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` 并将流添加到 PDF 库中。 |
| 在 .NET Framework 4.6 上运行 | 同样的代码可以工作，只需引用相应的 Aspose.BarCode 程序集。 |

## 可靠条形码生成的专业技巧

* **缓存生成器**，在对相同数据但不同尺寸生成大量条形码时使用。  
* **

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整可运行的代码示例和逐步解释。

- [如何使用 Aspose.BarCode for .NET 为一维 DataBar 生成并调整条形码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何使用 C# 和 Aspose.BarCode 创建 DataBar PNG 图像](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [如何在 C# 中生成条形码、设置自定义尺寸并保存图像](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}