---
category: general
date: 2026-09-18
description: 快速学习如何在 C# 中创建 PDF417 条形码图像，并设置列以生成紧凑的条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: 快速学习如何在 C# 中创建 PDF417 条形码图像，并设置列以生成紧凑的条形码。Aspose.BarCode 让这一过程变得轻松。
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: 创建 PDF417 条形码图像 – 逐步 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: 如何在 C# 中创建 PDF417 条形码图像 – 完整指南
url: /zh/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中创建 PDF417 条码图像 – 完整指南

如果你需要在 .NET 应用程序中 **创建 PDF417 条码图像**，你来对地方了。无论是打印登机牌标签、编码库存数据，还是构建移动票务系统，PDF417 都能提供高容量的二维条码。本指南将展示如何使用 Aspose.BarCode 生成图像，以及如何设置列以使条码尽可能紧凑。

## 快速答案
- **哪个库可以创建 PDF417 条码？** Aspose.BarCode for .NET。  
- **需要多少行代码？** 在控制台应用程序中大约 10 行。  
- **我可以控制条码宽度吗？** 可以，通过设置 `Columns` 属性。  
- **推荐使用哪种图像格式？** PNG，提供无损质量。  
- **是否支持 .NET 6？** 完全支持——该库可在 .NET 6、.NET 7 及更高版本上运行。

## 什么是 PDF417 条码图像？
PDF417 条码图像是一种二维矩阵，每行最多可存储 1 700 个字符，使用行和列紧密打包数据。Aspose.BarCode 将此矩阵渲染为 PNG、JPEG 或 BMP 等标准图像格式。它可以保存为多种格式，适用于标签、票据或移动屏幕的打印。

## 为什么要设置列以获得紧凑的 PDF417 条码图像？
设置列可以缩小条码的宽度，这对窄标签或空间受限的 UI 元素至关重要。Aspose.BarCode 支持 1‑30 列，选择较低的列数可将整体图像宽度降低最多约 40 %，同时保持数据完整性。此调整有助于在小标签上放置条码而不牺牲可读性。

## 如何在 C# 中创建 PDF417 条码图像？
加载 `Aspose.BarCode` 库，使用 `EncodeTypes.Pdf417` 配置 `BarcodeGenerator`，设置 `Columns` 和 `Truncate`，然后保存为 PNG。整个过程只需两次方法调用，即可生成可直接使用的图像文件。你还可以自定义尺寸、颜色，并添加可读文本以满足应用需求。

### 前置条件
- .NET 6+ SDK（或更高）  
- Visual Studio 2022 或任何 C# 编辑器  
- NuGet 包 `Aspose.BarCode`

### 步骤实现

## 步骤 1：安装 Aspose.BarCode NuGet 包
`Aspose.BarCode` 是一个用于生成和读取各种条码符号的 .NET 库。

```bash
dotnet add package Aspose.BarCode
```

