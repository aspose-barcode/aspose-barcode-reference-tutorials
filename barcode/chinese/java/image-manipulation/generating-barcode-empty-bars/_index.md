---
date: 2026-04-12
description: 学习如何使用 Aspose.BarCode 在 Java 中创建带空白条的 Code128 条形码。本指南向您展示如何快速生成条形码 Java
  图像。
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: 生成带空白条的条形码
second_title: Aspose.BarCode Java API
title: 如何在 Java 中创建带空白条的 Code128 条形码
url: /zh/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中创建带空白条的 Code128 条形码

## 介绍

在 Java 应用程序中集成条形码生成是一个常见需求，无论您是构建库存系统、票务平台，还是销售点解决方案。使用 **Aspose.BarCode for Java**，您可以仅用几行代码 **创建 Code128 条形码** 图像。在本教程中，我们将逐步演示如何 **生成带有空白（未填充）条的条形码 Java** 图像，让您完全掌控条形码的视觉样式。

## 快速答案
- **哪个库？** Aspose.BarCode for Java  
- **主要用例？** 为自定义 UI 设计创建带空白条的 Code128 条形码  
- **先决条件？** Java JDK 8+、Aspose.BarCode JAR、对输出图像文件夹的写入权限  
- **典型实现时间？** 基本示例 5‑10 分钟  
- **我可以自定义颜色吗？** 可以——API 提供了丰富的样式选项  

## 什么是 Code128 条形码？

Code128 是一种高密度线性条形码符号系统，能够编码完整的 ASCII 字符集。它在物流、运输和零售领域被广泛使用，因为它可以紧凑地表示字母数字数据。默认情况下，Aspose.BarCode 将 Code128 条形码的条渲染为实心矩形；将 **FilledBars** 属性设置为 `false` 可将其变为空心（轮廓）条，这对于品牌化的视觉效果很有用。

## 为什么使用 Aspose.BarCode for Java？

- **功能丰富** —— 支持 50 多种条形码类型，包括 QR、DataMatrix 和 PDF417。  
- **无外部依赖** —— 单个 JAR 可在任何 Java 运行时上运行。  
- **细粒度控制** —— 您可以调整条宽、颜色、字体以及 `FilledBars` 属性。  
- **跨平台** —— 在 Windows、Linux 和 macOS 上均可运行，无需本地库。  

## 先决条件

在开始之前，请确保您拥有：

1. **Java 开发环境** —— 已安装 JDK 8 或更高版本，并配置了 `JAVA_HOME`。  
2. **Aspose.BarCode for Java** —— 从[下载页面](https://releases.aspose.com/barcode/java/)下载最新的 JAR。  
3. **文档目录** —— 您电脑上的一个文件夹，用于保存生成的条形码图像。

## 导入包

在您的 Java 项目中，导入使用 Aspose.BarCode 所需的类：

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

这些导入为您提供了条形码生成器、图像格式枚举以及异常处理的访问权限。

## 步骤 1：设置资源目录

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您在先决条件中创建的文件夹的绝对路径。这是 PNG 文件将被写入的位置。

## 步骤 2：创建 Code128 条形码生成器实例

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

在这里我们使用 **CODE_128** 符号和示例文本 `"TEXT"` 实例化 `BarcodeGenerator`。这是一个 **barcode generator Java example**，您可以将其适配为任何需要编码的字符串。

## 步骤 3：将 FilledBars 属性设为 False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

通过将 `FilledBars` 设置为 `false`，生成的条形码将显示空白条而非实心条，从而实现我们想要的视觉效果。

## 步骤 4：保存条形码图像

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

`save` 方法将条形码以 PNG 格式写入指定目录。如果需要其他图像类型，可将 `BarCodeImageFormat.PNG` 更改为 `JPG`、`BMP` 或 `TIFF`。

## 常见用例

- **自定义品牌** —— 空白条可以叠加背景图案或颜色。  
- **可打印资产** —— 生成高分辨率 PNG，用于发票或运单标签。  
- **动态生成** —— 在 Web 服务或桌面应用程序中即时创建条形码。  

## 故障排除技巧

- **路径无效** —— 确保 `dataDir` 以文件分隔符（`/` 或 `\\`）结尾，或使用 `File.separator` 进行拼接。  
- **需要许可证** —— 试用版可用于评估，但生产环境需要完整许可证。  
- **不支持的字符** —— Code128 支持完整的 ASCII 集；除非切换到其他符号，否则避免使用 Unicode 字符。  

## 结论

您现在已经学习了如何使用 Aspose.BarCode for Java **创建带空白条的 Code128 条形码** 图像。这种简洁的方法让您能够快速生成可定制的条形码图形，无论是构建桌面库存工具还是基于云的 API。

## 常见问题

### Aspose.BarCode 是否兼容所有 Java 开发环境？

是的，Aspose.BarCode 旨在无缝集成到任何 Java IDE 或构建系统中，包括 Maven、Gradle 和普通 JAR 项目。

### 我可以自定义生成的条形码外观吗？

当然！除了 `FilledBars`，您还可以使用丰富的 API 修改颜色、条宽、边距，甚至添加可读文本。

### Aspose.BarCode 是否提供试用版？

是的，您可以通过获取免费试用 [here](https://releases.aspose.com/) 来探索 Aspose.BarCode 的功能。

### 如何获取 Aspose.BarCode 的支持？

如有任何疑问或需要帮助，请访问 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)。

### 在哪里可以找到 Aspose.BarCode 的详细文档？

完整的文档可在 [here](https://reference.aspose.com/barcode/java/) 查看。

**其他问题**

**Q: 如何以不同的格式（例如 JPEG）生成条形码图像？**  
A: 将 `save` 的第二个参数改为 `BarCodeImageFormat.JPEG`。

**Q: 我可以在循环中生成多个条形码吗？**  
A: 可以——在循环内部实例化新的 `BarcodeGenerator`，或使用同一实例并设置新的 `CodeText`。

---

**最后更新：** 2026-04-12  
**测试环境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}