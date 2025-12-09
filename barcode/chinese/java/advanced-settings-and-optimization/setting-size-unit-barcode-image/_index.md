---
date: 2025-12-08
description: 学习如何使用 Aspose.BarCode 在 Java 中创建 Code128 条码并生成条码图像。使用简洁、可复用的代码为条码图像设置精确的尺寸单位。
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 在 Java 中创建 Code128 条码
url: /zh/java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 code128 barcode java 并使用 Aspose.BarCode 设置尺寸单位

## 介绍

在本分步指南中，您将 **create code128 barcode java** 代码，用于生成条形码图像并让您控制输出的尺寸单位。无论您是在构建库存系统、运单标签生成器，还是任何需要可靠条形码的 Java 应用程序，Aspose.BarCode for Java 都能使过程简洁且高度可定制。

## 快速回答
- **需要什么库？** Aspose.BarCode for Java.
- **覆盖哪种条形码类型？** CODE_128 (create code128 barcode java).
- **如何设置尺寸单位？** 使用 `BarHeight` 属性并调用 `.setPoint()`.
- **我可以以其他格式生成 barcode image java 吗？** 可以 – PNG、JPEG、BMP 等.
- **前提条件是什么？** 已安装 JDK、Aspose.BarCode 库和 Java IDE.

## 什么是 **create code128 barcode java**？

在 Java 中创建 CODE_128 条形码意味着实例化 `BarcodeGenerator` 类，并使用 `EncodeTypes.CODE_128` 枚举被广泛使用，因为它支持完整的 ASCII 字符集并提供高数据密度。

## 为什么使用 Aspose.BarCode 来 **generate barcode image java**？

- **完全控制尺寸** – 您可以设置条高度、模块大小和图像分辨率。
- **无外部依赖** – 纯 Java，可在任何支持 JDK 的平台上运行。
- **丰富的自定义** – 支持颜色、字体、边距，甚至 QR 码。
- **高性能** – 在毫秒级生成图像，适合批处理。

## 前提条件

1. **Java Development Kit (JDK)** – 在您的机器上安装 8 版或更高版本。  
2. **Aspose.BarCode for Java library** – 从 Aspose 网站下载最新的 JAR（试用版或授权版）。  
3. **A Java IDE** – 如 IntelliJ IDEA、Eclipse 或带有 Java 扩展的 VS Code。  

## 导入命名空间

在 Java 类的顶部添加所需的 import，以便访问 Aspose.BarCode 的 API：

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## 如何使用 Aspose.BarCode **generate barcode image java**？

以下是完整的工作流程。每一步都用通俗的语言解释，原始代码块保持不变。

### 步骤 1：定义资源目录

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

将 `"Your Document Directory"` 替换为您希望保存条形码图像的绝对路径。

### 步骤 2：实例化条形码对象

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

这里我们通过传入 `EncodeTypes.CODE_128` 和数据字符串 `"1234567"` 来 **create code128 barcode java**。

### 步骤 3：设置条高度（尺寸单位）

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

`setPoint()` 方法以点为单位定义高度（1 点 = 1/72 英寸）。根据布局需求调整此值。

### 步骤 4：保存图像

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

`save()` 调用将生成的条形码写入您指定的文件夹。图像格式根据文件扩展名推断（此例为 JPEG）。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **未创建图像** | `dataDir` 路径不正确或缺少写入权限。 | 确认文件夹存在且应用程序具有写入权限。 |
| **条形码显示太小** | 条高度以点为单位设置，对所选 DPI 来说太低。 | 增加传递给 `setPoint()` 的值，或通过 `bb.getParameters().getImage().setResolution()` 调整图像 DPI。 |
| **不支持的字符** | CODE_128 仅支持 ASCII；您传入了 Unicode。 | 对非 ASCII 数据使用其他符号（例如 QR_CODE）。 |

## 常见问题

**Q: Aspose.BarCode for Java 是否适用于条形码生成和识别？**  
A: 是的，库支持广泛符号的生成和识别。

**Q: 我可以自定义生成的条形码图像的外观吗？**  
A: 完全可以。您可以更改颜色、添加标题、修改边距，甚至使用丰富的 `Parameters` API 嵌入徽标。

**Q: 如何获取 Aspose.BarCode for Java 的临时许可证？**  
A: 访问 [here](https://purchase.aspose.com/temporary-license/) 申请评估用的临时许可证。

**Q: 在哪里可以找到 Aspose.BarCode for Java 的支持？**  
A: Aspose.BarCode 社区论坛是获取帮助的最佳地点。查看 [forum](https://forum.aspose.com/c/barcode/13) 获取答案并提出新问题。

**Q: Aspose.BarCode for Java 支持哪些条形码符号？**  
A: 库支持数十种符号，包括 CODE_128、QR_CODE、UPC_A、DataMatrix、PDF417 等。

---

**最后更新：** 2025-12-08  
**测试环境：** Aspose.BarCode for Java 24.12（撰写时最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}