---
category: general
date: 2026-10-18
description: 使用 Java 为 Planet 符号生成条形码图像。学习如何使用自定义条形码尺寸和空白条创建 Planet 条形码。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: zh
lastmod: 2026-10-18
og_description: 在 Java 中生成 Planet 符号的条形码图像。本教程展示如何使用自定义条形码尺寸和轮廓条创建 Planet 条形码。
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: 为 Planet 符号学生成条形码图像 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: 在 Java 中为 Planet 符号生成条形码图像
url: /zh/python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中生成 Planet 符号的条形码图像

如果您需要为 Planet 符号 **生成条形码图像**，本指南将带您完整了解整个过程。无论您是构建邮政自动化系统还是自定义追踪解决方案，您都将学习如何使用 **自定义条形码尺寸** 和轮廓（空心）条来 **创建 planet 条形码**。

本示例使用 Aspose.BarCode for Java 库，该库为每种主要条形码标准提供流畅的 API。无需额外的图像处理工具，代码可在任何 Java 8+ 运行时上运行。

## 前置条件

* 已安装 Java 8 或更高版本（本教程在 JDK 17 上测试）。
* 用于管理依赖的 Maven 或 Gradle。
* 对 Java 语法和条形码概念有基本了解。

如果您是 Maven 新手，可以使用 `mvn archetype:generate` 创建一个简单项目，并添加下面显示的 Aspose.BarCode 依赖。

## 添加 Aspose.BarCode 依赖

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **技巧提示：** 锁定版本号，以避免库更新时出现意外的破坏性更改。

## 步骤 1：为 Planet 符号初始化条形码生成器

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**此步骤重要原因：**  
`EncodeTypes.PLANET` 告诉库使用 Planet 条形码规范，该规范常用于邮政服务。数据字符串 `"123456"` 是将在生成的图像中显示的负载。

## 步骤 2：设置自定义条形码尺寸（X 维度）

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**此步骤重要原因：**  
*X 维度* 定义每根条的宽度。将其设置为 **4 像素**，即可得到大多数扫描仪易于读取且仍能适配标准标签的条形码。更改此值是实现 **自定义条形码尺寸** 的主要方式。

## 步骤 3：使用空心（轮廓）条而非实心条

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**此步骤重要原因：**  
`setFilledBars(false)` 告诉渲染器仅绘制条的轮廓，内部保持透明。这种样式常用于背景可能包含其他印刷信息的邮政条形码。

## 步骤 4：将条形码图像保存为 PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**此步骤重要原因：**  
选择 `BarCodeImageFormat.Png` 可获得无损图像，保留轮廓条的清晰边缘。文件路径可以是您有写入权限的任意目录；示例使用相对于项目根目录的 `output` 文件夹。

### 预期输出

运行程序后会生成类似下图的文件：

![Generated barcode image for Planet symbology](/images/planet-barcode.png){.align-center alt="生成的条形码图像，显示带空心轮廓条的 Planet 条形码"}

该图像显示了带有细薄空心条的 **Planet 条形码**，完全符合您设置的自定义尺寸。

## 常见变体和边缘情况

| 情况 | 调整 |
|-----------|------------|
| **不同的数据长度** | Planet 条形码支持最多 12 位数字字符。相应地更改构造函数的第二个参数。 |
| **更高分辨率** | 增加 X 维度（`setPixels`）或设置 `YDimension` 以控制条的高度。 |
| **彩色条形码** | 使用 `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` 更改条的颜色。 |
| **保存为 SVG** | 将 `BarCodeImageFormat.Png` 替换为 `BarCodeImageFormat.Svg` 以获得矢量输出。 |
| **在 Android 上运行** | 使用适用于 Android 的 Aspose.BarCode，并将文件系统路径替换为 `Context.getFilesDir()`。 |

> **注意：** 将 X 维度设置得过低（例如 1 像素）可能导致条形码在低分辨率打印机上无法读取。更改尺寸后请始终使用真实扫描仪进行测试。

## 完整源码，快速复制粘贴

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

将代码复制到名为 `PlanetBarcodeDemo.java` 的文件中，放置在 `src/main/java/com/example/barcode/` 目录下，运行 `mvn compile exec:java`，即可在 `output` 文件夹中看到 **生成条形码图像** 的结果。

## 结论

现在，您已经了解如何在 Java 中为 Planet 符号 **生成条形码图像**，如何使用 **自定义条形码尺寸** **创建 planet 条形码**，以及如何将实心条切换为空心条以获得更清晰的视觉效果。完整示例演示了从初始化生成器到保存 PNG 文件的所有必需 API 调用。

**下一步** – 探索其他条形码类型（`EncodeTypes.CODE_128`、`EncodeTypes.QR`），并尝试背景颜色、边距和 DPI 设置等额外图像选项。如果需要将条形码嵌入 PDF，可将此代码与 Aspose.PDF for Java 结合，实现无缝的端到端解决方案。

祝编码愉快！

## 接下来您应该学习什么？

以下教程涵盖与本指南演示的技术密切相关的主题。每个资源都包含完整的可运行代码示例和逐步说明，帮助您掌握更多 API 功能并在自己的项目中探索替代实现方案。

- [如何创建带实心和空心条的 planet 条形码](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [创建 planet 条形码图像 – 步骤指南](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [如何在 Java 中生成条形码：创建精确条形码图像](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}