---
title: 使用 Aspose.BarCode 在 Java 中的单个图像上生成多个条形码
linktitle: 在单个图像上生成多个条形码
second_title: Aspose.BarCode Java API
description: 使用 Aspose.BarCode for Java 在单个图像上轻松生成多个条形码。请按照我们的分步指南进行无缝集成。
weight: 19
url: /zh/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Java 中的单个图像上生成多个条形码

## 介绍

在 Java 编程的动态世界中，有效地创建和管理条形码对于各种应用程序至关重要。 Aspose.BarCode for Java 简化了这一过程，允许开发人员在单个图像上无缝生成多个条形码。本教程将指导您完成在 Java 环境中使用 Aspose.BarCode 实现此目的的步骤。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- 对 Java 编程有基本的了解。
- 您的系统上安装了 Java 开发工具包 (JDK)。
- 下载并设置了 Aspose.BarCode for Java 库。你可以下载它[这里](https://releases.aspose.com/barcode/java/).
- 集成开发环境 (IDE)，例如 Eclipse 或 IntelliJ IDEA。

## 导入命名空间

在您的 Java 项目中，导入必要的命名空间以访问 Aspose.BarCode 功能。在 Java 类的开头添加以下导入语句：

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

## 第1步：设置资源目录

定义保存生成的条形码的资源目录的路径。该目录对于组织和管理条形码图像至关重要。

```java
//资源目录的路径。
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## 第 2 步：创建条形码集合

初始化一个HashMap来存储条码数据。集合中的每个条目代表一个条形码及其各自的编码类型。

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## 第 3 步：生成条形码图像

迭代集合并使用 Aspose.BarCode 库生成条形码图像。将图像存储在 ArrayList 中以供进一步处理。

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## 第 4 步：创建组合图像

确定条形码图像的最大宽度和总高度。创建 BufferedImage 将各个条形码图像组合成单个输出图像。

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
## 第 5 步：保存结果

将最终组合图像保存到指定的文件位置。

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## 结论

恭喜！您已使用 Aspose.BarCode for Java 在单个图像上成功生成了多个条形码。这个强大的库简化了条形码处理，使其成为 Java 开发人员的宝贵工具。

## 常见问题解答

### 问题 1：我可以自定义生成图像中各个条形码的外观吗？

A1：是的，Aspose.BarCode 为条形码外观提供了广泛的自定义选项，允许您根据自己的喜好定制每个条形码的样式。

### Q2：Aspose.BarCode 是否兼容不同的条形码符号？

A2：当然！ Aspose.BarCode 支持多种符号系统，包括 CODE_39、DATA_MATRIX、QR、CODE_128、EAN_13 和 AZTEC，如本教程所示。

### Q3：如何将 Aspose.BarCode 集成到我的 Java 项目中？

 A3：只需从以下位置下载 Aspose.BarCode for Java 库：[这里](https://releases.aspose.com/barcode/java/)并按照文档中提供的安装说明进行操作。

### Q4：我可以将Aspose.BarCode用于商业应用吗？

 A4：是的，您可以从以下位置获取许可证[这里](https://purchase.aspose.com/buy)将 Aspose.BarCode 用于商业目的。

### Q5：Aspose.BarCode 有可用的试用选项吗？

 A5：当然！您可以通过获取免费试用许可证来探索 Aspose.BarCode 的功能[这里](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
