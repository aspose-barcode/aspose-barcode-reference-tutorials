---
date: 2025-12-18
description: 学习如何创建 Codabar 条形码图像，并查看使用 Aspose.BarCode 的 Java 条形码读取器示例。通过本分步指南轻松生成和识别条形码。
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: 如何在 Java 中创建带校验码的 Codabar 条形码图像
url: /zh/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中创建带校验和的 Codabar 条形码图像

## 介绍

在本教程中，您将学习如何使用 Aspose.BarCode 在 Java 中**创建带校验和的 Codabar 条形码图像**。我们将演示生成 CodaBar 条形码、启用校验和，然后使用**java 条形码读取示例**读取它。完成后，您将拥有一段可直接放入任何 Java 项目的即用代码片段。

## 快速答案
- **校验和的作用是什么？** 它在扫描时验证条形码数据的完整性。  
- **需要哪个库？** Aspose.BarCode for Java。  
- **开发是否需要许可证？** 临时许可证可用于测试；生产环境需要正式许可证。  
- **我可以自定义条形码外观吗？** 可以——颜色、尺寸和字体可通过生成器参数进行更改。  
- **这兼容所有 Java 版本吗？** 该库支持 Java 8 及更高版本。

## 什么是 CodaBar 条形码？

CodaBar 是一种线性（1 维）符号，广泛用于图书馆、血库和零售业。它编码数字数据和少量特殊字符，非常适合用于简单的机器可读标签。添加校验和（Mod 10）可提升读取准确性，尤其是在低质量打印时。

## 为什么使用 Aspose.BarCode for Java？

Aspose.BarCode 提供了一个**java 条形码读取示例**，抽象了条形码生成和识别的底层细节。它提供：

* 对校验和模式的完整控制。  
* 与 Java IDE 的无缝集成。  
* 丰富的文档和支持。  

## 前提条件

在开始之前，请确保您已拥有：

- 已在机器上安装 Java Development Kit（JDK）。  
- Aspose.BarCode for Java 库。您可以从[此处](https://releases.aspose.com/barcode/java/)下载。  
- 对 Java 编程有基本了解。  

## 导入包

在您的 Java 项目中，导入使用 Aspose.BarCode 所需的类：

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

## 步骤指南

### 步骤 1：设置环境

创建一个新的 Java 项目并将 Aspose.BarCode JAR 添加到构建路径。定义一个文件夹用于保存生成的图像。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### 步骤 2：生成带校验和的 CodaBar 条形码图像

实例化 `BarcodeGenerator`，启用校验和，选择 Mod 10 模式，并保存图像。

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### 步骤 3：Java 条形码读取示例 – 识别条形码

现在读取条形码，开启校验和验证以确保数据正确。

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

运行代码后将输出解码文本、符号类型以及计算得到的校验和，确认条形码已正确生成并通过验证。

## 常见问题与解决方案

| 问题 | 解决方案 |
|------|----------|
| **校验和验证失败** | 确保 `EnableChecksum` 设置为 `YES`，并且 `CodabarChecksumMode` 与生成时使用的模式（Mod 10）匹配。 |
| **文件未找到错误** | 确保 `dataDir` 指向已存在的文件夹，并且在读取之前已将生成的图像（`Codabar_Mod10.png`）保存到该文件夹中。 |
| **不受支持的 Java 版本** | 使用 Java 8 或更高版本；较旧的版本可能缺少所需的 API。 |

## 常见问题

**问：Aspose.BarCode 是否兼容所有 Java 版本？**  
答：Aspose.BarCode 设计用于 Java 8 及更高版本。请查阅官方文档获取详细兼容性信息。

**问：我可以自定义生成的条形码外观吗？**  
答：可以，您可以通过生成器的参数 API 修改颜色、字体和图像格式。

**问：是否提供用于测试的临时许可证？**  
答：是的，您可以从[此处](https://purchase.aspose.com/temporary-license/)获取 Aspose.BarCode 的临时许可证。

**问：在哪里可以找到更多支持和资源？**  
答：请访问 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13)获取社区支持和讨论。

**问：是否提供免费试用？**  
答：是的，您可以从[此处](https://releases.aspose.com/)下载免费试用版，体验 Aspose.BarCode 的功能。

---

**最后更新：** 2025-12-18  
**测试环境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}