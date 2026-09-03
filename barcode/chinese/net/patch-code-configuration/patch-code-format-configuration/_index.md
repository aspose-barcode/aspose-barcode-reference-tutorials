---
date: 2026-03-02
description: 使用 Aspose.BarCode .NET 生成 Patch Code 条码。了解如何快速生成 Patch Code 条码并提升文档管理。立即下载库！
linktitle: Patch Code Format Configuration
second_title: Aspose.BarCode .NET API
title: Aspose 条形码 .NET – 在 .NET 中创建 Patch Code 条码
url: /zh/net/patch-code-configuration/patch-code-format-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 创建 Patch Code 条形码

在本教程中，您将学习 **如何使用 aspose barcode .net 生成 Patch Code 条形码**。Patch Code 是一种二维符号，可帮助在大型档案中组织和检索文档。阅读完本指南后，您只需几行代码即可在任何 .NET 应用程序中添加 Patch Code 条形码。

## 快速答复
- **需要哪个库？** Aspose.BarCode for .NET  
- **我可以在没有 QR 的情况下生成 Patch Code 吗？** 是的 – 设置 PatchFormat 并跳过 QR 设置。  
- **推荐使用哪种图像格式？** PNG 在无损渲染方面表现最佳。  
- **开发时需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **是否支持 .NET Core？** 当然 – 该库面向 .NET 5/6 和 .NET Core 3.1+。  

## 介绍

Patch Code 条形码是文档管理系统的重要组成部分，帮助文档的识别和组织。Aspose.BarCode for .NET 是一个强大的库，使开发人员能够轻松生成包括 Patch Code 在内的各种条形码。

在本教程中，我们将学习如何使用 Aspose.BarCode for .NET 创建 Patch Code 条形码。我们将介绍必要的前置条件、导入所需的命名空间，并将提供的示例分解为详细步骤。阅读完本指南后，您将能够在 .NET 应用程序中轻松生成 Patch Code 条形码。

## 什么是 aspose barcode .net？

Aspose.BarCode for .NET 是一个兼容 .NET 的 API，允许您 **生成和读取** 多种条形码符号，从经典的 1‑D 码到高级的 2‑D 符号，如 Patch Code 和 QR。它抽象了底层编码细节，让您专注于业务逻辑。

## 为什么生成 Patch Code 条形码？

- **快速文档检索** – 扫描 Patch Code 即可立即定位实体文件。  
- **紧凑的数据存储** – 将元数据（例如文档类型、创建日期）直接存储在符号中。  
- **内置 QR 补充** – 可选地添加 QR 码，以携带 URL 或更大的文本块。  

## 前置条件

在我们深入生成 Patch Code 条形码之前，您需要确保已具备以下前置条件：

- Visual Studio 或任何已在系统上安装的 .NET 开发环境。  
- Aspose.BarCode for .NET 库。您可以从 [here](https://releases.aspose.com/barcode/net/) 下载。  
- 基本的 C# 和 .NET 编程知识。

## 导入命名空间

首先，确保导入使用 Aspose.BarCode for .NET 所需的必要命名空间。以下是操作方法：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

现在我们已经准备好前置条件和命名空间，让我们将提供的示例拆分为多个步骤。

## 如何使用 aspose barcode .net 生成 Patch Code 条形码

### 步骤 1：设置路径

首先，定义要保存生成的 Patch Code 条形码图像的路径。您可以这样设置目录路径：

```csharp
string path = "Your Directory Path";
```

确保将 `"Your Directory Path"` 替换为您实际用于输出图像的文件夹路径。

### 步骤 2：初始化条形码生成器

创建 `BarcodeGenerator` 类的实例以开始生成 Patch Code 条形码。指定条形码类型，本例为 `EncodeTypes.PatchCode`，以及唯一的代码文本，例如 `"Patch I"`。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.PatchCode, "Patch I");
```

### 步骤 3：生成不带补充 QR 的 Patch Code

您可以生成不带补充 QR 码的 Patch Code 条形码。将 Patch Format 设置为 `PatchFormat.A4` 并保存生成的条形码图像。

```csharp
gen.Parameters.Barcode.PatchCode.PatchFormat = PatchFormat.A4;
gen.Save($"{path}PatchCodeA4WithoutQR.png", BarCodeImageFormat.Png);
```

### 步骤 4：生成带补充 QR 的 Patch Code

要生成带补充 QR 码的 Patch Code 条形码，先将 Patch Format 设置为 `PatchFormat.A4`。此外，您可以使用 `ExtraBarcodeText` 属性向条形码添加额外信息。将代码文本的位置设置为 `CodeLocation.None` 以禁用它。

```csharp
gen.Parameters.Barcode.PatchCode.PatchFormat = PatchFormat.A4;
gen.Parameters.Barcode.PatchCode.ExtraBarcodeText = "Aspose page extra info";
gen.Parameters.Barcode.CodeTextParameters.Location = CodeLocation.None;
gen.Save($"{path}PatchCodeA4WithQR.png", BarCodeImageFormat.Png);
```

通过这四个简单步骤，您即可使用 Aspose.BarCode for .NET 创建 Patch Code 条形码。该库简化了流程，使 .NET 开发人员能够高效且友好地使用。

## 常见问题及解决方案
- **Invalid path error** – 确保文件夹存在且应用程序具有写入权限。  
- **License exception** – 试用版可用于评估；在生产环境中使用有效许可证以去除水印。  
- **Unsupported image format** – API 支持 PNG、JPEG、BMP、GIF 和 TIFF。调用 `Save` 时使用其中一种格式。  

## 常见问答

### 什么是 Aspose.BarCode for .NET？

Aspose.BarCode for .NET 是一个强大的库，允许 .NET 开发人员生成和读取各种类型的条形码，包括 Patch Code、QR 码等。

### 我可以从哪里下载 Aspose.BarCode for .NET？

您可以从 [Aspose website](https://releases.aspose.com/barcode/net/) 下载 Aspose.BarCode for .NET。

### Aspose.BarCode for .NET 适用于文档管理系统吗？

是的，Aspose.BarCode for .NET 非常适合文档管理系统，因为它可以生成用于文档识别和组织的 Patch Code 条形码。

### 我可以在购买前试用 Aspose.BarCode for .NET 吗？

是的，您可以从 [here](https://releases.aspose.com/) 获取 Aspose.BarCode for .NET 的免费试用版。

### 我可以在哪里获得 Aspose.BarCode for .NET 的支持？

如果您有任何问题或需要帮助，可前往 Aspose.BarCode for .NET 支持论坛 [here](https://forum.aspose.com/c/barcode/13)。

**附加问答**

**Q:** *我可以自定义生成的 Patch Code 大小吗？*  
**A:** 可以。在调用 `Save` 之前调整 `gen.Parameters.Image.Width` 和 `Height`。

**Q:** *是否可以将条形码直接嵌入 PDF？*  
**A:** 当然。使用 Aspose.PDF 将生成的 PNG（或流）添加到 PDF 页面。

## 结论

在本教程中，我们探讨了如何使用 **aspose barcode .net** 生成 Patch Code 条形码。我们介绍了前置条件，导入了所需的命名空间，并通过清晰的逐步示例演示了如何创建无 QR 和带 QR 的 Patch Code。掌握这些知识后，您即可在任何文档管理或归档解决方案中集成可靠的可扫描标识符。

---

**最后更新：** 2026-03-02  
**测试环境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}