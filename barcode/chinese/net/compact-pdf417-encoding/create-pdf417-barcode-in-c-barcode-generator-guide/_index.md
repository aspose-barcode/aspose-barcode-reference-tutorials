---
category: general
date: 2026-07-18
description: 使用 C# PDF417 条码生成器在 C# 中创建 PDF417 条码。按照分步教程构建扩展代码文本，设置外观并保存图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: zh
lastmod: 2026-07-18
og_description: 在 C# 中即时创建 PDF417 条形码。本指南展示如何使用 C# PDF417 条形码生成器，配置扩展模式，并导出 PNG。
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: 在 C# 中创建 PDF417 条码 – 完整生成器教程
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 在 C# 中创建 PDF417 条码 – 条码生成器指南
url: /zh/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中创建 PDF417 条形码 – 条形码生成器指南

是否曾经需要在 C# 应用程序中**创建 PDF417 条形码**却不知从何入手？你并不孤单——许多开发者在首次接触二维条形码时都会遇到同样的难题。好消息是？使用内置的**C# PDF417 条形码生成器**，只需几行代码即可生成功能完整的条形码。

在本教程中，我们将完整演示整个过程：构建混合不同字符集的扩展编码文本，配置生成器以获得合适的视觉样式，最后将条形码保存为 PNG 文件。完成后，你将拥有一段可直接放入任何 .NET 项目的可用代码片段，并提供处理 Unicode 字符或自定义模块宽度等边缘情况的技巧。

---

## 你需要的准备

在开始之前，请确保你的机器上具备以下环境：

- **.NET 6.0** 或更高版本（示例同样适用于 .NET Framework 4.6+）
- **Aspose.BarCode for .NET**（或任何提供 `BarcodeGenerator`、`EncodeTypes.Pdf417` 等的兼容库）
- 一个代码编辑器——Visual Studio、Rider，甚至 VS Code 都可以
- 一个可写入的文件夹，因为生成器会将 PNG 保存到该位置

就这些——除条形码库本身外无需额外的 NuGet 包。

---

## 步骤指南：**创建 PDF417 条形码**

### 1. 安装条形码库

在项目文件夹的终端中运行：

```bash
dotnet add package Aspose.BarCode
```

该包会添加 `Aspose.BarCode` 命名空间，其中包含我们将在整个示例中使用的 `BarcodeGenerator` 类。

### 2. 构建扩展编码文本

PDF417 支持**扩展编码**，允许在同一个条形码中混合不同字符集。下面我们创建三个段落：

- 一个 Windows‑1251（西里尔文）段落
- 一个包含 Unicode 字符的 UTF‑8 段落（日文汉字“狗”和“右”）
- 一个纯文本段落

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**为什么重要：**  
如果仅使用纯文本，你只能使用默认的 ASCII 子集。通过显式声明 ECI（扩展信道解释）段落，你可以确保扫描器正确解释每一部分，无论使用何种语言或符号。

### 3. 初始化 **C# PDF417 条形码生成器**

现在我们已经拥有有效的编码文本字符串，将其交给生成器。`using` 语句可确保底层资源自动释放。

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. 配置外观和编码模式

默认设置会生成一个非常小的条形码，可能难以读取。我们来微调几个参数：

- **X‑Dimension** – 控制每个模块的宽度（像素大小）
- **EncodeMode** – 告诉引擎将输入视为扩展模式
- **TwoDDisplayText** – 可选的人类可读文本，显示在条形码下方

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**专业提示：** 如果在标签打印机上打印条形码，将 `XDimension` 提高到 20 px 或更高；大多数扫描器都喜欢留有一点额外空间。

### 5. 保存条形码图像

最后，将图像写入磁盘。库支持 PNG、JPEG、BMP 以及多种矢量格式——PNG 是安全的默认选项，因为它能保持边缘的清晰度。

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

确保 `YOUR_DIRECTORY` 已存在且可写。运行程序后，你应该会看到类似下方截图的文件。

![使用 C# PDF417 条形码生成器生成的 PDF417 条形码](https://example.com/images/pdf417-extended.png "使用 C# PDF417 条形码生成器生成的 PDF417 条形码")

---

## 深入使用 **C# PDF417 条形码生成器**

### 处理 Unicode 与特殊字符

当你直接将 Unicode 符号写入纯文本条形码时，生成器可能会回退到默认编码，导致输出乱码。使用 `AddECICodetext` 可以显式告诉编码器使用哪种字符集，消除猜测。如果需要支持**阿拉伯语**、**希伯来语**或**表情符号**，只需选择相应的 `ECIEncodings` 值。

### 调整错误纠正级别

PDF417 提供四个错误纠正级别（0‑8）。更高的级别提升容错能力，但也会增大条形码尺寸。通过以下方式调整：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### 打印与屏幕的缩放区别

在屏幕显示时可以保持默认的 96 dpi。若进行高分辨率打印（300 dpi 及以上），请设置：

```csharp
generator.Parameters.ImageResolution = 300;
```

这样可确保保存的 PNG 在激光打印机上保持足够的细节。

### 常见陷阱

- **缺少 `using` 指令** – 忘记 `using Aspose.BarCode.Encoding;` 会导致 `ECIEncodings` 未定义。
- **目录不存在** – `Save` 方法不会自动创建中间文件夹；请提前创建或使用 `Path.Combine` 与 `Environment.CurrentDirectory`。
- **错误的编码模式** – 若将 `EncodeMode` 保持为 `Pdf417EncodeMode.Auto`，库可能会将你的扩展编码文本当作普通文本处理，去除 ECI 标记。

---

## 完整、可直接运行的示例

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```

## 接下来该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在自己的项目中进一步掌握 API 功能并探索替代实现方式。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}