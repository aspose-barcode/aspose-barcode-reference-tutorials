---
category: general
date: 2026-10-28
description: 在 C# 中创建条形码图像，并学习如何使用 BarcodeGenerator API 调整高度。一步步指南，帮助自定义条形码高度和更改条形高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: zh
lastmod: 2026-10-28
og_description: 在 C# 中创建条形码图像，并立即了解如何调整高度。通过此完整示例使用 BarcodeGenerator 设置自定义条形码高度。
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: 在 C# 中创建自定义高度的条形码图像 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: 在 C# 中创建自定义高度的条形码图像
url: /zh/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建自定义高度的条形码图像

如果你需要 **创建条形码图像** 并控制其尺寸，本指南将手把手教你如何实现。使用 Aspose.BarCode .NET 库，你可以生成 GS1‑Databar Omni‑Directional 条形码，然后 **调整高度** 以满足任何布局需求。

你将通过一个完整、可运行的示例程序，演示 **c# 条形码生成器**，解释每个属性的设置，并展示两种不同的输出——一种条高为 30 像素，另一种条高为 60 像素。完成后，你将能够以编程方式 **更改条形码高度**，适用于库支持的任何条形码类型。

## 前置条件

- .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.6+）
- Visual Studio 2022 或任何能够构建 C# 项目的编辑器
- Aspose.BarCode for .NET NuGet 包（`Install-Package Aspose.BarCode`）
- 对 C# 语法的基本了解

> **专业提示：** 如果你使用 CI 流水线，请将 NuGet 包添加到 `csproj` 文件中，以便构建时自动还原。

## 第一步：设置项目并导入命名空间

创建一个新的控制台项目并添加所需的 `using` 语句。命名空间让你能够访问 `BarcodeGenerator`、`EncodeTypes` 以及图像格式帮助类。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **为何重要：** 导入正确的命名空间可以避免编译时错误，并让 API 在 IntelliSense 中可被发现。

## 第二步：为 GS1‑Databar Omni‑Directional 代码初始化 **c# 条形码生成器**

构造函数接受两个参数：条形码类型 (`EncodeTypes.DatabarOmniDirectional`) 和数据字符串。数据字符串必须遵循 GS1 应用标识符格式，例如 `(01)12345678901231`。

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **说明：** `BarcodeGenerator` 对象是所有条形码相关设置的入口。拥有该实例后，你可以微调尺寸、颜色和输出格式。

## 第三步：定义通用的 X‑dimension（最窄条的像素宽度）

2 像素的 X‑dimension 对大多数屏幕显示场景来说是一个不错的起点。

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **为何要设置 X‑dimension？** 它决定条形码的整体宽度。保持一致可确保在更改条高时不会导致视觉失衡。

## 第四步：使用 30 像素条高 **创建条形码图像**

现在我们配置条高，保存第一张图像，然后再更改条高生成第二张。

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **结果：** 你会得到一张 PNG 文件，其中每根垂直条的高度为 30 像素。X‑dimension 仍为 2 像素，整体宽度保持不变。

## 第五步：**如何调整高度** – 将条高改为 60 像素

为了演示 **自定义条形码高度**，只需给同一属性赋予新值并再次保存。

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **关键洞察：** `BarHeight` 属性是可变的；无需重新创建 `BarcodeGenerator` 实例。这使得在循环或批处理过程中生成多种尺寸变得非常轻量。

## 第六步：验证输出

运行控制台程序（`dotnet run`）。执行完毕后，你应在项目的输出文件夹中看到两张 PNG 文件：

- `DatabarBarHeight30Pixels.png` – 短条（30 px）
- `DatabarBarHeight60Pixels.png` – 长条（60 px）

两张图像编码的数据相同，但视觉高度不同，这在将条形码嵌入表单、产品标签或空间受限的 UI 组件时非常有用。

![创建自定义高度的条形码图像](barcode-example.png){.align-center width="600" alt="创建自定义高度的条形码图像"}

> **提示：** 用任意图像查看器打开 PNG 文件。较高的条形码应恰好是较低条形码垂直尺寸的两倍，而水平间距保持不变。

## 第七步：常见变体和边缘情况

| 情形 | 推荐设置 |
|-----------|---------------------|
| **在高分辨率标签打印机上打印** | 使用更大的 X‑dimension（例如 4 px），并相应增大 `BarHeight`。 |
| **在低 DPI 屏幕上显示** | 将 `XDimension` 保持在 1 px，`BarHeight` 设置在 20‑40 px 之间以保证可读性。 |
| **生成 QR 码或 2‑D 条形码** | `BarHeight` 属性被忽略；请使用 `EncodeTypes.QR` 并改用 `ImageHeight`。 |
| **批量生成多种高度** | 在高度数组上循环，在循环内部调用 `Save`；无需在每次迭代时重新创建生成器。 |

### 处理无效高度

如果将 `BarHeight` 设置为非正值，库会抛出 `ArgumentOutOfRangeException`。可以使用简单的检查来防护：

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## 完整源代码（可直接复制）

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **为何可行：** 所有必需的设置（`EncodeTypes`、`XDimension`、`BarHeight`）都在每次 `Save` 调用前完成。复用同一个 `BarcodeGenerator` 实例既节省内存，又易于阅读。

## 结论

现在你已经掌握了在 C# 中 **创建条形码图像** 并使用 `BarcodeGenerator` API 精确 **更改条形码高度** 的方法。通过调整 `BarHeight.Pixels`，即可实现 **自定义条形码高度**，而无需重新构建生成器，这使得该方案非常适合动态标签创建、UI 渲染或批处理流水线。

接下来，可进一步探索 **如何调整宽度**、**添加可读文本**，或 **导出为 SVG 以实现可伸缩的网页使用** 等相关主题。相同的模式——设置属性，调用 `Save`——同样适用于这些场景，让你能够自信地扩展本示例。

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在项目中进一步运用这些技巧。每篇资源都提供完整的可运行代码示例和逐步解释，帮助你掌握更多 API 功能并探索替代实现方式。

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example – create Planet and RM4SCC barcodes with custom height](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [How to create rm4scc barcode and control its height in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}