---
category: general
date: 2026-11-14
description: 学习如何在 C# 中从图像读取条形码，完整的条形码读取器教程。包括设置、完整代码以及处理 Macro PDF417 字段。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: zh
lastmod: 2026-11-14
og_description: 使用此 C# 条码读取器教程，从图像中读取条码。获取完整的工作示例并学习提取 Macro PDF417 数据。
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: 在 C# 中从图像读取条形码 – 完整教程
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: 使用 C# 从图像读取条形码的逐步指南
url: /zh/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 从图像读取条形码 – 步骤指南

如果您需要在 .NET 应用程序中 **从图像读取条形码**，本指南将详细演示。教程结束时，您将拥有一个完整、可运行的程序，能够提取基本条码数据以及 Macro PDF417 特定字段。

在本 **barcode reader tutorial c#** 中，我们将介绍项目设置、所需的 NuGet 包，以及一个可在最新 .NET 8 SDK 上运行的完整代码示例。无需外部服务——所有操作均在本地完成。

## 您将学习的内容

- 如何将 Aspose.BarCode（或类似）库添加到 C# 项目中。  
- 如何创建针对特定图像文件的 `BarCodeReader`。  
- 如何遍历所有检测到的条形码并输出其类型、文本以及 Macro PDF417 元数据。  
- 处理包含多个条形码或不同解码类型的图像的技巧。

### 前置条件

- 已安装 .NET 8 SDK（或您偏好的 .NET 6+）。  
- 对 C# 控制台应用有基本了解。  
- 包含 Macro PDF417 条码的图像文件（例如 `MacroPdf417.png`）。

---

## 步骤 1：创建新的控制台项目

打开终端并运行：

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

这将在终端中创建一个名为 **BarcodeReaderDemo** 的最小控制台应用。项目文件 (`BarcodeReaderDemo.csproj`) 将在下一步使用。

## 步骤 2：安装条码读取库

对于本教程，我们使用 **Aspose.BarCode for .NET** 库，因为它开箱即支持 Macro PDF417。通过 NuGet 安装：

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **为什么选择此库？** 它提供了单一的 `BarCodeReader` 类，支持数十种符号，并公开了包含 Macro PDF417 字段的 `Extended` 属性。

## 步骤 3：编写条码读取代码（barcode reader tutorial c#）

将 `Program.cs` 的内容替换为以下完整示例。它演示了 **如何从图像读取条形码**，并打印通用信息和 Macro PDF417 特定信息。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 各步骤说明

| 步骤 | 为什么重要 |
|------|----------------|
| **1️⃣ 定义图像路径** | 读取器可以使用文件路径或流。使用相对路径使示例易于复制粘贴。 |
| **2️⃣ 创建 BarCodeReader** | 传入 `DecodeType.MacroPdf417` 将扫描限制在该符号上，提升速度并确保 `Extended` 字段被填充。 |
| **3️⃣ 遍历结果** | 一张图像可能包含多个条码；`foreach` 循环确保全部捕获。 |
| **4️⃣ 通用输出** | `CodeTypeName` 和 `CodeText` 是开发者最常需要的信息。 |
| **5️⃣ Macro PDF417 字段** | Macro PDF417 包含额外数据（文件 ID、段 ID、段计数）。访问 `result.Extended.Pdf417` 可直接获取这些值，无需额外解析。 |
| **6️⃣ 可选额外字段** | 库还公开了其他宏字段（例如 `MacroPdf417FileName`）。您可以根据使用场景扩展输出。 |
| **7️⃣ 保持控制台打开** | 在 Visual Studio 或 `dotnet run` 运行时，有助于在窗口关闭前查看输出。 |

## 步骤 4：运行程序并验证输出

将您的 `MacroPdf417.png` 文件放置在 `imagePath` 所指的文件夹中。然后执行：

```bash
dotnet run
```

典型的控制台输出如下：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

如果图像包含多个 Macro PDF417 符号，程序将依次列出每组值。

## 常见变体和边缘情况

### 读取其他符号

如果您需要 **从图像读取条形码**，但不是 Macro PDF417，请将 `DecodeType.MacroPdf417` 替换为逗号分隔的列表，例如：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

对于不提供额外数据的符号，`Extended` 属性将为 `null`，因此在访问之前请始终检查是否为 `null`。

### 处理大图像

大型 PNG 或 JPEG 文件会增加内存使用。为保持轻量，可在传递给 `BarCodeReader` 前对图像进行降采样：

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### 使用流而非文件路径

当图像来自数据库或网络请求时，传入一个 `Stream`：

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## 条码读取体验的专业技巧

- **专业提示：** 始终将 `DecodeType` 设置为您预期的最小符号集合。这可减少误报并加快处理速度。  
- **注意事项：** 对比度低或压缩严重的图像可能导致读取失败。如果检测率低，建议对图像进行预处理（调整亮度/对比度）。  
- **技巧：** `BarCodeReader` 类实现了 `IDisposable`；使用 `using` 块可确保本机资源及时释放。  

---

## 结论

现在您已经了解如何在 C# 中 **从图像读取条形码**，并提取标准信息以及 Macro PDF417 特定信息。此 **barcode reader tutorial c#** 提供了一个完整、独立的解决方案，可直接嵌入任何 .NET 项目。

接下来您可能：

- 探索其他解码类型（QR、DataMatrix、Code128）。  
- 将读取器集成到 ASP.NET Core API 中，以实时处理上传。  
- 将提取的宏字段存入数据库，以便后续聚合。

祝编码愉快，欢迎尝试不同的图像来源和条码格式！

## 接下来您应该学习什么？

以下教程涵盖与本指南紧密相关的主题，构建在本教程演示的技术之上。每个资源都包含完整的可运行代码示例和逐步解释，帮助您掌握更多 API 功能并在项目中探索替代实现方案。

- [如何在 C# 中解码 PDF417 条码并读取条码图像](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [如何使用 Aspose.BarCode 从图像读取条码（C#）](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [从图像读取条码 C# – 包含 Macro PDF417 的完整指南](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}