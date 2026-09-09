---
date: 2026-04-08
description: 学习如何使用 Aspose.BarCode 在 Java 中从 PDF 读取条形码。本指南还展示了如何在 Java 中生成条形码图像以及从
  PDF 中提取图像。
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: 从 PDF 识别条形码
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 从 PDF 读取条形码
url: /zh/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 从 PDF 中读取条形码（Java）

## 介绍

欢迎阅读本分步指南，了解如何使用 Aspose.BarCode **在 Java 中从 PDF 读取条形码**。条形码是实现数据捕获自动化的关键，借助 Aspose.BarCode，您可以轻松在 PDF 文档中检测条形码。本教程将带您完成从设置许可证、生成条形码图像（Java）、将其添加到 PDF、从 PDF 提取图像（Java）到最终读取条形码的全部过程。

## 快速答案
- **我需要哪个库？** Aspose.BarCode for Java（加上用于 PDF 处理的 Aspose.PDF）。  
- **我可以在 Java 中生成条形码图像吗？** 可以——`BarcodeGenerator` 类可以创建 PNG/JPEG 图像。  
- **如何从 PDF 中提取图像？** 使用 Aspose.PDF 的 `PdfExtractor`。  
- **演示的条形码类型是什么？** CODE‑39（标准）。  
- **我需要许可证吗？** 生产环境需要有效的 Aspose.BarCode 和 Aspose.PDF 许可证。

## 为什么使用 Aspose.BarCode for Java？
- **高精度**——支持数十种符号，并在低分辨率图像上也能工作。  
- **无外部依赖**——纯 Java，无本地库。  
- **完整的 PDF 集成**——结合 Aspose.PDF 可直接在 PDF 文件中读取或嵌入条形码。

## 前置条件

在深入代码之前，请确保您已拥有：

1. **Aspose.BarCode for Java 许可证**——从 [Aspose Purchase](https://purchase.aspose.com/buy) 获取。  
2. **Aspose.PDF 许可证**——用于 PDF 操作；您可以在[此处](https://purchase.aspose.com/temporary-license/)申请许可证。  
3. **Aspose.BarCode 库**——从[此处](https://releases.aspose.com/barcode/java/)下载最新的 JAR。  

现在您已经具备必要的前置条件，让我们导入所需的包并开始编码。

## 导入包

在您的 Java 项目中，添加 Aspose.BarCode 和 Aspose.PDF 的导入语句。以下代码块与原教程保持一致：

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

## 步骤 1：生成条形码图像（Java）

首先，我们创建一个条形码图像，稍后将其嵌入 PDF 中。这演示了 **generate barcode image java** 功能。

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## 步骤 2：创建 PDF 并添加条形码图像

接下来，我们构建一个新的 PDF 文档，并插入刚生成的条形码图像。

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## 步骤 3：从 PDF 中提取图像（Java）

PDF 准备好后，我们需要将嵌入的图像提取出来，以便读取条形码。这使用了 **extract images from pdf java**。

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## 步骤 4：识别提取图像中的条形码

最后，我们将每个提取的图像传递给 `BarCodeReader`，以获取编码文本。

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

根据需要重复这些步骤，调整文件名和路径以匹配您的项目结构。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|-------|--------|-----|
| **未检测到条形码** | 图像质量太低或条形码太小。 | 保存时提高图像分辨率（`builder.save(..., BarCodeImageFormat.JPEG, 300)`）。 |
| **`PdfExtractor` 抛出异常** | 未找到 PDF 文件或路径不正确。 | 确认 `strPdfDoc` 指向现有文件且应用程序具有读取权限。 |
| **许可证未应用** | Aspose 组件以试用模式运行，输出受限。 | 在程序启动时加载许可证文件：`new License().setLicense("Aspose.BarCode.lic");`，Aspose.PDF 亦同。 |

## 常见问题 (FAQs)

### Q: 我可以在没有许可证的情况下使用 Aspose.BarCode for Java 吗？
虽然可以在没有许可证的情况下使用 Aspose.BarCode，但建议获取许可证以获得完整功能并遵守许可条款。

### Q: 如何获取 Aspose.BarCode for Java 的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### Q: Aspose.BarCode 支持的条形码类型是否有限制？
Aspose.BarCode 支持多种条形码类型。请参阅文档获取完整列表。

### Q: 是否有 Aspose.BarCode for Java 的试用版可供下载？
是的，您可以从[此处](https://releases.aspose.com/)下载试用版。

### Q: 我可以在哪里获取 Aspose.BarCode for Java 的支持或提问？
请访问 Aspose.BarCode [论坛](https://forum.aspose.com/c/barcode/13)获取支持和讨论。

## 结论

祝贺您！您已经学习了如何使用 Aspose.BarCode **在 Java 中读取 PDF 中的条形码**，以及如何 **在 Java 中生成条形码图像**，并 **在 Java 中从 PDF 提取图像** 以进行后续处理。欢迎探索批处理、不同条形码符号的处理或与其他 Aspose 产品的集成等更多功能。欲了解更深入的细节，请查阅官方[文档](https://reference.aspose.com/barcode/java/)。

---

**最后更新:** 2026-04-08  
**测试环境:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}