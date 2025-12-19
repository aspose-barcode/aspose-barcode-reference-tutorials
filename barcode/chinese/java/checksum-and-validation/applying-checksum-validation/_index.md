---
date: 2025-12-19
description: 了解如何在 Java 中使用 Aspose.BarCode 禁用校验和验证。本分步指南将向您展示如何读取条码、关闭校验和以及确保可靠的数据处理。
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: 如何在 Java 中禁用校验和验证
url: /zh/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中禁用校验和验证

在现代库存和物流应用中，**如何禁用校验和**可能是读取不包含校验位的旧版条码的关键。Aspose.BarCode for Java 让关闭校验和验证变得轻而易举，同时仍能提取编码数据。本教程将带您完成整个过程——从项目设置到读取不进行校验和验证的 ONE‑CODE 条码。

## 快速答案
- **禁用校验和会有什么作用？** 它告诉读取器忽略校验和字段，从而能够处理没有有效校验和的条码。  
- **何时应该禁用校验和？** 当处理遗留系统或省略或损坏校验和的非标准条码时。  
- **哪个类控制校验和验证？** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **禁用校验和安全吗？** 仅在您信任条码来源时安全；否则，验证有助于捕获错误。  
- **这会影响其他条码类型吗？** 此设置仅适用于当前的 `BarCodeReader` 实例。

## 什么是校验和验证？
校验和验证是一种数据完整性检查，它根据条码内容计算一个小值并将其与嵌入的校验和进行比较。如果两者不匹配，条码将被视为不可读取。禁用此检查会让 Aspose.BarCode 跳过比较。

## 为什么在 Aspose.BarCode 中禁用校验和？
- **遗留支持：** 旧式扫描仪常生成不含校验和的条码。  
- **性能：** 跳过计算可以加快批量读取速度。  
- **灵活性：** 您可以根据每个读取器实例决定是否强制验证。

## 先决条件
- **Java 开发工具包 (JDK)：** 确保已安装最新的 JDK。  
- **Aspose.BarCode 库：** 从官方站点[此处](https://releases.aspose.com/barcode/java/)下载库。  

## 导入包
在您的 Java 项目中，导入必要的 Aspose.BarCode 类以进行条码识别。

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 分步指南

### 步骤 1：设置项目
创建一个新的 Java 项目（使用您选择的 IDE），并将 Aspose.BarCode JAR 添加到项目的类路径中。

### 步骤 2：初始化 `BarCodeReader`
加载包含您想要读取的 ONE‑CODE 条码的图像。

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### 步骤 3：如何禁用校验和
通过将属性设置为 `OFF`，告诉读取器忽略校验和验证。

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### 步骤 4：读取条码
遍历结果并打印解码后的文本和符号类型。

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**结果：** 即使原始图像缺少有效校验和，仍会显示条码文本。

## 常见问题与技巧
- **文件路径错误：** 确认 `dataDir` 指向正确的文件夹；测试时使用绝对路径。  
- **不支持的条码类型：** 确保 `DecodeType` 与您读取的条码匹配。  
- **性能：** 在大批量时禁用校验和可以提升吞吐量，但对关键数据应始终重新启用。

## 常见问题

### Aspose.BarCode 是否兼容不同的条码类型？
是的，Aspose.BarCode 支持广泛的条码符号体系，从 QR 和 DataMatrix 到传统的线性码。

### 我可以将 Aspose.BarCode 用于商业用途吗？
当然可以。针对需要生产就绪功能的企业提供商业许可证。

### 如何获取 Aspose.BarCode 的支持？
访问 [Aspose.BarCode 论坛](https://forum.aspose.com/c/barcode/13) 与社区交流并获取产品团队的帮助。

### 是否提供免费试用？
是的，您可以通过下载 [免费试用版](https://releases.aspose.com/) 来体验完整功能。

### 在哪里可以找到详细文档？
请参考全面的 [文档](https://reference.aspose.com/barcode/java/) 获取 API 细节、代码示例和最佳实践。

---

**最后更新：** 2025-12-19  
**测试环境：** Aspose.BarCode for Java（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}