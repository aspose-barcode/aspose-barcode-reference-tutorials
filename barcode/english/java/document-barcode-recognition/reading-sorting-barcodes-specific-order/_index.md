---
title: How to Read Barcodes in Specific Order Using Java
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
description: Learn how to read barcodes and sort them in specific order using Aspose.BarCode for Java. This step‑by‑step guide shows how to use Aspose, Java barcode reader, and decode Code128 barcode.
weight: 10
url: /java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
date: 2026-04-08
keywords:
- how to read barcodes
- java barcode reader
- aspose barcode java
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read Barcodes in Specific Order Using Java


## Introduction

If you need to **how to read barcodes** and then arrange them in a particular sequence, Aspose.BarCode for Java gives you a clean, high‑performance way to do it. In many Java applications—inventory systems, shipping solutions, or point‑of‑sale terminals—reading multiple barcodes and sorting them by their textual value is a frequent requirement. This tutorial walks you through the complete process, from setting up the environment to displaying the sorted results, so you can integrate barcode handling quickly and confidently.

## Quick Answers
- **What library handles barcode reading?** Aspose.BarCode for Java  
- **Which barcode type is used in the example?** CODE_128  
- **Do I need a license for development?** A temporary license works for testing; a full license is required for production.  
- **Can I sort by other criteria?** Yes—modify the comparator to sort by location, confidence, etc.  
- **What Java version is required?** Java 8 or later (any JDK that supports the Aspose library).

## What is “how to read barcodes” in Java?

Reading barcodes means decoding the visual pattern into its original data string. Aspose.BarCode provides a `BarCodeReader` class that abstracts the low‑level image processing, letting you focus on business logic such as sorting or validation.

## Why use Aspose.BarCode for Java?

- **Robust decoding** – supports over 50 symbologies, including Code 128, QR, DataMatrix, and more.  
- **High accuracy** – optimized algorithms reduce false reads, even on low‑resolution images.  
- **Simple API** – a few lines of code get you from image to text.  
- **Cross‑platform** – works on any Java runtime, from desktop to server environments.

## Prerequisites

Before diving into the code, ensure you have the following prerequisites:

- Java Development Kit (JDK): Aspose.BarCode for Java requires a functioning JDK. You can download the latest version [here](https://www.oracle.com/java/technologies/javase-downloads.html).

- Aspose.BarCode Library: Make sure you have the Aspose.BarCode library. You can obtain it from the [download link](https://releases.aspose.com/barcode/java/).

## Import Packages

Begin by importing the necessary packages into your Java project. These packages provide the essential classes and methods for working with barcodes.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Now, let's break down the code into a step‑by‑step guide:

## Step 1: Set up the Resource Directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Replace `"Your Document Directory"` with the actual path to your document directory.

## Step 2: Specify Barcode Image Path and Initialize Reader

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Step 3: Read Barcodes and Store Results

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Step 4: Define Comparator for Sorting

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Step 5: Sort Barcodes

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Step 6: Display Sorted Barcodes

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Common Pitfalls & Tips

- **Incorrect image path** – double‑check that `dataDir` ends with a file separator (`/` or `\\`) so the full path resolves correctly.  
- **Unsupported barcode type** – if you need to decode a different symbology, change `DecodeType.CODE_128` to the appropriate enum value (e.g., `DecodeType.QR`).  
- **Sorting by numeric value** – the default comparator sorts lexicographically. For numeric sorting, parse `CodeText` to an integer inside the comparator.  
- **Resource cleanup** – `BarCodeReader` implements `Closeable`. In production code, wrap it in a try‑with‑resources block to ensure the underlying stream is released.

## Frequently Asked Questions

### Q: Where can I find the Aspose.BarCode for Java documentation?
The documentation is available [here](https://reference.aspose.com/barcode/java/).

### Q: How can I download Aspose.BarCode for Java?
You can download it from the [download link](https://releases.aspose.com/barcode/java/).

### Q: Is there a free trial available?
Yes, you can explore a free trial [here](https://releases.aspose.com/).

### Q: How do I get temporary licensing information?
Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).

### Q: Where can I seek support or ask questions?
Visit the support forum [here](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-04-08  
**Tested With:** Aspose.BarCode 24.10 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}