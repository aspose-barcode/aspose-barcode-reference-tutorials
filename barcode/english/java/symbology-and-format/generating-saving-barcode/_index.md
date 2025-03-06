---
title: Generating and Saving Barcode in Java
linktitle: Generating and Saving Barcode
second_title: Aspose.BarCode Java API
description: Generate and save barcodes effortlessly in Java with Aspose.BarCode. Integrate seamlessly, customize appearance, and enjoy extensive barcode support.
weight: 12
url: /java/symbology-and-format/generating-saving-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generating and Saving Barcode in Java


## Introduction

Are you looking to seamlessly integrate barcode generation into your Java application? Look no further! In this step-by-step guide, we'll walk you through the process of using Aspose.BarCode for Java to generate and save barcodes efficiently. Aspose.BarCode is a powerful Java library that simplifies barcode creation and manipulation, providing you with the tools needed to enhance your applications with barcode functionality.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites in place:

- Java Development Environment: Make sure you have a Java development environment set up on your machine.

- Aspose.BarCode Library: Download and install the Aspose.BarCode library. You can find the download link [here](https://releases.aspose.com/barcode/java/).

- MySQL Database: Set up a MySQL database where you intend to store barcode-related information.

- Database Connectivity: Ensure you have the necessary credentials and connectivity to interact with the MySQL database.

## Import Packages

In your Java project, import the required packages for Aspose.BarCode and MySQL connectivity.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Step 1: Generate and Save Barcode

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

Explanation: This step involves creating a barcode with Aspose.BarCode, setting the code text, and saving the barcode image to a specified location.

## Step 2: Insert Record in MySQL Database

```java
// Step 2 - Insert a new record in MySQL DB
Connection con = null;

// Open connection
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Prepare statement
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Set product number and product name
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 3rd column is for barcode image. DB type is BLOB
// For saving the image, we need to create a stream from the image file
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Execute the statement
pre.executeUpdate();
System.out.println("Insertion successful.");

// Close connection
pre.close();
con.close();
```

Explanation: This step involves connecting to a MySQL database and inserting a new record with product information and the associated barcode image.

## Conclusion

Congratulations! You have successfully integrated Aspose.BarCode for Java into your application to generate and save barcodes. This powerful library simplifies the process, making barcode implementation a breeze.

## Frequently Asked Questions

### Q: Is Aspose.BarCode compatible with different barcode types?
A: Yes, Aspose.BarCode supports various barcode types, including CODE_39_STANDARD, CODE_128, QR, and more.

### Q: Can I customize the appearance of generated barcodes?
A: Absolutely! Aspose.BarCode provides extensive customization options for barcode appearance, allowing you to tailor it to your specific needs.

### Q: Is there a free trial available for Aspose.BarCode?
A: Yes, you can access a free trial [here](https://releases.aspose.com/).

### Q: Where can I find detailed documentation for Aspose.BarCode?
A: Refer to the documentation [here](https://reference.aspose.com/barcode/java/).

### Q: How do I get support for Aspose.BarCode?
A: Visit the support forum [here](https://forum.aspose.com/c/barcode/13) for any assistance or queries.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
