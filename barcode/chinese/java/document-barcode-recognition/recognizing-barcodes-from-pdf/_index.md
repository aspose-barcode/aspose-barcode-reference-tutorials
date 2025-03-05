---
title: 用Java识别PDF中的条形码
linktitle: 识别 PDF 中的条形码
second_title: Aspose.BarCode Java API
description: 了解如何使用 Aspose.BarCode 在 Java 中识别 PDF 中的条形码。带有代码示例的分步指南。提高您的数据管理效率！
type: docs
weight: 11
url: /zh/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
---

## 介绍

欢迎阅读我们使用 Aspose.BarCode for Java 识别 PDF 中的条形码的分步指南。条形码在数据管理和组织中发挥着至关重要的作用，借助 Aspose.BarCode，该过程变得无缝。在本教程中，我们将引导您完成整个过程，从设置必要的先决条件到在 PDF 文件中实现条形码识别代码。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

1.  Aspose.BarCode for Java 许可证：获取并设置 Aspose.BarCode for Java 的有效许可证。您可以从以下位置获取许可证[提出购买](https://purchase.aspose.com/buy).

2. Aspose.PDF 许可证：此外，设置 Aspose.PDF 许可证，这是处理 PDF 文件所必需的。您可以申请许可证[这里](https://purchase.aspose.com/temporary-license/).

3. 下载 Aspose.BarCode for Java：从 下载 Aspose.BarCode 库[这里](https://releases.aspose.com/barcode/java/).

现在您已经具备了必要的先决条件，让我们继续导入所需的包并开始我们的教程。

## 导入包

在您的 Java 项目中，包含 Aspose.BarCode 和 Aspose.PDF 包。以下是帮助您入门的示例代码片段：

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## 第 1 步：生成条形码并添加到 PDF

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## 第 2 步：创建 PDF 并添加条形码图像

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## 步骤 3：从 PDF 中提取图像

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## 步骤 4：从提取的图像中识别条形码

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

根据需要重复这些步骤，相应地调整文件名和路径。

## 结论

恭喜！您已成功学习如何使用 Aspose.BarCode for Java 识别 PDF 中的条形码。本教程旨在提供全面的指南，同时保持简单性和清晰度。请随意探索 Aspose.BarCode 提供的更多特性和功能[文档](https://reference.aspose.com/barcode/java/).

## 常见问题 (FAQ)

### 问：我可以在没有许可证的情况下使用 Aspose.BarCode for Java 吗？
虽然 Aspose.BarCode 无需许可证即可使用，但建议您获取完整功能并遵守许可条款。

### 问：如何获得 Aspose.BarCode for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 问：Aspose.BarCode 支持的条形码类型有限制吗？
Aspose.BarCode 支持多种条形码类型。请参阅文档以获取完整列表。

### 问：Aspose.BarCode for Java 有试用版吗？
是的，您可以从以下位置下载试用版[这里](https://releases.aspose.com/).

### 问：我可以在哪里寻求有关 Aspose.BarCode for Java 的支持或提出问题？
访问 Aspose.BarCode[论坛](https://forum.aspose.com/c/barcode/13)以寻求支持和讨论。
