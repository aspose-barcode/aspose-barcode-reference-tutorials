---
category: general
date: 2026-09-07
description: 在 C# 中生成 PDF417 条码，并学习如何设置条码尺寸以实现精确控制。按照此分步指南创建 PNG 图像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: zh
lastmod: 2026-09-07
og_description: 在 C# 中生成 PDF417 条码并学习如何设置条码尺寸。本教程展示了一个完整的可运行示例。
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: 在 C# 中生成 PDF417 条码 – 完整指南及尺寸说明
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: 如何在 C# 中使用自定义尺寸生成 PDF417 条形码
url: /zh/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中生成具有自定义尺寸的 PDF417 条码

如果您需要在 .NET 应用程序中 **生成 PDF417 条码**，本指南将手把手教您完成整个过程。您将看到一个完整、可运行的示例，它会生成 PNG 图像，并让您能够控制条码的尺寸。

生成 PDF417 条码是库存系统、登机牌以及安全文档的常见需求。在本教程中，您还将学习 **如何设置条码尺寸**，以便输出符合您的布局需求。

## 前置条件

在开始之前，请确保您已经具备：

- 已安装 .NET 6.0 SDK 或更高版本  
- Visual Studio 2022（或任何支持 C# 的 IDE）  
- **Aspose.BarCode for .NET** NuGet 包（或任何支持 PDF417 的兼容库）  

您可以使用以下命令添加该包：

```bash
dotnet add package Aspose.BarCode
```

## 第一步：创建 PDF417 条码生成器

第一步是实例化一个 `BarcodeGenerator`，使用 `EncodeTypes.Pdf417` 类型并传入您想要编码的文本。生成器对象会保存条码的所有设置。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**为什么重要：** `EncodeTypes.Pdf417` 枚举告诉库使用 PDF417 符号集，该符号集支持大容量数据和错误纠正。文本字符串可以包含 Unicode 字符，因而可以直接编码国际符号，无需额外处理。

## 第二步：如何设置条码尺寸

控制每个模块（最小的黑白方块）的大小决定了整体图像的分辨率。`XDimension.Pixels` 属性用于设置单个模块的像素宽度。

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**为什么重要：** 更大的 `XDimension` 会产生更高分辨率的图像，适合远距离打印或扫描。相反，较小的数值可以减小文件体积，适用于网页使用。

## 第三步：定义 PDF417 布局（列数和行数）

PDF417 允许通过指定列数和行数来影响矩阵形状。这会影响可读性以及条码的实际尺寸。

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**为什么重要：** 调整列数和行数可以让条码适配特定空间或满足扫描仪的宽高比要求。如果数据未填满矩阵，库会自动添加填充。

## 第四步：将条码保存为 PNG 图像

最后，将生成的条码写入文件。PNG 保留无损质量，非常适合后续处理。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

运行程序后，`Pdf417Layout.png` 会出现在项目的输出文件夹中。图像效果如下：

![生成的具有自定义尺寸的 PDF417 条码图像](og_image_placeholder.png)

*图片替代文字：生成的具有自定义尺寸的 PDF417 条码图像*  

**为什么重要：** 保存为 PNG 可确保您设置的模块尺寸被完整保留，这对后续的扫描应用至关重要。

## 完整示例（单块代码）

下面是完整的程序代码，您可以直接复制、粘贴并运行（如需更改输出路径，请自行修改）。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### 预期输出

- **文件：** `Pdf417Layout.png`（PNG，无损）  
- **尺寸：** 由 `XDimension`（2 px）×（列 × 行）矩阵决定  
- **内容：** 可扫描的 PDF417 条码，编码 Unicode 字符串 `Åspóse.Barcóde©`

## 常见问题与边缘情况

### 如果需要更大的图像用于打印怎么办？

将 `XDimension.Pixels` 提升至 4 或 5。更大的数值会生成更高分辨率的条码，但文件大小也会随之增加。

### 能否编码比示例字符串更多的数据？

可以。PDF417 最多可容纳 1,850 个字符。只需在 `BarcodeGenerator` 构造函数中替换文本参数。如果数据超出矩阵容量，库会自动添加额外行数。

### 错误纠正是如何工作的？

PDF417 内置错误纠正。您可以通过以下方式调整其级别：

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

更高的级别提升鲁棒性，但会使条码体积增大。

### 条码在屏幕上显示模糊怎么办？

确保输出图像的 DPI 与显示环境匹配。保存时可以设置 DPI：

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## 专业技巧

- **专业提示：** 始终使用实际的扫描仪对生成的条码进行测试。不同设备对模块大小和安静区的容忍度各不相同。  
- **注意事项：** 极小的 `XDimension` 值（< 1 px）在高 DPI 屏幕上可能呈现为不可见的细线。  
- **Web 应用技巧：** 为 PNG 设置 `Cache-Control: public, max-age=86400`，以减少重复生成的开销。

## 结论

现在，您已经掌握了在 C# 中 **生成 PDF417 条码** 并精确 **设置条码尺寸** 的方法，以满足任何需求。完整、可运行的示例展示了如何创建具有自定义列/行布局和模块大小的 PNG 图像，适用于打印或数字分发。

### 后续步骤

- 探索 **如何使用不同图像格式（JPEG、BMP）生成 PDF417 条码**。  
- 学习 **如何根据用户输入或设备 DPI 动态设置条码尺寸**。  
- 将条码生成集成到 ASP.NET Core API 中，以按需提供条码服务。

欢迎尝试其他 PDF417 设置，如错误纠正、边距和颜色。祝编码愉快！


## 接下来该学习什么？

以下教程涵盖与本指南紧密相关的主题，帮助您在项目中进一步使用 API 功能并探索替代实现方案，每篇资源均提供完整的可运行代码示例和逐步解释。

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}