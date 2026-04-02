---
title: Create data matrix barcode and set code text location in Java
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
description: Learn how to create data matrix barcode and how to set barcode text location in Java using Aspose.BarCode. Follow our step‑by‑step guide for full customization.
weight: 12
url: /java/text-and-styling/setting-code-text-location/
date: 2025-12-27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create data matrix barcode and set code text location in Java

## Introduction

Generating barcodes is a routine requirement for inventory, shipping, and many other Java‑based applications. With **Aspose.BarCode for Java** you can **create data matrix barcode** quickly and control every visual aspect, including where the human‑readable text appears. In this tutorial we’ll walk through the exact steps to **create data matrix barcode** and demonstrate **how to set barcode text** above the symbol so it matches your design specifications.

## Quick Answers
- **What library is used?** Aspose.BarCode for Java  
- **Which barcode type is demonstrated?** Data Matrix  
- **How do you position the code text?** Using `CodeLocation.ABOVE`  
- **Do you need a license for production?** Yes, a commercial license is required  
- **Can the code run on Java 8+?** Absolutely, it supports Java 8 and later  

## What is a Data Matrix barcode?
A Data Matrix barcode is a two‑dimensional (2‑D) symbol that stores large amounts of data in a compact square or rectangular pattern. It’s widely used for marking small items, electronics, and medical devices because it can encode up to 2,335 alphanumeric characters.

## Why set barcode text location?
Placing the human‑readable text **above**, **below**, or **beside** the barcode helps users quickly verify the encoded data without scanning. Adjusting the text location improves UI consistency and meets branding guidelines.

## Prerequisites

- Basic knowledge of Java programming.  
- Java Development Kit (JDK) installed.  
- An IDE such as Eclipse or IntelliJ IDEA.  
- Aspose.BarCode for Java library (download it from [here](https://releases.aspose.com/barcode/java/)).  

## Import Packages

First, import the essential Aspose.BarCode classes into your project:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

These imports give you access to the barcode generator and the enumeration that controls text placement.

## Step‑by‑step guide

### Step 1: Define Directory Paths
Specify where you want to read/write files. Replace the placeholders with actual paths on your machine.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Step 2: Create a BarcodeGenerator Instance
Instantiate `BarcodeGenerator` with the **Data Matrix** type and provide the code text you wish to encode.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Step 3: How to set barcode text location
Use the `CodeLocation` enumeration to move the human‑readable text. In this example we place it **above** the barcode.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Step 4: Save the Generated Barcode Image
Finally, write the barcode image to disk. The file will contain the Data Matrix symbol with the text positioned above it.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Common Issues and Solutions
- **Text not appearing:** Ensure you are using a version of Aspose.BarCode that supports `CodeLocation`.  
- **File path errors:** Verify that `dataDir` ends with a file separator (`/` or `\\`) appropriate for your OS.  
- **Unsupported characters:** Data Matrix can encode only a limited set of characters; avoid special symbols not in the ISO/IEC 16022 standard.

## Frequently Asked Questions (FAQs)

### Q: Can I customize the appearance of the generated barcode?
A: Yes, Aspose.BarCode provides extensive customization options, allowing you to control colors, margins, and font styles.

### Q: Is Aspose.BarCode compatible with Java 8 and later versions?
A: Absolutely, the library works with Java 8 and all subsequent releases.

### Q: How can I integrate Aspose.BarCode into my existing Java project?
A: Add the Aspose.BarCode JAR files to your project’s classpath, import the required packages, and you’re ready to generate barcodes.

### Q: Is there a trial version available for Aspose.BarCode?
A: Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [here](https://releases.aspose.com/).

### Q: Where can I seek help or support for Aspose.BarCode?
A: Visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) for community assistance and official support.

## Additional Frequently Asked Questions

**Q: Can I generate a barcode with text positioned below the symbol?**  
A: Yes, set `CodeLocation.BELOW` in the same `setLocation` method.

**Q: Does the library support other 2‑D barcodes like QR Code?**  
A: Absolutely, simply change `EncodeTypes.DATA_MATRIX` to `EncodeTypes.QR`.

**Q: How do I change the font size of the barcode text?**  
A: Use `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Conclusion

You’ve now learned how to **create data matrix barcode** in Java and precisely control **how to set barcode text** location using Aspose.BarCode. Experiment with other `CodeLocation` values and styling options to match your application’s design requirements.

---

**Last Updated:** 2025-12-27  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}