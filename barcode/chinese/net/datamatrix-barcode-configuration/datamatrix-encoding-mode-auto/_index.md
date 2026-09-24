---
date: 2026-08-02
description: 逐步指南，介绍如何使用 Aspose.BarCode for .NET 的自动编码读取 DataMatrix 条码（C#）并生成条码图像（C#）。
keywords:
- how to read datamatrix
- read barcode from file
- how to generate datamatrix
- datamatrix encoding auto
lastmod: 2026-08-02
linktitle: DataMatrix 编码模式（Auto）
og_description: 了解如何使用 Aspose.BarCode for .NET 在 Auto 模式下读取 DataMatrix 条码（C#）并生成条码。本教程涵盖环境设置、代码示例及故障排除。
og_image_alt: 'Guide: Read and generate DataMatrix barcode in C# with Aspose.BarCode'
og_title: 如何读取 DataMatrix 条码（C#）– 自动模式
schemas:
- author: Aspose
  dateModified: '2026-08-02'
  description: Step‑by‑step guide on how to read DataMatrix barcode C# and generate
    barcode image C# using Aspose.BarCode for .NET with auto encoding.
  headline: How to read DataMatrix barcode C# – Auto mode
  type: TechArticle
- questions:
  - answer: It allows Aspose.BarCode to automatically select the optimal encoding
      method for the provided data, simplifying the **how to generate datamatrix**
      process.
    question: What is DataMatrix encoding mode "Auto"?
  - answer: Yes – adjust `generator.Parameters.Barcode.XDimension.Pixels` to change
      module size.
    question: Can I customize the dimensions of the generated barcode?
  - answer: Absolutely. Purchase a license from the [website](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can explore Aspose.BarCode with a free trial from [this link](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Aspose.BarCode supports UTF‑8, ASCII, and other ECI encodings; set the
      desired value via `ECIEncoding`.
    question: What encoding options are available for DataMatrix barcodes?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- Aspose.BarCode
- C# barcode generation
title: 如何读取 DataMatrix 条码（C#）– 自动模式
url: /zh/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何读取 DataMatrix 条形码 C# – 自动模式

在当今快速发展的数字世界中，**如何快速可靠地读取 DataMatrix** 对于库存跟踪、文档安全处理以及许多其他企业场景至关重要。本教程将指导您使用 Aspose.BarCode for .NET 在 *Auto* 模式下生成 DataMatrix 条形码，然后展示如何在 C# 中读取该条形码。无论您是遵循条形码教程指南还是需要一个即用的代码示例，您都将获得一个可直接放入任何 .NET 项目的生产就绪解决方案。

## 快速答案
- **“Auto” 模式的作用是什么？** 它让 Aspose.BarCode 自动为您的数据选择最佳的编码方案。  
- **需要哪个库？** Aspose.BarCode for .NET（提供免费试用）。  
- **我可以在同一个应用中读取条形码吗？** 可以 – 使用 `BarCodeReader` 与 `DecodeType.DataMatrix`。  
- **生产环境是否需要许可证？** 生产使用需要商业许可证。  
- **支持的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  

`BarCodeReader` 是 Aspose.BarCode 用于扫描图像并检索条形码信息的类。

## 什么是读取 DataMatrix 条形码 C#？

在 C# 中读取 DataMatrix 条形码是指将黑白模块的二维矩阵解码回原始文本或数据。Aspose.BarCode 抽象了底层图像处理，使您能够专注于业务逻辑，而库会自动处理错误纠正、符号尺寸选择和 Unicode 支持。

## 为什么使用 Aspose.BarCode 在 C# 中生成条形码图像？

Aspose.BarCode 自动选择最佳编码，支持 **30+ 条形码符号**，并且能够生成最高达 **1558 × 1558 模块** 的 DataMatrix 符号——远大于大多数竞争对手。它可在 Windows、Linux 和 macOS 上运行，无需本地依赖，为您提供一个用于生成和读取的统一跨平台 API。

## 前置条件

1. **.NET 环境** – 从 [.NET 网站](https://dotnet.microsoft.com/download/dotnet) 安装最新的 .NET 运行时。  
2. **Aspose.BarCode for .NET** – 从 [网站](https://releases.aspose.com/barcode/net/) 下载库。  

## 导入命名空间

`Aspose.BarCode` 命名空间包含创建和读取条形码所需的所有类。请在文件顶部、其他代码之前导入它。

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

现在命名空间已就位，让我们一步步浏览代码。

## 步骤 1：设置目录路径

选择一个文件夹用于保存生成的 PNG（或任何受支持的格式）。该路径可以是绝对路径，也可以是相对于项目的相对路径。

```csharp
string path = "Your Directory Path";
```

将 `"Your Directory Path"` 替换为您偏好的文件夹。保持输出文件夹可配置，使教程能够在不同环境中复用。

## 步骤 2：在 Auto 模式下创建 DataMatrix 条形码

`DataMatrixEncodeMode.Auto` 告诉生成器自动为提供的数据选择最佳编码方案。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose常に先を行く"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Auto;
    generator.Parameters.Barcode.DataMatrix.ECIEncoding = ECIEncodings.UTF8;
    Bitmap bitmap = generator.GenerateBarCodeImage();
}
```

您可以随意将示例文本替换为需要 **如何生成 DataMatrix** 的任意字符串。自动模式会在 Base‑256、ASCII 或其他方案之间自动切换，以实现尽可能小的符号。

## 步骤 3：读取条形码（读取 DataMatrix 条形码 C#）

`BarCodeReader` 是 Aspose.BarCode 用于扫描图像并检索条形码信息的类。它支持从流、文件和位图对象读取，非常适合 **从文件读取条形码** 场景。

```csharp
using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
{
    reader.ReadBarCodes();
    Console.WriteLine(reader.FoundBarCodes[0].CodeText);
}
```

此代码片段解码我们刚生成的图像并将原始文本打印到控制台，演示了从生成到读取的完整往返过程。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| **未检测到条形码** | 图像分辨率太低 | 增加 `XDimension.Pixels`（例如，设为 6） |
| **乱码字符** | ECI 编码错误 | 将 `ECIEncoding` 设置为匹配您的数据（UTF‑8、ASCII 等） |
| **在 `ReadBarCodes` 上出现异常** | 在读取前 Bitmap 已被释放 | 在读取完成前保持 `Bitmap` 实例存活 |

## 常见问答

**Q: DataMatrix 编码模式 “Auto” 是什么？**  
A: 它允许 Aspose.BarCode 自动为提供的数据选择最佳编码方法，简化了 **如何生成 DataMatrix** 的过程。

**Q: 我可以自定义生成的条形码尺寸吗？**  
A: 可以 – 调整 `generator.Parameters.Barcode.XDimension.Pixels` 以更改模块大小。

**Q: Aspose.BarCode for .NET 适合商业使用吗？**  
A: 绝对适合。请从 [网站](https://purchase.aspose.com/buy) 购买许可证。

**Q: 是否提供免费试用？**  
A: 有，您可以通过 [此链接](https://releases.aspose.com/) 免费试用 Aspose.BarCode。

**Q: DataMatrix 条形码有哪些编码选项？**  
A: Aspose.BarCode 支持 UTF‑8、ASCII 以及其他 ECI 编码；可通过 `ECIEncoding` 设置所需的值。

## 结论

您现在拥有一个完整的、可投入生产的示例，能够 **读取 DataMatrix 条形码 C#**，在 Auto 模式下生成条形码并验证结果——全部使用 Aspose.BarCode for .NET。尝试不同的文本、尺寸和 ECI 设置以适配您的特定场景，并参考官方 [文档](https://reference.aspose.com/barcode/net/) 进行更深入的定制。

---

**最后更新:** 2026-08-02  
**测试使用:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose

## 相关教程

- [如何使用 Aspose.BarCode for .NET 读取 DataMatrix 条形码](/barcode/net/datamatrix-barcode-reading/)
- [使用 Aspose.BarCode for .NET 的 DataMatrix 结构化追加配置](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)
- [使用 Aspose.BarCode for .NET 的 DataMatrix 读取器编程](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}