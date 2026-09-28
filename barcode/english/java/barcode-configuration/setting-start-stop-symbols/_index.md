---
date: 2026-08-28
description: Learn how to create barcode image java with Aspose Barcode Java, set
  CODABAR start and stop symbols, and generate PNG files without watermarks.
images:
- /java/barcode-configuration/setting-start-stop-symbols/og-image.png
keywords:
- create barcode image java
- barcode generation without watermark
- codabar start stop symbols
lastmod: 2026-08-28
linktitle: Setting Start and Stop Symbols
og_description: Create barcode image java using Aspose Barcode Java. This guide shows
  how to set CODABAR start/stop symbols and export PNG without watermarks.
og_image_alt: 'Aspose Barcode Java tutorial: create barcode image with start/stop
  symbols'
og_title: Create barcode image java – start/stop symbols guide
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to create barcode image java with Aspose Barcode Java, set
    CODABAR start and stop symbols, and generate PNG files without watermarks.
  headline: Aspose Barcode Java – Create barcode image with start/stop symbols
  type: TechArticle
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library creates barcode images in Java?
  - answer: Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.
    question: Can I customize start/stop symbols?
  - answer: CODABAR.
    question: Which barcode type is used in this example?
  - answer: A commercial license is required for non‑trial use.
    question: Do I need a license for production?
  - answer: PNG image saved to disk.
    question: What output format is generated?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode generation
- Aspose.BarCode
- Java barcode tutorial
title: Aspose Barcode Java – Create barcode image with start/stop symbols
url: /java/barcode-configuration/setting-start-stop-symbols/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Barcode Java – Create barcode image with start/stop symbols

## Introduction

In this comprehensive tutorial you’ll **create barcode image java** files with Aspose Barcode Java and learn **how to set start and stop symbols** for CODABAR barcodes. Whether you’re building a point‑of‑sale terminal, a warehouse‑management system, or any application that needs reliable barcode generation, customizing these symbols lets you meet legacy specifications while keeping the code clean and maintainable. We’ll walk through each step, explain why each setting matters, and show you how to produce a PNG image that contains no trial watermark.

## Quick answers
- **What library creates barcode images in Java?** Aspose.BarCode for Java.  
- **Can I customize start/stop symbols?** Yes, using `setCodabarStartSymbol` and `setCodabarStopSymbol`.  
- **Which barcode type is used in this example?** CODABAR.  
- **Do I need a license for production?** A commercial license is required for non‑trial use.  
- **What output format is generated?** PNG image saved to disk.

## What is Aspose Barcode Java?

Aspose Barcode Java is a **dependency‑free Java library that generates over 70 barcode symbologies**, from classic 1D codes such as CODABAR to modern 2D codes like QR and DataMatrix. It handles all low‑level encoding, so you can focus on business logic while guaranteeing compliance with industry standards.

## Why use Aspose Barcode Java for barcode generation without watermark?

Load your license first, and the library produces clean images—no “Aspose Evaluation” overlay. It also offers **fine‑grained control** (start/stop symbols, colors, sizes) and **cross‑platform compatibility** (any Java runtime, including Android). With support for **50+ output formats** and the ability to stream images directly to HTTP responses, it’s the go‑to choice for high‑throughput, production‑grade barcode creation.

## Prerequisites

Before we dive in, make sure you have:

