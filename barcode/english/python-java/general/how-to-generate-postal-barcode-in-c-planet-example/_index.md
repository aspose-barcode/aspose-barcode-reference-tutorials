---
category: general
date: 2026-10-28
description: Generate postal barcode in C# using the Planet format. This planet barcode
  example shows how to set barcode width and save both filled and empty bars.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: en
lastmod: 2026-10-28
og_description: Generate postal barcode in C# with a complete planet barcode example.
  Learn to set barcode width, produce filled bars, and create empty‑bar images.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Generate postal barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: How to generate postal barcode in C# – planet example
url: /python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate postal barcode in C# – planet example

If you need to generate postal barcode in C#, this guide walks you through a complete solution. You’ll see a practical planet barcode example that encodes a numeric string, lets you set barcode width, and saves both filled and empty bar images.

Creating a postal barcode doesn’t require a complex build pipeline. By the end of this tutorial you can integrate barcode generation into any .NET application, customize the X‑dimension, and choose whether the bars appear filled or empty.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A C# development environment (Visual Studio, VS Code, or Rider)  
* The **Aspose.BarCode for .NET** NuGet package (version 23.10 or newer)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

The code snippets below assume you have added `using Aspose.BarCode.Generation;` at the top of your file.

## Generate postal barcode with Planet symbology

The first step is to create a `BarcodeGenerator` instance that uses the Planet symbology. Planet is a postal barcode format used by several national postal services.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Why this matters:**  
`EncodeTypes.Planet` tells the library to use the Planet barcode standard, which encodes numeric data in a series of bars and spaces. The constructor receives the data string (`"123456"` in this case) that you want to encode.

Running the program produces two PNG files in the executable’s working directory:

* **PostalPlanetFilledBars.png** – bars are rendered as solid black rectangles.  
* **PostalPlanetEmptyBars.png** – bars are rendered as white rectangles with a black outline, useful for printing on dark backgrounds.

## Set barcode width (X‑dimension) in pixels

The visual size of a barcode is controlled by the X‑dimension, which defines the width of a single bar. Adjusting this value ensures the barcode scans correctly at the intended printing resolution.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Why you should set it:**  
A larger X‑dimension makes the barcode easier to scan with low‑resolution scanners, while a smaller value reduces the overall image size for high‑density printing. The default width is 2 pixels; 4 pixels is a common compromise for most desktop printers.

You can experiment with different values:

| Pixels | Typical use case |
|--------|-----------------|
| 2      | High‑density labels |
| 4      | Standard office printing |
| 6‑8    | Large‑format signage |

**Tip:** Always test the generated barcode with your target scanner after changing the X‑dimension.

## Planet barcode example – filled vs empty bars

A Planet barcode can be rendered with either solid (filled) bars or outlined (empty) bars. The `FilledBars` property toggles this behavior.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Why you might choose empty bars:**  
Empty bars improve contrast on dark‑toned packaging, because the white interior of each bar stands out against a dark background. Filled bars are the default and work well on light‑colored media.

**Expected output:**  

*Both images display the same encoded data (`123456`).* The only visual difference is the bar style. Below is a textual description of what you’ll see:

* **Filled bars image:** Solid black vertical bars on a white background.  
* **Empty bars image:** Black outlines forming the same pattern, with white interiors.

You can open the PNG files in any image viewer to verify that the pattern matches the Planet specification.

## Customize additional barcode properties (optional)

While the core steps above cover most scenarios, you may want to fine‑tune other settings:

| Property | Description | Typical value |
|----------|-------------|---------------|
| `Barcode.Color` | Foreground color of the bars | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Background fill color | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Human‑readable text displayed below the barcode | Same as encoded data or a custom label |
| `Barcode.ImageFormat` | Output format (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Example of setting a custom foreground color:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

These optional tweaks help you match corporate branding or meet specific printing requirements.

## Common pitfalls and how to avoid them

| Issue | Cause | Fix |
|-------|-------|-----|
| Barcode is unreadable | X‑dimension too small for the printer’s DPI | Increase `XDimension.Pixels` to 4 or higher |
| Image file is corrupted | Missing write permissions in the target folder | Use an absolute path or ensure the directory exists |
| Wrong symbology used | Passing `EncodeTypes.Code128` instead of `EncodeTypes.Planet` | Verify the `EncodeTypes` argument matches the postal format |

**Pro tip:** Always generate a test barcode and scan it with the intended hardware before deploying to production.

## Full, runnable example

Below is a self‑contained console application that incorporates all of the steps discussed. Copy the code into a new .NET console project and run it to see the two PNG files appear in the output folder.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Verification steps:**  

1. Build the project (`dotnet build`).  
2. Run the executable (`dotnet run`).  
3. Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the `bin/Debug/net6.0` folder.  
4. Open each image; you should see a series of vertical bars representing the numeric string


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create planet barcode with filled and empty bars](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}