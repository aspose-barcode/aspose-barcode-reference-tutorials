---
category: general
date: 2026-07-18
description: 使用 Aspose.BarCode 在 C# 中创建 GS1 条码图像，提供一步步指南，教您如何生成 C# 条码——不废话，只给可运行代码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create gs1 barcode images
- how to generate barcode c#
language: zh
lastmod: 2026-07-18
og_description: 使用本简明教程在 C# 中创建 GS1 条形码图像。学习如何使用 Aspose.BarCode 生成条形码并在几秒钟内将其保存为 PNG
  文件。
og_image_alt: Screenshot of a generated GS1‑MicroPDF417 barcode saved as a PNG file
og_title: 在 C# 中创建 GS1 条形码图像 – 完整操作指南
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create GS1 barcode images in C# with this step‑by‑step guide on how
    to generate barcode C# using Aspose.BarCode – no fluff, just working code.
  headline: Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly
  type: TechArticle
tags:
- barcode
- csharp
- gs1
- aspose
title: 在 C# 中创建 GS1 条码图像 – 如何快速生成条码
url: /zh/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 GS1 条码图像 – 如何生成条码 C#

是否曾需要为包装标签**创建 gs1 条码图像**但不知从何入手？你并不孤单。在本教程中，你将看到如何**生成 barcode c#**代码，在几分钟内生成 GS1‑MicroPDF417 图像。

我们将完整演示整个过程——安装库、配置生成器、替换 AI（Application Identifier）数据，最后保存一组 PNG 文件。完成后，你将拥有一个可直接运行的控制台应用程序，能够输出若干 GS1 条码图像，每个图像对应不同的 AI 组合。

---

## 你需要的条件

- **.NET 6+**（或 .NET Framework 4.6+）。最新运行时与 Aspose.BarCode 配合最佳。
- **Aspose.BarCode for .NET** – 通过 NuGet 安装（`Install-Package Aspose.BarCode`）。
- 一个磁盘文件夹，用于写入 PNG 文件（我们称之为 `YOUR_DIRECTORY`）。
- 对 C# 语法有基本了解——不需要高级技巧。

如果你已经具备上述条件，太好了。否则，请先获取 NuGet 包；只需在包管理器控制台中执行一行命令，即可自动处理所有依赖。

---

## 步骤 1：创建最小化控制台项目

打开你喜欢的 IDE（Visual Studio、Rider 或 VS Code），创建一个新的控制台项目：

```bash
dotnet new console -n Gs1BarcodeDemo
cd Gs1BarcodeDemo
dotnet add package Aspose.BarCode
```

用下一步中展示的代码替换自动生成的 `Program.cs`。此骨架为我们提供了一个干净的起点，以**创建 gs1 条码图像**，无需额外杂乱。

---

## 步骤 2：如何创建 gs1 条码图像 – 初始化生成器

操作的核心是 `BarcodeGenerator`。我们将使用初始的 GS1‑MicroPDF417 值启动它，例如 `(17)991231(10)ABCD`。该字符串编码了两个 AI：有效期 (17) 和批次/批号 (10)。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with a GS1‑MicroPDF417 barcode type
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(17)991231(10)ABCD");
```

**为什么重要：** `EncodeTypes.GS1MicroPdf417` 告诉 Aspose 我们使用的是紧凑的高密度 GS1 格式。使用有效的 AI 字符串开始，可确保我们保存的第一张 PNG 已符合 GS1 标准。

---

## 步骤 3：调整视觉参数 – 微调尺寸和布局

条码如果太小或形状异常将无法扫描。这里我们将 X‑dimension（模块宽度）设为 2 像素，限制列数以保持图像窄小，并启用链接，以便以后需要时可以将多个条码串联。

```csharp
        // Set visual parameters for a crisp, scannable image
        barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;      // module width
        barcodeGen.Parameters.Barcode.Pdf417.Columns = 2;        // column count
        barcodeGen.Parameters.Barcode.Pdf417.IsLinked = true;   // enable linking
```

**提示：** 如果需要更高的条码，请增加 `Rows` 而不是列数。调整 `XDimension` 以满足大多数扫描仪要求的最小 0.33 mm 模块尺寸。

---

## 步骤 4：保存第一张条码 – AI 17 + AI 10

现在我们实际将图像写入磁盘。文件名反映所使用的 AI，便于以后查找。

```csharp
        // Save the first image (AI 17 + AI 10)
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17_10.png",
                        BarCodeImageFormat.Png);
