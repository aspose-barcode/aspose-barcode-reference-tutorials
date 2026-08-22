---
category: general
date: 2026-08-22
description: 了解 C# 条码生成器如何更改条码尺寸、调整尺寸，并在 DataBar Expanded Stacked 条码中生成多行。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: zh
lastmod: 2026-08-22
og_description: C# 条码生成器教程，展示如何更改条码尺寸、调整尺寸参数，并使用自定义设置生成多行条码。
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: C# 条码生成器指南 – 更改尺寸、行和列
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何使用 C# 条码生成器自定义条码尺寸
url: /zh/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 条码生成器自定义条码尺寸

如果您需要一个 **c# barcode generator**，能够随时 **change barcode size**，本指南将精确演示如何操作。我们将生成一个 DataBar Expanded Stacked 条码，通过设置自定义列和行来调整其宽度和高度，并保存三个示例图像。

您将在本教程结束时获得一个完整、可运行的控制台程序，演示 **custom barcode dimensions**、**generate barcode multiple rows** 和 **adjust barcode dimensions**，且无需离开 IDE。

## 您需要的条件

| 前置条件 | 原因 |
|--------------|----------------|
| .NET 6.0 SDK 或更高版本 | 为控制台应用提供运行时 |
| Visual Studio 2022（或 VS Code） | 提供带 IntelliSense 的编辑器 |
| Aspose.Barcode for .NET NuGet 包 | 提供示例中使用的 `BarcodeGenerator` 类 |
| 对磁盘文件夹的写入权限 | 生成器会将 PNG 文件保存到该位置 |

Install the library with the NuGet CLI:

```bash
dotnet add package Aspose.Barcode
```

Or use the Visual Studio Package Manager:

```powershell
Install-Package Aspose.Barcode
```

## 步骤 1：设置基本的 C# 条码生成器

创建一个新的控制台项目并添加所需的 `using` 指令。此步骤创建一个最小的 **c# barcode generator**，能够输出一个简单的 DataBar Expanded Stacked 条码。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**为什么这样有效：** `EncodeTypes.DatabarExpandedStacked` 告诉生成器使用哪种符号。`Save` 方法将 PNG 文件写入磁盘。此时条码使用库的默认尺寸。

## 步骤 2：通过调整列来更改条码尺寸

DataBar Expanded Stacked 条码的宽度由 **columns** 属性控制。设置此属性可让 **c# barcode generator** 生成更宽或更窄的条码。

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**说明：** 列影响水平模块计数。列数越多，条码越宽，这在需要为更长的可读文本留出额外空间或在宽标签上打印时非常有用。

## 步骤 3：生成多行条码以控制高度

高度由 **rows** 属性决定。通过增加行数，您可以 **generate barcode multiple rows** 并使符号更高——适合高分辨率扫描。

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**为什么行数重要：** 行会增加垂直模块。更高的条码可以在低对比度背景或扫描仪焦距变化时提升可读性。

## 步骤 4：组合自定义列和行以实现完整控制

既然您已经了解如何 **adjust barcode dimensions**，现在可以同时设置这两个属性。此步骤创建一个具有六列十行的条码，展示 **c# barcode generator** 的全部灵活性。

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**结果：** 文件 `DatabarCols6Rows10.png` 包含的条码比默认尺寸更宽更高，证明您可以 **adjust barcode dimensions** 以满足任何布局需求。

## 完整可运行示例

下面是整合了全部四个步骤的完整程序。将其复制到 `Program.cs`，运行 `dotnet run`，并检查 `C:\Temp\Barcodes\` 文件夹中的四个 PNG 文件。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### 预期输出

运行程序会生成四个 PNG 文件：

| 文件名 | 视觉描述 |
|--------------------------|--------------------|
| `DefaultDatabar.png`     | 标准宽度和高度 |
| `DatabarCols4.png`       | 更宽的条码（4 列） |
| `DatabarRows3.png`       | 更高的条码（3 行） |
| `DatabarCols6Rows10.png` | 既更宽又更高（6 列，10 行） |

在图像查看器中打开任意 PNG；您会看到 DataBar Expanded Stacked 图案已按照指定精确调整。

## 常见陷阱与专业提示

- **Invalid column/row values** – 如果设置的值超出支持范围（列 1‑12，行 1‑10），库会抛出 `ArgumentException`。在赋值前请验证输入。
- **Directory permissions** – 如果输出文件夹受保护，`Save` 将失败。使用如示例所示的 `System.IO.Directory.CreateDirectory` 来确保路径存在。
- **Performance** – 在循环中创建大量条码可能会占用大量 CPU。复用同一个 `BarcodeGenerator` 实例，仅在保存之间修改 `Columns`/`Rows`，以降低对象分配开销。
- **Scanning considerations** – 极高或极宽的条码可能超出扫描仪的视野。调整尺寸后请使用目标硬件进行测试。

## 结论

现在您拥有一个完整的 **c# barcode generator** 示例，能够 **change barcode size**、**custom barcode dimensions**、**generate barcode multiple rows**，以及 **adjust barcode dimensions**，以适配任何应用。通过调节 `Columns` 和 `Rows` 属性，您可以精确控制 DataBar Expanded Stacked 条码的视觉占位。

随意尝试其他符号（`EncodeTypes.QR`、`EncodeTypes.Code128`）或输出格式（`BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Svg`）。相同的模式——创建 `BarcodeGenerator`、设置尺寸属性，然后调用 `Save`——适用于整个 Aspose.Barcode API。

**接下来的步骤**

- 探索 QR 码的 **error correction levels**。
- 结合 **custom colors** 和 **background images** 为条码打造品牌形象。
- 将生成器集成到 ASP.NET Core Web 服务中，实现按需条码创建。

Happy coding!


## 接下来您应该学习什么？

以下教程涵盖与本指南技术密切相关的主题，构建在所示技巧之上。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何使用 Aspose.BarCode for .NET 生成和调整一维 Databar 条码高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何使用 Aspose.BarCode for .NET 调整 Codablock F 条码尺寸 – 纵横比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 生成具有自定义纵横比的 Aztec 条码](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}