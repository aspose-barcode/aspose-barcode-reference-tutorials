---
category: general
date: 2026-08-03
description: 条形码生成器 C# 教程展示了如何使用 Aspose.BarCode 生成条形码图像，设置列和行，并为 DataBar Expanded
  Stacked 保存 PNG 文件。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: zh
lastmod: 2026-08-03
og_description: 条形码生成器 C# 教程说明如何使用 Aspose.BarCode 生成条形码图像，配置 DataBar Expanded Stacked
  的列和行，并保存为 PNG 文件。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: C# 条形码生成器 – 生成条形码图像的分步指南
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 条形码生成器 C# – 生成条形码图像
url: /zh/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 条形码生成器 C# – 生成条形码图像

如果您需要一个能够为 DataBar Expanded Stacked 生成条形码图像的 C# 条形码生成器，本指南将带您完成整个过程。您将学习如何配置列和行设置，将结果保存为 PNG，并将代码适配到其他符号系统。

以编程方式生成条形码图像可以消除手动步骤，并确保发票、运输标签和库存系统的一致性。本教程涵盖了您所需的全部内容，从项目设置到完整源代码，让您可以立即运行示例。

## 先决条件

在开始之前，请确保您拥有：

* 已安装 .NET 6.0 或更高版本  
* 如 Visual Studio 2022 等 IDE（任何支持 C# 的编辑器均可）  
* **Aspose.BarCode for .NET** 的许可证 – 免费评估版可用于测试  
* 对 C# 语法有基本了解  

如果缺少上述任意项，请从 dotnet.microsoft.com 安装 .NET SDK，并使用以下方式获取 Aspose.BarCode NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

## 步骤 1：创建条形码生成器 C# 项目

创建一个新的控制台应用程序并添加所需的 `using` 指令：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

`BarcodeGenerator` 类是条形码生成器 C# API 的核心。它接收符号类型和要编码的文本。

## 步骤 2：生成 DataBar Expanded Stacked 条形码并设置列数

第一个示例创建了一个具有四列的条形码。调整 `Columns` 属性会改变 DataBar Expanded Stacked 符号的视觉密度。

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**为什么这很重要：** 列数会影响在紧凑空间中可存储的数据量。将其设置为 4 会生成更宽的条形码，且大多数扫描仪仍能读取。

## 步骤 3：生成具有自定义行数的条形码

第二个示例展示了如何通过设置 `Rows` 属性来控制垂直布局。当水平空间受限且需要更高的条形码时，三行配置非常有用。

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**为什么这很重要：** 调整行数可以让条形码适配狭窄的列，同时保持可读性。条形码生成器 C# 会自动重新计算模块大小以符合规范。

## 步骤 4：完整、可运行的示例

下面是一个独立的程序，结合了前面的步骤。将代码复制到 `Program.cs`，将 `YOUR_DIRECTORY` 替换为现有文件夹路径，然后运行应用程序。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### 预期输出

运行程序后，目标目录中会出现两个 PNG 文件：

* **DatabarCols4.png** – 具有四列的 DataBar Expanded Stacked 条形码  
* **DatabarRows3.png** – 相同数据以三行方式编码  

使用任意图像查看器打开这些图片；它们显示出清晰、可扫描的条形码，已准备好用于打印或嵌入 PDF。

## 如何使用自定义尺寸生成条形码图像

如果需要特定的图像尺寸，请在调用 `Save` 之前调整 `ImageHeight` 和 `ImageWidth` 属性：

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

更改尺寸不会影响编码数据；它仅对视觉表现进行缩放。当将条形码集成到具有固定布局约束的 UI 组件时，此技术非常有用。

## 常见陷阱与专业提示

* **路径分隔符：** 使用逐字字符串 (`@"C:\Path\file.png"`) 或 `Path.Combine` 来避免 Windows 上的转义字符问题。  
* **许可证强制：** 如果没有有效许可证，生成的图像会带有水印。请在应用程序中尽早应用许可证：

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **编码限制：** DataBar Expanded Stacked 支持最多 74 个数字字符。超出此限制会抛出异常。请在创建生成器之前验证输入长度。  
* **性能：** 对多个保存操作复用同一个 `BarcodeGenerator` 实例可减少内存分配。如果编码文本保持不变，仅在保存之间更改 `Rows` 或 `Columns` 属性。

## 后续步骤

既然您已经可以使用条形码生成器 C# 生成条形码图像，接下来可以探索：

* **不同的符号系统** – 尝试 `EncodeTypes.QR`、`EncodeTypes.Code128` 或 `EncodeTypes.Pdf417`。  
* **颜色自定义** – 设置 `Parameters.Barcode.ForeColor` 和 `BackColor` 以匹配品牌色彩。  
* **嵌入 PDF** – 将生成的 PNG 与 Aspose.PDF 结合，创建可打印文档。  

这些扩展使您能够构建面向库存、物流或零售应用的完整条形码解决方案。

---

## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能，并在自己的项目中探索替代实现方法。

- [生成条形码图像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [创建 DotCode 条形码图像 – 行与列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条码 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}