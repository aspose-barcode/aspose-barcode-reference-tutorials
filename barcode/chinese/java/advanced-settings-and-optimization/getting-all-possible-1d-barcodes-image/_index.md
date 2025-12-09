---
date: 2025-11-29
description: 学习如何使用 Aspose.BarCode 在 Java 中读取 1D 条形码——利用强大的 Java 条形码库快速解码图像中的条形码。
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 读取一维条码
url: /zh/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 在 Java 中读取 1D 条码

## Introduction

在本实践指南中，您将学习如何使用强大的 **Aspose.BarCode** 库在 **Java** 中读取 **1D 条码**。无论是扫描产品标签、库存标签，还是图像中的任何线性条码，本教程将一步步指导您——从环境搭建到提取图像中所有可能的条码。完成后，您只需几行 Java 代码即可从图像文件中解码条码。

## Quick Answers
- **Aspose.BarCode 的作用是什么？** 它提供了一个功能完整的 **Java** 条码库，能够生成和解码 1D/2D 条码。  
- **我可以从同一图像读取多个条码吗？** 可以——`BarCodeReader.readBarCodes()` 方法返回所有检测到的符号。  
- **开发时需要许可证吗？** 临时许可证可用于测试；生产环境需要商业许可证。  
- **支持哪些 Java 版本？** Java 8 及以上（推荐 JDK 11）。  
- **该库足够快用于实时扫描吗？** 绝对可以——它针对高性能批处理进行了优化。

## What is “read 1d barcodes java”?

在 **Java** 中读取 1D 条码是指使用 **barcode library for Java** 分析图像，定位线性条码模式，并返回编码文本以及符号类型、方向等元数据。Aspose.BarCode 抽象了繁重的图像处理工作，让您专注于业务逻辑。

## Why choose Aspose.BarCode for decoding barcodes from image?

- **广泛的符号支持** —— 超过 50 种 1D 和 2D 类型。  
- **精准检测** —— 即使在低对比度或旋转的条码下也能工作。  
- **简洁的 API** —— 几个方法调用即可获取所有结果。  
- **无外部依赖** —— 纯 Java，易于嵌入任何项目。  

## Prerequisites

在开始编写代码之前，请确保您具备以下条件：

- **Java 开发工具包 (JDK)** —— 8 版或更高。请从官方 [Oracle JDK 页面](https://www.oracle.com/java/technologies/javase-downloads.html) 下载。  
- **Aspose.BarCode for Java** —— 从 [Aspose release page](https://releases.aspose.com/barcode/java/) 获取最新 JAR。  

环境准备就绪后，让我们开始编码。

## Import Namespaces

添加所需的 `import` 语句，以便编译器能够找到 Aspose 的类。

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Step 1: Initialize the BarCodeReader Object

创建一个指向图像文件的 `BarCodeReader` 实例。`DecodeType` 参数告诉引擎要查找哪些符号；以 `CODE_128` 为例可覆盖许多常见的 1D 条码。

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **技巧提示：** 如果想扫描*所有*受支持的 1D 类型，请传入 `DecodeType.ALL_1D` 而不是单一符号。

## Step 2: Read All Possible Barcodes

遍历 `readBarCodes()` 返回的集合。对每个 `BarCodeResult`，我们打印解码文本、符号名称、检测角度以及条码区域的四个角坐标。

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

循环会自动处理所有找到的条码，无需重复调用读取器。循环结束后，`iCount` 保存检测到的条码总数。

## Common Issues & How to Fix Them

| 症状 | 可能原因 | 解决方案 |
|---------|--------------|----------|
| 未返回条码 | 图像过于模糊或对比度低 | 在将图像提供给读取器之前进行预处理（提升对比度、二值化）。 |
| 报告的符号类型错误 | 使用了错误的 `DecodeType` | 使用 `DecodeType.ALL_1D` 让引擎自动检测任何 1D 类型。 |
| 角度值不正确 | 图像已旋转 | API 已返回旋转角度；如有需要可将图像旋转回正。 |

## Frequently Asked Questions

**问：Aspose.BarCode for Java 适用于商业项目吗？**  
答：是的。商业许可证消除所有评估限制，并授予完整的再分发权利。

**问：我可以在不购买许可证的情况下测试该库吗？**  
答：当然可以。可从 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于开发和测试。

**问：在哪里可以找到完整的 API 参考文档？**  
答：完整文档可在[here](https://reference.aspose.com/barcode/java/)查看。

**问：如果遇到问题，如何获取帮助？**  
答：请在 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 发帖，社区和 Aspose 工程师会提供帮助。

**问：是否有免费试用下载？**  
答：有——您可以从 [Aspose releases page](https://releases.aspose.com/) 下载试用版。

## Conclusion

现在，您已经学会如何使用 Aspose.BarCode 在 **Java** 中**读取 1D 条码**，这是一款强大的 **barcode library for Java**，能够简便可靠地解码图像文件中的条码。将此代码片段集成到自己的应用中，可实现库存扫描、票据验证或任何图像中出现线性条码的场景自动化。

---

**最后更新：** 2025-11-29  
**测试环境：** Aspose.BarCode 24.11 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}