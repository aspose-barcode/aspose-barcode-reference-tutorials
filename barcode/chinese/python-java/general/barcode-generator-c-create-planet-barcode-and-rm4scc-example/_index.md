---
category: general
date: 2026-08-03
description: 使用 Aspose.BarCode 的 C# 条形码生成器教程，演示如何创建 Planet 条码，设置 X 维度，并保存为 PNG 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: zh
lastmod: 2026-08-03
og_description: Barcode 生成器 C# 教程将带您一步步创建 Planet 条码、调整 X 维度，并使用 Aspose.BarCode 将其保存为
  PNG。
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: 条形码生成器 C# – 逐步创建 Planet 条码
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 条码生成器 C# – 创建 Planet 条码和 RM4SCC 示例
url: /zh/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – 创建 Planet 条码和 RM4SCC 示例

如果您需要一个能够生成邮政专用符号的 **barcode generator C#**，本指南将准确展示如何使用 Aspose.BarCode **创建 Planet 条码** 图像。您将看到如何配置 X‑dimension、生成匹配的 RM4SCC 条码，并将两者保存为 PNG 文件——只需几个简明步骤。

本教程涵盖在 .NET 6 或更高版本上运行代码所需的全部内容，解释每个设置的意义，并指出常见的陷阱，如模块宽度不正确或缺少目录权限。完成后，您将拥有两张符合 Planet 和 RM4SCC 标准的可直接打印的条码图像。

## 前提条件

* .NET 6 SDK（或任何 Aspose.BarCode 支持的 .NET 版本）
* Visual Studio 2022 或您喜欢的任何 C# IDE
* 对 **Aspose.BarCode** 的 NuGet 引用（`Install-Package Aspose.BarCode`）
* 对计划存放 PNG 文件的文件夹的写入权限

无需额外的外部服务；该库在本地完成所有编码。

## 步骤 1：初始化 barcode generator C# 对象

第一步是创建 `BarcodeGenerator` 的实例。构造函数接受条码符号（`EncodeTypes.Planet`）和要编码的数据。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*为什么这一步？*  
`BarcodeGenerator` 是您生成的每个条码的入口点。选择 `EncodeTypes.Planet` 告诉库遵循许多邮政服务使用的 ISO/IEC 24723 规范。

## 步骤 2：为 Planet 条码设置 X‑dimension（模块宽度）

X‑dimension 定义单个条码模块（最小的条或空格）的宽度。**4 像素**的值对大多数标签打印机效果良好。

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*为什么这很重要*  
如果模块太窄，条码可能无法读取；如果太宽，标签尺寸会不必要地增大。调整 `Pixels` 可让您针对特定打印机分辨率微调条码。

## 步骤 3：将 Planet 条码保存为 PNG 图像

Aspose.BarCode 会根据所选符号自动计算条码高度，因此您只需指定文件路径和格式。

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*提示*  
将 `YOUR_DIRECTORY` 替换为您机器上存在的绝对或相对路径。如果目录不存在，`Save` 方法会抛出 `DirectoryNotFoundException`。

**预期输出** – 一个 PNG 文件，外观类似下图（此处未显示实际图像，但您会看到带有数值负载 `123456` 的经典 Planet 条码）。

## 步骤 4：为 RM4SCC 条码初始化第二个生成器

许多邮政系统要求在同一邮件上同时使用 Planet 和 RM4SCC 符号。为 RM4SCC 符号创建一个新的 `BarcodeGenerator` 实例。

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*为什么需要单独的实例？*  
每种符号都有自己的一套参数。重复使用同一个生成器可能会无意中保留设置（如 X‑dimension），这些设置对第二个条码并不理想。

## 步骤 5：为 RM4SCC 条码配置 X‑dimension

RM4SCC 也遵循 X‑dimension 设置，因此我们使用相同的像素宽度以保持视觉一致性。

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*专业提示*  
如果需要更高的条码（例如用于更大的标签），您也可以设置 `Height.Pixels`。不设置则让库自动计算理想高度。

## 步骤 6：将 RM4SCC 条码保存为 PNG 图像

最后，将 RM4SCC 条码保存到磁盘。

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

现在您拥有两个 PNG 文件——`PostalPlanetBarHeightNone.png` 和 `PostalRM4SCCBarHeightNone.png`——可嵌入邮件标签、打印在信封上，或发送给第三方打印服务。

## 可选：调整高度或使用其他图像格式

如果您的工作流需要特定的条码高度或不同的图像格式（例如 JPEG 或 BMP），可以在调用 `Save` 之前修改参数：

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**边缘情况** – 当您设置自定义高度时，请确保该值符合 ISO 标准要求的最小高度；否则条码可能无法通过验证。

## 常见陷阱及其避免方法

| 陷阱 | 出现原因 | 解决办法 |
|---------|----------------|-----|
| `DirectoryNotFoundException` | 目标文件夹不存在或拼写错误。 | 先创建文件夹，或使用 `Path.Combine` 与 `Environment.CurrentDirectory`。 |
| 低分辨率打印机上条码不可读 | X‑dimension 对打印机 DPI 来说太小。 | 将 `XDimension.Pixels` 提升至 5 – 6（针对 203 dpi 打印机），或使用样本标签进行测试。 |
| 使用了错误的符号 | 传入 `EncodeTypes.Code128` 而非 `EncodeTypes.Planet`。 | 再次确认 `EncodeTypes` 枚举值与所需的邮政标准匹配。 |
| `Parameters` 空引用 | 使用了 Aspose.BarCode 的旧版本，API 不同。 | 升级到最新的 NuGet 包（v23.12 或更高）。 |

## 完整可运行示例

下面是完整的程序，您可以复制、粘贴并运行。它包含 `using` 语句、错误处理以及解释每行代码的注释。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

运行程序后，会在可执行文件旁创建一个 `Barcodes` 文件夹，并将两个 PNG 文件放入其中。使用任意图像查看器打开以验证输出。

## 结论

您现在拥有一个 **barcode generator C#** 解决方案，能够 **创建 Planet 条码** 图像、调整 X‑dimension 以实现最佳打印，并生成匹配的 RM4SCC 条码——仅需少量代码。该方法适用于 .NET 6+，仅需 Aspose.BarCode NuGet 包，并可通过更改 `EncodeTypes` 值扩展到其他符号，如 Code128、QR 或 DataMatrix。

### 接下来做什么？

* 尝试不同的 `XDimension.Pixels` 值，以匹配您打印机的 DPI。  
* 通过更改 `BarCodeImageFormat` 枚举，将条码生成其他格式（PDF、SVG）。  
* 使用如 **SkiaSharp** 的图形库将两个 PNG 文件合并为单个标签。  
* 探索完整的 Aspose.BarCode API，获取诸如校验和验证或自定义字体等高级功能。

欢迎将代码改编用于批处理，或集成到按需返回条码图像的 ASP.NET Core Web 服务中。祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方法。

- [创建条码 PNG – DataMatrix 长宽比 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [如何使用 DataMatrix C40 保存 PNG – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – 使用 Aspose.BarCode 为 .NET 定制 Code 16K 条码长宽比](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}