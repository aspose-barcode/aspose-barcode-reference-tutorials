---
title: 使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码
linktitle: 数据矩阵版本
second_title: Aspose.BarCode .NET API
description: 了解如何使用 Aspose.BarCode for .NET 在 .NET 中生成 DataMatrix 条形码。自定义尺寸、ECC 支持等等。
type: docs
weight: 12
url: /zh/net/datamatrix-barcode-reading/datamatrix-versions/
---
如果您正在寻找可靠的解决方案来在 .NET 应用程序中生成 DataMatrix 条形码，Aspose.BarCode for .NET 就是您的最佳选择。在本分步指南中，我们将引导您完成使用 Aspose.BarCode for .NET 创建 DataMatrix 条形码的过程。我们将把每个示例分解为多个步骤，确保您可以轻松地遵循。

## 先决条件

在我们深入研究代码之前，请确保您具备以下先决条件：
- 具有 .NET 支持的开发环境。
-  Aspose.BarCode for .NET 的副本，您可以从以下位置下载[这个链接](https://releases.aspose.com/barcode/net/).
- C# 和 .NET 框架的基础知识。

现在，让我们探索 DataMatrix 版本以及如何使用 Aspose.BarCode for .NET 生成它们。

## 导入命名空间

在任何 C# 项目中，导入必要的命名空间至关重要。对于 Aspose.BarCode，您需要包含以下内容：

```csharp
using Aspose.BarCode.Generation;
```

该命名空间提供对`BarcodeGenerator`类，这对于生成条形码至关重要。

现在，让我们将该示例分解为多个步骤。

## 第 1 步：设置目录路径

首先定义要保存生成的 DataMatrix 条形码的目录路径。

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`与您要保存条形码图像的实际路径。

## 第 2 步：初始化条形码生成器

创建一个实例`BarcodeGenerator`类并将条形码类型指定为`DataMatrix`。您还可以提供要在条形码中编码的数据。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    //生成条形码的代码位于此处
}
```

## 步骤 3：配置条形码属性

您可以自定义 DataMatrix 条形码的各种属性，例如尺寸和 ECC（纠错码）类型。以下是将 X 尺寸设置为 4 像素并选择 ECC200 的示例：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## 第4步：设置DataMatrix版本并保存

您可以通过设置行数和列数来指定 DataMatrix 版本。配置版本后，保存条形码图像。

例如，要使用 ECC200 创建 22 行 22 列的 DataMatrix 条形码：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

同样，您可以根据需要更改版本和ECC类型来生成具有不同参数的条码。

## 步骤 5：对其他版本重复此操作

对于其他 DataMatrix 版本，您可以重复步骤 4。例如，要使用 ECC200 创建 12 行 64 列的条形码：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## 步骤 6：切换 ECC 类型

如果要将 ECC 类型更改为 Ecc140，可以通过更新 ECC 属性来实现：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## 步骤 7：生成不同版本和 ECC 的条形码

对其他 DataMatrix 版本和 ECC 类型重复步骤 4，用唯一的文件名保存每个条形码。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

现在您已经了解了如何使用 Aspose.BarCode for .NET 生成 DataMatrix 条形码，您可以轻松地将此功能集成到您的 .NET 应用程序中。

## 结论

Aspose.BarCode for .NET 简化了在 .NET 应用程序中生成 DataMatrix 条形码的过程。通过此分步指南，您可以创建具有不同版本和 ECC 类型的条形码，从而提供灵活性和自定义来满足您的特定需求。

如果您有任何疑问或需要帮助，请随时访问[Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/)或查看[Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)为了支持。

## 常见问题解答

### Q1：DataMatrix 条码中的 ECC 是什么？

A1：ECC（纠错码）是 DataMatrix 条码的重要组成部分，有助于确保数据完整性。不同的 ECC 级别提供不同程度的纠错。

### 问题 2：我可以使用 Aspose.BarCode for .NET 生成具有自定义尺寸的 DataMatrix 条形码吗？

A2：是的，您可以通过设置行数和列数来自定义 DataMatrix 条形码的尺寸，如教程中所示。

### Q3：哪里可以下载 Aspose.BarCode for .NET？

 A3：您可以从以下位置下载 Aspose.BarCode for .NET[这个链接](https://releases.aspose.com/barcode/net/).

### Q4：Aspose.BarCode for .NET 有免费试用版吗？

 A4：是的，您可以免费试用 Aspose.BarCode for .NET[这里](https://releases.aspose.com/).

### Q5：如何获得 Aspose.BarCode for .NET 的临时许可证？

 A5：要获取 Aspose.BarCode for .NET 的临时许可证，请访问[这个链接](https://purchase.aspose.com/temporary-license/).