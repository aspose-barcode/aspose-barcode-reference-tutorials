---
category: general
date: 2026-10-21
description: 学习如何使用 Aspose.BarCode 在 C# 中创建邮政条码图像——生成 Planet 和 RM4SCC 条码，控制实心条，保存为
  PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- generate planet barcode
- how to generate barcode c#
language: zh
lastmod: 2026-10-21
og_description: 使用 Aspose.BarCode 在 C# 中创建邮政条码图像。本教程展示了如何生成 Planet 和 RM4SCC 条码、切换实心条以及保存
  PNG 文件。
og_image_alt: Screenshot of a generated Planet postal barcode with filled bars
og_title: 在 C# 中创建邮政条形码图像 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  headline: How to create postal barcode images in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to create postal barcode images in C# with Aspose.BarCode
    – generate Planet and RM4SCC barcodes, control filled bars, and save PNG files.
  name: How to create postal barcode images in C# using Aspose.BarCode
  steps:
  - name: 1. Prepare the output folder
    text: The barcode images need a writable directory. The code creates the folder
      if it does not exist, preventing a runtime `DirectoryNotFoundException`.
  - name: 2. Generate a Planet barcode with filled bars
    text: Planet barcodes are used by many postal services for domestic mail. The
      default `FilledBars` setting renders solid bars, which is the most common visual
      style.
  - name: 3. Generate a Planet barcode with empty bars
    text: Some postal specifications require **empty** (hollow) bars. You can toggle
      this behavior via the `FilledBars` property.
  - name: 4. Generate an RM4SCC barcode with filled bars
    text: RM4SCC (Royal Mail 4‑State Customer Code) is the UK postal barcode. Like
      Planet, the default appearance uses solid bars.
  - name: Full source code in one block
    text: Copy the following snippet into a new C# console project. It compiles with
      .NET 6.0 and produces three PNG files in the `Barcodes` subfolder.
  - name: Next steps
    text: '* **Generate other postal barcodes** – try `EncodeTypes.Postnet` or `EncodeTypes.USPSIntelligentMail`.
      * **Customize appearance** – experiment with `BarHeight`, `ForeColor`, and `BackColor`
      to match your branding. * **Integrate into a web service** – expose the generation
      logic via ASP.NET Core endp'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 Aspose.BarCode 在 C# 中创建邮政条形码图像
url: /zh/python-java/general/how-to-create-postal-barcode-images-in-c-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode 在 C# 中创建邮政条码图像

如果您需要在 .NET 项目中 **创建邮政条码** 图像，本指南提供了一个完整、可直接运行的解决方案。您将看到如何生成 Planet 和 RM4SCC 条码，如何在实心条和空心条之间切换，并将结果保存为 PNG 文件——只需几行 C# 代码。

生成可靠的邮政条码对于邮件自动化、大批量标签打印以及与物流平台的集成至关重要。完成本教程后，您将拥有一段可复用的代码片段，能够复制到任何 C# 控制台或 Web 应用程序中。

## 前提条件

在开始之前，请确保您已具备：

* .NET 6.0 SDK 或更高版本  
* Visual Studio 2022（或任何支持 .NET 的 IDE）  
* 有效的 **Aspose.BarCode** NuGet 包（`Install-Package Aspose.BarCode`）  

这些工具足以编译并运行示例，无需额外依赖。

## **创建邮政条码** 图像的分步指南

整个过程包括四个逻辑步骤：

1. 准备输出文件夹。  
2. 生成实心条的 Planet 条码（默认外观）。  
3. 生成空心条的 Planet 条码。  
4. 生成实心条的 RM4SCC 条码。

下面将逐步解释每个步骤，完整源码位于说明之后。

### 1. 准备输出文件夹

条码图像需要可写入的目录。代码会在文件夹不存在时创建它，从而避免运行时出现 `DirectoryNotFoundException`。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Define the output folder (adjust the path to your environment)
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the folder exists
        Directory.CreateDirectory(outputFolder);
