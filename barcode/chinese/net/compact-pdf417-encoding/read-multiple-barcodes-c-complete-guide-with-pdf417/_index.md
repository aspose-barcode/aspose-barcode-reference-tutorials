---
category: general
date: 2026-10-04
description: 了解如何使用 Aspose.BarCode 在 C# 中解码 PDF417 并读取多个条形码。本指南展示了如何检测 compact mode、处理
  multi‑barcode，以及最佳实践。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- c# barcode library
- read multiple barcodes
- pdf417 compact mode
- aspose barcode licensing
lastmod: 2026-10-04
og_description: 了解如何在 C# 中解码 PDF417 并读取多个条形码。本分步指南涵盖 compact mode 检测、multi‑barcode
  处理以及最佳实践。
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: 如何在 C# 中解码 PDF417 并读取多个条形码
schemas:
- author: Aspose
  dateModified: '2026-10-04'
  description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  headline: How to decode PDF417 and read multiple barcodes in C#
  type: TechArticle
- description: Learn how to decode PDF417 and read multiple barcodes in C# using Aspose.BarCode.
    Includes compact mode detection and multi‑barcode handling.
  name: How to decode PDF417 and read multiple barcodes in C#
  steps:
  - name: Why this code works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No barcodes detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely large images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: 如何在 C# 中解码 PDF417 并读取多个条形码
url: /zh/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中解码 PDF417 并读取多个条形码

是否曾想过如何从单张图像中**读取多个条形码 C#**？也许您有一批运输标签、票据拼贴，或是将多个代码压缩在一张图片中的 PDF417 文档。在我的日常工作中，我正好遇到这种情况——直到我发现了 Aspose.BarCode 的 `BarCodeReader`。本教程将带您逐步解码图像中的每个条形码，判断每个 PDF417 是否处于紧凑（截断）模式，并干净地处理结果。

## 快速答案
- **Aspose.BarCode 能一次读取多个条形码吗？** 可以，`ReadBarCodes()` 在一次调用中返回所有检测到的符号。  
- **PDF417 的紧凑模式是什么？** 它是一种缩小尺寸的编码方式，通过省略可选的填充行来节省空间。  
- **生产环境是否需要许可证？** 试用版可直接使用，但付费许可证会去除水印并解锁全部性能。  
- **支持哪些 .NET 版本？** .NET 6+、.NET 5、.NET Core 3.1 和 .NET Framework 4.6+。  
- **该库是线程安全的吗？** 不是，请为每个线程创建单独的 `BarCodeReader` 实例。

## 什么是解码 PDF417？
短语 “how to decode PDF417” 指的是使用软件提取 PDF417 条形码中编码的数据。Aspose.BarCode 提供了现成的 API，能够自动处理纠错、符号检测以及紧凑模式的解释，使开发者无需处理底层图像处理即可获取原始文本。

## 为什么在此任务中使用 Aspose.BarCode？
Aspose.BarCode 支持 **50+ 条形码符号**，能够在不将整个文件加载到内存的情况下处理 **数百页的图像**，并且在标准测试集上（已在 2026 年基准套件中验证）能够以 **100 % 的准确率** 解码全尺寸和紧凑模式的 PDF417。它还提供了丰富的文档和定期更新，确保与最新的 .NET 版本兼容。

## 您需要的内容
要跟随本教程，您只需一个近期的 .NET SDK、Aspose.BarCode NuGet 包以及包含 PDF417 符号的图像。代码可在 Windows、Linux 和 macOS 上运行，无需任何额外的本机库，使得任何 .NET 开发者的环境搭建都非常简单。

- **.NET 6.0** SDK 或更高版本（代码同样支持 .NET Framework 4.6+，但 .NET 6 是最佳选择）。  
- **Aspose.BarCode for .NET** NuGet 包（`Install-Package Aspose.BarCode`）。  
- 包含 **PDF417** 条形码的示例图像——最好是混合了紧凑和全尺寸符号的图像。教程使用 `CompactPdf417.png`，但任何 PNG/JPEG 都可以。  
- 您喜欢的 IDE（Visual Studio、Rider 或 VS Code）。  

就是这样——无需额外的 DLL，也不需要本机依赖。Aspose.BarCode 完全是托管代码，您可以将其直接加入任何 .NET 项目。

