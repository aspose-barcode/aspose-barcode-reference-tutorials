---
category: general
date: 2026-09-10
description: How to set barcode in C# using a Barcode Generator. Adjust barcode module
  width, generate barcode images, and learn how to save barcode files.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: en
lastmod: 2026-09-10
og_description: How to set barcode in C# with a Barcode Generator. Learn to adjust
  module width, generate a barcode, and save the barcode image efficiently.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: How to set barcode properties using C# Barcode Generator
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: How to set barcode properties with the C# Barcode Generator
url: /python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set barcode properties with the C# Barcode Generator

How to set barcode properties is essential when you need precise control over a barcode’s visual style. This guide shows you how to generate a Planet barcode, adjust the barcode module width, and save the barcode image using the C# Barcode Generator.

You will see a complete, runnable example that covers every step from creating the barcode object to writing the PNG files to disk. No external documentation is required—just the code below and the Aspose.BarCode library (or any compatible barcode SDK). By the end of the tutorial you can answer questions such as “how to generate barcode with custom dimensions?” and “how to save barcode in different formats?”.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed  
* Visual Studio 2022 (or any C# IDE)  
* The **Aspose.BarCode** NuGet package (or another library that provides `BarcodeGenerator`)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## How to set barcode module width

The *module width* (also called X‑dimension) determines the pixel size of each narrow bar in the barcode. Setting this value lets you control the overall size and readability of the image.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters*: A larger X‑dimension produces a bigger barcode that is easier for scanners to read at a distance, while a smaller value reduces file size for on‑screen rendering.

## Generating a barcode with filled bars

The default style for the Planet barcode uses **filled bars** (solid black bars). The following code creates the image and saves it as PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Result**: `PostalPlanetFilledBars.png` contains a standard Planet barcode where every bar is filled.

## Creating an empty‑bar barcode

Sometimes you need a barcode that shows only the outlines of the bars (empty bars). To achieve this, you duplicate the generator, keep the same module width, and turn off the `FilledBars` flag.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Result**: `PostalPlanetEmptyBars.png` displays the same data but with unfilled bars, useful for design‑heavy documents where you want the barcode to blend with the background.

## How to save barcode in different formats

The `Save` method accepts any format supported by the SDK, such as **Jpeg**, **Bmp**, **Gif**, or **Svg**. Changing the format only requires swapping the `BarCodeImageFormat` enum value.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Tip*: Use SVG when you need a vector graphic that scales without pixelation, especially for print‑ready PDFs.

## Full, runnable example

Putting all the pieces together gives you a self‑contained program you can paste into a console app.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Expected output**

| File name                     | Description                              |
|-------------------------------|------------------------------------------|
| `PostalPlanetFilledBars.png`  | Planet barcode with solid black bars     |
| `PostalPlanetEmptyBars.png`   | Same data, bars rendered as outlines     |
| `PostalPlanet.svg`            | Vector version for scaling without loss  |

Run the program, open the generated files, and verify that the barcodes match the numeric string “123456”.

## Common variations and edge cases

| Situation                               | Adjustment                                                                 |
|----------------------------------------|---------------------------------------------------------------------------|
| Need a thicker barcode                 | Increase `XDimension.Pixels` (e.g., `8`)                                   |
| Want a smaller file size               | Use `BarCodeImageFormat.Jpeg` or lower the X‑dimension                    |
| Generating other symbologies           | Replace `EncodeTypes.Planet` with `EncodeTypes.Code128`, `QR`, etc.       |
| Printing on high‑resolution printers   | Save as `BarCodeImageFormat.Tiff` for lossless raster output              |
| Running on a headless server           | No UI code required; the generator works in a console or service context  |

**Pro tip**: Always validate the generated barcode with a scanner or a verification tool before deploying it to production. Incorrect module width or format can cause scan failures.

## Conclusion

You now know how to set barcode properties using the C# Barcode Generator, how to control the barcode module width, how to generate both filled and empty bar styles, and how to save the barcode in PNG or SVG formats. These steps give you a solid foundation for adding barcode creation to any .NET application.

Next, explore related topics such as **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, and **creating QR codes with custom colors**. Experiment with different `EncodeTypes` and image formats to find the best fit for your project.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Barcode Generator Tutorial: How to Generate PDF417 Barcode in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}