这行代码会引入所有所需的类型，包括 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat` 枚举。

> **专业提示：** 如果你的目标是 .NET Framework 而不是 .NET 6，请在包管理器控制台中使用经典的 `Install-Package Aspose.BarCode` PowerShell 命令。

## 步骤 2：创建最小化控制台应用程序
`BarcodeGenerator` 根据指定的设置创建条码图像。`EncodeTypes` 列举了受支持的条码符号。`BarCodeImageFormat` 列举了图像格式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**为什么这很重要：**  
- `EncodeTypes.Pdf417` 告诉库我们需要 PDF417 条码，而不是 QR 或 Code128。  
- `XDimension.Pixels` 控制每个微小黑白模块的分辨率。  
- **如何设置列** 块直接影响 **PDF417 条码图像** 的形状。  
- `Truncate = true` 会去除任何不必要的空行，呈现出许多扫描仪喜爱的“紧凑”外观。

## 步骤 3：深入了解 – 列和截断
### 如何设置列
PDF417 将数据排列在 *行* × *列* 的矩阵中。库默认使用 5 列，适用于大多数情况。然而，你可能需要更窄的条码以适配标签，或更宽的条码以提升扫描可靠性。属性：

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

接受 **1** 到 **30** 的值（确切上限取决于数据长度）。以下是快速速查表：

| 列数 | 约宽度 (mm) | 使用场景 |
|------|------------|----------|
| 1‑3  | 非常窄     | 小标签，空间受限 |
| 4‑6  | 标准       | 大多数收据、票据 |
| 7‑10 | 较宽       | 高密度数据，更好可读性 |

### 截断（紧凑模式）
设置 `Truncate = true` 告诉编码器在底部去除任何不必要的空行。结果是一个 **紧凑的 PDF417 条码图像**，占用最小面积，同时仍包含所有数据。如果出现 “条码太大无法贴标签” 的错误，请切换此标志。

## 步骤 4：运行应用并验证输出
```bash
dotnet run
```

你应该会在控制台看到确认保存位置的消息。导航到该文件夹并打开 `CompactPdf417.png`。图像大致如下所示：

![生成的 PDF417 条码图像](./CompactPdf417.png "生成的 PDF417 条码图像 – 由 Aspose.BarCode 创建的紧凑 PNG")

[生成的 PDF417 条码图像](./CompactPdf417.png "生成的 PDF417 条码图像 – 由 Aspose.BarCode 创建的紧凑 PNG")

*图片 alt 文本:* **生成的 PDF417 条码图像** – 由教程代码生成的紧凑 PNG 文件。

如果你的扫描仪能够读取它，恭喜——你已经成功 **生成 PDF417 条码** 并掌握了 **如何设置列**，以获得整洁的 **PDF417 条码图像**。

## 步骤 5：常见问题及解决方法

| 症状 | 可能原因 | 快速修复 |
|------|----------|----------|
| 条码模糊 | `XDimension.Pixels` 设置过低（例如 1） | 提高到 2‑3 像素以获得更清晰的图像。 |
| 扫描仪无法读取 | 对于给定数据列数过多 | 减少 `Columns` 或启用 `Truncate`。 |
| 文件格式错误 | 错误地使用 `BarCodeImageFormat.Jpeg` 保存 | 使用 `BarCodeImageFormat.Png` 获得无损结果。 |
| 异常 `ArgumentOutOfRangeException` | 列数超出允许范围 | 将列数保持在 1‑30 之间并确保数据适配。 |

## 步骤 6：进一步 – 自定义颜色和添加文本

如果你想让条码匹配品牌配色方案，可以调整前景色和背景色：

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

或者在条码下方覆盖可读文本：

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

这些添加是可选的，但它们展示了 **生成 PDF417 条码** 工作流的灵活性。

## 结论
我们已经完整演示了使用 Aspose.BarCode **生成 PDF417 条码** 的端到端示例，解释了 **如何设置列** 以控制条码尺寸，并将结果保存为 PNG 格式的清晰 **PDF417 条码图像**。代码自包含，适用于 .NET 6+，可轻松集成到任何现有项目中。

接下来可以尝试编码更大的负载（例如 JSON 字符串），实验不同的图像格式，或将生成器集成到按需提供条码的 Web API 中。可能性无限，而你已经拥有了坚实的基础。

祝编码愉快，愿你的条码总是一次成功扫描！

## 接下来应该学习什么？
以下教程涵盖与本指南紧密相关的主题，帮助你进一步掌握 API 功能并探索替代实现方式：

- [如何使用 Aspose.BarCode 创建条码 – 紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 在 Java 中生成条码图像](/barcode/english/java/barcode-rendering-techniques/)
- [在 Java 中生成条码 – 使用 Aspose.BarCode 设置图像分辨率](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## 常见问题

**问：我可以在网页中直接使用生成的 PNG 而无需额外转换吗？**  
答：可以，PNG 被所有现代浏览器原生支持，你可以直接使用 `<img>` 标签嵌入文件。

**问：PDF417 条码可以容纳多少字符？**  
答：每行最多 1 700 个字符，最多 30 行，理论最大约 51 000 个字符，实际上限取决于扫描仪的能力。

**问：Aspose.BarCode 开发是否需要许可证？**  
答：提供免费评估许可证用于测试；生产部署需要商业许可证。

**问：是否可以在后台服务中生成 PDF417 条码？**  
答：完全可以。库对只读操作是线程安全的，因而可以在 ASP.NET Core 或 Windows 服务中生成条码，无需 UI 交互。

**问：除了 PNG 之外，还支持哪些图像格式？**  
答：通过 `BarCodeImageFormat` 枚举，支持 BMP、JPEG、GIF、TIFF 和 SVG。

**最后更新：** 2026-09-18  
**测试版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## 相关教程

- [使用 Aspose 完整指南创建 Pdf417 条码](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [如何使用 Aspose 在 C# 中生成 Pdf417 条码图像](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [在 C 中创建 Pdf417 条码的分步指南](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}