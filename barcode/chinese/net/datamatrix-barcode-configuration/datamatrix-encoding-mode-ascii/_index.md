---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode for .NET 在 ASCII 模式下创建 DataMatrix 条码。本指南快速演示如何生成
  C# 条码。
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: DataMatrix 编码模式 (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode for .NET 在 ASCII 模式下创建 DataMatrix 条码
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 在 ASCII 模式下创建 DataMatrix 条码

## 介绍

准备好使用高效的 ASCII 编码来**创建 DataMatrix 条码**图像了吗？在本教程中，您将学习如何使用 Aspose.BarCode for .NET 在 ASCII 模式下生成 DataMatrix 条码。我们将逐步演示每一步——从项目设置到保存最终图像——让您能够在几分钟内将条码生成功能添加到 C# 应用程序中。

## 快速回答
- **在 .NET 中哪个库最适合 DataMatrix？** Aspose.BarCode for .NET  
- **需要多少行代码？** About 5‑7 lines for a basic ASCII barcode  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要许可证  
- **支持的平台？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **我可以更改尺寸或颜色吗？** 是的，Aspose.BarCode 提供用于设置尺寸和前景/背景颜色的属性  

## 什么是 DataMatrix 条码？

## 如何在 ASCII 模式下创建 DataMatrix 条码？

加载 Aspose.BarCode 命名空间，实例化 `BarcodeGenerator`，将 `EncodeMode` 设置为 **EncodeMode.ASCII**，分配您的数据字符串，然后调用 `Save` 将图像文件写入。此方法仅用几行 C# 代码即可生成符合标准的仅使用 ASCII 编码的 DataMatrix 条码。

## 为什么在 DataMatrix 中使用 ASCII 编码？

ASCII 模式是纯文本数据的默认且最高效的编码，可为字母数字字符串提供最小的符号尺寸。它支持全部 128 个 ASCII 字符，处理速度快于扩展模式，并确保与期望标准 ASCII 符号的旧版扫描仪最大兼容性。

## 先决条件

1. **开发环境** – Visual Studio、Rider 或任何兼容 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 从[此处](https://releases.aspose.com/barcode/net/)下载最新包。  
   - 文档: [Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)  
   - 社区帮助: [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)  
3. **基本的 C# 知识** – 熟悉 .NET 项目结构将帮助您快速跟随步骤。  
4. **其他 Aspose 产品** 可在[此处](https://releases.aspose.com/)找到。

## 导入命名空间

要开始，请在 C# 文件顶部添加所需的 `using` 指令：

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

这些命名空间让您能够访问 `BarcodeGenerator` 类以及用于保存输出的图像相关类型。

## 步骤 1：创建目录

选择一个用于存放生成的条码图像的文件夹。将 `"Your Directory Path"` 替换为您机器上存在的绝对或相对路径。

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

此代码在尝试写入任何文件之前确保目录已存在，从而防止运行时错误。

## 步骤 2：以 ASCII 模式编码数据

`BarcodeGenerator` 类用于创建和配置条码图像。`DataMatrixEncodeMode` 枚举用于选择 DataMatrix 符号的编码算法。

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

运行代码后，您将在指定的文件夹中找到 `datamatrix_ascii.png`。该图像包含一个使用紧凑 ASCII 模式对字符串 `"1234567890"` 进行编码的 DataMatrix 条码。

## 常见问题及解决方案

- **文件访问错误** – 确保应用程序对目标文件夹具有写入权限。在 Windows 上以管理员身份运行 Visual Studio 可以解决权限问题。  
- **符号尺寸不正确** – 如果条码显示过大或过小，请调整 `generator.Parameters.Image.Width` 和 `Height`，或通过省略这些属性让 Aspose 自动计算最佳尺寸。  
- **不支持的字符** – ASCII 模式仅接受 0‑127 范围内的字符。对于 Unicode 数据，请切换到 `DataMatrixEncodeMode.Base256` 或其他合适的模式。

## 常见问题

**Q: 我可以在商业应用中使用此代码吗？**  
A: 是的，生产使用需要有效的 Aspose 许可证；可使用免费试用版进行评估。

**Q: 该库支持 .NET Core 吗？**  
A: 绝对支持 – Aspose.BarCode 完全支持 .NET Core 3.1+、.NET 5、.NET 6 以及更高版本。

**Q: 在 ASCII 模式下我可以编码多少字符？**  
A: 使用 ASCII 编码时，单个 DataMatrix 符号最多可容纳 2,335 个字母数字字符。

**Q: 我可以更改条码的前景色或背景色吗？**  
A: 是的，调整 `generator.Parameters.Image.ForeColor` 和 `BackColor` 为任意 `System.Drawing.Color` 值。

**Q: 我在哪里可以找到更高级的示例？**  
A: 官方文档包含数十个示例，涵盖自定义尺寸、颜色和错误纠正级别等。

## 常见问答

### Q1: 我可以在 C# 之外的其他编程语言中使用 Aspose.BarCode for .NET 吗？

A1: Aspose.BarCode 支持多种编程语言，但本教程侧重于 C#。

### Q2: DataMatrix 条码有哪些不同的编码模式？

A2: DataMatrix 条码支持多种编码模式，包括 ASCII、C40、Text 和 Base256。每种模式适用于不同类型的数据。

### Q3: 我可以自定义生成的条码外观，例如尺寸和颜色吗？

A3: 是的，Aspose.BarCode 提供广泛的参数来自定义条码外观，包括尺寸、颜色等。

### Q4: 是否提供 Aspose.BarCode for .NET 的免费试用版？

A4: 是的，您可以从[此处](https://releases.aspose.com/)获取 Aspose.BarCode for .NET 的免费试用版。

### Q5: 我可以在哪里购买 Aspose.BarCode for .NET 的许可证？

A5: 您可以在 Aspose 网站的[此处](https://purchase.aspose.com/buy)购买许可证。

---

**最后更新：** 2026-06-09  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.BarCode for .NET 的字节模式 DataMatrix 编码](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [读取 DataMatrix 条码 C# – 自动生成 DataMatrix 模式](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}