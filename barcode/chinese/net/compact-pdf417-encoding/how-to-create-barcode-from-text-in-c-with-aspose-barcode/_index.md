---
category: general
date: 2026-10-02
description: 使用 Aspose.BarCode 在 C# 中从文本创建条形码。了解如何生成 PDF417 条形码，并查看如何在紧凑模式下生成 PDF417
  条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: zh
lastmod: 2026-10-02
og_description: 使用 Aspose.BarCode 在 C# 中从文本创建条形码。本指南展示了如何生成 PDF417 条形码以及如何在紧凑模式下生成
  PDF417 条形码。
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: 在 C# 中从文本创建条形码 – 步骤指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: 如何使用 Aspose.BarCode 在 C# 中从文本创建条形码
url: /zh/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 从文本创建条形码

如果您需要在 .NET 应用程序中 **从文本创建条形码**，本指南将一步步带您完成整个过程。您将看到一个可直接运行的示例，**生成 PDF417 条形码**，并解答 **如何在紧凑布局中生成 PDF417 条形码**。

以编程方式生成条形码可以省去手动操作，并确保所有文档的一致性。完成本教程后，您将得到一个包含 PDF417 条形码的 PNG 文件，可嵌入发票、票据或身份证等场景。

## 您需要准备的环境

- .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Framework 4.7.2+）
- Visual Studio 2022 或任何支持 C# 的编辑器
- **Aspose.BarCode for .NET** 的 NuGet 许可证（免费试用版可用于测试）

> **专业提示：** 通过 CLI 添加 NuGet 包以保持项目整洁：  
> `dotnet add package Aspose.BarCode`

## 第一步：创建控制台项目

创建一个新的控制台应用并引用 Aspose.BarCode 库。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 命令会生成一个 `Program.cs` 文件，我们将在后面用完整示例代码替换它。

## 第二步：如何从文本创建条形码 – 核心代码

打开 `Program.cs`，将其内容替换为以下代码。每行代码均已添加注释，说明其作用。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 每个设置的重要性

| 设置 | 目的 |
|--------|----------|
| `EncodeTypes.Pdf417` | 选择 PDF417 编码方式，可在二维矩阵中存储大量数据。 |
| `XDimension.Pixels = 2` | 控制每个模块的宽度；2 像素在可读性和文件大小之间取得平衡。 |
| `Pdf417.Columns = 3` | 减少列数，使条形码更紧凑且不丢失数据。 |
| `Pdf417.Truncate = true` | 启用紧凑模式，去除不必要的填充，缩短条形码。 |
| `BarCodeImageFormat.Png` | PNG 保持无损质量，适合后续处理或打印。 |

## 第三步：生成 PDF417 条形码 – 运行示例

构建并运行项目：

```bash
dotnet run
```

执行完成后您将看到：

```
Barcode saved to CompactPdf417.png
```

打开 `CompactPdf417.png` 查看结果。图像中包含一个编码为 **Åspóse.Barcóde©** 的 PDF417 条形码。

![Create barcode from text example](barcode-example.png)

*Alt text: 从文本创建条形码 – PDF417 条形码已保存为 PNG*

## 第四步：如何使用自定义错误纠正生成 PDF417 条形码（可选）

如果扫描环境噪声较大，可以提升错误纠正级别：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

提高错误纠正级别会使条形码变大，但能增强对损坏的抵抗力。

## 第五步：常见陷阱与边缘情况处理

1. **无效字符** – PDF417 支持 Unicode，但某些老旧扫描仪可能会拒绝非 ASCII 符号。请在目标硬件上进行测试。  
2. **文件路径权限** – 确保写入的目录具有写权限，否则 `Save` 会抛出 `UnauthorizedAccessException`。  
3. **图像尺寸** – 过高的 `XDimension` 会生成大的 PNG 文件。大多数屏幕显示场景下，像素大小保持在 1 到 4 之间即可。

## 小结

现在您已经掌握了如何在 C# 中使用 Aspose.BarCode **从文本创建条形码**，以及如何 **生成紧凑布局的 PDF417 条形码**，并了解了 **如何使用自定义设置生成 PDF417 条形码** 的完整步骤。上面的完整可运行代码可以直接复制到任何 .NET 项目中，并根据不同的文本输入或输出格式（如 JPEG、BMP）进行调整。

## 后续步骤

- 通过更改 `EncodeTypes`，探索 QR Code、Code128 等其他编码方式。  
- 使用 Aspose.PDF 将生成的 PNG 嵌入 PDF，实现端到端文档创建。  
- 尝试 `generator.Parameters.Barcode.Pdf417.Rows` 来控制垂直密度。

欢迎修改示例，将条形码嵌入您自己的应用，并与社区分享成果。祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您进一步掌握 API 功能并探索在项目中的其他实现方式。每篇资源均提供完整可运行的代码示例和逐步解释。

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}