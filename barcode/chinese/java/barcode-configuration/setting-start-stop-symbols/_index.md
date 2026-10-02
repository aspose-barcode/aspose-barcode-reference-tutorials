---
date: 2026-08-28
description: 了解如何使用 Aspose Barcode Java 在 Java 中创建条形码图像，设置 CODABAR 起始和终止符，并生成不含水印的
  PNG 文件。
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: 设置起始和终止符
og_description: 使用 Aspose Barcode Java 创建 Java 条形码图像。本指南展示了如何设置 CODABAR 起始/终止符并导出不含水印的
  PNG。
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: 创建 Java 条形码图像 – 起始/终止符指南
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – 使用起始/终止符创建条形码图像
url: /zh/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – 使用起始/结束符号创建条形码图像

## 介绍

在本综合教程中，您将使用 Aspose Barcode Java **create barcode image java** 并学习 **如何设置起始和结束符号** 用于 CODABAR 条形码。无论您是在构建销售点终端、仓库管理系统，还是任何需要可靠条形码生成的应用程序，定制这些符号都能让您满足旧有规范，同时保持代码简洁易维护。我们将逐步演示每一步，解释每个设置的重要性，并展示如何生成不带试用水印的 PNG 图像。

## 快速回答
- **什么库在 Java 中创建条形码图像？** Aspose.BarCode for Java.  
- **我可以自定义起始/结束符号吗？** 可以，使用 `setCodabarStartSymbol` 和 `setCodabarStopSymbol`。  
- **本示例使用哪种条形码类型？** CODABAR.  
- **生产环境需要许可证吗？** 非试用使用需要商业许可证。  
- **生成的输出格式是什么？** 保存到磁盘的 PNG 图像.

## Aspose Barcode Java 是什么？

Aspose Barcode Java 是一个 **无需依赖的 Java 库，能够生成超过 70 种条形码符号**，从传统的 1D 码如 CODABAR 到现代的 2D 码如 QR 和 DataMatrix。它处理所有底层编码，让您专注于业务逻辑，同时确保符合行业标准。

## 为什么在生成无水印条形码时使用 Aspose Barcode Java？

首先加载许可证，库即可生成干净的图像——没有 “Aspose Evaluation” 覆盖。它还提供 **细粒度控制**（起始/结束符号、颜色、尺寸）和 **跨平台兼容性**（任何 Java 运行时，包括 Android）。支持 **50 多种输出格式**，并且能够将图像直接流式传输到 HTTP 响应，是高吞吐、生产级条形码创建的首选。

## 前置条件

在开始之前，请确保您已拥有：

1. **Java Development Kit (JDK)** – 从 [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) 安装最新的 JDK。  
2. **Aspose.BarCode for Java 库** – 从 [download link](https://releases.aspose.com/barcode/java/) 下载。

准备好这些后，您即可 **create barcode image java**，无需缺少组件。

## 导入包

以下导入语句为您提供生成条形码所需的核心类：

`CodabarSymbol` 枚举定义了 CODABAR 条形码允许的起始/结束字符。  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步骤指南

### 如何定义条形码图像的输出文件夹？

指定 PNG 文件写入的文件夹。使用 `Paths.get` 可使代码在 Windows、macOS 和 Linux 上保持可移植性。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### 如何为 CODABAR 创建条形码生成器？

`BarcodeGenerator` 类用于为指定的符号和数据创建条形码图像。

使用 CODABAR 符号和要编码的数据字符串实例化 `BarcodeGenerator`。

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### 如何设置 CODABAR 起始符号？

`setCodabarStartSymbol` 设置标记 CODABAR 条形码起始的字符。

调用 `setCodabarStartSymbol` 并传入支持的字符之一（`A`、`B`、`C`、`D`），本例使用 `A`。

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### 如何设置 CODABAR 结束符号？

`setCodabarStopSymbol` 设置标记 CODABAR 条形码结束的字符。

使用 `setCodabarStopSymbol` 并传入对应的结束字符——本例为 `D`。

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### 如何将生成的条形码保存为 PNG 文件？

`SaveFormat` 枚举指定条形码图像的保存文件格式。

调用 `save` 方法，提供完整的文件名和 `SaveFormat.Png` 枚举值。只要应用了有效许可证，图像将不带任何水印地写入。

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## 常见陷阱与技巧

`License` 类加载 Aspose 许可证文件以启用完整功能模式。

- **目录路径不正确** – 确保 `dataDir` 以适当的文件分隔符结尾，或使用 `Paths.get` 构建路径。  
- **不支持的起始/结束字符** – CODABAR 仅接受 `A`、`B`、`C` 或 `D`。提供其他值会抛出 `IllegalArgumentException`。  
- **未应用许可证** – 试用模式下输出会包含水印。在创建生成器之前使用 `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` 加载许可证文件以避免此问题。  
- **大规模生成** – 生成数千个条形码时，复用同一个 `BarcodeGenerator` 实例，仅更改代码文本，以减少对象创建开销。

## 常见问题

### 我可以在商业项目中使用 Aspose.BarCode for Java 吗？

可以。购买商业许可证 [purchase a commercial license](https://purchase.aspose.com/buy) 以去除评估水印并获得完整技术支持。

### 是否提供免费试用？

当然。下载试用版 [download the trial version](https://releases.aspose.com/) 以在购买前评估所有功能。

### 如何获取 Aspose.BarCode for Java 的支持？

访问 Aspose.BarCode 论坛 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 获取社区帮助，或通过 Aspose 账户门户提交支持工单。

### 如何获取用于测试的临时许可证？

您可以请求临时 30 天许可证 [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/)。这使您能够在不完整购买的情况下进行类似生产的测试。

### Aspose.BarCode 还支持哪些条形码符号？

该库支持 **70 多种符号**，包括 Code128、EAN‑13、QR、DataMatrix、PDF417 等。完整列表请参阅官方文档。

## 附加问答（AI 友好）

**Q:** 除 PNG 外，我还能导出哪些图像格式？  
**A:** Aspose.BarCode 支持 PNG、JPEG、BMP、GIF 和 TIFF。通过在 `save` 调用中更改 `SaveFormat` 枚举值来选择所需格式。

**Q:** 我可以在内存中生成条形码图像而不写入磁盘吗？  
**A:** 可以。调用 `generator.save(OutputStream)` 直接写入流——适用于返回图像作为 HTTP 响应的 Web API。

**Q:** 该库能在 Android 上运行吗？  
**A:** Java 版本可在 Android 上运行，但需手动包含所需依赖（Android 没有 Maven Central）。核心 API 保持一致。

## 结论

您现在已经学习了如何使用 Aspose Barcode Java **create barcode image java** 并精确 **设置 CODABAR 条形码的起始/结束符号**。此方法为您提供了满足旧有规范的灵活性，同时保持代码库清晰易维护。通过查阅官方 API 参考文档 [documentation](https://reference.aspose.com/barcode/java/) 可进一步探索自定义——例如更改颜色、添加可读文本或切换到其他符号。

---

**最后更新：** 2026-08-28  
**测试环境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose

## 相关教程

- [在 Java 中使用 Aspose.BarCode 验证校验和并创建 Codabar 条形码](/barcode/java/checksum-and-validation/)
- [使用 Aspose 创建条形码 - 在 Java 中设置 X 与 Y 尺寸](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [如何生成 barcode java：创建精确条形码图像](/barcode/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}