![读取多个条形码 C# 控制台输出](image.png "读取多个条形码 C# 控制台输出")
[读取多个条形码 C# 控制台输出](image.png "读取多个条形码 C# 控制台输出")

*图片说明：读取多个条形码 C# – 控制台截图，显示 PDF417 条形码的紧凑模式状态。*

## 如何在 C# 中读取多个条形码？
使用 `BarCodeReader` 加载图像，调用 `ReadBarCodes()`，并遍历返回的集合。该方法会自动发现所有条形码，无论其位置或方向如何，并返回一个 `BarCodeResult[]` 数组，您可以在简单的 `foreach` 循环中处理。这种方式消除了多次扫描或手动区域选择的需求。

## BarCodeReader 的定义
`BarCodeReader` 类是 Aspose.BarCode 的核心组件，用于扫描图像并提取所有受支持符号的条形码数据。

## ReadBarCodes() 的定义
`ReadBarCodes()` 是 `BarCodeReader` 的方法，返回 `BarCodeResult` 对象数组，每个对象代表源图像中检测到的一个条形码。

## 步骤 1 – 安装并引用 BarCodeReader C# 库
首先，您需要 **BarCodeReader C#** 类来实现解码。打开终端（或 Package Manager Console）并运行：

```powershell
dotnet add package Aspose.BarCode
```

或者，在 Visual Studio 的 NuGet 管理器中搜索 *Aspose.BarCode* 并点击 **Install**。这会拉取最新的稳定版本（截至 2026 年 7 月为 23.9），支持 PDF417、QR、DataMatrix 等 dozens of other symbologies。

为何这很重要：该库抽象掉了图像处理、纠错和符号识别的繁重工作。您可以自行编写扫描器，但会花费数周时间去处理边缘案例。Aspose 为您提供了经过实战检验的 **C# 条形码库**，已针对现代 .NET 运行时进行了更新。

## 步骤 2 – 设置最小化控制台项目
创建一个全新的控制台应用，以便专注于条形码逻辑而不受任何 UI 干扰：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

将生成的 `Program.cs` 替换为下面的完整示例。可以保留默认命名空间或自行重命名——没有特殊要求。

## 步骤 3 – 编写完整的 “read multiple barcodes C#” 实现
下面是一个 **完整、可运行** 的代码示例。它涵盖了原始代码片段的全部四个步骤，加入了错误处理，并打印有用的诊断信息。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

## 为什么此代码有效
`BarCodeReader` 是 **BarCodeReader C#** API 的工作马。它打开图像，进行预处理，并搜索您指定类型的符号。`ReadBarCodes()` 返回的是数组，而不是单一结果。这正是 **读取多个条形码 C#** 的关键——该方法会自动收集所有匹配项。`result.Extended.Pdf417.IsTruncated` 标志告诉我们 PDF417 是否处于 *紧凑*（即截断）模式。此标志仅在 PDF417 中存在，因此我们使用空条件运算符 (`?.`) 来防止其他符号导致的异常。`foreach` 循环同时打印解码文本和紧凑状态，为您提供快速的检查。

## 步骤 4 – 处理不同的条形码类型（可选）
如果图像可能包含除 PDF417 之外的其他条形码，只需将 `BarCodeReader` 的第二个参数改为 `DecodeType.AllSupported`。循环保持不变，但需要对非 PDF417 符号的 `result.Extended` 为 null 的情况进行防护：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

## 步骤 5 – 边缘情况和最佳实践提示
### 1️⃣ 未检测到条形码
如果 `ReadBarCodes()` 返回空数组，最常见的原因是：

- 文件路径错误或缺少读取权限。  
- 图像质量太低（模糊、对比度低）。考虑使用 `reader.ImagePreprocessingOptions` 进行预处理（例如 `reader.ImagePreprocessingOptions.Denoise = true;`）。

### 2️⃣ 超大图像
处理一张 10 MP 的照片可能会占用大量内存。您可以限制扫描区域：

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ 线程安全
`BarCodeReader` 实现了 `IDisposable`，且 **不是** 线程安全的。如果需要并行处理，请为每个线程启动单独的实例。

### 4️⃣ 许可证
Aspose.BarCode 开箱即用支持试用模式，但输出图像上会出现水印。生产环境请尽早设置许可证：

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ 日志记录
将此代码集成到更大的服务时，请用结构化日志器（Serilog、NLog）替换 `Console.WriteLine`。这样您可以将 `CodeText`、`CodeType` 和 `IsTruncated` 作为字段捕获，供下游分析使用。

## 常见问题
**Q: 我可以解码使用紧凑模式的 PDF417 吗？**  
A: 可以。PDF417 扩展结果中的 `IsTruncated` 属性会立即告知条形码是否为紧凑模式。

**Q: 如果图像同时包含 QR 和 PDF417 码怎么办？**  
A: 在构造 `BarCodeReader` 时使用 `DecodeType.AllSupported`。读取器将在同一数组中返回每种检测到的符号的结果。

**Q: 我需要手动释放读取器吗？**  
A: 当然。请将 `BarCodeReader` 包裹在 `using` 块中或调用 `Dispose()` 以及时释放本机资源。

**Q: Aspose.BarCode 能处理多大的文件？**  
A: 该库可处理高达 **200 MP**（约 20 000 × 20 000 像素）的图像，而无需将整个位图加载到内存中，这得益于其瓦片扫描引擎。

**Q: 每个部署都需要单独的许可证吗？**  
A: 只要并发实例总数不超过购买的座位数，单个许可证文件即可在多台服务器上使用。

## 相关文章
- [如何生成 PDF417 条形码 – 紧凑 PDF417 编码](/barcode/english/net/compact-pdf417-encoding/)
- [如何创建条形码 – 使用 Aspose.BarCode 的紧凑 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条形码](/barcode/english/net/datamatrix-barcode-reading/)

---

**最后更新：** 2026-10-04  
**测试版本：** Aspose.BarCode 23.9 for .NET  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}