```

运行程序后，你应该在 `YOUR_DIRECTORY` 中看到一张清晰的 PNG。打开它——你会看到细小的条纹以及下方的人类可读文本。这就是我们将生成的众多 **gs1 条码图像** 中的第一张。

---

## 步骤 5：更改编码数据 – 重用同一生成器

我们不为每个 AI 对创建新的 `BarcodeGenerator`，而是直接交换 `CodeText` 属性并再次调用 `Save`。这种做法是批量**创建 gs1 条码图像**的最高效方式。

```csharp
        // AI 15 (best before) + AI 10 (batch)
        barcodeGen.CodeText = "(15)991231(10)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_15_10.png",
                        BarCodeImageFormat.Png);

        // AI 13 (production date) + AI 21 (serial)
        barcodeGen.CodeText = "(13)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_13_21.png",
                        BarCodeImageFormat.Png);

        // AI 11 (manufacture date) + AI 21 (serial)
        barcodeGen.CodeText = "(11)991231(21)ABCD";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_11_21.png",
                        BarCodeImageFormat.Png);

        // Only AI 17 (expiration) – no batch number
        barcodeGen.CodeText = "(17)991231";
        barcodeGen.Save(@"YOUR_DIRECTORY\GS1MicroPdf417_17.png",
                        BarCodeImageFormat.Png);
```

**为什么要重用？** 更改 `CodeText` 可避免重新实例化生成器的开销，并确保所有图像的视觉设置保持一致。

---

## 步骤 6：运行、验证并微调

编译并运行：

```bash
dotnet run
```

现在你应该拥有五个 PNG 文件，每个文件名对应其包含的 AI 对。用图像查看器打开任意一个，你会看到条码以及下方的编码文本。为再次确认数据正确，可在手机上使用免费 GS1 扫描器应用——对准屏幕上的 PNG，即可弹出 AI 值。

**常见问题及避免方法**

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| 条码无法读取 | `XDimension` 太低（例如 1 像素） | 提升至 2 或 3 像素 |
| 缺少 AI 括号 | `CodeText` 格式错误 | 始终在每个 AI 周围加括号 |
| 图像过大 | 列/行过多 | 减少 `Columns` 或让 Aspose 自动尺寸 |
| 运行时错误 `EncodeTypes` 未找到 | 缺少 `using Aspose.BarCode.Generation` | 添加缺失的 `using` 指令 |

---

## 步骤 7：扩展示例 – 生成更多 AI 组合

如果需要为数十种产品变体**创建 gs1 条码图像**，可以考虑从 CSV 文件加载 AI 对：

```csharp
using System.IO;

string[] lines = File.ReadAllLines(@"ai_pairs.csv"); // format: "(17)991231,(10)ABCD"
foreach (var line in lines)
{
    barcodeGen.CodeText = line.Replace(',', ' ');
    string fileName = $"GS1MicroPdf417_{line.Replace("(", "").Replace(")", "").Replace(",", "_")}.png";
    barcodeGen.Save(Path.Combine(@"YOUR_DIRECTORY", fileName), BarCodeImageFormat.Png);
}
```

这个小循环读取每一行，交换数据，并使用描述性名称保存 PNG——非常适合大规模标签打印流水线。

---

## 结论

现在你拥有一个完整的、可直接运行的 C# 程序，能够为多种 AI 场景**创建 gs1 条码图像**，展示了使用 Aspose.BarCode **如何生成 barcode c#** 的最直接方法。通过重用同一个 `BarcodeGenerator` 实例、微调视觉参数并更换 `CodeText`，你可以根据项目需求生成任意数量符合标准的 GS1‑MicroPDF417 PNG。

接下来可以尝试添加颜色（`barcodeGen.Parameters.Barcode.ForeColor`）、将条码嵌入 PDF，或切换到其他 GS1 符号如 DataMatrix。相同的模式仍然适用——初始化、配置、设置 `CodeText`，然后保存。

如果遇到任何问题，欢迎留言，或分享你的实现方式。祝编码愉快，愿你的扫描始终顺畅！

## 接下来你应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在本教程演示的技巧之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助你掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 为 Code 16K 创建条码安静区](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 为 ITF-14 创建条码安静区](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [如何使用 Aspose.BarCode 生成条码 – Code 39 配置](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}