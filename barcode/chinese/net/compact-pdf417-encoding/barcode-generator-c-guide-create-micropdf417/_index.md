---
category: general
date: 2026-09-29
description: Barcode generator C# 指南展示了如何生成 MicroPdf417 条码、更改尺寸、设置列数，并仅用几行代码自定义条码大小。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: zh
lastmod: 2026-09-29
og_description: Barcode 生成器 C# 指南展示了如何生成 MicroPdf417 条码、修改尺寸、设置列数，并在几行代码内自定义条码大小。
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: 条码生成器 C# 指南 – 创建和自定义 MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 条形码生成器 C# 指南：创建 MicroPdf417
url: /zh/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成器 C# 指南：创建 MicroPdf417

如果您需要一个用于 .NET 项目的 **barcode generator C#**，本教程将手把手教您从零创建 MicroPdf417 条形码。您将学习 **如何生成条形码**、更改尺寸、设置列数，以及轻松 **自定义条形码大小**。

MicroPdf417 是一种紧凑的 2‑D 符号，适用于标记小部件、票据或库存标签。阅读完本指南后，您将拥有一个完整的可运行控制台应用程序，能够输出条形码的 PNG 图像，并且了解每个参数如何影响最终尺寸。

## 前置条件

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7+）
* 支持 C# 的 IDE（Visual Studio、VS Code、Rider 等）
* **GroupDocs.Barcode** NuGet 包 – 使用以下方式安装  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

无需额外的外部工具；该库负责编码、渲染和文件保存。

## Barcode generator C#: 初始化生成器

第一步是创建 `BarcodeGenerator` 的实例，并指定符号类型（`EncodeTypes.MicroPdf417`）以及要编码的数据。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**为什么这很重要：**  
`BarcodeGenerator` 是所有条形码操作的入口点。构造函数将所选的 **EncodeTypes**（MicroPdf417）绑定到原始数据字符串。库会自动处理诸如 “Å” 和 “©” 的 Unicode 字符，因此您无需额外的编码逻辑。

## 如何更改条形码的尺寸

条形码的可读性在很大程度上取决于模块宽度（X 维度）。将其设置为更大的像素数会使条形更宽，图像更易于扫描，尤其是在低分辨率显示器上。

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**解释：**  
`XDimension.Pixels` 控制单个条形码模块的宽度。默认值为 1 像素，在高 DPI 显示器上可能显得太细。将其提升至 2 像素会使整体宽度加倍，而不会影响编码数据。

**提示：** 如果您计划以 300 dpi 打印条形码，3 或 4 像素的值通常能在尺寸和扫描可靠性之间取得最佳平衡。

## 如何设置列数以控制尺寸

MicroPdf417 允许您指定列数（最多 4 列）。列数少会产生更高的条形码；列数多则使其更宽但更短。调整此值是 **自定义条形码大小** 的主要方式。

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**为什么这样有效：**  
`Pdf417.Columns` 属性在所有基于 PDF417 的符号中共享，包括 MicroPdf417。将其设置为最大值（4）会将数据分布在最宽的布局上，从而降低整体高度。如果需要更紧凑的高度，可将列数降低至 2 或 3。

**边缘情况：** 当数据字符串较长时，库可能会自动增加行数以容纳内容，而不受列数限制。将负载保持在 50 个字符以下，以获得可预测的尺寸。

## 为不同输出自定义条形码尺寸

除了 X 维度和列数之外，您还可以通过选择合适的图像格式和 DPI 来影响最终图像尺寸。PNG 是无损的，适合网页显示，而 BMP 或 TIFF 可能更适合高质量打印。

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

如果需要更高的 DPI，您可以显式设置：

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**结果：** 保存的 PNG 文件包含清晰的 MicroPdf417 条形码，遵循您配置的尺寸。使用任意图像查看器打开文件即可验证视觉大小。

### 预期输出

运行程序会生成名为 **MicroPdf417.png**（如果设置了 DPI，则为 **MicroPdf417_300dpi.png**）的文件。条形码将类似下图所示：

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*替代文字:* *Barcode generator C# 输出显示 MicroPdf417 PNG*

使用标准的 2‑D 条形码阅读器扫描该图像会返回原始字符串 `Åspóse.Barcóde©`。

## 完整源代码，快速复制粘贴

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

将代码复制到新的控制台项目中，恢复 NuGet 包，并运行 `dotnet run`。控制台会确认图像位置，您将在项目文件夹中看到生成的条形码。

## 常见问题与故障排除

| 问题 | 答案 |
|----------|--------|
| **如果条形码看起来模糊怎么办？** | 增加 `XDimension.Pixels` 或 DPI（`Parameters.Image.DpiX/Y`）。两者都会放大模块并提升视觉清晰度。 |
| **我可以使用不同的图像格式吗？** | 可以。将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Bmp` 或 `Tiff`。PNG 仍是无损质量的最安全选择。 |
| **我的数据包含表情符号——它们会被编码吗？** | MicroPdf417 支持 UTF‑8，因此大多数表情符号能够正确编码。如果遇到错误，请确认字符串已正确规范化（`System.Text.Encoding.UTF8`）。 |
| **如何生成其他符号？** | 将 `EncodeTypes.MicroPdf417` 更改为 `EncodeTypes` 中的其他任意值（ |

## 接下来应该学习什么？

以下教程涵盖与本指南紧密相关的主题，基于本指南展示的技术进行扩展。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方案。

- [如何在 C# 中生成条形码图像 – MicroPdf417 指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [如何在 C# 中使用自定义尺寸生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}