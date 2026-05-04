---
date: 2026-05-04
description: 了解如何使用 Java 条码库创建 Data Matrix 条码，并使用 Aspose.BarCode 将条码文本位置设置在符号上方。请按照我们的逐步条码生成示例进行操作。
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: 设置代码文本位置
second_title: Aspose.BarCode Java API
title: 使用 Java 条码库创建 Data Matrix 条码并设置代码文本位置
url: /zh/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 条形码库创建 Data Matrix 条码并设置代码文本位置

## 介绍

如果您正在使用 Java 构建库存、运输或跟踪系统，您会很快发现可靠的 **java barcode library** 是必不可少的。使用 **Aspose.BarCode for Java**，您只需几行代码即可生成 **Data Matrix 条码**，并完全控制视觉布局，包括人类可读文本出现的位置。在本教程中，我们将演示完整的 **barcode generation example**，展示如何 **customize barcode text** 的放置，并解释为何将文本放置在符号上方可以提升可用性。

## 快速答案
- **使用了哪个库？** Aspose.BarCode for Java  
- **演示的条码类型是？** Data Matrix  
- **如何定位代码文本？** 使用 `CodeLocation.ABOVE`（您也可以使用 `BELOW`）  
- **生产环境是否需要许可证？** 是的，需要商业许可证  
- **代码能在 Java 8+ 上运行吗？** 当然，支持 Java 8 及更高版本  

## 什么是 Java 条形码库？

**java barcode library** 为开发者提供即用的 API，直接在 Java 应用程序中创建、读取和样式化 1‑D 和 2‑D 条码。它抽象了复杂的编码规则，使您能够专注于业务逻辑，而不是低层图像处理。

## 为什么在条码生成示例中使用 Java 条形码库？

- **速度：** 在毫秒级生成高质量条码。  
- **可靠性：** 内置符合 ISO/IEC 标准。  
- **灵活性：** 完全控制尺寸、颜色、边距以及 **barcode text** 的放置。  
- **跨平台：** 在任何基于 JVM 的环境中运行，从桌面应用到云服务。  

## 什么是 Data Matrix 条码？

Data Matrix 条码是一种二维（2‑D）符号，以紧凑的方形或矩形图案存储大量数据。它广泛用于标记小件、电子产品和医疗设备，因为它可以编码最多 2,335 个字母数字字符。

## 为什么设置条码文本位置？

将人类可读的文本 **above**、**below** 或 **beside** 条码放置，有助于用户在不扫描的情况下快速验证编码数据。调整文本位置可提升 UI 一致性，符合品牌指南，并可减少手动数据录入错误。

## 前提条件

- 具备 Java 编程的基础知识。  
- 已安装 Java Development Kit (JDK)。  
- 使用 Eclipse 或 IntelliJ IDEA 等 IDE。  
- Aspose.BarCode for Java 库（从 [此处](https://releases.aspose.com/barcode/java/) 下载）。  

## 导入包

首先，将必要的 Aspose.BarCode 类导入到项目中：

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

这些导入为您提供对条码生成器和控制文本放置的枚举的访问。

## 步骤指南

### 步骤 1：定义目录路径

指定读取/写入文件的位置。将占位符替换为您机器上的实际路径。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 步骤 2：创建 BarcodeGenerator 实例

使用 **Data Matrix** 类型实例化 `BarcodeGenerator`，并提供您希望编码的代码文本。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 步骤 3：设置条码文本位置（自定义条码文本）

使用 `CodeLocation` 枚举来移动人类可读的文本。在本例中，我们将其放置在条码的 **above** 位置。

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **技巧提示：** 若要将文本放在符号的 **below**，只需将 `CodeLocation.ABOVE` 更改为 `CodeLocation.BELOW`。

### 步骤 4：保存生成的条码图像

最后，将条码图像写入磁盘。文件将包含带有文本位于上方的 Data Matrix 符号。

```java
generator.save(dataDir + "codetextAbove.png");
```

## 常见问题及解决方案
- **文本未显示：** 确保使用的 Aspose.BarCode 版本支持 `CodeLocation`。  
- **文件路径错误：** 验证 `dataDir` 以适合您操作系统的文件分隔符（`/` 或 `\\`）结尾。  
- **不支持的字符：** Data Matrix 只能编码有限的字符集；请避免使用 ISO/IEC 16022 标准中未包含的特殊符号。  

## 常见问题解答 (FAQs)

### 问：我可以自定义生成的条码外观吗？

答：可以，Aspose.BarCode 提供广泛的自定义选项，允许您控制颜色、边距和字体样式。

### 问：Aspose.BarCode 与 Java 8 及更高版本兼容吗？

答：当然，库兼容 Java 8 及所有后续版本。

### 问：如何将 Aspose.BarCode 集成到现有的 Java 项目中？

答：将 Aspose.BarCode 的 JAR 文件添加到项目的 classpath，导入所需的包，即可生成条码。

### 问：Aspose.BarCode 有试用版吗？

答：是的，您可以通过获取免费试用版 [此处](https://releases.aspose.com/) 来体验 Aspose.BarCode 的功能。

### 问：我可以在哪里寻求 Aspose.BarCode 的帮助或支持？

答：访问 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 获取社区帮助和官方支持。

## 其他常见问题

**问：我可以生成文本位于符号下方的条码吗？**  
答：可以，在相同的 `setLocation` 方法中设置 `CodeLocation.BELOW`。

**问：该库支持其他 2‑D 条码，如 QR Code 吗？**  
答：当然，只需将 `EncodeTypes.DATA_MATRIX` 更改为 `EncodeTypes.QR`。

**问：如何更改条码文本的字体大小？**  
答：使用 `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`。

## 结论

您现在已经学习了如何使用 **java barcode library** 在 Java 中 **创建 Data Matrix 条码**，并通过 Aspose.BarCode 精确控制 **如何设置条码文本** 的位置。尝试其他 `CodeLocation` 值、字体设置和颜色选项，以满足您应用的设计需求。

**最后更新：** 2026-05-04  
**测试环境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}