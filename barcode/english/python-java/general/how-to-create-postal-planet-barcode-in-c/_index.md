---
category: general
date: 2026-11-23
description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
  generate planet barcode, set X‑dimension, and save filled or empty bars.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: en
lastmod: 2026-11-23
og_description: Create postal planet barcode in C# and learn how to generate planet
  barcode with Aspose.BarCode. Follow the complete example to produce filled and empty
  bars.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: How to create postal planet barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: How to create postal planet barcode in C#
url: /python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create postal planet barcode in C#

If you need to **create postal planet barcode** in a .NET application, this guide shows you exactly **how to generate planet barcode** using the Aspose.BarCode library. You will see how to configure the X‑dimension, switch between filled and empty bars, and save the images in PNG format.

Generating a Planet barcode is common for postal services that require high‑density, machine‑readable symbols. By the end of this tutorial you will have two PNG files—one with solid bars and one with hollow bars—ready for integration into any mailing workflow.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed.
* Visual Studio 2022 (or any C# editor) configured for .NET development.
* An active NuGet license for **Aspose.BarCode for .NET**. Install the package with:

```bash
dotnet add package Aspose.BarCode
```

No additional external services are required; the library performs all encoding locally.

## Step 1 – create postal planet barcode

The first operation is to instantiate a `BarcodeGenerator` for the **Planet** symbology and provide the data to encode. The data string must be numeric and up to 12 digits according to the postal specification.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Creating the generator allocates all internal structures needed for rendering. The `EncodeTypes.Planet` enum value selects the correct encoding algorithm for the postal format.

## Step 2 – set the X‑dimension for better visibility

The X‑dimension defines the width of a single module (the smallest bar element). A value of 4 pixels provides a clear visual representation without enlarging the overall image.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Adjusting the X‑dimension is essential when the barcode will be printed on low‑resolution media. The same setting will be reused for the empty‑bars version to keep both images consistent.

## Step 3 – save the barcode with filled bars

By default the generator renders **filled bars** (solid black modules). Saving the image is a single method call that writes the PNG file to disk.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Replace `YOUR_DIRECTORY` with the actual path where you want the output files. The `BarCodeImageFormat.Png` enumeration guarantees lossless compression, which is ideal for downstream processing.

## Step 4 – create another Planet barcode generator for empty bars

To produce a version that uses **empty bars** (white modules on a black background), you need a second `BarcodeGenerator` instance. Reusing the same data string ensures both images represent the identical postal code.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Creating a separate generator isolates the `FilledBars` property, allowing you to toggle the visual style without affecting the first image.

## Step 5 – configure the generator to render empty bars

The `FilledBars` flag flips the rendering mode. Setting it to `false` tells the library to draw the bars as empty (transparent) while keeping the background solid.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Keeping the X‑dimension identical to the filled version guarantees that both PNG files have the same dimensions, which simplifies layout calculations in printing templates.

## Step 6 – save the barcode that renders empty bars

Finally, write the empty‑bars image to disk. The same PNG format is used, but you could switch to JPEG or BMP by changing the `BarCodeImageFormat` value.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

At this point you have two files:

* `PostalPlanetFilledBars.png` – solid black bars.
* `PostalPlanetEmptyBars.png` – hollow bars on a black background.

Both satisfy the postal specification for the Planet symbology.

## Complete source code

Putting all steps together yields a compact console application that you can run directly.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Compile and run the program:

```bash
dotnet run
```

The console prints *Barcodes generated successfully.* and the two PNG files appear in the project folder.

## Expected output

Below is a visual representation of the filled‑bars image. The empty‑bars counterpart looks identical except that the bars are transparent.

![Example of a created postal planet barcode with filled bars](postal-planet-filled.png)

*Image alt text:* **Example of a created postal planet barcode with filled bars** (contains the primary keyword).

Both images are 150 × 150 pixels by default, but you can control the overall size with the `ImageWidth` and `ImageHeight` parameters if a different resolution is required.

## Optional variations

### Changing the image format

If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use it only when file size is a critical constraint.

### Scaling the barcode

You can enlarge the barcode while preserving the module width by adjusting the `Resolution` property:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Higher DPI values improve print quality on laser printers.

### Using a custom background color

The background can be set with:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

This is useful for visual testing but should be avoided in production postal labels, which require a white background.

## Frequently asked questions

**Does this work with .NET Core?**  
Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible with .NET 5, .NET 6, and .NET Core 3.1.

**What if the data string contains non‑numeric characters?**  
Planet barcodes accept only numeric input. Supplying letters or symbols triggers a `BarcodeException`. Validate the input before creating the generator.

**Can I generate a barcode in memory without writing to disk?**  
Use the `GenerateBarCodeImage` method to obtain a `System.Drawing.Image` object, then stream it directly to a response or database.

## Conclusion

You now know how to **create postal planet barcode** in C# and understand **how to generate planet barcode** with both filled and empty bar styles. The tutorial covered the full workflow—from initializing the generator, configuring the X‑dimension, toggling the `FilledBars` flag, to saving PNG files. Experiment with image formats, DPI settings, and background colors to adapt the barcode to your specific mailing system.

For the next step, explore other postal symbologies such as **POSTNET** or **Intelligent Mail** using the same Aspose.BarCode API. Adjusting parameters like `EncodeTypes.Postnet` follows the same pattern demonstrated here, allowing you to build a comprehensive barcode generation suite in a single codebase.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}