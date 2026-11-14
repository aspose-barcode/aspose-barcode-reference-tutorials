---
category: general
date: 2026-11-14
description: Learn how to generate a GS1 MicroPDF417 barcode image in C# using Aspose.BarCode. This step‑by‑step guide covers barcode generator C# setup, GS1 formatting and PNG export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: en
lastmod: 2026-11-14
og_description: Generate a GS1 MicroPDF417 barcode image in C# quickly. Follow this guide to learn how to generate barcode, use Aspose.BarCode, and export a PNG.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Generate GS1 MicroPDF417 barcode image in C# – full guide
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to generate a GS1 MicroPDF417 barcode image in C# using Aspose.BarCode. This step‑by‑step guide covers barcode generator C# setup, GS1 formatting and PNG export.
  headline: How to generate a GS1 MicroPDF417 barcode image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Generate a GS1 MicroPDF417 barcode image in C# with Aspose.BarCode
url: /net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate a GS1 MicroPDF417 barcode image in C# with Aspose.BarCode

If you need to **create barcode image** in C#, this guide shows you a complete, ready‑to‑run solution. You’ll see **how to generate barcode** data that follows the GS1 standard, configure the generator, and export a high‑quality PNG file.

The tutorial covers everything from installing the required library to handling common data‑format pitfalls. By the end you will be able to produce a **barcode image from data** with just a few lines of code, and you’ll understand why each setting matters.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed (the code also works with .NET Framework 4.7+).
* An IDE such as Visual Studio 2022 or Visual Studio Code.
* The **Aspose.BarCode for .NET** NuGet package. Install it with:

```bash
dotnet add package Aspose.BarCode
```

* Basic familiarity with C# syntax and the GS1 Application Identifier (AI) format.

> **Pro tip:** Keep the library version up‑to‑date; the latest release adds support for newer barcode symbologies and performance improvements.

## Create barcode image with BarcodeGenerator

This section contains the core implementation. The code creates a **barcode generator c#** instance, configures the X‑dimension for readability, and saves the result as a PNG file.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Why each line matters

* **EncodeTypes.MicroPdf417** tells the library to use the GS1 MicroPDF417 symbology, which is compact and ideal for mobile scanning.
* The **data string** must start with the GS1 AI `(01)` for the Global Trade Item Number (GTIN) followed by `(21)` for the serial number. If the format is incorrect, the generator throws an exception.
* **XDimension.Pixels** controls the width of the smallest bar. A larger value increases readability on low‑resolution displays, while a smaller value reduces image size.
* **BarCodeImageFormat.Png** produces a lossless image, preserving the sharp edges required for reliable scanning.

Running the program creates `GS1MicroPdf417.png` on your desktop. Opening the file shows a dense, black‑on‑white barcode that encodes the GTIN `12345678901234` and the serial `ABC123`.

## How to generate barcode using GS1 MicroPDF417

If you are new to GS1 formatting, here are the essential rules:

| GS1 AI | Meaning                     | Example               |
|--------|-----------------------------|-----------------------|
| (01)   | Global Trade Item Number    | 12345678901234        |
| (21)   | Serial number (optional)    | ABC123                |

When you concatenate the AIs with their values, wrap each AI in parentheses and place the values directly after. The resulting string can be passed to the **barcode generator c#** without further encoding.

### Common pitfalls

* **Missing parentheses** – The generator treats the string as raw data and will not apply GS1 checks.
* **Exceeding length limits** – MicroPDF417 supports up to 155 characters. Trim unnecessary whitespace.
* **Invalid characters** – Only numeric characters are allowed for the GTIN; the serial can include uppercase letters and digits.

## Customising the barcode image from data

Beyond the basic X‑dimension, Aspose.BarCode offers many visual tweaks. Below are a few adjustments you might apply depending on your project’s requirements.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Each setting is optional; the defaults already produce a clean, scannable **barcode image**. Experiment with colors and resolutions only after confirming that scanners can still read the code.

## Saving the barcode in other formats

While PNG is the most common format for web and mobile, you may need JPEG, BMP, or SVG. The `Save` method accepts any `BarCodeImageFormat` value.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG reduces file size but introduces compression artifacts that can affect readability.
* SVG preserves vector quality and is ideal for responsive web designs.

## Verifying the generated barcode

A quick way to confirm that the **create barcode image** step succeeded is to use a mobile scanner app that supports GS1 MicroPDF417. Scan the saved PNG; the app should display:

```
GTIN: 12345678901234
Serial: ABC123
```

If the scanner reports an error, double‑check the AI formatting and the X‑dimension value.

## Full example – a self‑contained console program

Below is a complete program you can copy, paste, and run without modification (aside from the NuGet install step).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

When you run the program, the console prints the full file path, and the PNG appears on your desktop. This example demonstrates **how to generate barcode** data, customise appearance, and export a **barcode image from data** in a single, cohesive workflow.

## Frequently asked questions

| Question | Answer |
|----------|--------|
| *Can I generate other GS1 symbologies?* | Yes. Replace `EncodeTypes.MicroPdf417` with `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix`, etc., and adjust the data string accordingly. |
| *What if my data exceeds the MicroPDF417 capacity?* | Switch to the regular PDF417 symbology, which supports longer payloads. |
| *Do I need a license for Aspose.BarCode?* | A free evaluation license works for development. For production, purchase a license to remove the evaluation watermark. |
| *Is the PNG suitable for printing on labels?* | Increase `ImageResolution` to 300 dpi or higher, and consider saving as TIFF for industrial printers. |

## Conclusion

You now know how to **create barcode image** in C# using the **barcode generator c#** approach, format data for a **create gs1 barcode** scenario, and export the result as a PNG or other image type. The full example demonstrates every step—from data preparation to visual customisation—so you can integrate barcode creation into any .NET application.

Next, explore related topics such as **barcode image from data** for QR codes, adding multiple barcodes to a single PDF, or automating batch generation for inventory systems. Experiment with different X‑dimension values and image formats to find the sweet spot for your specific scanning environment.

Happy coding, and let your applications start **creating barcode images** that work reliably in the real world!

## What should you learn next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step‑by‑step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- {{< relref "/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/" >}} – How to create barcode image with Aspose.Barcode in C#
- {{< relref "/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/" >}} – How to create postal barcode image in C# using Aspose.BarCode
- {{< relref "/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/" >}} – How to create PDF417 barcode image in C# – complete guide

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}