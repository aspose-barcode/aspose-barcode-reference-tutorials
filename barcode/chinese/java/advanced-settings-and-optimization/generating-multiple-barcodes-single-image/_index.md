---
date: 2026-10-19
description: 了解如何使用 Aspose.BarCode for Java 创建 QR code java 并在单个图像上生成多个条形码。包括设置、代码和故障排除。
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: 在单个图像上生成多个条形码
og_description: 使用 Aspose.BarCode for Java 创建 QR code java 并将多种条形码类型合并到单个图像中。按照分步指南操作，查看代码片段，并学习故障排除技巧。
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: 创建 QR code java – 在单个图像上生成多个条形码
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: 创建 QR code java – 在单个图像上生成多个条形码
url: /zh/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 QR 码 java – 在单个图像上生成多个条形码

## 介绍

在本教程中，您将学习**如何创建 QR 码 java**，并使用**Aspose.BarCode for Java**将多种不同的条形码类型合并到同一个画布上。无论您需要紧凑的 QR 标签、产品条形码，还是 2‑D 与线性符号的混合，本指南都会一步步带您完成——从项目设置到保存最终的合成图像——让您立即在 Java 应用程序中集成条形码生成。

## 快速答案
- **应该使用哪个库？** Aspose.BarCode for Java 提供最完整的符号集。  
- **可以一起生成不同类型的条形码吗？** 可以，您可以在同一画布上混合 CODE_39、QR、AZTEC 等。  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需要商业许可证。  
- **支持哪个 Java 版本？** 完全兼容 Java 8 及更高版本。  
- **输出格式可以配置吗？** 您可以将合成图像导出为 PNG、JPEG、BMP 或 TIFF。

## 什么是 create QR code java？

`create QR code java` 指的是将文本字符串转换为可被智能手机或条形码阅读器扫描的二维矩阵的过程。Aspose.BarCode for Java 执行编码和渲染，让您专注于业务逻辑，而无需处理像素级图像。

## 为什么使用 Aspose.BarCode Java 来生成条形码 java？

Aspose.BarCode 支持**超过 50 种条形码符号**——包括 QR、Data Matrix、Code 128、AZTEC 和传统线性码——是最通用的 Java 条形码库。它能够以最高 1200 dpi 渲染**抗锯齿图像**，确保在屏幕和打印时都能获得清晰的扫描效果。该 API 只需 JVM 即可运行，并提供流畅的配置模型，几行代码即可自定义尺寸、颜色、边距和纠错级别。

## 前置条件

在开始之前，请确保您已经：

- 扎实掌握 Java 基础。  
- 安装并在 PATH 中配置了 JDK 8 或更高版本。  
- 获取 Aspose.BarCode for Java JAR（从官方 Aspose.BarCode for Java 下载页面下载）。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE 编辑并运行示例。  

## 导入命名空间

导入语句将 Aspose.BarCode 的类（如 `BarcodeGenerator`、`EncodeTypes` 和 `BarCodeImageFormat`）引入作用域，便于在代码中直接使用而无需写全限定名。  
`BarcodeGenerator` 是用于配置和生成条形码图像的主要类。  
`EncodeTypes` 是 Aspose.BarCode 中的枚举，指定要生成的条形码符号。  
`BarCodeImageFormat` 定义生成条形码的输出图像格式。

## 步骤 1：设置资源目录

资源目录是文件系统中用于写入所有生成条形码图像的文件夹。一次性定义可以保持项目结构清晰，并便于清理旧文件。

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步骤 2：创建条形码集合

`HashMap<String, EncodeTypes>` 用于存储每个条形码的数据字符串以及对应的符号类型。`HashMap` 是 Java 的键值映射集合。该集合驱动后续的生成循环。`EncodeTypes` 是一个枚举，指定要生成的条形码类型。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 步骤 3：生成条形码图像

生成循环遍历 `HashMap`，为每个条目创建 `BarcodeGenerator`，并调用 `generateBarCodeImage()` 获取 `BufferedImage`。`generateBarCodeImage()` 会生成包含渲染条形码的 `BufferedImage`。`BufferedImage` 是 Java 中表示内存中图像的类。所有图像随后被添加到 `ArrayList<BufferedImage>` 中，以便后续合成。`ArrayList` 是 Java 中可动态扩展的列表实现。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 步骤 4：创建合成图像

首先，算法计算所有条形码图像的**最大宽度**以及垂直堆叠所需的**总高度**（可选间距）。随后创建相应大小的 `BufferedImage`，并使用 `Graphics2D` 对象将每个条形码绘制到画布上。`Graphics2D` 是 Java 提供的 2D 渲染类，用于绘制形状和图像。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 步骤 5：保存结果

最后，使用 `ImageIO.write` 将合成图像写入磁盘，格式为您指定的 PNG、JPEG、BMP 或 TIFF。`ImageIO.write` 将 `BufferedImage` 按指定格式写入文件。文件路径相对于前面定义的资源目录。

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## 生成多个条形码的常见用例

- **包装标签** – 在单个标签上合并产品码、批次码和运输码，以降低打印成本。  
- **活动票据** – 为场馆内不同扫描点嵌入 QR、Data Matrix 和 Code 128 标识。  
- **库存管理** – 同时显示 SKU、RFID 标签数据和序列号，实现快速审计和可追溯性。

## 故障排除与技巧

- **图像尺寸问题** – 调整 `offset` 变量以增减条形码之间的间距。  
- **不支持的符号** – 确认您使用的 Aspose.BarCode 版本支持所需的条形码类型；新版会加入更多 2‑D 符号。  
- **性能** – 在循环中生成大量图像时，复用同一个 `Graphics2D` 对象以减少对象分配开销。  

## 常见问题

**问：我可以自定义生成图像中各条形码的外观吗？**  
答：可以。使用 `BarcodeGenerator` 的属性，如 `setBarColor`、`setBackgroundColor` 和 `setXDimension`，在将条形码加入画布前独立设置样式。

**问：Aspose.BarCode 是否兼容多种条形码符号？**  
答：完全兼容。库支持 50 多种符号，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 和 AZTEC，正如本教程所示。

**问：如何将 Aspose.BarCode 集成到我的 Java 项目中？**  
答：从 Aspose.BarCode for Java 库下载页面获取 JAR，加入项目的 classpath，然后按“导入命名空间”章节的示例导入所需类。

**问：我可以在商业应用中使用 Aspose.BarCode 吗？**  
答：可以。请在 Aspose.BarCode 许可证购买页面购买许可证，以去除试用限制并获得完整的生产支持。

**问：Aspose.BarCode 有试用选项吗？**  
答：有。您可以从 Aspose.BarCode 免费试用下载页面获取免费试用许可证，获得完整 API 访问权限用于评估。

**问：如何生成用于打印的高分辨率 QR 码？**  
答：在调用 `generateBarCodeImage()` 之前，使用 `setResolutionDpi` 属性设置分辨率，然后以 PNG 等无损格式保存结果。

**问：如果合成图像出现截断该怎么办？**  
答：检查 `offset` 和画布尺寸计算是否正确考虑了所有条形码的高度；增大画布高度或减小单个条形码尺寸通常可以解决截断问题。

---

**最后更新：** 2026-10-19  
**测试环境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  








```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 相关教程

- [如何使用 Aspose 创建条形码图像 Java – 添加边框](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [如何生成条形码 Java：使用 Aspose.BarCode 保存到流](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [如何生成条形码 Java 并使用 Aspose 打印条形码](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}