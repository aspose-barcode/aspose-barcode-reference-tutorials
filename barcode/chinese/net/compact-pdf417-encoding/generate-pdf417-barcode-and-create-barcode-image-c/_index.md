---
category: general
date: 2026-10-08
description: 在 C# 中生成 PDF417 条码，并学习如何使用 Aspose.BarCode 高效生成 PDF417 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: zh
lastmod: 2026-10-08
og_description: 使用 C# 生成 PDF417 条码，提供一步步指南。学习如何生成 PDF417 并将条码图像保存为 PNG。
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: 在 C# 中生成 PDF417 条码并创建条码图像
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: 生成 PDF417 条码并创建条码图像（C#）
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成 PDF417 条形码并创建条形码图像（C#）

如果您需要在 .NET 应用程序中 **生成 PDF417 条形码**，本教程将手把手教您如何实现。您将看到一个完整、可运行的示例，演示如何创建条形码、定制布局并将结果保存为 PNG 图像。

生成 PDF417 条形码是运输标签、登机牌和库存系统的常见需求。阅读完本指南后，您将能够 **生成 PDF417**，并对尺寸和布局进行细粒度控制，同时学会 **创建条形码图像 C#** 文件，以便在 UI 中显示或发送至打印机。

## 前置条件

- .NET 6.0 或更高版本（代码同样适用于 .NET Framework 4.7.2+）
- Visual Studio 2022 或任意支持 C# 的 IDE
- Aspose.BarCode for .NET（免费试用版或正式授权版）  
  通过 NuGet 安装：

```bash
dotnet add package Aspose.BarCode
```

无需额外配置；库内部已处理 PNG 编码。

## 第一步：创建项目并导入命名空间

新建一个控制台项目并添加必要的 `using` 指令。下面的代码块包含了编译示例所需的全部内容。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*此步骤的重要性*：导入 `Aspose.BarCode.Generation` 命名空间后，您即可使用 `BarcodeGenerator`、`EncodeTypes` 以及用于定制条形码的参数对象。

## 第二步：使用所需文本生成 PDF417 条形码

在 `Main` 方法中，实例化 `BarcodeGenerator` 并传入 `EncodeTypes.Pdf417`。构造函数接受条形码类型和要编码的文本。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*说明*：`EncodeTypes.Pdf417` 告诉库生成 PDF417 符号。字符串 `"Layout demo"` 将作为条形码中编码的数据负载。

## 第三步：使用 X‑dimension 微调条形码尺寸

X‑dimension 控制单个模块（最小的黑白方块）的宽度。以像素为单位设置可精确控制最终图像尺寸。

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*此设置的意义*：较小的 X‑dimension 会生成更紧凑的条形码，适用于标签或 UI 元素空间受限的场景。

## 第四步：自定义 PDF417 布局（列数和行数）

PDF417 允许指定列数和行数。调整这些值会改变条形码的宽高比。

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*说明*：使用 4 列 9 行时，条形码的高度大于宽度，符合许多票据打印格式的要求。

## 第五步：将生成的条形码保存为 PNG 图像

最后，将条形码写入文件。`BarCodeImageFormat.Png` 枚举确保使用无损压缩。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*这里发生了什么*：`Save` 会在磁盘上创建图像文件。如需其他格式，可将 `BarCodeImageFormat.Png` 替换为 `Jpeg` 或 `Bmp`。

### 完整示例（单块代码）

下面是完整的可直接运行的程序。将 `YOUR_DIRECTORY` 替换为您机器上的实际文件夹路径。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

运行程序（`dotnet run`）并打开生成的 `LayoutPdf417.png`。您应当看到一个清晰的 PDF417 条形码，编码文本为 *Layout demo*。

![Generated PDF417 barcode example](image-placeholder.png){: .responsive-img alt="已保存为 PNG 的 PDF417 条形码示例"}

*预期输出*：一个约 150 × 300 像素的 PNG 文件（尺寸随 X‑dimension 而变化），其中包含可扫描的 PDF417 条形码。

## 常见变体与边缘情况

| 场景 | 代码适配方式 |
|----------|----------------------|
| **不同的数据负载** | 将 `BarcodeGenerator` 的第二个参数（`"Layout demo"`）改为任意字符串，最长可达 1 800 个字符。 |
| **更高分辨率** | 增大 `XDimension.Pixels`（例如 `4`），或通过 `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;` 设置分辨率。 |
| **透明背景** | 使用 `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`。 |
| **在 Windows Forms PictureBox 中嵌入** | 替代 `Save`，调用 `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`。 |
| **错误处理** | 将生成代码包装在 `try…catch` 块中，以捕获不支持字符时抛出的 `BarCodeException`。 |

## 专业技巧

- **验证条形码**：保存后，可使用条形码扫描 SDK 加载 PNG，确保数据与原始字符串一致。
- **性能优化**：对多个条形码复用同一个 `BarcodeGenerator` 实例，可降低分配开销。
- **安全性**：若编码数据包含敏感信息，建议在传递给生成器前先进行加密。

## 结论

现在您已经掌握了在 C# 中 **生成 PDF417 条形码** 并 **创建条形码图像 C#** 文件的完整流程，能够满足自定义布局需求。完整示例展示了如何初始化生成器、调节尺寸与布局以及保存为 PNG。接下来，您可以探索颜色定制、嵌入徽标或批量生成条形码以实现批量打印等高级功能。

---

*后续步骤*：  
- 使用相同的 `BarcodeGenerator` 类尝试其他符号（Code128、QR）。  
- 学习使用 Aspose.BarCode 的 `BarCodeReader` 读取 PDF417 条形码。  
- 将生成的 PNG 集成到 ASP.NET Core MVC 视图中，实现即时条形码渲染。

## 接下来您应该学习什么？

以下教程与本指南紧密相关，帮助您进一步深化技术并探索替代实现方式。每篇资源均提供完整可运行的代码示例和逐步说明。

- [如何在 C# 中使用 Aspose 保存条形码并生成 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Aspose 完整指南：生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [在 C# 中使用自定义尺寸生成 PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}