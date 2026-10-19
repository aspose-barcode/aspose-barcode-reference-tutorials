---
category: general
date: 2026-10-18
description: Generate barcode image for Planet symbology using Java. Learn to create
  planet barcode with custom barcode dimensions and empty bars.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- create planet barcode
- custom barcode dimensions
language: en
lastmod: 2026-10-18
og_description: Generate barcode image for Planet symbology in Java. This tutorial
  shows how to create planet barcode with custom barcode dimensions and outline bars.
og_image_alt: Generated barcode image showing a Planet barcode with empty outline
  bars
og_title: Generate barcode image for Planet symbology – Java guide
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Generate barcode image for Planet symbology using Java. Learn to create
    planet barcode with custom barcode dimensions and empty bars.
  headline: Generate barcode image for Planet symbology in Java
  type: TechArticle
tags:
- barcode
- Java
- imaging
title: Generate barcode image for Planet symbology in Java
url: /python-java/general/generate-barcode-image-for-planet-symbology-in-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode image for Planet symbology in Java

If you need to **generate barcode image** for the Planet symbology, this guide walks you through the complete process. Whether you are building a postal automation system or a custom tracking solution, you’ll learn how to **create planet barcode** with **custom barcode dimensions** and outline (empty) bars.

The example uses the Aspose.BarCode for Java library, which provides a fluent API for every major barcode standard. No additional image‑processing tools are required, and the code runs on any Java 8+ runtime.

## Prerequisites

Before you start, make sure you have:

* Java 8 or newer installed (the tutorial was tested with JDK 17).
* Maven or Gradle to manage dependencies.
* Basic familiarity with Java syntax and the concept of a barcode.

If you are new to Maven, you can create a simple project with `mvn archetype:generate` and add the Aspose.BarCode dependency shown below.

## Add the Aspose.BarCode dependency

```xml
<!-- pom.xml -->
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-barcode</artifactId>
    <version>23.12</version> <!-- Use the latest version available -->
</dependency>
```

> **Pro tip:** Lock the version number to avoid unexpected breaking changes when the library updates.

## Step 1: Initialize the barcode generator for Planet symbology

```java
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Step 1 – create a generator that encodes data using the Planet symbology
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,          // Planet is the barcode type
                "123456");                   // Data to encode
```

**Why this step matters:**  
`EncodeTypes.PLANET` tells the library to use the Planet barcode specification, which is commonly used for postal services. The data string `"123456"` is the payload that will appear in the generated image.

## Step 2: Set custom barcode dimensions (X dimension)

```java
        // Step 2 – adjust the X dimension (module width) to 4 pixels.
        // This controls the thickness of each bar.
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);
```

**Why this step matters:**  
The *X dimension* defines how wide each individual bar is. By setting it to **4 pixels**, you obtain a barcode that is easily readable by most scanners while still fitting on a standard label. Changing this value is the primary way to achieve **custom barcode dimensions**.

## Step 3: Use empty (outline) bars instead of solid bars

```java
        // Step 3 – configure the generator to draw empty bars (outline only)
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);
```

**Why this step matters:**  
`setFilledBars(false)` tells the renderer to draw only the bar outlines, leaving the interior transparent. This style is often required for postal barcodes where the background may contain other printed information.

## Step 4: Save the barcode image as PNG

```java
        // Step 4 – save the generated barcode as a PNG file
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

**Why this step matters:**  
Choosing `BarCodeImageFormat.Png` gives you a lossless image that preserves the crisp edges of the outline bars. The file path can be any directory you have write access to; the example uses an `output` folder relative to the project root.

### Expected output

Running the program creates a file similar to the image below:

![Generated barcode image for Planet symbology](/images/planet-barcode.png){.align-center alt="Generated barcode image showing a Planet barcode with empty outline bars"}

The image displays a **Planet barcode** with thin, empty bars, exactly matching the custom dimensions you set.

## Common variations and edge cases

| Situation | Adjustment |
|-----------|------------|
| **Different data length** | Planet barcodes support up to 12 numeric characters. Change the second constructor argument accordingly. |
| **Higher resolution** | Increase the X dimension (`setPixels`) or set the `YDimension` to control bar height. |
| **Color barcode** | Use `barcodeGenerator.getParameters().getImageOptions().setForeColor(Color.BLUE);` to change bar color. |
| **Saving as SVG** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg` for a vector output. |
| **Running on Android** | Use the Android‑compatible Aspose.BarCode for Android and replace file‑system paths with `Context.getFilesDir()`. |

> **Watch out for:** Setting the X dimension too low (e.g., 1 pixel) can make the barcode unreadable on low‑resolution printers. Always test with a real scanner after changing dimensions.

## Full source code for quick copy‑paste

```java
package com.example.barcode;

import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generator.BarcodeGenerator;

public class PlanetBarcodeDemo {
    public static void main(String[] args) {
        // Create the generator for Planet barcode with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.PLANET,
                "123456");

        // Custom X dimension – 4 pixels per module
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .getXDimension()
                        .setPixels(4);

        // Use outline (empty) bars
        barcodeGenerator.getParameters()
                        .getBarcode()
                        .setFilledBars(false);

        // Save as PNG
        String outputPath = "output/PlanetEmptyBars.png";
        barcodeGenerator.save(outputPath, BarCodeImageFormat.Png);

        System.out.println("Barcode image generated at: " + outputPath);
    }
}
```

Copy the code into a file named `PlanetBarcodeDemo.java`, place it under `src/main/java/com/example/barcode/`, run `mvn compile exec:java`, and you’ll see the **generate barcode image** result in the `output` folder.

## Conclusion

You now know how to **generate barcode image** for the Planet symbology in Java, how to **create planet barcode** with **custom barcode dimensions**, and how to switch from solid to empty bars for a cleaner visual style. The complete example demonstrates every required API call, from initializing the generator to saving a PNG file.

**Next steps** – explore other barcode types (`EncodeTypes.CODE_128`, `EncodeTypes.QR`) and experiment with additional image options such as background color, margins, and DPI settings. If you need to embed the barcode in a PDF, combine this code with Aspose.PDF for Java for a seamless end‑to‑end solution.

Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [create planet barcode image – Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [How to generate barcode java: Create an Exact Barcode Image](/barcode/english/java/barcode-basics/creating-image-exact-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}