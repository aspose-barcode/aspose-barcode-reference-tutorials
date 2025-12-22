---
date: 2025-12-22
description: 了解如何使用 Aspose.BarCode for Java 创建带空白条的条形码图像。此一步步的条形码生成示例可帮助您快速生成 Java
  条形码。
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
title: 如何在 Java 中创建带空白条的条形码图像
url: /zh/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中创建带空白条的条形码图像

## 介绍

在现代 Java 应用程序中，能够 **create barcode image** 文件并即时生成是一项对库存管理、票务系统以及许多其他业务场景都非常有价值的功能。Aspose.BarCode for Java 提供了强大且易于使用的 API，只需几行代码即可生成高质量的条形码。在本教程中，我们将逐步演示 **step‑by‑step barcode** 的创建过程，生成带有空白（未填充）条的条形码，适用于需要空心外观的设计。

## 快速答案
- **“empty bars” 是什么意思？** 条形码的条在渲染时不使用默认的实心填充，呈现空心外观。  
- **使用哪种条形码类型？** Code 128（广泛支持的线性符号）。  
- **试用是否需要许可证？** 提供免费试用版；生产环境需要许可证。  
- **支持哪些输出格式？** PNG、JPEG、BMP、GIF、TIFF 等。  
- **是否兼容所有 Java 版本？** 是的，库支持 Java 8 及更高版本。

## 什么是 create barcode image？
创建条形码图像是指将一串数据转换为扫描仪能够读取的可视化表示。生成的图像可以保存为 PNG、JPEG 或其他常见格式，并可嵌入 PDF、打印在标签上或显示在 UI 中。

## 为什么使用 Aspose.BarCode Java 库？
- **功能丰富** – 支持 50 多种条形码符号，包括 Code 128、QR、DataMatrix 等。  
- **细粒度控制** – `FilledBars`、颜色、边距和图像尺寸等属性均可轻松配置。  
- **无外部依赖** – 单个 JAR 文件即可完成所有工作，简化部署。  
- **文档完善** – 示例、API 参考和论坛帮助您快速上手。

## 前置条件

在开始条形码生成之旅之前，请确保具备以下前置条件：

1. **Java 开发环境** – 确保已安装 Java 8+，并拥有兼容的 IDE 或构建工具。  
2. **Aspose.BarCode for Java 库** – 从[下载页面](https://releases.aspose.com/barcode/java/)下载并安装 Aspose.BarCode for Java 库。  
3. **文档目录** – 在系统上创建一个目录，用于存放生成的条形码图像。

## 导入包

在您的 Java 项目中，导入使用 Aspose.BarCode 所需的包：

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何创建带空白条的条形码图像

### 步骤 1：设置资源目录

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望保存输出文件的实际路径。

### 步骤 2：创建条形码生成器实例（Code128 条形码 Java）

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

这里我们使用 **Code 128** 符号——最流行的线性条形码之一，使本示例成为经典的 **code128 barcode java** 示例。

### 步骤 3：将 FilledBars 属性设为 False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

将 `FilledBars` 设置为 `false` 可让 Aspose.BarCode 将条渲染为空（空心）形状，而非实心块。

### 步骤 4：保存条形码图像

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

图像以 PNG 格式保存，您也可以将 `BarCodeImageFormat` 枚举更改为 JPEG、BMP 或其他受支持的类型。

重复上述步骤，即可在 Java 应用程序中轻松 **create barcode image** 带空白条的文件，使用 Aspose.BarCode for Java。

## 结论

总之，本教程通过 **step‑by‑step barcode** 的创建过程，展示了如何在 Java 中 **create barcode image** 带空白条的文件。凭借直观的 API 和丰富的自定义选项，Aspose.BarCode 简化了条形码集成，是需要可靠 **java barcode library** 的开发者的宝贵资产。

## 常见问答

### Aspose.BarCode 是否兼容所有 Java 开发环境？
是的，Aspose.BarCode 旨在无缝集成到各种 Java 开发环境中。

### 我可以自定义生成的条形码外观吗？
当然！Aspose.BarCode 提供众多自定义选项，您可以根据具体需求调整条形码的外观。

### 是否提供 Aspose.BarCode 的试用版？
是的，您可以通过获取免费试用版[此处](https://releases.aspose.com/)来体验 Aspose.BarCode 的功能。

### 如何获取 Aspose.BarCode 的支持？
如有任何疑问或需要帮助，请访问[Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)。

### 在哪里可以找到 Aspose.BarCode 的详细文档？
完整文档可在[此处](https://reference.aspose.com/barcode/java/)查阅。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose  

---