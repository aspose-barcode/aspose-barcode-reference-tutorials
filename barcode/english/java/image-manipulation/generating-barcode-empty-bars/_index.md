---
title: How to Create Code128 Barcode with Empty Bars in Java
linktitle: Generating Barcode with Empty Bars
second_title: Aspose.BarCode Java API
description: Learn how to create Code128 barcode with empty bars in Java using Aspose.BarCode. This guide shows you how to generate barcode Java images quickly.
date: 2026-04-12
weight: 14
url: /java/image-manipulation/generating-barcode-empty-bars/
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Create Code128 Barcode with Empty Bars in Java

## Introduction

Integrating barcode generation into Java applications is a frequent requirement, whether you’re building inventory systems, ticketing platforms, or point‑of‑sale solutions. With **Aspose.BarCode for Java**, you can **create Code128 barcode** images in just a few lines of code. In this tutorial we’ll walk through the steps to **generate barcode Java** images that feature empty (non‑filled) bars, giving you full control over the visual style of the barcode.

## Quick Answers
- **Which library?** Aspose.BarCode for Java  
- **Primary use case?** Creating Code128 barcodes with empty bars for custom UI designs  
- **Prerequisites?** Java JDK 8+, Aspose.BarCode JAR, write access to a folder for the output image  
- **Typical implementation time?** 5‑10 minutes for a basic example  
- **Can I customize colors?** Yes – the API provides extensive styling options  

## What is a Code128 barcode?

Code128 is a high‑density linear barcode symbology that encodes the full ASCII character set. It’s widely used in logistics, shipping, and retail because it can represent alphanumeric data compactly. By default, Aspose.BarCode renders Code128 bars as solid rectangles; setting the **FilledBars** property to `false` turns them into empty (outline) bars, which is useful for stylistic branding.

## Why use Aspose.BarCode for Java?

- **Rich feature set** – supports over 50 barcode types, including QR, DataMatrix, and PDF417.  
- **No external dependencies** – a single JAR works on any Java runtime.  
- **Fine‑grained control** – you can adjust bar width, colors, fonts, and the `FilledBars` property.  
- **Cross‑platform** – works on Windows, Linux, and macOS without native libraries.

## Prerequisites

Before you start, make sure you have:

1. **Java Development Environment** – JDK 8 or later installed and `JAVA_HOME` configured.  
2. **Aspose.BarCode for Java** – download the latest JAR from the [download page](https://releases.aspose.com/barcode/java/).  
3. **Document Directory** – a folder on your computer where the generated barcode image will be saved.

## Import Packages

In your Java project, import the classes you’ll need to work with Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

These imports give you access to the barcode generator, image format enumeration, and exception handling.

## Step 1: Set Up the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the absolute path to the folder you created in the prerequisites. This is where the PNG file will be written.

## Step 2: Create Code128 Barcode Generator Instance

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Here we instantiate `BarcodeGenerator` with **CODE_128** symbology and the sample text `"TEXT"`. This is a **barcode generator Java example** that you can adapt to any string you need to encode.

## Step 3: Set FilledBars Property to False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

By setting `FilledBars` to `false`, the generated barcode will display empty bars instead of solid ones, achieving the visual effect we’re after.

## Step 4: Save the Barcode Image

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

The `save` method writes the barcode to the specified directory in PNG format. You can change `BarCodeImageFormat.PNG` to `JPG`, `BMP`, or `TIFF` if a different image type is required.

## Common Use Cases

- **Custom branding** – empty bars can be overlaid with background patterns or colors.  
- **Print‑ready assets** – generate high‑resolution PNGs for inclusion in invoices or shipping labels.  
- **Dynamic generation** – create barcodes on the fly in web services or desktop applications.

## Troubleshooting Tips

- **Invalid path** – ensure `dataDir` ends with a file separator (`/` or `\\`) or concatenate using `File.separator`.  
- **License required** – a trial works for evaluation, but a full license is needed for production.  
- **Unsupported characters** – Code128 supports the full ASCII set; avoid Unicode characters unless you switch to a different symbology.

## Conclusion

You’ve now learned how to **create Code128 barcode** images with empty bars using Aspose.BarCode for Java. This straightforward approach lets you generate customizable barcode graphics quickly, whether you’re building a desktop inventory tool or a cloud‑based API.

## FAQs

### Is Aspose.BarCode compatible with all Java development environments?
Yes, Aspose.BarCode is designed to seamlessly integrate with any Java IDE or build system, including Maven, Gradle, and plain JAR projects.

### Can I customize the appearance of the generated barcode?
Absolutely! Apart from `FilledBars`, you can modify colors, bar width, margins, and even add human‑readable text using the extensive API.

### Is a trial version available for Aspose.BarCode?
Yes, you can explore the capabilities of Aspose.BarCode by obtaining a free trial [here](https://releases.aspose.com/).

### How can I get support for Aspose.BarCode?
For any queries or assistance, visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13).

### Where can I find detailed documentation for Aspose.BarCode?
The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).

**Additional Questions**

**Q: How do I generate a barcode image in a different format, such as JPEG?**  
A: Change the second argument of `save` to `BarCodeImageFormat.JPEG`.

**Q: Can I generate multiple barcodes in a loop?**  
A: Yes – instantiate a new `BarcodeGenerator` inside your loop or reuse the same instance with a new `CodeText`.

---

**Last Updated:** 2026-04-12  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}