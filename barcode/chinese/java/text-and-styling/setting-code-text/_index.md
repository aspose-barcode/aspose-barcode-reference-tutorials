---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode 在 Java 中创建 Code128 条形码。本分步指南展示了如何生成 Java 条形码、设置自定义文本、调整条宽以及保存图像。
keywords:
- create code128 barcode java
- how to generate barcode java
- java barcode generator example
linktitle: 设置代码文本
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  type: TechArticle
- description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library should I use?
  - answer: CODE_128.
    question: Which barcode type is demonstrated?
  - answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
    question: How do I set custom barcode text?
  - answer: Yes—adjust `XDimension` (bar width) in millimetres.
    question: Can I change the bar width?
  - answer: A commercial license is required for non‑trial deployments.
    question: Do I need a license for production?
  type: FAQPage
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 创建 Code128 条形码 Java – 设置代码文本
url: /zh/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 Code128 条形码 Java – 使用 Aspose.BarCode 设置代码文本

在本教程中，您将学习如何使用 Aspose.BarCode Java 库 **创建 Code128 条形码 Java**。无论您是在构建库存系统、文档跟踪解决方案，还是任何需要条形码的应用程序，我们都会一步步指导您——从实例化 **Code128** 条形码到自定义代码文本并微调条宽。完成后，您将拥有一张随时可用的图像，可嵌入到任何需要的地方。

## 快速答案
- **我应该使用哪个库？** Aspose.BarCode for Java.  
- **演示的条形码类型是什么？** CODE_128.  
- **如何设置自定义条形码文本？** 使用 `BarcodeGenerator` 构造函数或 `setCodeText` 方法。  
- **我可以更改条宽吗？** 可以——通过调整 `XDimension`（条宽）以毫米为单位。  
- **生产环境是否需要许可证？** 非试用部署需要商业许可证。

## 如何在 Java 中创建 Code128 条形码？

使用 `CODE_128` 符号和所需文本加载 `BarcodeGenerator`，通过 `XDimension` 设置条宽，然后调用 `save` 将图像文件写入磁盘。此三步模式可在几秒钟内生成高质量条形码，并且可在任何 Java 8+ 运行时、Windows、Linux 或 macOS 上运行。

## 生成条形码 Java 的先决条件

- 基本的 Java 编程知识。  
- Java 开发环境（JDK 8 或更高）。  
- Aspose.BarCode for Java 库 – 在 **[here](https://releases.aspose.com/barcode/java/)** 下载。  
- 您喜欢的 IDE（IntelliJ IDEA、Eclipse 等）。

## 导入包

导入必要的 Aspose.BarCode 命名空间，以便在项目中使用这些类。

## 什么是 BarcodeGenerator 类？

`BarcodeGenerator` 是 Aspose.BarCode 的核心类，用于在内存中创建条形码图像。它提供流式 API，可设置符号、代码文本、尺寸、颜色以及其他渲染选项，然后将结果导出为 PNG、JPEG、SVG 或 PDF 等格式。您还可以根据需要自定义标题、边距和错误纠正级别。

## 条形码生成器教程：创建 Code128 条形码

### 步骤 1：创建 `BarcodeGenerator` 实例

`BarcodeGenerator` 构造函数接受两个参数：条形码符号（`CODE_128`）和您想要编码的 **自定义代码文本**，例如 `"12345678"`。

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### 步骤 2：为自定义条形码文本调整条宽

设置 `XDimension` 属性（条宽）以控制每根条的宽度。在本例中我们使用 `0.5` mm，这一尺寸在大多数应用中兼顾可读性和标签空间。

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### 步骤 3：保存条形码图像

调用 `save` 方法，指定输出路径和图像格式（JPEG、PNG、SVG 等）。示例将文件保存为项目文档文件夹中的 **`setCodeText.jpg`**。

```java
generator.save(dataDir + "setCodeText.jpg");
```

## 为什么使用 Aspose.BarCode for Java？

Aspose.BarCode for Java 提供了一整套功能，简化了跨平台的条形码生成。它支持超过六十种符号，提供高分辨率光栅和矢量输出，并针对批量处理进行性能优化，使其成为企业级应用的理想选择，并能无缝集成到现有的 Java 项目中。

- **广泛的符号支持** – 超过 **60** 种条形码类型，包括 Code128、QR、DataMatrix 和 PDF417。  
- **高分辨率渲染** – 生成清晰的 PNG、JPEG、SVG 和 PDF 图像，宽度可达 **2000 mm**，且不失真。  
- **性能导向** – 在标准服务器硬件上，处理 500 页条形码批次耗时不足 **2 秒**。  
- **跨平台** – 完全兼容 Windows、Linux 和 macOS，并可在任何 Java 8+ 运行时上运行。

## 常见问题及解决方案

| 问题 | 解决方案 |
|-------|----------|
| **条形码模糊** | 提高图像分辨率或导出为矢量格式（SVG、PDF）。 |
| **文本被截断** | 增大 `XDimension` 和 `BarHeight`，为符号提供足够空间。 |
| **许可证未生效** | 将 `Aspose.BarCode.lic` 放置在项目根目录，并使用 `License license = new License(); license.setLicense("Aspose.BarCode.lic");` 加载。 |

## 常见问答

**问：** *`CODE_128` 与其他 Code128 变体有什么区别？*  
**答：** `CODE_128` 会根据输入自动选择最有效的编码方式（A、B 或 C），从而提供最佳的密度和速度。

**问：** *我可以将输出格式改为 PNG 而不是 JPEG 吗？*  
**答：** 可以——使用 `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`。

**问：** *可以在条形码下方添加可读的标题吗？*  
**答：** 当然。设置 `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` 并通过 `setText` 定义标题文本。

**问：** *Aspose.BarCode 支持 Unicode 字符吗？*  
**答：** 支持。提供 UTF‑8 编码的文本，并确保所选符号支持该字符集。

**问：** *如何在循环中生成多个条形码？*  
**答：** 在循环内部实例化新的 `BarcodeGenerator`，为每次迭代分配唯一的文本，并使用不同的文件名调用 `save`。

---

**最后更新：** 2026-06-09  
**测试环境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [在 Java 中创建 Data Matrix 条形码并设置代码文本位置](/barcode/java/text-and-styling/setting-code-text-location/)
- [如何在 Java 中使用 Aspose.BarCode 设置条形码文本颜色](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [生成 Java 条形码 – 使用 Aspose.BarCode 设置图像分辨率](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```