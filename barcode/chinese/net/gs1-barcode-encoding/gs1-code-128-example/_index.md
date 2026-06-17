---
date: 2026-02-02
description: 学习如何自定义条形码生成、生成 GS1 条形码以及使用 Aspose.BarCode for .NET 在 C# 中创建条形码图像。一步一步的教程。
linktitle: GS1 Code 128 Example
second_title: Aspose.BarCode .NET API
title: 如何定制条形码——基于 GS1 Code 128 示例的逐步指南
url: /zh/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何自定义条形码 – GS1 Code 128 示例

## 介绍

如果您正在寻找 **如何自定义条形码** 的创建方法，您来对地方了。在本指南中，我们将 walkthrough Aspose.BarCode for .NET 的要点，向您展示如何 **生成 GS1 条形码**，并演示如何仅用几行 C# 代码 **创建条形码图像** 文件。完成后，您将能够自定义条形码参数，保存结果，并将其集成到实际项目中。

## 快速答案
- **哪个库最适合条形码自定义？** Aspose.BarCode for .NET  
- **本示例覆盖哪种条形码类型？** GS1 Code 128  
- **运行示例是否需要许可证？** 开发阶段可使用免费试用版；生产环境需要许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **实现大约需要多长时间？** 基础设置约 5‑10 分钟。

## 什么是 .NET 世界中的“如何自定义条形码”？
自定义条形码意味着根据业务需求调整其符号集、尺寸、空白区、颜色以及额外的数据字段。Aspose.BarCode 提供流畅的 API，允许您在 C# 代码中调节从 X‑dimension 到可读文本的每一个细节，而无需离开开发环境。

## 为什么使用 Aspose.BarCode for .NET？
- **完全控制** 条形码标准（包括 GS1）。  
- **无外部依赖** —— 纯 .NET 库。  
- **丰富的文档** 与示例代码，帮助快速入门。  
- **高性能渲染** 支持 PNG、JPEG、SVG 等多种格式。

## 前提条件
在深入 Aspose.BarCode for .NET 的精彩世界之前，请确保已满足以下前提条件。您需要准备：

1. .NET 开发环境：需要一个可用的 .NET 开发环境，包括 Visual Studio 或其他首选 IDE。  
2. Aspose.BarCode for .NET：可从 [此链接](https://releases.aspose.com/barcode/net/) 下载。请确保正确安装并配置库。  
3. C# 基础：了解 C# 编程语言的基本概念，有助于跟随示例并编写代码。  
4. 对 GS1 Code 128 有一定了解：虽然不是强制要求，但了解 GS1 Code 128 条形码的基本概念会帮助您更好地理解示例。

现在，让我们将 GS1 Code 128 示例拆解为多个步骤，提供逐步指南：

## 如何自定义条形码 – 导入命名空间
要开始使用 Aspose.BarCode for .NET，您需要导入必要的命名空间。这些命名空间提供对库功能的访问。下面演示如何操作：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 步骤 1：设置目录路径
在生成 GS1 Code 128 条形码之前，需要指定保存条形码图像的目录路径。可以这样设置：

```csharp
string path = "Your Directory Path";
```

将 `"Your Directory Path"` 替换为实际的保存路径。

## 步骤 2：创建 GS1 Code 128 条形码
接下来，使用 Aspose.BarCode for .NET 创建 GS1 Code 128 条形码。本示例将生成数据为 **"(01)12345678901231(21)ASPOSE(30)9876"** 的条形码。代码如下：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

此代码使用指定的类型和数据初始化条形码生成器。

## 步骤 3：自定义条形码参数
Aspose.BarCode for .NET 允许您自定义条形码的各种参数，例如 **XDimension**（条形码中窄元素的宽度）。本例中，我们将 XDimension 设置为 2 像素：

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

您可以根据需求调整这些参数。

## 步骤 4：保存条形码图像
最后，将生成的条形码保存为图像文件。本例将其保存为 PNG 格式：

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

请将 `GS1Code128Example.png` 替换为您希望的文件名。

## 常见问题及解决方案
- **数据格式不正确** —— GS1 条形码需要用括号括起的应用标识符（AI）。请确保数据字符串遵循 `(AI)Data` 形式。  
- **文件路径错误** —— 使用 `Path.Combine` 以实现跨平台兼容，例如 `Path.Combine(path, "GS1Code128Example.png")`。  
- **许可证未生效** —— 若出现水印，请在创建生成器前添加许可证文件：`License lic = new License(); lic.SetLicense("Aspose.BarCode.lic");`。

## 常见问答

**Q: 我可以用相同的代码生成其他条形码类型吗？**  
A: 可以，只需将 `EncodeTypes.GS1Code128` 更改为其他受支持的符号，例如 `EncodeTypes.Code128` 或 `EncodeTypes.QR`。

**Q: 如何在条形码下方添加可读文本？**  
A: 设置 `gen.Parameters.Barcode.ShowCodeText = true;` 并通过 `gen.Parameters.Barcode.CodeTextParameters` 自定义字体。

**Q: 能否以 SVG 格式生成条形码？**  
A: 完全可以。在 `Save` 方法中使用 `BarCodeImageFormat.Svg`。

**Q: Aspose.BarCode 是否支持 .NET Core？**  
A: 支持，库完全兼容 .NET Core、.NET 5、.NET 6 以及更高版本。

**Q: 哪里可以找到更高级的示例？**  
A: 官方文档和示例仓库提供了针对每种条形码标准的丰富示例。

## 原始常见问题

### 在哪里可以找到 Aspose.BarCode for .NET 的文档？
您可以访问文档页面 [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/)。

### 如何下载 Aspose.BarCode for .NET？
请从 [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) 下载库。

### 是否提供免费试用版？
是的，您可以在 [https://releases.aspose.com/](https://releases.aspose.com/) 获取免费试用。

### 在哪里购买 Aspose.BarCode for .NET 的许可证？
请前往 [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy) 进行购买。

### 需要帮助或有疑问？在哪里可以获得支持？
有关支持和社区讨论，请访问 [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2026-02-02  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose