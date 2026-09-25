---
date: 2026-08-12
description: Learn how to improve barcode readability by customizing the CODE_128
  wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
  Follow our step‑by‑step barcode generation tutorial Java.
images:
- /java/barcode-configuration/configuring-wide-narrow-ratio/og-image.png
keywords:
- improve barcode readability
- customize code128 barcode
- barcode generation tutorial java
- step by step barcode
lastmod: 2026-08-12
linktitle: Configuring wide‑narrow ratio
og_description: Learn how to improve barcode readability by customizing the CODE_128
  wide‑narrow ratio in Java with Aspose.BarCode. This step‑by‑step tutorial shows
  you how to generate PNG barcodes quickly.
og_image_alt: Guide to creating CODE_128 barcode with custom wide‑narrow ratio in
  Java
og_title: Improve barcode readability with CODE_128 wide‑narrow ratio (58 chars)
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  headline: Improve barcode readability with CODE_128 wide‑narrow ratio
  type: TechArticle
- description: Learn how to improve barcode readability by customizing the CODE_128
    wide‑narrow ratio in Java using Aspose.BarCode, and generate PNG images efficiently.
    Follow our step‑by‑step barcode generation tutorial Java.
  name: Improve barcode readability with CODE_128 wide‑narrow ratio
  steps:
  - name: set document directory
    text: Make sure the directory exists and you have write permissions; this is where
      the **saved barcode image** file will be placed.
  - name: instantiate barcode object
    text: The `BarcodeGenerator` class creates barcode images based on the specified
      symbology and encoding options. Here we **create a CODE_128 barcode** by passing
      `EncodeTypes.CODE_128` to the constructor.
  - name: set wide‑narrow ratio
    text: '`setWideNarrowRatio` sets the proportion between wide and narrow bars for
      the generated barcode. The `setWideNarrowRatio` method lets you fine‑tune the
      visual spacing. A value of `3.0f` means the wide bar is three times the width
      of a narrow bar, which falls within the optimal 2.0‑3.0 range for most'
  - name: save image to disk
    text: Calling `save` will **generate a barcode image** and store it as a PNG file,
      completing the **save barcode image** step.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and
      other Java environments.
    question: Can I use Aspose.BarCode with other Java frameworks?
  - answer: Change the symbology type in the `BarcodeGenerator` constructor, for example
      `EncodeTypes.QR` for QR codes.
    question: How can I generate barcodes with different symbologies?
  - answer: Yes, you can access the free trial version on the [Aspose.BarCode free
      trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.BarCode?
  - answer: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).
    question: Where can I find detailed documentation for Aspose.BarCode?
  - answer: Visit the Aspose.BarCode community forum at [Aspose.BarCode community
      forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.
    question: How to get support for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode readability
- Aspose.BarCode
- Java barcode tutorial
title: Improve barcode readability with CODE_128 wide‑narrow ratio
url: /java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Improve barcode readability with CODE_128 wide‑narrow ratio

## Introduction

If you need to **improve barcode readability** for inventory labels, shipping tags, or any application that uses CODE_128, adjusting the wide‑narrow ratio is the most effective technique. In this tutorial we’ll walk through a **step‑by‑step barcode** creation process using Aspose.BarCode for Java, showing you how to configure the ratio, **generate barcode PNG** images, and **save the barcode image** to disk. You’ll also see why the ratio matters for scanner performance and how to fine‑tune it for your specific printing environment.

## Quick answers
- **What is the wide‑narrow ratio?** It controls the relative width of the wide bars versus the narrow bars in a barcode.  
- **Which symbology supports ratio adjustment?** Most 1‑D symbologies, including CODE_128, allow you to set a custom ratio.  
- **Do I need a license?** A free trial is available, but a commercial license is required for production use.  
- **Can I generate a barcode image in PNG format?** Yes—use `generator.save(...)` to generate barcode PNG images.  
- **Is the code compatible with Java 8+?** Absolutely; Aspose.BarCode works with all modern Java versions.

## Prerequisites

Before we dive into the code, ensure you have the following:

- Java Development Kit (JDK) installed on your machine.  
- Aspose.BarCode for Java library. Download it from the [download link](https://releases.aspose.com/barcode/java/).

## Import packages

To start, import the essential Aspose.BarCode class into your project.  
`BarcodeGenerator` is the core class used to generate barcode images with specified symbology and options.  

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## What is the wide‑narrow ratio and why adjust it?

The wide‑narrow ratio defines how many times wider a “wide” bar is compared to a “narrow” bar. Adjusting this ratio improves scanner compatibility (most scanners read best with ratios between 2.0 and 3.0), compensates for printer DPI limitations, and lets you match a brand’s visual style without sacrificing reliability.

## How to improve barcode readability by creating CODE_128 barcode with wide‑narrow ratio in Java

Begin by adding the Aspose.BarCode library to your Java project, then create a `BarcodeGenerator` instance specifying `EncodeTypes.CODE_128`. Configure the generator with the desired wide‑narrow ratio using `setWideNarrowRatio`, optionally adjust other visual settings, and finally call `save` to write the barcode as a PNG file. This concise workflow ensures consistent barcode quality and improves scanner read rates across diverse devices.

### Step 1: set document directory

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Make sure the directory exists and you have write permissions; this is where the **saved barcode image** file will be placed.

### Step 2: instantiate barcode object

The `BarcodeGenerator` class creates barcode images based on the specified symbology and encoding options.  
```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

Here we **create a CODE_128 barcode** by passing `EncodeTypes.CODE_128` to the constructor.

### Step 3: set wide‑narrow ratio

`setWideNarrowRatio` sets the proportion between wide and narrow bars for the generated barcode.  
```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

The `setWideNarrowRatio` method lets you fine‑tune the visual spacing. A value of `3.0f` means the wide bar is three times the width of a narrow bar, which falls within the optimal 2.0‑3.0 range for most scanners.

### Step 4: save image to disk

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

Calling `save` will **generate a barcode image** and store it as a PNG file, completing the **save barcode image** step.

## Why adjust the wide‑narrow ratio?

Adjusting the wide‑narrow ratio improves scanner compatibility because most industrial scanners read best when the ratio falls between 2.0 and 3.0. It also enhances print quality by compensating for printer resolutions of 150–300 dpi, reducing bar distortion. Additionally, the ratio lets companies align barcode aesthetics with branding guidelines while maintaining reliable scan performance.

## Common issues and solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Barcode looks distorted | Ratio too high/low for the printer | Adjust the value passed to `setWideNarrowRatio` (e.g., 2.0‑2.5). |
| File not created | Invalid `dataDir` path or insufficient permissions | Verify the directory path and ensure the application has write access. |
| Scanner cannot read barcode | Ratio outside recommended range for the symbology | Use standard ratios (2.0‑3.0) or test with the target scanner. |

## Frequently asked questions

**Q: Can I use Aspose.BarCode with other Java frameworks?**  
A: Yes, Aspose.BarCode works seamlessly with Spring, Java EE, Android, and other Java environments.

**Q: How can I generate barcodes with different symbologies?**  
A: Change the symbology type in the `BarcodeGenerator` constructor, for example `EncodeTypes.QR` for QR codes.

**Q: Is there a trial version available for Aspose.BarCode?**  
A: Yes, you can access the free trial version on the [Aspose.BarCode free trial page](https://releases.aspose.com/).

**Q: Where can I find detailed documentation for Aspose.BarCode?**  
A: Refer to the documentation on the [Aspose.BarCode Java API documentation](https://reference.aspose.com/barcode/java/).

**Q: How to get support for Aspose.BarCode?**  
A: Visit the Aspose.BarCode community forum at [Aspose.BarCode community forum](https://forum.aspose.com/c/barcode/13) for support and community discussions.

---

**Last Updated:** 2026-08-12  
**Tested With:** Aspose.BarCode for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)
- [Detect Barcode Orientation in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}