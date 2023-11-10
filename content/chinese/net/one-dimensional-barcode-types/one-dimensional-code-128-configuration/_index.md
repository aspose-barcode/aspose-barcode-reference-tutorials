---
title: 一维码128配置
linktitle: 一维码128配置
second_title: Aspose.BarCode .NET API
description: 了解如何使用 Aspose.BarCode 在 .NET 中生成一维 Code 128 条形码。请遵循我们的无缝条形码集成分步指南。
type: docs
weight: 10
url: /zh/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

如果您是一名 .NET 开发人员，正在寻找一个强大的工具来在应用程序中生成条形码，那么 Aspose.BarCode for .NET 是您的首选解决方案。本综合指南将引导您完成利用 Aspose.BarCode for .NET 的功能创建一维 Code 128 条形码的过程，它是为初学者和经验丰富的开发人员设计的。 

## 先决条件

在我们深入了解使用 Aspose.BarCode 生成条形码的激动人心的世界之前，请确保您具备以下先决条件：

1. Visual Studio：确保您的系统上安装了 Visual Studio。

2.  Aspose.BarCode for .NET：您需要下载并安装Aspose.BarCode for .NET。你可以从[这里](https://releases.aspose.com/barcode/net/).

3. 您的 .NET 项目：您应该设置一个 .NET 项目并准备好集成条形码生成。

现在，让我们开始吧！

## 导入命名空间

第一步是导入项目所需的命名空间。这些命名空间将使您能够访问 Aspose.BarCode 的特性和功能。

### 第 1 步：导入命名空间

```csharp
using Aspose.BarCode.Generation;
```

## 一维码128配置

现在，让我们使用 Aspose.BarCode for .NET 创建 Code 128 条形码。我们将详细介绍每个步骤，确保您清楚地了解该过程。

### 第2步：设置路径

首先，设置要保存生成的条形码图像的目录的路径。

```csharp
string path = "Your Directory Path";
```

### 第 3 步：创建 Code 128 条形码生成器

创建一个`BarcodeGenerator`用于生成 Code 128 条形码的实例。您可以指定要生成的条形码类型（在本例中为 Code128）以及要编码的值。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### 步骤4：配置条码参数

在生成条形码之前，您可以配置各种参数。例如，您可以选择显示或隐藏校验和。

#### 选项 1：不显示校验和

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### 选项 2：显示校验和

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### 第 5 步：保存条形码图像

现在，是时候将生成的条形码图像保存到您指定的目录了。您可以保存带或不带校验和的条形码，具体取决于您在上一步中选择的配置。

#### 保存不带校验和的条形码

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### 保存带校验和的条形码

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

就是这样！您已使用 Aspose.BarCode for .NET 成功生成一维 Code 128 条形码。您可以在各种应用中使用这些条形码，例如库存管理、产品标签等。

## 结论

Aspose.BarCode for .NET 为 .NET 应用程序中的条形码生成提供了强大且用户友好的解决方案。凭借其直观的 API 和丰富的文档，您可以轻松地将条形码功能集成到您的项目中。无论您需要创建一维还是二维条形码，Aspose.BarCode 都能满足您的需求。

立即将 Aspose.BarCode 整合到您的 .NET 应用程序中，轻松简化您的条形码生成过程。

### 常见问题解答

### Aspose.BarCode for .NET 与 .NET Core 兼容吗？
是的，Aspose.BarCode for .NET 与 .NET Framework 和 .NET Core 兼容。

### 我可以自定义生成的条形码的外观吗？
绝对地！ Aspose.BarCode 允许您自定义条形码的各个方面，包括大小、颜色和文本位置。

### Aspose.BarCode适合生成二维码吗？
虽然 Aspose.BarCode 主要关注一维条形码，但您也可以使用 Aspose.BarCode for .NET 生成 QR 码。

### 有免费试用吗？
是的，您可以通过下载试用版免费试用 Aspose.BarCode for .NET[这里](https://releases.aspose.com/).

### 在哪里可以获得 Aspose.BarCode for .NET 支持？
您可以在 Aspose.BarCode for .NET 论坛上寻求帮助并分享您的经验[这里](https://forum.aspose.com/c/barcode/13).
