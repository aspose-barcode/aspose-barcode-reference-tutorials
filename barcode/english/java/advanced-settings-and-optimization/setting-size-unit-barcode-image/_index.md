---
date: 2026-07-23
description: Create code128 barcode java with Aspose.BarCode. Generate barcode image
  java, set precise size units, and optimize for inventory systems or shipping labels.
images:
- /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/og-image.png
keywords:
- create code128 barcode java
- barcode for inventory system
- generate shipping label barcode
- generate barcode image java
lastmod: 2026-07-23
linktitle: Setting Size Unit for Barcode Image
og_description: Create code128 barcode java using Aspose.BarCode. Learn to generate
  barcode image java, control size units, and boost inventory or shipping label workflows.
og_image_alt: 'Guide: create code128 barcode java with size unit settings'
og_title: 'create code128 barcode java: Set Size Unit for Barcode Image'
schemas:
- author: Aspose
  dateModified: '2026-07-23'
  description: Create code128 barcode java with Aspose.BarCode. Generate barcode image
    java, set precise size units, and optimize for inventory systems or shipping labels.
  headline: 'create code128 barcode java: Set Size Unit for Barcode Image'
  type: TechArticle
- description: Create code128 barcode java with Aspose.BarCode. Generate barcode image
    java, set precise size units, and optimize for inventory systems or shipping labels.
  name: 'create code128 barcode java: Set Size Unit for Barcode Image'
  steps:
  - name: Define the Resource Directory
    text: First, specify the folder where the generated files will be written. This
      directory must exist and be writable by the Java process. Replace `"Your Document
      Directory"` with the absolute path where you want the barcode image saved. This
      folder will hold the generated PNG/JPEG files that you can later
  - name: Instantiate the Barcode Object
    text: '`EncodeTypes.CODE_128` specifies the CODE_128 barcode symbology. `BarcodeGenerator`
      is Aspose.BarCode''s core class that represents a barcode image in memory. Creating
      a `create code128 barcode java` instance is as simple as passing the `EncodeTypes.CODE_128`
      enum and the data string you wish to enco'
  - name: Set Bar Height (Size Unit)
    text: '`BarHeight` defines the vertical size of the bars. The `.setPoint()` method
      sets this height in points (1 point = 1/72 inch), giving you precise control
      over the final visual size. The `setPoint()` method defines the height in points.
      Adjust this value to meet your layout requirements—larger values '
  - name: Save the Image
    text: Calling `save()` writes the barcode to the folder you specified. The image
      format is inferred from the file extension; you can switch to PNG, BMP, or TIFF
      simply by changing the extension. The `save()` call writes the generated barcode
      to the folder you specified. The image format is inferred from t
  type: HowTo
