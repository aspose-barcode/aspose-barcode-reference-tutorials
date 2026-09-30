---
date: 2026-09-08
description: 了解如何在 C# 中使用 Aspose.BarCode for .NET 创建 Code 128 条码并生成 GS1 条码。提供逐步指南、前置条件以及免代码自定义。
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 示例
og_description: 了解如何在 C# 中使用 Aspose.BarCode for .NET 创建 Code 128 条码并生成 GS1 条码。按照逐步指南快速生成并保存条码图像。
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: 如何使用 Aspose.BarCode 创建带 GS1 的 Code 128 条码
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: 如何使用 Aspose.BarCode 创建带 GS1 的 Code 128 条码
url: /zh/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 创建符合 GS1 标准的 Code 128 条形码

在本教程中，您将学习如何使用 .NET 的 Aspose.BarCode 库 **创建符合 GS1 标准的 Code 128 条形码**。无论您需要用于库存、运输还是销售点的条形码，本指南都会一步步带您完成——从搭建开发环境到保存最终图像——让您在几分钟内开始生成可靠的条形码。

## 快速答案
- **生成条形码的主要类是什么？** `BarcodeGenerator` 用于创建和配置条形码图像。  
- **GS1 Code 128 使用哪种符号系统？** 它使用 `EncodeTypes.Code128` 类型并采用 GS1 特定的数据格式。  
- **开发是否需要许可证？** 免费试用可用于评估；生产环境需要商业许可证。  
- **我可以更改图像格式吗？** 可以——通过更改文件扩展名保存为 PNG、JPEG、BMP 或 TIFF。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5+ 和 .NET 6+。

## 什么是创建 Code 128 条形码？
`create code 128 barcode` 指的是使用 Code 128 符号系统生成线性条形码，以编码字母数字数据。该符号系统因支持完整的 ASCII 集并能嵌入 GS1 应用标识符（AI）而被物流广泛采用。条形码可存储产品标识、序列号及其他自定义数据，适用于各种业务场景。

## 为什么在 GS1 Code 128 中使用 Aspose.BarCode？
Aspose.BarCode 支持 **30+ 条形码符号系统**，并能渲染最高 **10,000 × 10,000 px** 的图像而不失真，适合高分辨率标签打印。库会自动验证 GS1 数据结构，降低生产线中条形码格式错误的风险。此外，它提供丰富的尺寸、颜色和布局自定义选项，帮助满足严格的行业标准。

## 前置条件
1. **.NET 开发环境** – Visual Studio 2022、Rider 或任何支持 .NET 6+ 的 IDE。  
2. **Aspose.BarCode for .NET** – 从 **Aspose.BarCode for .NET 下载页面** 下载，链接为 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/)，并将 NuGet 包 `Aspose.BarCode` 添加到项目中。  
3. **基本的 C# 知识** – 你应当熟悉创建控制台或 Windows 应用程序。  
4. **了解 GS1 Code 128** – 可选但有帮助；GS1 使用诸如 `(01)` 表示 GTIN、`(21)` 表示序列号的应用标识符 (AI)。

## 分步创建 Code 128 条形码
加载库、配置条形码类型、设置 GS1 数据、自定义尺寸，最后保存图像。对 “如何创建 Code 128 条形码？” 的直接回答是：**实例化 `BarcodeGenerator` 并使用 `EncodeTypes.Code128` 与 GS1 格式化数据，必要时调整 `XDimension`，随后调用 `Save` 并指定文件名和格式**。以下章节将逐步拆解每一步。

### 步骤 1：设置目录路径
定义生成图像的存放文件夹。将路径设为可配置有助于代码在不同环境下复用。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

将 `"Your Directory Path"` 替换为应用程序可写入的绝对或相对路径，例如 `@"C:\Barcodes"` 或 `Path.Combine(Environment.CurrentDirectory, "Output")`。

