---
category: general
date: 2026-10-28
description: 快速在 C# 中创建条形码图像。学习条形码生成器 C# 的使用方法，如何设置像素大小，以及如何更改 DataBar 的宽高比。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: zh
lastmod: 2026-10-28
og_description: 使用条码生成器在 C# 中创建条码图像。按照本指南设置像素大小、更改宽高比并生成 DataBar 条码。
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: 在 C# 中创建条形码图像 – 步骤指南
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: 如何使用条形码生成器在 C# 中创建条形码图像
url: /zh/python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Barcode Generator 在 C# 中创建条形码图像

如果您需要在 .NET 应用程序中**创建条形码图像**，本指南将准确展示如何操作。您将看到一个完整、可运行的示例，使用 Barcode Generator C# 库生成 DataBar 堆叠全向条码，设置像素大小，并更改宽高比。

以编程方式生成条形码可以省去外部工具的需求，并且可以直接将图像嵌入到 PDF、报告或 UI 控件中。下面的步骤还会介绍**如何设置像素大小**和**如何更改宽高比**，这两个在需要清晰、正确缩放的条形码时的常见需求。

## 前置条件

在开始之前，请确保您已具备：

* .NET 6.0 SDK 或更高版本已安装  
* 支持 C# 的 IDE（Visual Studio、Rider 或 VS Code）  
* 项目中已安装 `BarcodeGenerator` NuGet 包（例如 `GroupDocs.Barcode` 或 `Aspose.Barcode`）  

您可以使用以下命令添加该包：

```bash
dotnet add package GroupDocs.Barcode
```

> **专业提示：** 确认包的版本与目标框架匹配，以避免运行时不兼容。

## 使用 Barcode Generator C# 创建条形码图像

第一步是使用所需的条码类型和数据实例化生成器。下面的示例创建了一个**DataBar 堆叠全向**条码，适用于零售扫描场景。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 为什么每行代码都很重要

* **实例化 `BarcodeGenerator`** – 构造函数接受条码符号集 (`EncodeTypes.DatabarStackedOmniDirectional`) 和原始数据字符串。选择正确的符号集可确保扫描器能够读取该码。
* **设置 `XDimension.Pixels`** – 此属性控制最小条元素的宽度。值为 `2` 时可生成细腻的图像，在大多数屏幕上仍保持可读。若需在低分辨率打印机上使用更大的条码，可将其调高。
* **配置 `AspectRatio`** – DataBar 系列支持多种宽高比，影响高度与宽度的比例。常用值为 `15` 和 `30`；`15` 生成较短的条码，`30` 则生成更高的条码。
* **`Save` 方法** – 将生成的条码保存为 PNG 文件。如果下游系统需要其他格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Bmp`。

## 如何为不同渲染环境设置像素大小

像素大小决定条码的视觉密度。如果条码将在高 DPI 显示器上展示，您可以将像素大小提升至 `3` 或 `4`。相反，在低分辨率热敏打印机上，使用较小的像素大小（例如 `1`）可以减少墨水消耗。

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**边缘情况：** 将像素大小设置得过低（< 1）会抛出 `ArgumentOutOfRangeException`。在赋值前请务必验证该值。

## 如何在不重新创建生成器的情况下更改宽高比

更改宽高比只需更新属性；**不需要**重新实例化 `BarcodeGenerator`。这可以节省内存并提升在需要多种形状图像时的性能。

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

如果需要超过两种比例，可以遍历数组：

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## 预期输出

运行程序会生成两个 PNG 文件（如果使用循环则会更多）。在任意图像查看器中打开它们，您应能看到清晰的 DataBar 条码：

* **DatabarAspectRatio15.png** – 短而宽的条码，适用于狭窄标签空间。  
* **DatabarAspectRatio30.png** – 更高的条码，可提升在倾斜扫描器上的读取可靠性。

两张图像使用相同的像素大小（每模块 2 px），仅在高度上有所不同，演示了**如何更改宽高比**而保持其他参数不变。

## 常见陷阱及规避方法

| 症状 | 原因 | 解决方案 |
|------|------|----------|
| 条码模糊不清 | `XDimension.Pixels` 对输出分辨率设置过低 | 将像素大小至少提升至 `2`（屏幕显示），打印时提升至 `3` |
| 扫描器无法读取代码 | 为数据格式选择了错误的 `EncodeTypes` | 确认 GTIN‑14 数据与所选符号集匹配 |
| 更改宽高比时抛出 `ArgumentOutOfRangeException` | 宽高比值不在库支持范围（有效范围：15‑30） | 仅使用库文档中列出的值，或捕获异常并回退到默认值 |
| `Save` 后文件未找到 | 相对路径指向不存在的目录 | 使用绝对路径或先调用 `Directory.CreateDirectory` 确保目录存在 |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## 下一步 – 扩展条码工作流

既然您已经能够**创建条形码图像**，接下来可能想要：

* 使用 `PdfSharp` 或 `iTextSharp` 等库将 PNG **嵌入 PDF**。  
* 通过更改 `EncodeTypes` 枚举**生成其他符号**（QR、Code128、PDF417）。  
* 通过访问 `barcode.Parameters.Barcode.Image.Color` **应用颜色转换**。  
* 在 ASP.NET Core 端点中**提供图像服务**，实现 Web 应用的即时生成。

这些主题都基于本教程中讲解的核心概念，如 **barcode generator c#** 的使用、像素大小控制以及宽高比操作。

## 结论

现在，您已经掌握了如何使用 Barcode Generator 在 C# 中**创建条形码图像**、如何设置像素大小、如何更改宽高比，以及如何高效生成 DataBar 条码。完整、可运行的示例可以复制到任何 .NET 项目中，针对其他符号集进行适配，并扩展以满足实际工作流的需求。

欢迎尝试不同的 `XDimension` 值、宽高比和输出格式。如果遇到问题，请参考“常见陷阱”表格或查阅库的官方文档获取更深入的配置选项。祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，均基于本教程演示的技巧。每个资源都提供完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中创建条形码图像并调整其宽高比](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [如何在 C# 中生成自定义尺寸的条形码并保存图像](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [如何使用 C# 条码生成器创建 DataBar 条码](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}