```

*为什么重要*：缺少目录会在生成任何条码之前导致程序停止。使用 `Directory.CreateDirectory` 是安全的，因为如果文件夹已经存在，它什么也不做。

### 2. 生成实心条的 Planet 条码

Planet 条码被许多邮政服务用于国内邮件。默认的 `FilledBars` 设置会渲染实心条，这是最常见的视觉样式。

```csharp
        // Step 2: Generate a Planet barcode with filled bars (default)
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // XDimension controls the width of a single bar; 4 pixels works well for screen display
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);
```

*说明*：  
* `EncodeTypes.Planet` 告诉 Aspose.BarCode 使用 Planet 标准。  
* 数据字符串 `"123456"` 是有效的 Planet 负载（6 位数字）。  
* `XDimension.Pixels = 4` 产生每条宽度为 4 px 的条码，在可读性和文件大小之间取得平衡。  
* `Save` 将图像保存为 PNG，这是一种适合后续处理的无损格式。

### 3. 生成空心条的 Planet 条码

某些邮政规范要求 **空心**（空心）条。您可以通过 `FilledBars` 属性切换此行为。

```csharp
        // Step 3: Generate a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        // Setting FilledBars to false creates hollow bars
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);
```

*提示*：在实心条与空心条之间切换时，保持 `XDimension` 值不变，以确保图像尺寸的一致性。

### 4. 生成实心条的 RM4SCC 条码

RM4SCC（Royal Mail 4‑State Customer Code）是英国的邮政条码。与 Planet 类似，默认外观使用实心条。

```csharp
        // Step 4: Generate an RM4SCC barcode with filled bars (default)
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);
    }
}
```

*为什么选择 RM4SCC*：RM4SCC 格式编码 6 位数字字符串加校验码，非常适合英国邮寄服务。

### 完整源码（单块）

将以下代码片段复制到新的 C# 控制台项目中。它在 .NET 6.0 下编译，并在 `Barcodes` 子文件夹中生成三个 PNG 文件。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // 1. Prepare the output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // -------------------------------------------------
        // 2. Planet barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
        planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                          BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3. Planet barcode – empty bars
        // -------------------------------------------------
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false;
        planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4. RM4SCC barcode – filled bars (default)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFilled.Save(Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png"),
                          BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been saved to: " + outputFolder);
    }
}
```

#### 预期输出

运行程序后会在控制台打印确认信息，并创建以下三个文件：

* `PostalPlanetFilledBars.png` – 实心条 Planet 条码  
* `PostalPlanetEmptyBars.png` – 空心条 Planet 条码  
* `PostalRM4SCCFilledBars.png` – 实心条 RM4SCC 条码  

每张图像的条宽为 4 px，适合屏幕预览或用于打印就绪的 PDF 嵌入。

## 常见问题与边缘情况处理

| 问题 | 回答 |
|----------|--------|
| **如果数据字符串无效怎么办？** | Aspose.BarCode 会抛出 `ArgumentException`。在创建生成器之前，请验证输入长度（Planet = 6 位数字，RM4SCC = 6 位数字）。 |
| **可以更改图像格式吗？** | 可以。将 `BarCodeImageFormat.Png` 替换为 `Jpeg`、`Gif`、`Bmp` 或 `Tiff` 即可。 |
| **如何调整条码高度？** | 使用 `planetFilled.Parameters.Barcode.BarHeight`（默认 50 px）。 |
| **在 Web API 中使用这段代码安全么？** | 完全安全。生成器对只读操作是线程安全的，但建议每个请求实例化一个新的 `BarcodeGenerator`，以避免共享状态。 |
| **其他邮政标准怎么办？** | Aspose.BarCode 还支持 `EncodeTypes.Postnet`、`EncodeTypes.USPSIntelligentMail` 等。使用方式相同，只需更改 `EncodeTypes` 的取值。 |

## 结论

现在您已经掌握了使用 Aspose.BarCode 在 C# 中 **创建邮政条码** 图像的方法，涵盖了 Planet 和 RM4SCC 两种格式，并演示了如何在实心条与空心条之间切换。完整的可运行示例可以直接放入任何 .NET 项目，立即获得可视化输出。

### 后续步骤

* **生成其他邮政条码** – 试试 `EncodeTypes.Postnet` 或 `EncodeTypes.USPSIntelligentMail`。  
* **自定义外观** – 试验 `BarHeight`、`ForeColor`、`BackColor` 等属性，以匹配品牌风格。  
* **集成到 Web 服务** – 通过 ASP.NET Core 端点公开生成逻辑，实现按需条码创建。  

掌握这些技巧后，您即可 **生成 planet 条码** 图像，并自信地回答 “**how to generate barcode C#**” 类的问题，无论是构建桌面邮件工具还是云端运输 API。祝编码愉快！

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您在已有技巧的基础上进一步提升。每篇资源都提供完整可运行的代码示例和逐步解释，助您掌握更多 API 功能并探索项目中的替代实现方案。

- [如何使用实心条和空心条创建 Planet 条码](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [如何在 C# 中创建 RM4SCC 条码并生成 Planet 条码](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [在 C# 中生成邮政条码 – 包含 Planet 条码的完整指南](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}