### 步骤 2：创建 GS1 Code 128 条形码
创建条形码生成器，指定符号系统，并提供 GS1 格式化数据。数据字符串必须包含用括号括起的应用标识符。

```csharp
string path = "Your Directory Path";
```

示例使用 GTIN `(01)12345678901231`、序列号 `(21)ASPOSE`，以及自定义 AI `(30)9876`。Aspose.BarCode 会自动插入符合 GS1 要求的 FNC1 字符。

### 步骤 3：自定义条形码参数
调整视觉参数，如 `XDimension`（窄条宽度），以控制条形码密度。还可以修改高度、颜色和边距。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

将 `XDimension = 2` 可生成大多数手持阅读器易于扫描的条形码，同时保持图像尺寸适中。

### 步骤 4：保存条形码图像
将生成的条形码持久化到磁盘。可选择 PNG（无损质量）、JPEG（文件更小）或 TIFF（打印工作流）。`Save` 方法会根据文件扩展名写入相应格式的图像文件。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

将 `GS1Code128Example.png` 替换为任意有效的文件名和扩展名，以匹配所需的输出格式。

### 步骤 5：验证条形码（可选）
保存后，您可以将图像重新加载到应用程序中，或使用条形码扫描器确认编码数据与原始字符串一致。此步骤在开发和自动化测试时非常有用。

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## 常见问题及排查技巧
- **未检测到 FNC1** – 确保数据字符串以左括号开头并包含有效的 GS1 AI；库仅在识别的模式下自动插入 FNC1。  
- **图像未保存** – 验证目标目录是否存在且应用程序拥有写入权限。可使用 `Directory.CreateDirectory(path)` 动态创建目录。  
- **条形码过于密集** – 降低 `XDimension` 或增加图像高度，以为扫描器提供更多读取窄条的空间。  
- **不支持的字符** – Code 128 只能编码完整的 ASCII 集合；请避免使用超出此范围的 Unicode 字符。

## 常见问答

**Q: 我可以在不安装完整 .NET Framework 的情况下通过 Web API 生成条形码吗？**  
A: 可以，Aspose.BarCode 支持 .NET Core 和 .NET 5/6，您可以暴露轻量级的 REST 端点按需返回条形码图像。

**Q: 该库是否支持批量生成多个条形码？**  
A: 完全支持。遍历数据字符串集合，为每个实例化 `BarcodeGenerator`，并在循环中调用 `Save`。库对并行处理是线程安全的。

**Q: 是否有办法直接将条形码嵌入 PDF？**  
A: 使用 Aspose.PDF 创建 PDF 文档，然后调用 `PdfPage.AddImage` 并传入条形码图像流。这样可避免写入中间文件到磁盘。

**Q: 如何确保条形码符合 ISO/GS1 质量标准？**  
A: 将 `BarcodeGenerator.Options.Barcode.XDimension` 设置为至少 0.33 mm，并根据标签尺寸启用 `BarHeight`。Aspose.BarCode 会验证 AI 格式并在数据无效时抛出异常。

**Q: 生产环境有哪些授权选项？**  
A: Aspose 提供永久授权、订阅授权和基于云的授权模式。试用授权可用于评估，但付费授权会去除评估水印并解锁全部功能。

## 其他资源

- **文档** – 在 [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/) 查看完整的 API 参考。  
- **下载** – 从 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) 获取最新的库发布。  
- **免费试用** – 在 [https://releases.aspose.com/](https://releases.aspose.com/) 开始 30 天试用。  
- **购买** – 在 [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy) 购买商业许可证。  
- **支持** – 加入社区论坛 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) 获取故障排查帮助。

---

**最后更新：** 2026-09-08  
**已测试于：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [如何在 .NET 中创建 ITF-14 条形码 – Aspose.BarCode 综合教程](/barcode/net/)
- [使用 Aspose.BarCode .NET API 生成一维 Databar 2D 条形码](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}