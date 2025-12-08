---
title: Create code128 barcode java with Aspose.BarCode
linktitle: Setting Size Unit for Barcode Image
second_title: Aspose.BarCode Java API
description: Learn how to create code128 barcode java and generate barcode image java using Aspose.BarCode. Set precise size units for barcode images with simple, reusable code.
weight: 15
url: /java/advanced-settings-and-optimization/setting-size-unit-barcode-image/
date: 2025-12-08
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create code128 barcode java and set size unit with Aspose.BarCode

## Introduction

In this step‑by‑step guide you’ll **create code128 barcode java** code that generates a barcode image and lets you control the size unit of the output. Whether you’re building an inventory system, a shipping label generator, or any Java application that needs a reliable barcode, Aspose.BarCode for Java makes the process straightforward and highly customizable.

## Quick Answers
- **What library do I need?** Aspose.BarCode for Java.
- **Which barcode type is covered?** CODE_128 (create code128 barcode java).
- **How do I set the size unit?** Use the `BarHeight` property with `.setPoint()`.
- **Can I generate barcode image java in other formats?** Yes – PNG, JPEG, BMP, etc.
- **What are the prerequisites?** JDK installed, Aspose.BarCode library, and a Java IDE.

## What is **create code128 barcode java**?

Creating a CODE_128 barcode in Java means instantiating the `BarcodeGenerator` class with the `EncodeTypes.CODE_128` enum and providing the data string you want to encode. This symbology is widely used in logistics because it supports the full ASCII character set and offers high data density.

## Why use Aspose.BarCode to **generate barcode image java**?

- **Full control over dimensions** – you can set bar height, module size, and image resolution.
- **No external dependencies** – pure Java, works on any platform that supports the JDK.
- **Rich customization** – colors, fonts, margins, and even QR codes are supported.
- **High performance** – generates images in milliseconds, suitable for batch processing.

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

Below is the complete workflow. Each step is explained in plain language, and the original code blocks are kept exactly as they were.

### Step 1: Define the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the absolute path where you want the barcode image saved.

### Step 2: Instantiate the Barcode Object

```java
// Instantiate barcode object, Set the symbology type to code128 and Set the
// Code text for the barcode
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "1234567");
```

Here we **create code128 barcode java** by passing `EncodeTypes.CODE_128` and the data string `"1234567"`.

### Step 3: Set Bar Height (Size Unit)

```java
// Set the bar height to 3 points
bb.getParameters().getBarcode().getBarHeight().setPoint(3.0f);
```

The `setPoint()` method defines the height in points (1 point = 1/72 inch). Adjust this value to meet your layout requirements.

### Step 4: Save the Image

```java
// Save the image
bb.save(dataDir + "barcode-size-unit.jpg");
```

The `save()` call writes the generated barcode to the folder you specified. The image format is inferred from the file extension (JPEG in this case).

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

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.BarCode for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}