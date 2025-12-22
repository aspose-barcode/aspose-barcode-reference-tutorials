---
title: How to Create Barcode Image with Empty Bars in Java
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
description: Learn how to create barcode image with empty bars using Aspose.BarCode for Java. This step‑by‑step barcode generation example helps you generate barcode java quickly.
date: 2025-12-22
weight: 14
url: /java/image-manipulation/generating-barcode-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Create Barcode Image with Empty Bars in Java

## Introduction

In modern Java applications, the ability to **create barcode image** files on the fly is a valuable feature for inventory management, ticketing systems, and many other business scenarios. Aspose.BarCode for Java provides a powerful, easy‑to‑use API that lets you generate high‑quality barcodes in just a few lines of code. In this tutorial we’ll walk through a **step‑by‑step barcode** creation process that produces a barcode with empty (unfilled) bars, perfect for designs that require a hollow look.

## Quick Answers
- **What does “empty bars” mean?** Bars are rendered without the default solid fill, giving a hollow appearance.  
- **Which barcode type is used?** Code 128 (a widely supported linear symbology).  
- **Do I need a license to try it?** A free trial is available; a license is required for production use.  
- **What output formats are supported?** PNG, JPEG, BMP, GIF, TIFF, and more.  
- **Is this compatible with all Java versions?** Yes, the library works with Java 8 and later.

## What is create barcode image?
Creating a barcode image means converting a string of data into a visual representation that scanners can read. The resulting image can be saved as PNG, JPEG, or other common formats and embedded in PDFs, printed on labels, or displayed on a UI.

## Why use Aspose.BarCode Java library?
- **Rich feature set** – supports over 50 barcode symbologies, including Code 128, QR, DataMatrix, and more.  
- **Fine‑grained control** – properties such as `FilledBars`, colors, margins, and image size are easily configurable.  
- **No external dependencies** – a single JAR file handles everything, simplifying deployment.  
- **Comprehensive documentation** – examples, API reference, and forums help you get up to speed quickly.

## Prerequisites

Before we embark on the barcode generation journey, make sure you have the following prerequisites in place:

1. **Java Development Environment** – Ensure you have Java 8+ installed and a compatible IDE or build tool.  
2. **Aspose.BarCode for Java Library** – Download and install the Aspose.BarCode for Java library from the [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – Create a directory on your system to store the generated barcode image.

## Import Packages

In your Java project, import the necessary packages for working with Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to Create Barcode Image with Empty Bars

### Step 1: Set Up the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the actual path where you want to save the output file.

### Step 2: Create Barcode Generator Instance (Code128 Barcode Java)

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Here, we’re using the **Code 128** symbology—one of the most popular linear barcodes—making this a classic **code128 barcode java** example.

### Step 3: Set FilledBars Property to False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Setting `FilledBars` to `false` tells Aspose.BarCode to render the bars as empty (hollow) shapes instead of solid blocks.

### Step 4: Save the Barcode Image

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

The image is saved in PNG format, but you can change the `BarCodeImageFormat` enum to produce JPEG, BMP, or other supported types.

Repeat these steps in your Java application to effortlessly **create barcode image** files with empty bars using Aspose.BarCode for Java.

## Conclusion

In conclusion, this tutorial has walked you through a **step‑by‑step barcode** creation process that shows how to **create barcode image** files with empty bars in Java. With its intuitive API and extensive customization options, Aspose.BarCode simplifies barcode integration, making it a valuable asset for developers who need a reliable **java barcode library**.

## FAQs

### Is Aspose.BarCode compatible with all Java development environments?
Yes, Aspose.BarCode is designed to seamlessly integrate with various Java development environments.

### Can I customize the appearance of the generated barcode?
Absolutely! Aspose.BarCode provides numerous options for customization, allowing you to tailor the barcode to your specific needs.

### Is a trial version available for Aspose.BarCode?
Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [here](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode?
For any queries or assistance, visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Where can I find detailed documentation for Aspose.BarCode?
The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-22  
**Tested With:** Aspose.BarCode Java 24.11 (latest)  
**Author:** Aspose  

---