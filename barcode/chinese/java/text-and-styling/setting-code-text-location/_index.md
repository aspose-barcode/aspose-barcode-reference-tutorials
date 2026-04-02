---
date: 2025-12-27
description: 学习如何使用 Aspose.BarCode 在 Java 中创建 Data Matrix 条码以及设置条码文本位置。请按照我们的分步指南进行完整自定义。
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: 在 Java 中创建数据矩阵条码并设置代码文本位置
url: /zh/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中创建 Data Matrix 条码并设置代码文本位置

## 介绍

生成条码是库存、运输以及许多其他基于 Java 的应用程序的常规需求。使用 **Aspose.BarCode for Java**，您可以快速 **create data matrix barcode**，并控制每个视觉细节，包括人类可读文本出现的位置。在本教程中，我们将逐步演示 **create data matrix barcode** 的完整步骤，并展示 **how to set barcode text** 如何在符号上方设置，以符合您的设计规范。

## 快速答案
- **使用的库是什么？** Aspose.BarCode for Java  
- **演示的条码类型是什么？** Data Matrix  
- **如何定位代码文本？** Using `CodeLocation.ABOVE`  
- **生产环境需要许可证吗？** 是的，需要商业许可证  
- **代码可以在 Java 8+ 上运行吗？** 当然，它支持 Java 8 及更高版本  

## 什么是 Data Matrix 条码？

Data Matrix 条码是一种二维（2‑D）符号，可在紧凑的方形或矩形图案中存储大量数据。它广泛用于标记小件物品、电子产品和医疗设备，因为它可以编码最多 2,335 个字母数字字符。

## 为什么要设置条码文本位置？

将可读的文本 **above**、**below** 或 **beside** 放置在条码上方、下方或旁边，可帮助用户在不扫描的情况下快速验证编码数据。调整文本位置可提升 UI 一致性并符合品牌指南。

## 先决条件

- 对 Java 编程的基本了解。  
- 已安装 Java Development Kit (JDK)。  
- 如 Eclipse 或 IntelliJ IDEA 等 IDE。  
- Aspose.BarCode for Java 库（从 [here](https://releases.aspose.com/barcode/java/) 下载）。

## 导入包

首先，将必要的 Aspose.BarCode 类导入到项目中：

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 分步指南

### 步骤 1：定义目录路径
指定读取/写入文件的位置。将占位符替换为您机器上的实际路径。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### 步骤 2：创建 BarcodeGenerator 实例
使用 **Data Matrix** 类型实例化 `BarcodeGenerator`，并提供要编码的代码文本。

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### 步骤 3：如何设置条码文本位置
使用 `CodeLocation` 枚举来移动可读文本。在本例中，我们将其放置在条码的 **above** 位置。

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### 步骤 4：保存生成的条码图像
最后，将条码图像写入磁盘。文件将包含带有文本位于上方的 Data Matrix 符号。

```java
generator.save(dataDir + "codetextAbove.png");
```

## 常见问题及解决方案
- **文本未显示：** 确保使用的 Aspose.BarCode 版本支持 `CodeLocation`。  
- **文件路径错误：** 验证 `dataDir` 以适合您操作系统的文件分隔符（`/` 或 `\\`）结尾。  
- **不支持的字符：** Data Matrix 只能编码有限的字符集；请避免使用 ISO/IEC 16022 标准中未包含的特殊符号。

## 常见问题 (FAQs)

### 问：我可以自定义生成的条码外观吗？
**答：** 是的，Aspose.BarCode 提供了丰富的自定义选项，您可以控制颜色、边距和字体样式。

### 问：Aspose.BarCode 与 Java 8 及更高版本兼容吗？
**答：** 当然，库兼容 Java 8 以及所有后续版本。

### 问：我如何将 Aspose.BarCode 集成到现有的 Java 项目中？
**答：** 将 Aspose.BarCode 的 JAR 文件添加到项目的类路径，导入所需的包，即可开始生成条码。

### 问：Aspose.BarCode 有试用版吗？
**答：** 是的，您可以通过获取免费试用版 [here](https://releases.aspose.com/) 来了解 Aspose.BarCode 的功能。

### 问：我可以在哪里寻求 Aspose.BarCode 的帮助或支持？
**答：** 访问 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 获取社区帮助和官方支持。

## 附加常见问题

**问：我可以生成文本位于符号下方的条码吗？**  
**答：** 是的，在相同的 `setLocation` 方法中设置 `CodeLocation.BELOW`。

**问：库是否支持其他 2‑D 条码，如 QR Code？**  
**答：** 当然，只需将 `EncodeTypes.DATA_MATRIX` 更改为 `EncodeTypes.QR`。

**问：如何更改条码文本的字体大小？**  
**答：** 使用 `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`。

## 结论

您现在已经学习了如何在 Java 中 **create data matrix barcode** 并使用 Aspose.BarCode 精确控制 **how to set barcode text** 位置。尝试其他 `CodeLocation` 值和样式选项，以满足您应用的设计需求。

---

**最后更新：** 2025-12-27  
**测试环境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}