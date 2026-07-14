---
date: 2026-02-25
description: 了解如何使用 Aspose.BarCode for .NET 生成条形码图像。本分步指南展示了如何生成带校验码和不带校验码的 Code 39
  条形码。
linktitle: One-Dimensional Code 39 Configuration
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode 生成条形码 – Code 39 配置
url: /zh/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/
weight: 11
---

.

Now write final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一维 Code 39 配置

## 简介

在本教程中，您将学习 **如何生成条形码** 图像，特别是一维 Code 39 条形码，使用 Aspose.BarCode for .NET。条形码在现代企业中发挥着关键作用，从库存跟踪到实现快速、准确的数据检索。Aspose.BarCode for .NET 是一个强大的库，可简化在 .NET 应用程序中生成和自定义条形码的过程。本分步指南将过程拆分为易于消化的部分，确保即使是条形码生成新手的开发者也能轻松跟随。

## 快速回答
- **主要的库是什么？** Aspose.BarCode for .NET  
- **我可以创建带校验和的条形码吗？** Yes – set `IsChecksumEnabled = EnableChecksum.Yes`  
- **校验和是必需的吗？** No – you can generate a barcode without checksum by disabling it  
- **示例中使用的图像格式是什么？** PNG (`BarCodeImageFormat.Png`)  
- **开发时需要许可证吗？** A temporary license is available for evaluation  

## 什么是使用 Aspose.BarCode 生成条形码？

条形码生成是将文本或数字数据转换为机器可读的视觉模式的过程。Aspose.BarCode for .NET 支持数十种符号系统，包括 Code 39，并且让您能够从尺寸、颜色到校验和计算等各方面进行控制。

## 为什么使用 Code 39 以及校验和选项？

Code 39 在物流和制造业中被广泛采用，因为它能够在不使用特殊字符的情况下编码字母数字数据。添加校验和（或不添加）可以在错误检测与简洁性之间取得平衡——非常适合库存标签、运输标签或简单的销售点系统。

## 先决条件

在开始之前，请确保您具备以下条件：

1. **.NET 开发环境** – 对 .NET 框架有一定了解，并使用如 Visual Studio 的 IDE。如果您是 .NET 新手，请从官方文档开始：[Microsoft .NET Documentation](https://docs.microsoft.com/en-us/dotnet/)。  
2. **Aspose.BarCode for .NET** – 下载并安装该库。文档和下载链接如下：[Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 和 [Download Aspose.BarCode for .NET](https://releases.aspose.com/barcode/net/)。

既然我们已经介绍了先决条件，接下来让我们进入创建一维 Code 39 条形码的主要步骤。

## 如何生成条形码：导入命名空间

要开始使用 Aspose.BarCode for .NET，请在项目中导入必要的命名空间。添加这些 `using` 语句即可访问条形码生成类。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 如何生成 Code 39 条形码（带校验和和不带校验和）

下面我们将创建两个条形码：一个 **不带校验和**，一个 **带校验和**。代码唯一的区别在于 `IsChecksumEnabled` 标志。

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneCSCode39:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "CODE");

// Example 1: Create a Code 39 barcode without checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
gen.Save($"{path}OneCSCode39WithoutChecksum.png", BarCodeImageFormat.Png);

// Example 2: Create a Code 39 barcode with checksum
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Save($"{path}OneCSCode39WithChecksum.png", BarCodeImageFormat.Png);
```

**代码功能说明**

1. **实例化** `BarcodeGenerator`，使用 `EncodeTypes.Code39Extended` 和数据字符串 `"CODE"`。  
2. **切换** `IsChecksumEnabled` 以控制是否附加校验和数字。  
3. **保存** 每个条形码为 PNG 文件到指定文件夹。

现在您已经拥有两个可直接使用的条形码图像：`OneCSCode39WithoutChecksum.png` 和 `OneCSCode39WithChecksum.png`。

## 常见问题及解决方案
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **未找到文件路径** | `path` 变量指向一个不存在的文件夹。 | 确保目录存在，或使用 `Directory.CreateDirectory(path)`。 |
| **数据中包含无效字符** | Code 39 仅支持字母数字以及少量特殊符号。 | 使用扩展的 Code 39（`Code39Extended`），它支持完整的 ASCII 集，如上所示。 |
| **校验和错误** | 在需要时忘记设置 `IsChecksumEnabled`。 | 根据实际情况显式将标志设置为 `EnableChecksum.Yes` 或 `No`。 |

## 常见问题 (FAQs)：

### Q: 我可以在其他编程语言中使用 Aspose.BarCode for .NET 吗？
A: Aspose.BarCode 主要面向 .NET 设计，但 Aspose 也提供其他平台的条形码库。

### Q: Aspose.BarCode for .NET 有哪些授权选项可用？
A: 有，您可以在 Aspose 网站上查看授权选项并申请临时授权：[Aspose.BarCode Licensing](https://purchase.aspose.com/temporary-license/)。

### Q: Aspose.BarCode for .NET 适用于 Web 应用程序吗？
A: 是的，Aspose.BarCode for .NET 可用于 Web 应用程序，适用于各种开发项目。

### Q: 我可以自定义生成的条形码外观吗？
A: 当然，您可以自定义条形码的各个方面，包括尺寸、颜色和字体。

### Q: 我在哪里可以获得 Aspose.BarCode for .NET 的支持或提问？
A: 您可以在 Aspose.BarCode 论坛上找到答案并寻求支持：[Aspose.BarCode Forum](https://forum.aspose.com/c/barcode/13)。

## 其他常见问题

**Q: 带校验和的条形码与不带校验和的条形码有什么区别？**  
A: 校验和会添加一个额外的数字，以帮助检测抄写错误。当数据完整性至关重要时使用。

**Q: 生成的 PNG 大小可以有多大？**  
A: 大小通过 `gen.Parameters.ImageWidth/Height` 控制。调用 `Save` 之前请调整这些属性。

**Q: 我可以生成其他图像格式的条形码吗？**  
A: 可以，Aspose.BarCode 支持 JPEG、BMP、GIF、TIFF 等格式，只需更改 `BarCodeImageFormat` 枚举即可。

**Q: 是否有办法在 Web 应用中生成条形码而不写入磁盘？**  
A: 您可以保存到 `MemoryStream`，并直接将字节数组返回给客户端。

## 结论
通过遵循这些简单步骤，您可以在 .NET 中 **生成条形码** 图像，并全面控制校验和处理、图像格式和视觉样式。无论是管理库存、处理订单，还是构建支持条形码的 Web 门户，Aspose.BarCode for .NET 都提供了可靠且对开发者友好的解决方案。

---

**最后更新：** 2026-02-25  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}