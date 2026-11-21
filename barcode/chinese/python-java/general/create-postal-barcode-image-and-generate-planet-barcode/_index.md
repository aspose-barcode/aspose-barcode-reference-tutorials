---
category: general
date: 2026-11-20
description: 快速在 C# 中创建邮政条形码图像。了解如何生成 Planet 条码和 RM4SCC 条码，并可自定义条形样式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: zh
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中创建邮政条形码图像。本教程展示如何生成 Planet 条码、定制条形样式以及生成 RM4SCC
  图像。
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: 在 C# 中创建邮政条形码图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 创建邮政条形码图像并生成星球条码
url: /zh/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建邮政条码图像并生成行星条码

使用 Aspose.BarCode 库在 C# 中创建邮政条码图像。如果您需要为邮件应用生成行星条码或 RM4SCC 条码，本教程提供完整的、可直接运行的解决方案。

为邮政服务生成条码通常需要精确的尺寸，并且可以在实心条和空心条样式之间切换。本指南将带您完成设置输出文件夹、创建实心和空心两种 Planet 条码，以及使用相同视觉设置生成 RM4SCC 条码的全过程。完成后，您将拥有四个可直接用于邮件工作流的 PNG 文件。

## Prerequisites

在开始之前，请确保您已具备：

* 已安装 .NET 6.0 或更高版本  
* Visual Studio 2022（或您喜欢的任何 C# IDE）  
* **Aspose.BarCode** NuGet 包（`Install-Package Aspose.BarCode`）  

无需额外配置；代码仅使用默认字体和 PNG 编码器。

## Create postal barcode image – overview

该过程的核心是 `BarcodeGenerator` 类。它接受一个 `EncodeTypes` 值，用于确定条码的符号系统（例如，`EncodeTypes.Planet` 表示 Planet 条码）。配置生成器后，调用 `Save` 将图像写入文件。

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: 创建邮政条码图像示例，展示实心和空心条。*

## Step 1: Set up the output folder

首先定义一个用于保存 PNG 文件的文件夹。使用绝对路径或相对路径均可，只需确保文件夹存在，或让代码自行创建。

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

以编程方式创建文件夹可以防止在全新机器上运行教程时出现 `DirectoryNotFoundException`。

## Step 2: Generate planet barcode with filled bars

实心条的 Planet 条码是默认的视觉样式。以下代码创建条码，将 X 维度设置为 4 像素（邮政应用的常用尺寸），并保存图像。

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Why this works:**  
* `EncodeTypes.Planet` 告诉生成器使用 Planet 符号系统，这在许多邮政服务中是必需的。  
* `XDimension.Pixels` 控制每根条的宽度；4 px 可产生清晰、易于扫描的图像，同时文件大小适中。  
* `Save` 方法会根据 `BarCodeImageFormat` 枚举自动选择 PNG 编码器。

## Step 3: Generate planet barcode with empty bars

某些邮政规范更倾向于在深色背景上使用空（白色）条。只需将 `FilledBars` 设置为 `false` 即可实现。

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** 当 `FilledBars` 为 `false` 时，生成器会在背景色（默认白色）上绘制条码，而在前景色（默认黑色）上绘制空白。如果需要不同的配色方案，请调整 `Parameters.Barcode.ForeColor` 和 `BackColor`。

## Step 4: Generate RM4SCC barcode with filled bars

RM4SCC 是英国使用的另一种邮政符号系统。创建步骤与 Planet 示例相同，唯一变化是 `EncodeTypes` 的取值。

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**What to expect:** 生成的 PNG 显示符合英国邮政指南的紧凑型 RM4SCC 条码。由于 X 维度相同，图像尺寸与 Planet 条码相似。

## Step 5: Verify the generated images

运行程序后，打开 `Barcodes` 文件夹中的四个文件。您应看到：

* `PostalPlanetFilledBars.png` – 深色条码在浅色背景上  
* `PostalPlanetEmptyBars.png` – 浅色条码在深色背景上（反转）  
* `PostalRM4SCCFilledBars.png` – 标准 RM4SCC 图案  

如果任何图像出现失真，请检查以下内容：

* **X‑dimension** – 过小（< 2 px）会导致模糊，过大（> 10 px）可能超出标签尺寸限制。  
* **Data string** – 值 `"123456"` 必须符合所选符号系统的长度要求（Planet 需要 6 位数字，RM4SCC 也需要 6 位数字）。  
* **Folder permissions** – 确保应用程序对输出目录具有写入权限。

## Common variations and edge cases

| Scenario | Adjustment |
|----------|------------|
| **Different barcode data** | 将 `"123456"` 替换为任意有效的数字字符串。对于 Planet，长度必须恰好为 6 位；RM4SCC 也同样要求 6 位。 |
| **Custom colors** | 设置 `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` 并将 `BackColor = System.Drawing.Color.LightYellow;`。 |
| **Higher resolution** | 将 `XDimension.Pixels` 提升至 6 或 8，以获得更大的打印尺寸。 |
| **Other image formats** | 在 `Save` 调用中使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 |
| **Batch generation** | 对字符串集合进行循环，在循环内部调用相同的生成器逻辑，并复用 `outputFolder` 路径。 |

## Full, runnable example

将以下代码复制到新的 C# 控制台项目中。它在 .NET 6.0 下编译，并自动生成所有四个条码图像。



## What Should You Learn Next?

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 的其他功能并探索在项目中实现的替代方案。每个资源都包含完整的可运行代码示例和逐步说明。

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}