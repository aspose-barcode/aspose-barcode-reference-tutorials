---
date: 2026-02-17
description: 了解如何使用 Aspose Barcode Java 创建条形码图像，设置 CODABAR 的起始和结束符号，并生成不带水印的 PNG 文件。
linktitle: Setting Start and Stop Symbols
second_title: Aspose.BarCode Java API
title: Aspose 条码 Java – 创建带起止符的条码图像
url: /zh/java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

 >}}

All preserved.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – 使用起始/结束符号创建条形码图像

## 简介

在本综合教程中，您将使用 **Aspose Barcode Java** **create barcode image java** 文件，并学习 **how to set symbols** 用于 Codabar 条码。无论您是构建销售点系统、物流应用，还是任何需要可靠条码生成的解决方案，自定义起始和结束符号都能让您完全控制条码格式。我们将逐步演示每一步，解释每个设置的重要性，并展示如何生成可直接使用的 PNG 图像——无需试用水印。

## 快速回答
- **哪个库在 Java 中创建条码图像？** Aspose.BarCode for Java.  
- **我可以自定义起始/结束符号吗？** Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.  
- **此示例使用哪种条码类型？** CODABAR.  
- **生产环境需要许可证吗？** A commercial license is required for non‑trial use.  
- **生成的输出格式是什么？** PNG image saved to disk.

## 什么是 Aspose Barcode Java？

Aspose Barcode Java 是一个强大且无依赖的库，允许您以编程方式生成各种条码符号。它抽象了底层编码逻辑，使您能够专注于业务规则，同时确保输出符合行业标准。

## 为什么在无水印的条码生成中使用 Aspose Barcode Java？

- **生产环境无水印** – 一旦应用有效许可证，图像将是干净的。  
- **广泛的符号支持** – 从经典的 1D 码如 CODABAR 到 2D 码如 QR 和 DataMatrix。  
- **细粒度控制** – 您可以设置起始/结束符号、颜色、尺寸，甚至直接将图像生成到流中以供 Web 应用使用。  
- **跨平台** – 可在任何 Java 运行时上运行，包括 Android（需手动处理依赖）。

## 先决条件

在深入之前，请确保您拥有：

1. **Java Development Kit (JDK)** – 从 [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html) 安装最新的 JDK。  
2. **Aspose.BarCode for Java library** – 从 [download link](https://releases.aspose.com/barcode/java/) 下载。

准备好这些后，您即可 **generate barcode image java**，无需任何缺失的组件。

## 导入包

在您的 Java 项目中，导入使用 Aspose.BarCode 所需的类：

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 分步指南

### 步骤 1：定义文档目录

将 `"Your Document Directory"` 替换为您希望保存条码图像的绝对或相对路径。请记得在路径末尾添加适当的文件分隔符（`/` 或 `\`），或使用 `Paths.get` 进行跨平台处理。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### 步骤 2：创建条码生成器实例

这里我们指示 Aspose.BarCode 使用 **CODABAR** 符号并提供数据字符串 `"12345678"`。

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### 步骤 3：设置 Codabar 起始符号

`setCodabarStartSymbol` 方法允许您 **set barcode symbols** 起始字符。在本例中我们选择 `A`。

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### 步骤 4：设置 Codabar 结束符号

同样，`setCodabarStopSymbol` 定义结束字符。使用 `D` 完成许多旧系统所需的 CODABAR 格式。

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### 步骤 5：保存生成的图像

`save` 调用将条码写入 PNG 文件，文件名为 **startAndStopSymbols.png**，保存在您之前指定的目录中。

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## 常见问题与技巧

- **目录路径不正确** – 确保 `dataDir` 以文件分隔符（`/` 或 `\`）结尾，或使用 `Paths.get` 进行拼接。  
- **不支持的起始/结束符号** – CODABAR 仅支持 `A`, `B`, `C`, `D` 作为起始/结束符号。使用其他任何值都会抛出异常。  
- **未应用许可证** – 在试用模式下，生成的图像可能包含水印。请在部署到生产环境前应用许可证，以实现 **barcode generation without watermark**。

## 常见问题

### 我可以在商业项目中使用 Aspose.BarCode for Java 吗？

可以，您可以。在商业使用时，请考虑在 [here](https://purchase.aspose.com/buy) 购买许可证。

### 是否提供免费试用？

可以，您可以在 [here](https://releases.aspose.com/) 探索免费试用版。

### 如何获取 Aspose.BarCode for Java 的支持？

请访问 Aspose.BarCode 论坛 [here](https://forum.aspose.com/c/barcode/13) 获取支持或咨询。

### 如何获取临时许可证？

如有需要，您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证。

### Aspose.BarCode for Java 是否支持更多条码符号？

是的，Aspose.BarCode 支持广泛的条码符号。请参阅文档获取完整列表。

## 附加问答（AI 友好）

**Q:** 除 PNG 外，我可以导出哪些图像格式？  
**A:** Aspose.BarCode 支持 PNG、JPEG、BMP、GIF 和 TIFF。请在 `save` 方法中使用相应的文件扩展名。

**Q:** 我可以在内存中生成条码图像而不写入磁盘吗？  
**A:** 可以，调用 `generator.save(OutputStream)` 可直接写入流，这对于 Web 响应非常理想。

**Q:** 该库能在 Android 上运行吗？  
**A:** Java 版本兼容 Android，但您必须手动包含所需的依赖项。

## 结论

您现在已经学习了如何使用 **Aspose Barcode Java** **create barcode image java** 文件，并精确 **set barcode symbols** 用于 Codabar 条码。此技术为您提供了满足行业特定条码规范的灵活性，同时保持代码简洁可维护。通过查阅官方 API 文档 [documentation](https://reference.aspose.com/barcode/java/)，探索更多自定义选项——如更改颜色、添加可读文本或切换到其他符号集。

---

**最后更新：** 2026-02-17  
**测试环境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}