---
category: general
date: 2026-08-25
description: 使用 C# 创建 RM4SCC 条码，提供逐步代码，并学习如何设置条码高度以实现精确尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: zh
lastmod: 2026-08-25
og_description: 使用 Aspose.BarCode 在 C# 中创建 RM4SCC 条码，并学习如何在 .NET 应用程序中设置条码高度，以实现精确控制。
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: 创建 RM4SCC 条码 C# – 条码高度设置指南
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: 使用 C# 创建 RM4SCC 条码并设置条码高度
url: /zh/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 RM4SCC 条形码 C# 并设置条码高度

使用 Aspose.BarCode 库快速创建 RM4SCC 条形码 C#。本教程展示了 **如何设置条码高度** 并自定义其他视觉属性，以便条码精确匹配您的布局。

您将看到一个完整的、可直接运行的控制台程序，它会生成三个 PNG 文件：

* 一个默认高度的 Planet 条形码（用于对比）  
* 一个手动高度为 100 像素的 RM4SCC 条形码  
* 一个条纹为空（未填充）的 Planet 条形码  

示例假设您已经安装了 Visual Studio 2022（或任何 .NET 6+ IDE）并拥有有效的 Aspose.BarCode for .NET 许可证或评估版。

## 前提条件

| 要求 | 原因 |
|-------------|--------|
| .NET 6 SDK (or later) | Provides the runtime for the console app |
| Aspose.BarCode for .NET NuGet package | Supplies `BarcodeGenerator`, `EncodeTypes`, and image export APIs |
| Basic C# knowledge | Needed to understand the code flow |

使用以下命令安装 NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

> **专业提示：** 如果在没有许可证的情况下运行代码，生成的图像会带有小的 Aspose 水印。

## 步骤 1：设置项目结构

创建一个新的控制台项目并添加必要的 `using` 指令：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

`using` 语句让您能够访问条码生成器类和 PNG 格式枚举。

## 步骤 2：定义输出文件夹

选择一个文件夹用于保存 PNG 文件。调用 `Save` 之前必须确保该文件夹已存在。

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

以编程方式创建目录可以避免在全新机器上运行代码时出现 *FileNotFoundException*。

## 步骤 3：生成默认高度的 Planet 条形码（基准）

Planet 条形码不是本指南的重点，但它提供了一个可视化基准，以便与手动设置大小的 RM4SCC 条形码进行比较。

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*为什么这很重要：*  
`XDimension` 决定单根条的宽度。保持它不变而更改 `BarHeight` 可以单独观察高度的影响。

## 步骤 4：**创建 RM4SCC 条形码 C#** – 设置手动高度

现在我们来完成主要任务：**创建 RM4SCC 条形码 C#** 并显式控制其高度。

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### 如何设置条码高度

`BarHeight` 属性位于 `Parameters.Barcode` 下。它接受一个 `float` 值，单位可以是 **像素**、**点** 或 **毫米**，具体取决于您选择的 `Unit`（`Pixels`、`Points`、`Millimeters`）。示例中使用 `Pixels`，因为输出格式为 PNG。

如果需要以毫米为单位的高度，请先切换单位：

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## 步骤 5：生成条纹为空（未填充）的 Planet 条形码

此步骤演示另一个有用的属性——`FilledBars`。将其设为 `false` 可创建“空心”条形码，适用于设计需求。

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## 完整、可运行的程序

将以下代码复制到 `Program.cs` 中。构建并运行项目；三个 PNG 文件将出现在 `GeneratedBarcodes` 文件夹中。



## 接下来应该学习什么？

以下教程涵盖了与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式，每篇资源均提供完整的可运行代码示例和逐步说明。

- [如何创建 code128 条形码 Java 并设置条高度](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [如何使用 Aspose.BarCode 为 .NET 创建 Code 16K 条形码的静区](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 创建 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}