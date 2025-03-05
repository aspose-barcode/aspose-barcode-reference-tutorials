---
title: 用 Java 生成和保存条形码
linktitle: 生成并保存条形码
second_title: Aspose.BarCode Java API
description: 使用 Aspose.BarCode 在 Java 中轻松生成并保存条形码。无缝集成、自定义外观并享受广泛的条形码支持。
type: docs
weight: 12
url: /zh/java/symbology-and-format/generating-saving-barcode/
---

## 介绍

您是否希望将条形码生成无缝集成到您的 Java 应用程序中？别再犹豫了！在本分步指南中，我们将引导您完成使用 Aspose.BarCode for Java 高效生成和保存条形码的过程。 Aspose.BarCode 是一个功能强大的 Java 库，可简化条形码的创建和操作，为您提供通过条形码功能增强应用程序所需的工具。

## 先决条件

在深入学习本教程之前，请确保您具备以下先决条件：

- Java 开发环境：确保您的计算机上设置了 Java 开发环境。

- Aspose.BarCode 库：下载并安装 Aspose.BarCode 库。你可以找到下载链接[这里](https://releases.aspose.com/barcode/java/).

- MySQL 数据库：设置一个 MySQL 数据库，用于存储条形码相关信息。

- 数据库连接：确保您拥有与 MySQL 数据库交互所需的凭据和连接。

## 导入包

在您的 Java 项目中，导入 Aspose.BarCode 和 MySQL 连接所需的包。

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## 第 1 步：生成并保存条形码

```java
//第 1 步 - 生成条形码并临时保存在文件中
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

说明：此步骤涉及使用Aspose.BarCode创建条形码、设置代码文本以及将条形码图像保存到指定位置。

## 步骤2：在MySQL数据库中插入记录

```java
//第 2 步 - 在 MySQL DB 中插入一条新记录
Connection con = null;

//打开连接
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

//准备声明
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

//设置产品编号和产品名称
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

//第三列用于条形码图像。数据库类型是BLOB
//为了保存图像，我们需要从图像文件创建一个流
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

//执行语句
pre.executeUpdate();
System.out.println("Insertion successful.");

//紧密连接
pre.close();
con.close();
```

说明：此步骤涉及连接到 MySQL 数据库并插入包含产品信息和关联条形码图像的新记录。

## 结论

恭喜！您已成功将 Aspose.BarCode for Java 集成到您的应用程序中以生成和保存条形码。这个强大的库简化了流程，使条形码的实施变得轻而易举。

## 经常问的问题

### 问：Aspose.BarCode 是否兼容不同的条形码类型？
答：是的，Aspose.BarCode 支持各种条形码类型，包括 CODE_39_STANDARD、CODE_128、QR 等。

### 问：我可以自定义生成的条形码的外观吗？
答：当然！ Aspose.BarCode 为条形码外观提供了广泛的自定义选项，允许您根据您的特定需求进行定制。

### 问：Aspose.BarCode 是否有免费试用版？
答：是的，您可以免费试用[这里](https://releases.aspose.com/).

### 问：哪里可以找到 Aspose.BarCode 的详细文档？
答：参考文档[这里](https://reference.aspose.com/barcode/java/).

### 问：如何获得对 Aspose.BarCode 的支持？
答：访问支持论坛[这里](https://forum.aspose.com/c/barcode/13)如有任何帮助或疑问。