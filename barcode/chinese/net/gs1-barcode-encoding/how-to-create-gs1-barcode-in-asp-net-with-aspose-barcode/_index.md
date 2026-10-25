---
category: general
date: 2026-10-24
description: 学习如何在 ASP.NET 中使用 Aspose.BarCode 创建 GS1 条码。一步一步的指南，帮助您从字符串生成条码并渲染为 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: zh
lastmod: 2026-10-24
og_description: 如何在 ASP.NET 中使用 Aspose.BarCode 创建 GS1 条码。请按照本教程从字符串生成条码、配置视觉设置并保存
  PNG 文件。
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: 如何在 ASP.NET 中创建 GS1 条码 – 完整的 Aspose 指南
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: 如何在 ASP.NET 中使用 Aspose.BarCode 创建 GS1 条码
url: /zh/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 ASP.NET 中使用 Aspose.BarCode 创建 GS1 条码

如果您需要在 ASP.NET 应用程序中 **如何创建 GS1 条码**，本指南将向您展示完整步骤。您将看到如何从字符串生成条码、配置视觉外观，并将结果保存为 PNG 图像。

创建 GS1 条码不需要自定义编码逻辑。使用 Aspose.BarCode，您可以获得一个可靠、符合标准的解决方案，适用于 .NET 6+ 以及更早的框架。本教程涵盖从项目设置到验证输出的全部内容，您可以直接将代码复制到自己的 Web 项目中。

## 前置条件

在开始之前，请确保您拥有：

* Visual Studio 2022（或任何支持 .NET 的 IDE）
* .NET 6 SDK（或 .NET Framework 4.7.2 及以上）
* 基本的 ASP.NET Core 或 ASP.NET Framework 知识
* Aspose.BarCode 许可证（免费评估版可用于测试）

不需要额外的第三方库，因为 Aspose.BarCode 在内部处理所有编码和渲染。

## 第 1 步：创建一个新的 ASP.NET 项目

打开 Visual Studio，创建一个 **ASP.NET Core Web App**（选择 *Empty* 模板）。对于经典的 Web Forms 项目，相同的代码也可以放在代码隐藏文件中使用。

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

运行项目后，浏览器应显示 *GS1 barcode generator is ready.*，这表明 Web 主机已正常工作。

## 第 2 步：通过 NuGet 安装 Aspose.BarCode

打开 **Package Manager Console**，运行：

```powershell
Install-Package Aspose.BarCode
```

该包会添加 `Aspose.BarCode.Generation` 命名空间，其中包含您将用于 **从字符串生成条码** 的 `BarcodeGenerator` 类。NuGet 命令还会在项目文件中添加所需的引用。

## 第 3 步：从字符串生成简单条码

为演示基本用法，创建一个返回 PNG 字节数组的帮助方法。该方法可以从控制器、Razor 页面或任何端点调用。

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

现在您可以在任意端点调用 `GenerateBarcode("HelloWorld", EncodeTypes.Code128)`，并将生成的字节写入 HTTP 响应。这展示了 **barcode generator asp.net** 的通用字符串模式。

## 第 4 步：如何创建 GS1 条码 – Micro PDF417 示例

GS1 条码嵌入了表示产品信息的应用标识符（AI）。Aspose.BarCode 支持 GS1 兼容的 Micro PDF417 变体，非常适合紧凑的数据表示。

### 4.1 准备 GS1 数据字符串

GS1 数据必须用括号包围 AI 代码。对于产品标识符 (01) 和批次号 (10)，字符串如下：

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

括号是标准的一部分；Aspose.BarCode 会自动解析它们。

### 4.2 构建 GS1 Micro PDF417 生成器

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 通过 ASP.NET 端点公开生成器

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

访问 `https://localhost:5001/gs1barcode` 即可流式传输生成的 PNG。图像符合 GS1 规范，文件也会存储到磁盘以供后续使用。

## 第 5 步：渲染其他条码类型

相同的 **create barcode with aspose** 方法同样适用于其他符号。下面是一个从 URL 创建 QR 码的快速示例：

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

您可以将 `EncodeTypes.QR` 替换为 `EncodeTypes.Code128`、`EncodeTypes.DataMatrix` 或其他受支持的类型。视觉参数（`XDimension`、`Resolution`、`Color`）可通过 `Parameters` 对象进行配置。

## 第 6 步：常见陷阱与最佳实践提示

| 问题 | 产生原因 | 规避方法 |
|------|----------|----------|
| **AI 格式不正确** | 缺少括号或 AI 长度错误会导致编码错误。 | 始终严格按照标准构建 GS1 字符串。使用帮助方法拼接 AI。 |
| **列数过多** | Micro PDF417 仅支持 1‑4 列，设置为 5 会抛出异常。 | 在赋值前验证列数：`if (columns < 1 || columns > 4) throw …` |
| **图像分辨率过低** | 较小的 `XDimension` 值会导致条码在打印机上难以读取。 | 对于打印级条码，提升 `Resolution`（例如 `generator.Parameters.Image.Resolution = 300`）。 |
| **Linux 上的文件路径问题** | 硬编码的反斜杠在非 Windows 主机上失效。 | 使用 `Path.Combine` 构建文件路径，它会自动处理操作系统特定的分隔符。 |
| **许可证未应用** | 免费评估版在 30 天后会添加水印。 | 及早应用许可证：`new License().SetLicense("Aspose.BarCode.lic");` |

## 第 7 步：验证生成的条码

运行端点后，在任意图像查看器中打开 PNG。要确认 GS1 数据已正确编码，您可以使用支持 GS1 Micro PDF417 的免费移动扫描器（许多条码扫描应用都列出了此符号）。扫描图像后，应用应返回：

```
(01)12345678901234
(10)ABCD
```

如果扫描器报错，请再次检查 AI 格式和列数。

## 结论

现在您已经掌握了在 ASP.NET 环境中使用 Aspose.BarCode **如何创建 GS1 条码**。本教程涵盖了：

* 设置 ASP.NET 项目并安装 Aspose.BarCode NuGet 包。  
* 使用 **generate barcode from string** 生成通用条码。  
* 实现 **create barcode with aspose** 生成 GS1 兼容的 Micro PDF417 图像。  
* 将图像保存到磁盘并通过 HTTP 端点流式传输。  

接下来，您可以探索其他 GS1 符号（例如 GS1 DataMatrix），或将生成器集成到更大的订单处理工作流中。尝试不同的 `XDimension`、颜色和纠错级别，以匹配您的品牌和扫描环境。

祝编码愉快，让您的应用说出条码的通用语言！

## 接下来您应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每个资源都提供完整的可运行代码示例和逐步解释。

- [How to create code 128 barcode with GS1 using Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}