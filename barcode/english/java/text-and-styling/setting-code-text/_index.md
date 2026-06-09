---
title: "Create Code128 Barcode Java – Set Code Text using Aspose.BarCode"
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
description: "Learn how to create Code128 barcode Java using Aspose.BarCode. This step‑by‑step guide shows how to generate barcode Java, set custom text, adjust bar width, and save the image."
weight: 13
url: /java/text-and-styling/setting-code-text/
date: 2026-06-09
keywords:
  - create code128 barcode java
  - how to generate barcode java
  - java barcode generator example
schemas:
- type: TechArticle
  headline: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  dateModified: '2026-06-09'
  author: Aspose
- type: HowTo
  name: Create Code128 Barcode Java – Set Code Text using Aspose.BarCode
  description: Learn how to create Code128 barcode Java using Aspose.BarCode. This
    step‑by‑step guide shows how to generate barcode Java, set custom text, adjust
    bar width, and save the image.
  steps:
  - name: Create an Instance of `BarcodeGenerator`
    text: 'The `BarcodeGenerator` constructor takes two arguments: the barcode symbology
      (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.'
  - name: Adjust Barcode Width for Custom Barcode Text
    text: Set the `XDimension` property (bar width) to control how wide each bar appears.
      In this example we use `0.5` mm, a size that balances readability and label
      space for most applications.
  - name: Save the Barcode Image
    text: Call the `save` method, specifying the output path and image format (JPEG,
      PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the
      project’s document folder.
- type: FAQPage
  questions:
  - question: What library should I use?
    answer: Aspose.BarCode for Java.
  - question: Which barcode type is demonstrated?
    answer: CODE_128.
  - question: How do I set custom barcode text?
    answer: Use the `BarcodeGenerator` constructor or the `setCodeText` method.
  - question: Can I change the bar width?
    answer: Yes—adjust `XDimension` (bar width) in millimetres.
  - question: Do I need a license for production?
    answer: A commercial license is required for non‑trial deployments.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create Code128 Barcode Java – Set Code Text using Aspose.BarCode

In this tutorial, you'll learn how to **create Code128 barcode Java** using the Aspose.BarCode Java library. Whether you're building an inventory system, a document‑tracking solution, or any application that needs barcodes, we’ll walk you through every step—from instantiating a **Code128** barcode to customizing the code text and fine‑tuning the bar width. By the end, you’ll have a ready‑to‑use image that you can embed wherever you need it.

## Quick Answers
- **What library should I use?** Aspose.BarCode for Java.  
- **Which barcode type is demonstrated?** CODE_128.  
- **How do I set custom barcode text?** Use the `BarcodeGenerator` constructor or the `setCodeText` method.  
- **Can I change the bar width?** Yes—adjust `XDimension` (bar width) in millimetres.  
- **Do I need a license for production?** A commercial license is required for non‑trial deployments.

## How to create a Code128 barcode in Java?

Load the `BarcodeGenerator` with the `CODE_128` symbology and your desired text, set the bar width via `XDimension`, then call `save` to write the image file. This three‑step pattern produces a high‑quality barcode in seconds and works on any Java 8+ runtime, Windows, Linux, or macOS.

## Prerequisites for generating barcode Java

- Basic knowledge of Java programming.  
- A Java development environment (JDK 8 or later).  
- Aspose.BarCode for Java library – download it **[here](https://releases.aspose.com/barcode/java/)**.  
- Your preferred IDE (IntelliJ IDEA, Eclipse, etc.).

## Import Packages

Import the essential Aspose.BarCode namespaces so the classes are available in your project.

## What is the BarcodeGenerator class?

`BarcodeGenerator` is the core Aspose.BarCode class that creates barcode images in memory. It provides a fluent API to set symbology, code text, dimensions, colors, and additional rendering options before exporting the result to formats such as PNG, JPEG, SVG, or PDF. You can also customize captions, margins, and error correction levels as needed.

## Barcode Generator Tutorial: Create a Code128 Barcode

### Step 1: Create an Instance of `BarcodeGenerator`

The `BarcodeGenerator` constructor takes two arguments: the barcode symbology (`CODE_128`) and the **custom code text** you want to encode, such as `"12345678"`.

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

### Step 2: Adjust Barcode Width for Custom Barcode Text

Set the `XDimension` property (bar width) to control how wide each bar appears. In this example we use `0.5` mm, a size that balances readability and label space for most applications.

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

### Step 3: Save the Barcode Image

Call the `save` method, specifying the output path and image format (JPEG, PNG, SVG, etc.). The example saves the file as **`setCodeText.jpg`** in the project’s document folder.

```java
generator.save(dataDir + "setCodeText.jpg");
```

## Why Use Aspose.BarCode for Java?

Aspose.BarCode for Java offers a comprehensive set of features that simplify barcode generation across platforms. It supports over sixty symbologies, delivers high‑resolution raster and vector outputs, and provides performance optimizations for bulk processing, making it ideal for enterprise‑grade applications and seamless integration with existing Java projects.

- **Broad symbology support** – Over **60** barcode types, including Code128, QR, DataMatrix, and PDF417.  
- **High‑resolution rendering** – Generates crisp PNG, JPEG, SVG, and PDF images up to **2000 mm** wide without quality loss.  
- **Performance‑focused** – Processes a 500‑page batch of barcodes in under **2 seconds** on standard server hardware.  
- **Cross‑platform** – Fully compatible with Windows, Linux, and macOS, and works with any Java 8+ runtime.

## Common Issues and Solutions

| Issue | Solution |
|-------|----------|
| **Barcode looks blurry** | Increase the image resolution or export to a vector format (SVG, PDF). |
| **Text is truncated** | Enlarge `XDimension` and `BarHeight` to give the symbology enough space. |
| **License not applied** | Place `Aspose.BarCode.lic` in the project root and load it with `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Frequently Asked Questions

**Q:** *What is the difference between `CODE_128` and other Code128 variants?*  
**A:** `CODE_128` automatically selects the most efficient encoding (A, B, or C) based on the input, providing optimal density and speed.

**Q:** *Can I change the output format to PNG instead of JPEG?*  
**A:** Yes—use `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Is it possible to add a human‑readable caption below the barcode?*  
**A:** Absolutely. Set `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` and define the caption text via `setText`.

**Q:** *Does Aspose.BarCode support Unicode characters?*  
**A:** It does. Provide UTF‑8 encoded text and ensure the selected symbology supports the character set.

**Q:** *How can I generate multiple barcodes in a loop?*  
**A:** Instantiate a new `BarcodeGenerator` inside the loop, assign a unique text for each iteration, and call `save` with a distinct filename.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for Java  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Create data matrix barcode and set code text location in Java](/barcode/java/text-and-styling/setting-code-text-location/)
- [How to Set Barcode Text Color in Java with Aspose.BarCode](/barcode/java/text-and-styling/setting-code-text-foreground-color/)
- [Generate Barcode Java – Set Image Resolution with Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```