---
category: general
date: 2026-07-15
description: 如何在 C# 中读取 PDF417 条码并从图像中读取多个条码。学习使用 C# 读取条码图像，提供详细代码和技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: zh
lastmod: 2026-07-15
og_description: 如何在 C# 中快速读取 PDF417 条码。本指南展示了如何从单张图像中读取多个条码并解码每个属性。
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: 如何在 C# 中读取 PDF417 – 完整代码示例与解释
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: 如何在 C# 中读取 PDF417 – 完整的逐步指南
url: /zh/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取 PDF417 – 完整分步指南

是否曾想过 **如何从图像中读取 PDF417**？你并不是唯一的遇到这个问题的开发者。大多数人在需要从扫描文档中提取扩展的 Macro‑PDF417 字段时都会卡住。好消息是，只需几行代码就能解码 PDF417，读取同一图片中的多个条码，并获取规范提供的所有隐藏属性。

在本教程中，我们将通过一个真实案例演示 **如何读取 PDF417**、如何 **从单个文件读取多个条码**，以及为什么 **read barcode image C#** 代码会是这样的。完成后，你将拥有一个可直接运行的控制台应用程序，能够打印出你可能需要的所有信息——文件 ID、段 ID、校验和、时间戳，等等。

## 前置条件

在开始之前，请确保你具备以下条件：

* .NET 6.0 SDK 或更高版本（代码同样适用于 .NET Core 和 .NET Framework）。  
* Visual Studio 2022（或你喜欢的任何编辑器）。  
* **Aspose.BarCode for .NET** NuGet 包——这就是实际解析 PDF417 的库。  
* 包含 Macro‑PDF417 条码的示例图像（例如 `ExtPDF417Meta.png`）。  

无需额外配置；库已自带所有所需的解码器。

## 第一步：安装 Aspose.BarCode

在终端中打开项目文件夹并运行：

```bash
dotnet add package Aspose.BarCode
```

该命令会拉取最新的稳定版本（截至 2026 年 7 月为 23.12）。如果你更喜欢在 Visual Studio 内的 Package Manager Console 中操作，请使用：

```powershell
Install-Package Aspose.BarCode
```

> **小贴士：** 在 `.csproj` 中锁定版本号（`23.12.0`），以避免后期意外的破坏性更改。

## 第二步：创建控制台应用骨架

如果还没有控制台项目，请新建一个：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

用下面的代码替换自动生成的 `Program.cs`。我们将在后面的章节逐块解释。

## 第三步：编写完整的 “如何读取 PDF417” 代码

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### 为什么这段代码可行

* **`BarCodeReader`** 是核心类，用于流式读取图像、检测条码，并返回 `BarCodeResult` 对象集合。  
* 传入 **`DecodeType.MacroPdf417`** 告诉库特殊处理 Macro‑PDF417；它仍会返回普通 PDF417 符号，从而满足 **read multiple barcodes** 的需求。  
* **`Extended.Pdf417.MacroPdf417`** 对象包含 ISO/IEC 15438 标准定义的所有可选字段——这就是你获取 `FileID`、`SegmentID`、`Checksum` 等信息的地方。  
* `using` 块保证本机资源被释放，防止长时间运行的服务出现内存泄漏。

## 第四步：运行应用并验证输出

在终端中执行：

```bash
dotnet run
```

你应该会看到类似如下的输出：

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

如果图像中包含多个条码，循环会打印分隔线（`----------------------------------------`），并继续处理下一个结果——这正是 **read multiple barcodes** 在实际中的表现。

## 常见问题与边缘情况

### 如果图像同时包含 Macro‑PDF417 和普通 PDF417 符号怎么办？

同一次 `BarCodeReader` 调用会返回两者。你可以通过检查 `result.CodeType`（`MacroPdf417` 与 `Pdf417`）来区分。对于普通 PDF417，扩展属性会为 `null`，因此 `if (macro != null)` 判断可以防止 `NullReferenceException`。

### 我的条码被旋转或倾斜——读取器还能工作吗？

Aspose.BarCode 内置了旋转和畸变补偿。只要条码宽度至少占图像宽度的 30%，解码器通常能够成功。对于极端情况，你可以在调用 `ReadBarCodes()` 前启用 `reader.Options.AllowInvertedBarcodes = true;`。

### 如何处理大量图像批量读取？

将读取逻辑包装在 `foreach (var file in Directory.GetFiles(folder, "*.png"))` 循环中。`using` 模式确保每张图像的本机资源在下一次迭代前被释放，从而保持低内存占用。

## 完整源码列表（可直接复制粘贴）

下面是一整块的完整程序，方便快速复制粘贴。没有隐藏依赖——只需 Aspose.BarCode NuGet 包。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## 小结 – 本文覆盖内容

* 使用 Aspose.BarCode 在 C# 中 **读取 PDF417**。  
* 从单张图像 **读取多个条码** 的完整步骤。  
* 如何 **read barcode image C#** 并提取每个 Macro‑PDF417 字段。  
* 旋转、批处理以及缺失扩展数据的处理技巧。

## 后续步骤与相关主题

* **Encode PDF417** – 使用 `BarCodeBuilder` 生成自己的 Macro‑PDF417 条码。  
* **读取其他 2‑D 符号** – QR、DataMatrix、Aztec ——同样使用 `BarCodeReader` 类。  
* **与 ASP.NET Core 集成** – 暴露一个 Web 端点，接受上传的图像并返回包含解码字段的 JSON。  

尽情实验吧：更改图像路径、在同一文件夹中放入普通 PDF417，或调节 `DecodeType` 标志观察库的行为。玩得越多，你对 **read barcode image C#** 场景的掌握就越熟练。

遇到难解的图像？在下方留言或在示例项目的 GitHub 仓库中提交 Issue。祝编码愉快！

## 接下来你应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助你在项目中进一步扩展 API 功能并探索替代实现方式，每篇都提供完整可运行的代码示例和逐步解释。

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}