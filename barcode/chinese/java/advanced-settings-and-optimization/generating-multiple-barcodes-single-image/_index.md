---
date: 2026-04-03
description: 学习如何使用 Aspose.BarCode for Java 创建 QR 码并在单个图像上生成多个条形码。包括设置、代码和故障排除。
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: 在单张图像上生成多个条形码
second_title: Aspose.BarCode Java API
title: 创建 QR 码 Java – 在同一图像上生成多个条形码
url: /zh/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建 QR Code Java – 在单个图像上生成多个条形码

## 介绍

在本教程中，您将学习 **how to create QR code java** 并使用 **Aspose.BarCode for Java** 将多种不同的条形码类型合并到单个图像中。无论您需要紧凑的 QR 标签、产品条形码，还是 2‑D 与线性符号的混合，本指南都会逐步引导您完成每一步——从项目设置到保存最终的合并图像——让您能够立即在 Java 应用程序中集成条形码生成。

## 快速答案
- **What library should I use?** Aspose.BarCode for Java 提供最完整的符号集。  
- **Can I generate different barcode types together?** 是的，您可以在同一画布上混合 CODE_39、QR、AZTEC 等。  
- **Do I need a license for development?** 免费试用可用于测试；生产环境需要商业许可证。  
- **Which Java version is supported?** 完全兼容 Java 8 及更高版本。  
- **Is the output format configurable?** 您可以将合并图像导出为 PNG、JPEG、BMP 等格式。  

## 什么是 create QR code java？

在 Java 中创建 QR 码意味着将文本字符串转换为可被智能手机或条码阅读器扫描的二维矩阵。**Aspose.BarCode for Java** 负责编码和渲染，让您专注于业务逻辑，而无需处理底层图像处理。

## 为什么在 generate barcodes java 中使用 Aspose.BarCode Java？

- **Broad symbology support** – 从经典线性码到现代 2‑D 矩阵。  
- **High‑quality rendering** – 抗锯齿输出，适用于任何设备。  
- **Simple API** – 只需少量方法调用即可创建、定制和合并条码。  
- **No external dependencies** – 所有内容均在 JVM 上运行，无需本地库。  

## 先决条件

在深入教程之前，请确保您具备以下先决条件：

- 对 Java 编程的基本了解。  
- 已在系统上安装 Java Development Kit (JDK)。  
- 已下载并设置 Aspose.BarCode for Java 库。您可以在[此处](https://releases.aspose.com/barcode/java/)下载。  
- 集成开发环境 (IDE)，如 Eclipse 或 IntelliJ IDEA。  

## 导入命名空间

在您的 Java 项目中，导入必要的命名空间以访问 Aspose.BarCode 功能。请在 Java 类的开头添加以下 import 语句：

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

## 步骤 1：设置资源目录

定义生成的条码将保存的资源目录路径。该目录对于组织和管理条码图像至关重要。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 步骤 2：创建条码集合

初始化一个 `HashMap` 来存储条码数据。集合中的每个条目代表一个具有相应编码类型的条码。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 步骤 3：生成条码图像

遍历集合，使用 Aspose.BarCode 库生成条码图像。将图像存储在 `ArrayList` 中以便后续处理。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 步骤 4：创建合并图像

确定条码图像的最大宽度和总高度。创建一个 `BufferedImage` 将各个条码图像合并为单个输出图像。

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

## 步骤 5：保存结果

将最终的合并图像保存到指定的文件位置。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 生成多个条码的常见用例

- **Packaging labels** – 在单个标签上合并产品、批次和运输代码。  
- **Event tickets** – 为不同的扫描站点嵌入 QR、Data Matrix 和 Code 128 标识符。  
- **Inventory management** – 将 SKU、RFID 标签数据和序列号一起显示，以便快速审计。  

## 故障排除与技巧

- **Image size issues** – 调整 `offset` 变量以增大或减小条码之间的间距。  
- **Unsupported symbology** – 验证您的 Aspose.BarCode 版本是否支持所需的条码类型。  
- **Performance** – 如果在循环中生成大量图像，请复用单个 `Graphics` 对象。  

## 常见问题

**Q1: 我可以自定义生成图像中各个条码的外观吗？**  
A1: 是的，Aspose.BarCode 提供了广泛的条码外观自定义选项，您可以根据需求定制每个条码的样式。

**Q2: Aspose.BarCode 是否兼容不同的条码符号？**  
A2: 当然！Aspose.BarCode 支持广泛的符号，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 和 AZTEC，如本教程所示。

**Q3: 我如何将 Aspose.BarCode 集成到我的 Java 项目中？**  
A3: 只需从[此处](https://releases.aspose.com/barcode/java/)下载 Aspose.BarCode for Java 库，并按照文档中提供的安装说明进行操作。

**Q4: 我可以在商业应用中使用 Aspose.BarCode 吗？**  
A4: 是的，您可以从[此处](https://purchase.aspose.com/buy)获取许可证，以在商业用途下使用 Aspose.BarCode。

**Q5: Aspose.BarCode 有试用选项吗？**  
A5: 当然！您可以通过获取免费试用许可证[此处](https://releases.aspose.com/)来体验 Aspose.BarCode 的功能。

**Q6: 我如何生成用于打印的高分辨率 QR 码？**  
A6: 在调用 `generateBarCodeImage()` 之前，在 `BarcodeGenerator` 上设置所需的 DPI，然后将图像保存为无损格式（如 PNG）。

**Q7: 如果合并图像出现截断该怎么办？**  
A7: 确认 `offset` 和画布尺寸计算正确考虑了所有条码的高度；增大画布高度或减小单个条码尺寸通常可以解决截断问题。

---

**最后更新:** 2026-04-03  
**测试环境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}