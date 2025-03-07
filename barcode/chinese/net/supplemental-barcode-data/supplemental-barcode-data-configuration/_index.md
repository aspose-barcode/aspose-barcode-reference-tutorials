---
title: 使用 Aspose.BarCode for .NET 创建补充条形码数据
linktitle: 补充条形码数据配置
second_title: Aspose.BarCode .NET API
description: 使用 Aspose.BarCode for .NET 生成补充条形码数据。轻松定制 EAN-2 和 EAN-5 条形码。 .NET 开发人员的分步指南。
weight: 10
url: /zh/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 创建补充条形码数据


在条形码生成和定制领域，Aspose.BarCode for .NET 是一款功能强大且多功能的工具。无论您是经验丰富的开发人员还是刚刚起步，本分步指南都将引导您完成使用 Aspose.BarCode for .NET 配置补充条形码数据的过程。 

## 先决条件

在我们深入了解补充条形码数据的世界之前，请确保您具备以下先决条件：

- 使用 Visual Studio 或任何其他 .NET 开发工具设置的开发环境。
-  .NET 的 Aspose.BarCode 副本。如果您还没有，您可以下载[这里](https://releases.aspose.com/barcode/net/).
- C# 编程基础知识。
- 可以保存生成的条形码图像的目录。

## 导入命名空间

首先，确保您的 C# 代码中包含必要的命名空间，以便与 Aspose.BarCode for .NET 一起使用。在 C# 文件的开头导入所需的命名空间：

```csharp
using Aspose.BarCode.Generation;
```

现在，让我们将配置补充条形码数据的过程分解为多个步骤。

## 第1步：设置目录路径

在 C# 代码中，定义要保存生成的条形码图像的目录路径。代替`"Your Directory Path"`与您的实际目录路径。

```csharp
string path = "Your Directory Path";
```

## 第 2 步：创建条形码生成器

创建一个实例`BarcodeGenerator`通过指定条形码类型和要编码的数据。在此示例中，我们使用数据为“1234567890128”的 EAN-13 条形码。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## 第 3 步：自定义条形码尺寸

设置条形码的尺寸，例如X尺寸（条形码中最小元素的宽度）和补充空间。在此示例中，我们将 X 尺寸设置为 2 像素，将补充空间设置为 20 像素。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## 步骤 4：配置 EAN-2 补充

要配置 EAN-2 补充条形码，请将补充数据设置为所需的值。在本例中，我们将其设置为“12”。 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## 第 5 步：保存条形码图像

使用有意义的名称将生成的条形码图像保存到指定目录。在此示例中，我们将 EAN-2 补充条形码保存为“SupplementEAN2.png”。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## 步骤 6：配置 EAN-5 补充

要配置 EAN-5 补充条形码，只需更改`SupplementData`到您想要的值。在这里，我们将其设置为“12345”。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## 步骤 7：保存条形码图像 (EAN-5)

最后，将 EAN-5 补充条形码图像保存在您指定的目录中。在本例中，我们将其保存为“SupplementEAN5.png”。

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

现在，您已经使用 Aspose.BarCode for .NET 成功配置并生成了补充条形码数据。您可以使用此方法创建具有不同补充数据的各种条形码类型。

## 结论

Aspose.BarCode for .NET 是一个强大的条形码生成和定制工具。在本指南中，我们逐步完成了配置和生成补充条形码数据的过程。通过正确的先决条件和一些编码，您可以有效地处理条形码数据并满足您的特定需求。

有关更多信息和高级用法，请参阅[Aspose.BarCode for .NET 文档](https://reference.aspose.com/barcode/net/).

## 经常问的问题

### 我可以在 .NET Core 项目中使用 Aspose.BarCode for .NET 吗？
是的，Aspose.BarCode for .NET 与 .NET Core 兼容。

### Aspose.BarCode for .NET 是否有免费试用版？
是的，您可以访问免费试用[这个链接](https://releases.aspose.com/).

### 在哪里可以获得 Aspose.BarCode for .NET 的临时许可证？
您可以从以下地址获取临时许可证[这个链接](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode 是否支持多种条形码类型？
是的，它支持各种条形码类型，包括 EAN-13、QR 码、Code 128 等。

### 我可以自定义生成的条形码的外观吗？
当然，您可以自定义条形码的尺寸、颜色和其他方面来满足您的要求。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