- questions:
  - answer: Yes, the library supports both generation and recognition of a wide range
      of symbologies.
    question: Is Aspose.BarCode for Java suitable for both barcode generation and
      recognition?
  - answer: Absolutely. You can change colors, add captions, modify margins, and even
      embed logos using the extensive `Parameters` API.
    question: Can I customize the appearance of the generated barcode images?
  - answer: Visit [here](https://purchase.aspose.com/temporary-license/) to request
      a temporary license for evaluation.
    question: How can I obtain a temporary license for Aspose.BarCode for Java?
  - answer: The Aspose.BarCode community forum is the best place for help. Check the
      [forum](https://forum.aspose.com/c/barcode/13) for answers and to ask new questions.
    question: Where can I find support for Aspose.BarCode for Java?
  - answer: The library supports dozens of symbologies, including CODE_128, QR_CODE,
      UPC_A, DataMatrix, PDF417, and many more.
    question: What are the supported barcode symbologies in Aspose.BarCode for Java?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create code128 barcode java
- barcode for inventory system
- Aspose.BarCode
- Java barcode generation
title: 'create code128 barcode java: Set Size Unit for Barcode Image'
url: /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create code128 barcode java: Set Size Unit for Barcode Image

## Introduction

In this step‑by‑step tutorial you’ll **use Aspose.BarCode for Java** to **create code128 barcode java**, generate a barcode image java, and precisely control the size unit of the output. Whether you’re building a barcode for an inventory system, a shipping label generator, or any Java‑based application that needs reliable barcodes, Aspose.BarCode gives you full flexibility with just a few lines of code.

## Quick Answers
- **What library do I need?** Aspose.BarCode for Java (aspose barcode java).  
- **Which barcode type is covered?** CODE_128 (create code128 barcode java).  
- **How do I set the size unit?** Use the `BarHeight` property with `.setPoint()`.  
- **Can I generate barcode image java in other formats?** Yes – PNG, JPEG, BMP, etc.  
- **What are the prerequisites?** JDK installed, Aspose.BarCode library, and a Java IDE.

## What is **create code128 barcode java**?

`create code128 barcode java` means using the `BarcodeGenerator` class with the `EncodeTypes.CODE_128` enum to encode a data string into a CODE_128 symbology. This symbology supports the full ASCII set and offers high data density, making it ideal for barcode for inventory system and shipping label scenarios.

## Why use Aspose.BarCode to **generate barcode image java**?

Generating barcode image java with Aspose.BarCode lets you control dimensions, colors, and resolution while keeping the implementation pure‑Java. The library supports **50+ input and output formats** and can create multi‑hundred‑page barcode images without loading the whole file into memory, delivering millisecond‑level performance for batch label creation.

## Prerequisites

Before we start, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or later installed on your machine.  
2. **Aspose.BarCode for Java library** – download the latest JAR from the Aspose website (trial or licensed).  
3. **A Java IDE** – such as IntelliJ IDEA, Eclipse, or VS Code with Java extensions.  

## Import Namespaces

Add the required imports at the top of your Java class so you can access Aspose.BarCode’s API:

```java
import java.io.IOException;

import com.aspose.barcode.*;

import com.aspose.barcode.generation.BarcodeGenerator;
```

## How to **generate barcode image java** with Aspose.BarCode?

Load your `BarcodeGenerator`, configure size, and save the image – all in a clear, linear flow that can be wrapped in a loop for bulk processing. This direct‑answer paragraph tells you exactly what to do before we dive into the step‑by‑step details.

### Step 1: Define the Resource Directory

First, specify the folder where the generated files will be written. This directory must exist and be writable by the Java process.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the absolute path where you want the barcode image saved. This folder will hold the generated PNG/JPEG files that you can later embed in invoices, packing slips, or inventory reports.

### Step 2: Instantiate the Barcode Object

`EncodeTypes.CODE_128` specifies the CODE_128 barcode symbology.

`BarcodeGenerator` is Aspose.BarCode's core class that represents a barcode image in memory. Creating a `create code128 barcode java` instance is as simple as passing the `EncodeTypes.CODE_128` enum and the data string you wish to encode.

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Here we **create code128 barcode java** by passing `EncodeTypes.CODE_128` and the data string `"1234567"`.

### Step 3: Set Bar Height (Size Unit)

`BarHeight` defines the vertical size of the bars. The `.setPoint()` method sets this height in points (1 point = 1/72 inch), giving you precise control over the final visual size.

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

The `setPoint()` method defines the height in points. Adjust this value to meet your layout requirements—larger values produce taller bars, which is often needed for high‑resolution shipping labels.

### Step 4: Save the Image

Calling `save()` writes the barcode to the folder you specified. The image format is inferred from the file extension; you can switch to PNG, BMP, or TIFF simply by changing the extension.

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

The `save()` call writes the generated barcode to the folder you specified. The image format is inferred from the file extension (JPEG in this case). You can switch to PNG, BMP, or TIFF simply by changing the extension.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| **Image not created** | `dataDir` path is incorrect or missing write permissions. | Verify the folder exists and your application has write access. |
| **Barcode appears too small** | Bar height set in points is too low for the chosen DPI. | Increase the value passed to `setPoint()` or adjust image DPI via `bb.getParameters().getImage().setResolution()`. |
| **Unsupported characters** | CODE_128 supports only ASCII; you passed Unicode. | Use a different symbology (e.g., QR_CODE) for non‑ASCII data. |

## Frequently Asked Questions

**Q: Is Aspose.BarCode for Java suitable for both barcode generation and recognition?**  
A: Yes, the library supports both generation and recognition of a wide range of symbologies.

**Q: Can I customize the appearance of the generated barcode images?**  
A: Absolutely. You can change colors, add captions, modify margins, and even embed logos using the extensive `Parameters` API.

**Q: How can I obtain a temporary license for Aspose.BarCode for Java?**  
A: Visit [here](https://purchase.aspose.com/temporary-license/) to request a temporary license for evaluation.

**Q: Where can I find support for Aspose.BarCode for Java?**  
A: The Aspose.BarCode community forum is the best place for help. Check the [forum](https://forum.aspose.com/c/barcode/13) for answers and to ask new questions.

**Q: What are the supported barcode symbologies in Aspose.BarCode for Java?**  
A: The library supports dozens of symbologies, including CODE_128, QR_CODE, UPC_A, DataMatrix, PDF417, and many more.

### Additional Tips (Pro tip)

`getParameters().getImage().setResolution()` sets the image resolution in DPI.

- **Batch processing:** Wrap the steps above in a loop to generate hundreds of barcodes for bulk inventory uploads.  
- **Resolution control:** Use `bb.getParameters().getImage().setResolution(300)` to produce 300 dpi images, which are ideal for high‑quality print labels.  

---

**Last Updated:** 2026-07-23  
**Tested With:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [How to create small barcode labels in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/getting-minimum-barcode-size/)
- [Custom Barcode Size Java - Configure Exact Dimensions with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-custom-size-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}