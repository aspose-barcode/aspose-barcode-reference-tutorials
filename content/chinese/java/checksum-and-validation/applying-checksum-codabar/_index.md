---
title: 在 Java 中为 CodaBar 应用校验和
linktitle: 为 CodaBar 应用校验和
second_title: Aspose.BarCode Java API
description: 了解如何使用 Aspose.BarCode 在 Java 中应用 CodaBar 的校验和。使用此分步指南轻松生成和识别条形码。
type: docs
weight: 11
url: /zh/java/checksum-and-validation/applying-checksum-codabar/
---

## 介绍

欢迎来到这个关于使用 Aspose.BarCode 在 Java 中应用 CodaBar 校验和的分步教程。 Aspose.BarCode for Java 是一个功能强大的库，允许开发人员在 Java 应用程序中无缝生成和识别条形码。在本教程中，我们将重点关注为 CodaBar 条形码应用校验和的具体任务。

## 先决条件

在我们深入学习本教程之前，请确保您具备以下先决条件：

- 您的计算机上安装了 Java 开发工具包 (JDK)。
-  Aspose.BarCode for Java 库。您可以从以下位置下载：[这里](https://releases.aspose.com/barcode/java/).
- 对 Java 编程有基本的了解。

## 导入包

在您的 Java 项目中，确保导入必要的包以使用 Aspose.BarCode：

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 第 1 步：设置环境

首先创建一个新的 Java 项目并将 Aspose.BarCode 库包含在项目的依赖项中。使用所需的资源设置您的开发环境。

```java
//资源目录的路径。
String dataDir = "Your Document Directory";
```

## 第2步：生成CodaBar条码

现在，让我们生成一个启用校验和的 CodaBar 条形码。

```java
//实例化 BarcodeGenerator 对象
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

//将 EnableChecksum 属性设置为 yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

//设置 CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

//将图像保存到系统上
generator.save(dataDir + "Codabar_Mod10.png");
```

## 第三步：CodaBar条码识别

现在，我们来实现带有校验和的 CodaBar 条形码的识别部分。

```java
//初始化读取器对象
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

//将阅读器的 ChecksumValidation 属性设置为 On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    //获取校验和值
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

按照以下步骤使用 Aspose.BarCode 轻松应用 Java 中的 CodaBar 校验和。

## 结论

在本教程中，我们探索了如何使用 Aspose.BarCode 在 Java 中应用 CodaBar 条形码的校验和。该库提供了一种使用各种自定义选项生成和识别条形码的简单方法。

---

## 常见问题解答

### Aspose.BarCode 与所有 Java 版本兼容吗？
Aspose.BarCode 设计用于各种 Java 版本。确保检查文档以了解兼容性详细信息。

### 我可以自定义生成的条形码的外观吗？
是的，Aspose.BarCode 提供了广泛的自定义选项，允许您控制生成的条形码的外观。

### 临时许可证是否可用于测试目的？
是的，您可以从以下位置获取 Aspose.BarCode 的临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 我在哪里可以找到额外的支持和资源？
参观[Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)以获得社区支持和讨论。

### 有免费试用吗？
是的，您可以通过下载免费试用版来探索 Aspose.BarCode 的功能[这里](https://releases.aspose.com/).