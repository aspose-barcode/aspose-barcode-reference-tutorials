---
title: Fetching and Recognizing Barcode in Java
linktitle: Fetching and Recognizing Barcode
second_title: Aspose.BarCode Java API
description: Integrate Aspose.BarCode for Java effortlessly - fetch and recognize barcodes from a database. Download now for a seamless barcode integration experience.
weight: 11
url: /java/symbology-and-format/fetching-recognizing-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Fetching and Recognizing Barcode in Java


## Introduction

Are you looking to integrate barcode recognition into your Java application effortlessly? Aspose.BarCode for Java provides a powerful and user-friendly solution for fetching and recognizing barcodes with ease. In this step-by-step guide, we'll walk you through the process of fetching and recognizing barcodes using Aspose.BarCode, ensuring a seamless integration into your Java project.

## Prerequisites

Before diving into the tutorial, make sure you have the following prerequisites in place:

- Basic understanding of Java programming.
- Aspose.BarCode for Java library installed. You can download it [here](https://releases.aspose.com/barcode/java/).
- Access to a database with barcode images stored in BLOB format.
- Java Development Kit (JDK) installed on your machine.

## Import Packages

To get started, import the necessary packages for your Java project. Ensure that the Aspose.BarCode library is included in your project dependencies.

```java

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## Step 1: Establish Database Connection

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

// Open a connection to the database
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## Step 2: Execute SQL Query

```java
// Create a statement to execute the SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## Step 3: Fetch and Create Images

```java
while (rs.next()) {
    // Read BLOB field and create an image from it
    String len1 = rs.getString("BarCodeImage");
    int len = len1.length();
    byte[] b = new byte[len];
    InputStream in = rs.getBinaryStream("BarCodeImage");

    int index = in.read(b, 0, len);
    OutputStream outImgBarCode = new FileOutputStream(strBarCodeImage);

    while (index != -1) {
        // Write bytes to file
        outImgBarCode.write(b, 0, index);
        // Read next bytes
        index = in.read(b, 0, len);
    }
    outImgBarCode.close();
```

## Step 4: Read Barcode from Image

```java
// Read the barcode from the image
BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_STANDARD);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}

nCount++;
}

System.out.println(nCount + " records found.");
con.close();
} catch (Exception ex) {
System.out.println(ex.getMessage());
}
```

By following these steps, you can seamlessly integrate Aspose.BarCode into your Java application, enabling efficient fetching and recognition of barcodes from a database.

## Conclusion

In conclusion, Aspose.BarCode for Java simplifies the process of fetching and recognizing barcodes, making it an ideal choice for developers seeking a reliable and efficient solution. By following this guide, you can effortlessly implement barcode recognition in your Java applications.

## Frequently Asked Questions

### Is Aspose.BarCode compatible with all barcode types?
Yes, Aspose.BarCode supports a wide range of barcode types, including CODE_39_STANDARD, QR Code, and more. Check the documentation for the full list.

### Can I use Aspose.BarCode with different databases?
Absolutely, Aspose.BarCode is designed to work with various databases. Ensure that you adapt the database connection details accordingly.

### How can I handle errors during barcode recognition?
Exception handling is crucial. Make sure to implement robust error handling to address any unforeseen issues during barcode recognition.

### Is Aspose.BarCode suitable for large-scale applications?
Yes, Aspose.BarCode is designed to handle large-scale applications, providing high performance and reliability.

### Are temporary licenses available for testing purposes?
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/) for testing and evaluation purposes.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
