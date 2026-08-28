---
category: general
date: 2026-08-06
description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
  Databar, adjust custom barcode size, and change barcode height with simple code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: en
lastmod: 2026-08-06
og_description: Generate barcode image in C# with Aspose.BarCode. This tutorial shows
  you how to create a Databar Omnidirectional barcode, customize its size, and change
  the barcode height efficiently.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Generate barcode image in C# – full Aspose.BarCode guide
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Generate barcode image in C# with Aspose.BarCode
url: /python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode image in C# with Aspose.BarCode

If you need to **generate barcode image** programmatically, this guide shows you exactly how. Whether you are building a retail inventory system or a logistics tracking portal, you’ll see the complete workflow for creating a Databar Omnidirectional barcode, adjusting its dimensions, and saving the result as a PNG file.

Generating a barcode image is a common requirement, but developers often wonder **how to generate Databar** with the exact size they need. In this tutorial you’ll learn to create a Databar barcode, customize its width and height, and change the barcode height without rewriting the entire generator.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code works with .NET Core and .NET Framework)
* Visual Studio 2022 (or any IDE that supports C#)
* A valid Aspose.BarCode for .NET license (the free evaluation works for testing)
* Basic familiarity with C# syntax

## Step 1: Install Aspose.BarCode

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

The package contains the `BarcodeGenerator` class used throughout this tutorial. After the installation, restore the project to pull the dependencies.

## Step 2: Create a basic barcode generator

The first line of code creates a **barcode generator** that will produce a Databar Omnidirectional symbol. The `EncodeTypes.DatabarOmniDirectional` enum tells the library which symbology to use, and the data string follows GS1 Application Identifier syntax.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Why this matters:** The `BarcodeGenerator` object is the entry point for every barcode operation. By selecting `DatabarOmniDirectional` you ensure the output complies with the GS1 standard for retail scanning.

## Step 3: Set a custom X‑dimension (module width)

The X‑dimension controls the width of the narrowest bar. Setting it to a small pixel value gives you a compact barcode, while larger values increase overall width.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explanation:** A 2‑pixel X‑dimension is a common choice for high‑resolution screens. Adjust this value if you need a tighter or looser visual density.

## Step 4: Generate the first barcode image with a specific height

Barcode height is independent of X‑dimension. Here we set the bar height to **30 px**, then save the image as PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Result:** You now have a file named `DatabarBarHeight30Pixels.png` that shows a Databar barcode 30 px tall. This demonstrates the **custom barcode size** capability for a specific use case such as a small label.

## Step 5: Change barcode height for a larger version

If the same barcode must appear on a larger label, you only need to modify the height property and reuse the same generator instance.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Why you can reuse the generator:** Changing `BarHeight.Pixels` updates the internal layout without recreating the object, which saves memory and keeps the data string intact. This is the recommended way to **change barcode height** on the fly.

## Step 6: Verify the output

Open the two PNG files in any image viewer. You should see two Databar Omnidirectional barcodes that encode the same GTIN but differ in vertical size:

* `DatabarBarHeight30Pixels.png` – 30 px tall, suitable for compact receipts.
* `DatabarBarHeight60Pixels.png` – 60 px tall, ideal for larger shelf‑edge labels.

Both images retain the same X‑dimension, so the bar‑to‑space ratio stays consistent while the overall height scales.

## Common variations and edge cases

| Situation | How to handle it |
|-----------|------------------|
| **Different barcode symbology** | Replace `EncodeTypes.DatabarOmniDirectional` with another enum value (e.g., `EncodeTypes.Code128`). The rest of the code remains unchanged. |
| **Non‑pixel dimensions** | Use `generator.Parameters.Barcode.XDimension.Millimeters` or `BarHeight.Millimeters` if you need physical measurements for print‑ready output. |
| **Transparent background** | Set `generator.Parameters.ImageBackgroundColor = Color.Transparent;` before calling `Save`. |
| **High‑resolution output** | Increase both `XDimension.Pixels` and `BarHeight.Pixels` proportionally, or save as `BarCodeImageFormat.Tiff` for lossless quality. |
| **Multiple barcodes in one image** | Create separate `BarcodeGenerator` instances, render each to a `Bitmap`, then compose them using `Graphics.DrawImage`. |

**Pro tip:** Always test the generated barcode with a real scanner before deploying to production. Scanners may interpret very thin bars differently depending on lighting and sensor quality.

## Full source code for reference

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Copy the code into a new console project, run it, and you’ll see the two PNG files appear in the output folder.

## Frequently asked questions

**Q: Can I generate a barcode without installing a license?**  
A: The evaluation version of Aspose.BarCode works without a license but adds a small watermark. For production use, apply a purchased license using `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: Does changing the X‑dimension affect readability?**  
A: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution printers. A minimum of 1 px for screen rendering is recommended; for print, use at least 0.25 mm.

**Q: What if I need to generate a barcode in JPEG format?**  
A: Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You may also set `generator.Parameters.ImageQuality` to control compression.

## Conclusion

You now know how to **generate barcode image** in C# using Aspose.BarCode, how to **create Databar barcode**, adjust a **custom barcode size**, and **change barcode height** on demand. The complete example demonstrates the most common workflow, and the variations table equips you to handle real‑world edge cases.

Next, explore related topics such as **embedding barcodes in PDF documents**, **batch generating multiple barcodes**, and **using QR codes for mobile payments**. Each of those scenarios builds on the same principles covered here, so you can extend this knowledge confidently.

Happy coding, and may your barcodes scan flawlessly!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}