---
category: general
date: 2026-08-09
description: 快速在 C# 中生成 PDF417 条码。了解如何使用 BarcodeGenerator API 通过紧凑模式、列控制和 PNG 输出生成
  PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: zh
lastmod: 2026-08-09
og_description: 在 C# 中生成 PDF417 条码的简明示例。本指南展示如何配置紧凑模式、设置列数，并将结果保存为 PNG 图像。
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: 在 C# 中生成 PDF417 条形码 – 完整教程
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: 在 C# 中生成 PDF417 条码 – 步骤指南
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中生成 PDF417 条形码 – 步骤指南

如果您需要在 .NET 应用程序中**生成 PDF417 条形码**，本教程将向您展示具体的实现方法。您将看到一个完整、可运行的程序，它可以创建紧凑的 PDF417 条形码、定制其尺寸，并将图像保存为 PNG 文件。

生成 PDF417 条形码是移动票务、库存跟踪和文档安全等场景的常见需求。本指南涵盖关键的配置选项，解释每个设置的意义，并提供实用的真实场景使用技巧。

## 前置条件

在开始之前，请确保您具备以下条件：

* .NET 6.0 SDK 或更高版本已安装  
* C# IDE，例如 Visual Studio 2022 或 Visual Studio Code  
* **Aspose.BarCode for .NET** NuGet 包（版本 23.10 或更高）  

您可以使用以下 CLI 命令安装该包：

```bash
dotnet add package Aspose.BarCode
```

下面的代码假设已引用该包，并且您对输出目录拥有写入权限。

## 步骤 1：设置项目并导入命名空间

创建一个新的控制台项目并添加所需的 `using` 指令。这些命名空间公开 `BarcodeGenerator` 类和图像格式枚举。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**为什么这很重要：** 导入正确的命名空间可确保编译器能够定位 `BarcodeGenerator` 类型和 `BarCodeImageFormat` 枚举。缺少命名空间会导致编译错误，从而中断条形码生成过程。

## 步骤 2：使用 PDF417 编码初始化 `BarcodeGenerator`

`BarcodeGenerator` 构造函数接受两个参数：条形码符号系统 (`EncodeTypes.Pdf417`) 和要编码的文本。PDF417 支持广泛的字符集，包括 Unicode 符号。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**说明：**  
* `EncodeTypes.Pdf417` 告诉库使用 PDF417 标准。  
* 示例文本包含重音字符和版权符号，以演示 Unicode 处理。  

如果只需要编码数字数据，可以传入类似 `"1234567890"` 的普通字符串。

## 步骤 3：调整 X 维度以获得更高分辨率

X 维度控制单个条形码模块（最小的黑白单元）的宽度。设置更小的像素值可获得更高分辨率的图像。

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么要调整？** 默认的 3–4 像素 X 维度在高 DPI 屏幕上可能导致条形码显得粗糙。将其降低到 **2 像素** 可在保持可读性的同时平衡文件大小，尤其是在随后启用紧凑模式时。

## 步骤 4：配置列数

PDF417 允许您指定条形码应包含的列数。列数少会使条形码更窄但更高，列数多则生成更宽、较短的条形码。

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**实用提示：** 对于需要放在窄标签内的移动票务，**3–5** 列的设置效果良好。如果数据量大且希望条形码更短，可增加列数。

## 步骤 5：启用紧凑模式以截断空行

紧凑模式会移除条形码矩阵中不必要的行，从而在不丢失编码数据的前提下降低整体图像尺寸。

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**何时使用：** 如果您生成的条形码用于存储或网络传输，紧凑模式可将 PNG 文件大小缩小最多 30 %。但某些旧版扫描仪可能不支持截断的 PDF417；请在目标硬件上进行测试。

## 步骤 6：将条形码保存为 PNG 图像

选择输出路径并调用 `Save`。`BarCodeImageFormat.Png` 枚举会生成适用于大多数场景的无损图像。

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**结果验证：** 在任意图像查看器中打开 PNG 文件。您应该看到一条密集、高对比度的条形码，且内容与示例文本一致。使用 PDF417 读取器（例如 ZXing 或手机应用）扫描该图像，可返回原始字符串 `"Åspóse.Barcóde©"`。

![已保存为 PNG 的生成的 PDF417 条形码图像](compact-pdf417.png "C# 中生成的 PDF417 条形码")

*上图展示了本教程代码的最终输出效果。*

## 完整、可运行的示例

将所有步骤组合在一起，以下是一个完整的控制台程序，您可以复制、粘贴并直接运行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 预期输出

运行程序后会打印：

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

文件 `CompactPdf417.png` 包含一个紧凑的 PDF417 条形码，编码了提供的 Unicode 字符串。使用标准 PDF417 读取器扫描该图像可得到完全相同的文本。

## 常见变体和边缘情况

| 情形 | 调整 | 原因 |
|-----------|------------|--------|
| **数据负载较长**（例如 > 150 字符） | 将 `generator.Parameters.Barcode.Pdf417.Columns` 增加至 6‑8 | 更多列可防止条形码变得过高。 |
| **需要透明背景** | 使用 `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | 透明 PNG 更易在 UI 覆盖层中使用。 |
| **为 Web 生成 JPEG** | 将格式改为 `BarCodeImageFormat.Jpeg` 并可选设置 `ImageQuality` | JPEG 可在牺牲无损性的前提下降低文件大小。 |
| **处理 null 或空输入** | 在创建生成器前进行检查：`if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | 防止运行时异常并确保生成有意义的条形码。 |

## 生产环境使用技巧

* **异常处理：** 将生成逻辑包装在 `try/catch` 块中，以记录磁盘空间不足或参数无效等错误。  
* **性能：** 在大量生成条形码且设置相同的情况下，复用同一个 `BarcodeGenerator` 实例；只在保存之间更新 `CodeText` 属性。  
* **安全性：** 当编码的文本包含敏感信息时，考虑在传递给生成器之前进行加密，扫描后再解密。  

## 结论

您现在已经掌握了使用 Aspose.BarCode 库在 C# 中**生成 PDF417 条形码**的完整流程，能够配置紧凑模式、控制列数，并将结果导出为 PNG 图像。本教程覆盖了从项目搭建到边缘案例处理的每一步，为条形码驱动的应用提供了即插即用的解决方案。

接下来，您可以进一步探索 **在 C# 中创建 QR 码**、**批量条形码生成**以及**将条形码扫描集成到移动应用**等相关主题。所有这些都基于您刚刚掌握的 `BarcodeGenerator` 基础。

祝编码愉快！

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中尝试不同的实现方式。每篇资源都提供完整的可运行代码示例和逐步解释。

- [如何生成 PDF417 条形码 – 紧凑 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何创建条形码 – 使用 Aspose.BarCode 的紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义宽高比的 Aztec 条形码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}