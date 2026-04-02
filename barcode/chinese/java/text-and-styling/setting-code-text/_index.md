---
date: 2025-12-30
description: 学习如何使用 Aspose.BarCode 在 Java 中生成条形码。本分步指南向您展示如何设置自定义条形码文本、调整宽度以及保存图像。
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 生成条形码 Java：使用 Aspose.BarCode 设置代码文本
url: /zh/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 生成条形码 Java：使用 Aspose.BarCode 设置代码文本

## 简介

在本教程中，您将学习如何使用 Aspose.BarCode Java 库 **generate barcode java** 生成条形码。无论您是在构建库存系统、文档跟踪解决方案，还是任何需要条形码的应用程序，本指南都会一步步带您完成——从创建 **Code128** 条形码到自定义代码文本并调整条宽。完成后，您将拥有一张可随时嵌入的可用图像。

## 快速解答
- **我应该使用哪个库？** Aspose.BarCode for Java.
- **演示的条形码类型是什么？** CODE_128.
- **如何设置自定义条形码文本？** 使用 `BarcodeGenerator` 构造函数或 `setCodeText` 方法。
- **我可以更改条宽吗？** 可以，通过以毫米为单位的 `XDimension`。
- **生产环境需要许可证吗？** 是的，需要商业许可证。

## 前提条件

在深入教程之前，请确保您已具备以下条件：

- 对 Java 编程有基本了解。  
- 已安装可用的 Java 开发环境。  
- Aspose.BarCode for Java 库。您可以在 **[here](https://releases.aspose.com/barcode/java/)** 下载。  
- 代码编辑器，例如 IntelliJ IDEA 或 Eclipse。  

## 导入软件包

首先在您的 Java 项目中导入必要的包。这些包是使用 Aspose.BarCode 所必需的。

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

现在，让我们探讨在 Java 中使用 Aspose.BarCode 设置代码文本的过程。请按照以下步骤操作：

## 条形码生成器教程：创建 Code128 条形码

### 步骤 1：创建 `BarcodeGenerator` 实例

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

这里，我们创建了一个 `BarcodeGenerator` 实例，指定条形码符号 (**CODE_128**) 和 **自定义条形码文本** `"12345678"`。

### 步骤 2：为自定义条形码文本调整条宽

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

根据需要调整条的宽度。在本示例中，我们将 **条形码宽度** 调整为 `0.5` mm，适用于大多数标签尺寸。

### 步骤 3：保存条形码图像

```java
generator.save(dataDir + "setCodeText.jpg");
```

将生成的条形码图像保存到指定目录。在本例中，文件保存为文档目录下的 **`setCodeText.jpg`**。

## Why Use Aspose.BarCode for Java?

- **全面的 API** – 支持 60 多种条形码符号，包括 Code128、QR、DataMatrix 等。  
- **高质量渲染** – 生成 PNG、JPEG、SVG 和 PDF 格式的清晰图像。  
- **易于定制** – 只需几行代码即可更改文本、尺寸、颜色，甚至添加可读的说明文字。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可运行，支持任何 Java 8+ 运行时。

## Common Issues and Solutions

| 问题 | 解决方案 |
|-------|----------|
| **条形码模糊** | 提高图像分辨率或导出为矢量格式（SVG、PDF）。 |
| **文本被截断** | 确保 `XDimension`（条宽）和 `BarHeight` 对所选符号足够大。 |
| **许可证未应用** | 将许可证文件 (`Aspose.BarCode.lic`) 放在项目根目录，并使用 `License license = new License(); license.setLicense("Aspose.BarCode.lic");` 加载。 |

## 其他常见问题

**问：** *`CODE_128` 与其他 Code128 变体有什么区别？*  
**答：** `CODE_128` 是标准符号，会根据输入文本自动选择最有效的编码（A、B 或 C）。

**问：** *我可以将输出格式改为 PNG 而不是 JPEG 吗？*  
**答：** 当然可以。使用 `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`。

**问：** *可以在条形码下方添加可读的说明文字吗？*  
**答：** 可以。设置 `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` 并指定说明文字。

**问：** *Aspose.BarCode 支持 Unicode 字符吗？*  
**答：** 支持。请使用 UTF‑8 提供文本，并确保所选符号支持该字符集。

**问：** *如何在循环中生成多个条形码？*  
**答：** 在循环内部实例化新的 `BarcodeGenerator`，为每次迭代设置文本，并使用唯一的文件名调用 `save`。

---

**最后更新：** 2025-12-30  
**测试环境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}