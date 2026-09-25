---
category: general
date: 2026-08-22
description: 条码生成器 C# 教程展示了如何生成条码 PNG 文件、创建 DataBar 条码以及仅需几步即可调整条码高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: zh
lastmod: 2026-08-22
og_description: 条形码生成器 C# 指南将手把手教您如何生成条形码 PNG、创建 DataBar 条形码，并高效调整条形码高度。
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: 条形码生成器 C# – 创建 DataBar 条码并调整高度
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# 条码生成器创建 DataBar 全向条码
url: /zh/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条码生成器创建 DataBar Omni‑directional 条码

如果您需要一个能够生成高质量 PNG 图像的 **barcode generator C#**，本指南将满足您的需求。您将学习如何生成条码 PNG 文件、创建 DataBar Omni‑directional 条码，并在不离开 IDE 的情况下调整条码高度。

以编程方式生成条码可以省去使用图形编辑器的手动步骤。完成本教程后，您将拥有两个 PNG 文件——一个条码高度为 30 像素，另一个为 60 像素——可直接用于发票、标签或库存系统。

**Prerequisites**

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7+）
- 引用 `Aspose.BarCode` NuGet 包（或任何提供类似 API 的库）
- 对 C#、Visual Studio 或您喜欢的 IDE 有基本了解

---

## 步骤 1：设置 C# 条码生成器项目

创建 **barcode generator C#** 实例是第一步。构造函数接受两个参数：条码类型 (`EncodeTypes.DatabarOmniDirectional`) 和数据负载。在本例中，负载遵循 GS1 应用标识符格式，用于 14 位 GTIN。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Why this matters:** `EncodeTypes.DatabarOmniDirectional` 枚举告诉库渲染一种可以从任意方向读取的 DataBar，这对于小型零售标签尤为理想。

---

## 步骤 2：定义模块尺寸（X‑dimension）

X‑dimension 控制单个条码模块的宽度。将其设为 2 像素可在保持文件体积小的同时获得清晰、易读的图像。

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** 如果空间受限需要更紧凑的条码，可将数值降低到 1 像素，但请使用扫描仪测试可读性。

---

## 步骤 3：生成高度为 30 像素的首个 PNG

条码高度决定条纹的垂直长度。30 像素的高度是标准标签的常用默认值。

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

文件 `DatabarBarHeight30Pixels.png` 现在包含一个 **generate barcode PNG**，可直接用于网页或按需打印。

---

## 步骤 4：将条码高度调整为 60 像素并保存第二个 PNG

更改条码高度只需为同一属性赋予新值。这演示了生成器的 **adjust barcode height** 能力。

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

现在您拥有 `DatabarBarHeight60Pixels.png`，非常适合需要从远距离扫描的较大包装。

**预期输出**

- `DatabarBarHeight30Pixels.png` – 紧凑的 DataBar Omni‑directional 条码，30 px 高。
- `DatabarBarHeight60Pixels.png` – 同一条码，高度加倍以提升可视性。

两张图片均为 PNG 格式，保持无损质量，并在需要时支持透明度。

---

## 如何以不同格式生成条码 PNG 文件

虽然本教程聚焦于 PNG，`Save` 方法同样接受 `Jpeg`、`Bmp`、`Svg` 等其他格式。若要 **how to generate barcode** 为其他格式的文件，只需将 `BarCodeImageFormat.Png` 替换为相应的枚举值：

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

在需要可随比例缩放且不出现像素化的矢量图时，选择 SVG 非常方便。

---

## 创建 DataBar 条码 图像时的常见陷阱

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| 条码看起来模糊 | X‑dimension 对目标分辨率太低 | 将 `XDimension.Pixels` 提高到 3 或 4 |
| 扫描仪无法读取代码 | 条码高度对扫描仪光学系统太短 | 使用至少 30 像素的高度或遵循扫描仪规格 |
| 数据字符串被拒绝 | GS1 格式不正确 | 确保字符串以正确的应用标识符开头，例如 GTIN‑14 的 `(01)` |

提前解决这些问题可在将条码集成到生产流水线时节省时间。

---

## 高级技巧：在多个条码中复用同一生成器

如果需要为一批产品 **generate barcode PNG**，可复用同一个 `BarcodeGenerator` 实例，仅更新 `CodeText` 属性：

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

此模式可最大限度减少对象创建开销，使代码保持简洁。

---

## 结论

您现在拥有完整的 **barcode generator C#** 工作流，能够 **creates DataBar barcodes**、**generates barcode PNG** 文件，并通过单一属性更改 **adjust barcode height**。示例涵盖了从项目设置到处理边缘情况的全部内容，帮助您自信地将条码创建集成到任何 .NET 应用中。

**下一步**

- 探索其他条码符号（`EncodeTypes.QR`、`EncodeTypes.Code128`），以扩展解决方案的适用范围。  
- 将生成器与 ASP.NET Core 结合，通过 API 端点实时提供条码。  
- 试验颜色选项（`generator.Parameters.Barcode.ForeColor`），实现品牌化效果。

祝编码愉快，愿您的扫描始终快速顺畅！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在项目中进一步掌握 API 功能并探索替代实现方式。每篇资源均提供完整可运行的代码示例和逐步解释。

- [如何使用 Aspose.BarCode for .NET 生成并调整一维 Databar 的条码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [使用 Aspose.BarCode .NET API 生成一维 Databar 2D 条码](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 – 步骤指南](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}