1. **Java Development Kit (JDK)** – Install the latest JDK from [Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).  
2. **Aspose.BarCode for Java library** – Download it from the [download link](https://releases.aspose.com/barcode/java/).

Having these ready ensures you can **create barcode image java** without missing components.

## Import packages

The following imports give you access to the core classes needed for barcode generation:

The `CodabarSymbol` enum defines the allowed start/stop characters for CODABAR barcodes.  

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.CodabarSymbol;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Step‑by‑step guide

### How do you define the output folder for the barcode image?

Specify the folder where the PNG file will be written. Using `Paths.get` makes the code portable across Windows, macOS, and Linux.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### How do you create a barcode generator for CODABAR?

The `BarcodeGenerator` class creates a barcode image for a given symbology and data.  

Instantiate `BarcodeGenerator` with the CODABAR symbology and the data string you want to encode.

```java
// Create instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "12345678");
```

### How do you set the CODABAR start symbol?

`setCodabarStartSymbol` sets the character that marks the beginning of a CODABAR barcode.  

Call `setCodabarStartSymbol` and pass one of the supported characters (`A`, `B`, `C`, `D`). In this example we use `A`.

```java
// Set the Codabar start symbol to A
generator.getParameters().getBarcode().getCodabar().setCodabarStartSymbol(CodabarSymbol.A);
```

### How do you set the CODABAR stop symbol?

`setCodabarStopSymbol` sets the character that marks the end of a CODABAR barcode.  

Use `setCodabarStopSymbol` with the matching stop character—`D` in this case.

```java
// Set the Codabar stop symbol to D
generator.getParameters().getBarcode().getCodabar().setCodabarStopSymbol(CodabarSymbol.D);
```

### How do you save the generated barcode as a PNG file?

The `SaveFormat` enum specifies the file format for saving the barcode image.  

Invoke the `save` method, providing the full file name and the `SaveFormat.Png` enum value. The image is written without any watermark once a valid license is applied.

```java
// Save the image to disk in PNG format
generator.save(dataDir + "startAndStopSymbols.png");
```

## Common pitfalls & tips

The `License` class loads an Aspose license file to enable full‑feature mode.

- **Incorrect directory path** – Ensure `dataDir` ends with the appropriate file separator or build the path with `Paths.get`.  
- **Unsupported start/stop characters** – CODABAR only accepts `A`, `B`, `C`, or `D`. Supplying any other value throws an `IllegalArgumentException`.  
- **License not applied** – In trial mode the output contains a watermark. Load your license file with `License license = new License(); license.setLicense("Aspose.Total.Java.lic");` before creating the generator to avoid this.  
- **Large‑scale generation** – When generating thousands of barcodes, reuse a single `BarcodeGenerator` instance and only change the code text to reduce object‑creation overhead.

## Frequently asked questions

### Can I use Aspose.BarCode for Java in a commercial project?

Yes. Purchase a commercial license [purchase a commercial license](https://purchase.aspose.com/buy) to remove the evaluation watermark and obtain full technical support.

### Is there a free trial available?

Absolutely. Download the trial version [download the trial version](https://releases.aspose.com/) to evaluate all features before buying.

### How can I get support for Aspose.BarCode for Java?

Visit the Aspose.BarCode forum [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) for community help, or open a support ticket through your Aspose account portal.

### How do I obtain a temporary license for testing?

You can request a temporary 30‑day license [request a temporary 30‑day license](https://purchase.aspose.com/temporary-license/). This lets you run production‑like tests without a full purchase.

### What other barcode symbologies does Aspose.BarCode support?

The library supports **70+ symbologies**, including Code128, EAN‑13, QR, DataMatrix, PDF417, and many more. See the full list in the official documentation.

## Additional Q&A (AI‑friendly)

**Q:** What image formats can I export besides PNG?  
**A:** Aspose.BarCode supports PNG, JPEG, BMP, GIF, and TIFF. Choose the desired format by changing the `SaveFormat` enum value in the `save` call.

**Q:** Can I generate barcode images in memory without writing to disk?  
**A:** Yes. Call `generator.save(OutputStream)` to write directly to a stream—ideal for web APIs that return the image as an HTTP response.

**Q:** Does the library work on Android?  
**A:** The Java version runs on Android, but you must manually include the required dependencies (no Maven Central for Android). The core API remains identical.

## Conclusion

You’ve now learned how to **create barcode image java** and precisely **set start/stop symbols** for a CODABAR barcode using Aspose Barcode Java. This approach gives you the flexibility to satisfy legacy specifications while keeping your codebase clean and maintainable. Explore further customizations—such as altering colors, adding human‑readable text, or switching to other symbologies—by consulting the official API reference at [documentation](https://reference.aspose.com/barcode/java/).

---

**Last Updated:** 2026-08-28  
**Tested With:** Aspose.BarCode for Java 24.12  
**Author:** Aspose

## Related Tutorials

- [Validate Checksum and Create Codabar Barcode in Java with Aspose.BarCode](/barcode/java/checksum-and-validation/)
- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/java/barcode-basics/creating-image-exact-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}