---
category: general
date: 2026-10-15
description: 如何使用 BarCodeReader 在 C# 中快速读取条码图像。学习读取多个条码，并查看适用于 Macro‑PDF417 的 C# 条码读取器示例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: zh
lastmod: 2026-10-15
og_description: 如何在 C# 中使用 BarCodeReader 读取条形码。本教程展示了一个完整的 C# 条形码读取示例，能够处理多个条形码并提取
  Macro‑PDF417 元数据。
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: 如何在 C# 中读取条形码 – 步骤示例
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中读取条形码图像 – 完整示例指南
url: /zh/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中读取条形码图像 – 完整示例指南

如果您需要在 .NET 应用程序中**读取条形码**数据，本指南提供了一个可直接运行的解决方案。您将看到一个完整的**c# 条形码读取示例**，它支持 Macro‑PDF417 符号，并且能够**从单张图片读取多个条形码**。

读取条形码是库存系统、票据验证和文档处理的常见需求。完成本教程后，您将能够：

* 为任意受支持的格式初始化 `BarCodeReader`。  
* 提取基本信息，如代码类型和解码文本。  
* 获取 Macro‑PDF417 特有的元数据（文件 ID、段号、校验和，……）。  
* 在不编写额外代码的情况下处理包含多个条形码的图像。

## 前提条件

在开始之前，请确保您已具备：

* 已安装 .NET 6.0 SDK 或更高版本。  
* 开发环境（Visual Studio 2022、VS Code 或 Rider）。  
* **Aspose.BarCode for .NET** NuGet 包（`Aspose.BarCode`）——它提供本示例中使用的 `BarCodeReader` 类。  
* 包含 Macro‑PDF417 条形码的图像文件（例如 `MacroPdf417.png`）。  

您可以使用以下命令安装 NuGet 包：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中使用 BarCodeReader 读取条形码

解决方案的核心分为四个简洁步骤。每个步骤都放在 `using` 块中，以确保及时释放非托管资源。

### 步骤 1：初始化 `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**为什么这很重要：**  
`BarCodeReader` 接受文件路径和 `DecodeType`。指定 `DecodeType.MacroPdf417` 可让库仅搜索 Macro‑PDF417 符号，从而提升检测速度并降低误报。

### 步骤 2：读取图像中出现的所有条形码

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**为什么这很重要：**  
`ReadBarCodes()` 方法返回一个数组，可能包含一个或多个 `BarCodeResult` 对象。这正是**读取多个条形码**功能发挥作用的地方——您无需为每个可能的条形码编写单独的循环。

### 步骤 3：显示基本条形码详情

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**为什么这很重要：**  
`CodeTypeName` 告诉您检测到的符号类型（例如 “MacroPDF417”），而 `CodeText` 保存了解码后的负载。这两个字段是下游逻辑中最常用的。

### 步骤 4：获取并展示 Macro‑PDF417 特定的元数据

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**为什么这很重要：**  
Macro‑PDF417 在普通 PDF417 格式基础上添加了文档级元数据。访问 `Extended.Pdf417` 属性即可获取重建原始文件、验证完整性或将数据路由至正确接收方所需的全部信息。

### 完整可运行程序

下面是一个自包含的控制台应用程序，将上述四个步骤整合在一起。将代码复制到新的 `.cs` 文件，修改 `imagePath`，然后运行 `dotnet run`。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### 预期的控制台输出

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

如果图像中包含多个 Macro‑PDF417 符号，程序会为每个条形码打印一个独立的块，展示**读取多个条形码**的能力，而无需额外代码。

## 处理常见边缘情况

| 情况 | 处理方法 | 原因 |
|-----------|------------|--------|
| **文件未找到** | 将 `BarCodeReader` 的构造放在 `try/catch (FileNotFoundException)` 块中，并显示友好的提示信息。 | 防止应用崩溃并告知用户缺少资源。 |
| **未检测到条形码** | 检查 `results.Length == 0`（如完整程序所示），并进行相应处理。 | 当图像不包含任何受支持的符号时提供明确反馈。 |
| **不同的条形码类型** | 将 `DecodeType.MacroPdf417` 改为 `DecodeType.AllSupportedTypes` 或其他具体枚举值。 | 使相同代码能够处理 QR、Code128、DataMatrix 等，同时仍支持**读取多个条形码**。 |
| **大图像** | 设置 `reader.AutoSize = true` 或在将图像传递给读取器之前进行下采样。 | 提升性能并降低 CLR 的内存压力。 |
| **线程安全使用** | 为每个线程创建单独的 `BarCodeReader` 实例；该类本身不是线程安全的。 | 避免在多线程扫描器或 Web 服务中出现竞争条件。 |

## 生产代码的专业提示

* **提前释放：** `using` 语句确保本机资源（例如图像缓冲区）能够及时释放。在长期运行的服务中，处理完每张图像后尽快释放读取器。  
* **批量处理**  

## 接下来应该学习什么？

以下教程涵盖与本指南技术紧密相关的主题，帮助您进一步掌握 API 功能并在项目中探索替代实现方式。每篇资源均提供完整可运行的代码示例和逐步解释。

- [从图像读取条形码 C# – 包含 Macro PDF417 的完整指南](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [如何在 C# 中使用 Aspose.BarCode 创建 Macro PDF417 条形码](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 中读取 PDF417 – 完整条形码读取示例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}