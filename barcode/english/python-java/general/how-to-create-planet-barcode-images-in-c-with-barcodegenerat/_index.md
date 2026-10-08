---
category: general
date: 2026-09-26
description: Learn how to create planet barcode in C# quickly. This guide covers filled
  and empty Planet barcodes, X‑dimension settings, and image export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: en
lastmod: 2026-09-26
og_description: Create planet barcode in C# with a full code example. Generate both
  filled and empty Planet barcodes, set bar width, and save as PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Create planet barcode images in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to create planet barcode images in C# with BarcodeGenerator
url: /python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create planet barcode images in C# with BarcodeGenerator

If you need to **create planet barcode** images in a .NET application, this tutorial shows you the exact steps. You’ll learn how to generate both a filled and an empty Planet barcode, adjust the bar width, and export the results as PNG files—all with the Aspose.BarCode for .NET library.

Generating a **Planet barcode C#** solution is straightforward once you understand the key **barcode generator parameters**. In the sections that follow, we’ll walk through the complete, runnable code, explain why each setting matters, and point out common pitfalls so you can avoid them on the first try.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed.
* Visual Studio 2022 (or any C# IDE you prefer).
* The **Aspose.BarCode for .NET** NuGet package (`Aspose.BarCode`) added to your project.

You can add the package via the NuGet Package Manager Console:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the BarcodeGenerator

The `BarcodeGenerator` class is the entry point for all barcode creation tasks. It requires two arguments: the barcode type (`EncodeTypes.Planet`) and the data to encode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Why this matters:* Instantiating the generator with `EncodeTypes.Planet` tells the library to use the **Planet barcode** symbology, which is commonly used for postal services in some countries. The string `"123456"` is the payload that will appear in the barcode.

## Step 2: Configure the X‑dimension (bar width)

The X‑dimension controls the physical width of each bar. A typical value for on‑screen rendering is 4 pixels, but you can adjust it to meet printing requirements.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters:* Setting `XDimension.Pixels` ensures that the generated barcode is neither too thin (causing scanning failures) nor too thick (wasting space). The same setting will be reused for the empty barcode.

## Step 3: Save the filled Planet barcode

Export the barcode to a PNG file using the `Save` method. The `BarCodeImageFormat.Png` enum tells the library to produce a lossless image suitable for further processing.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

After running the program, you’ll find `PostalPlanetFilledBars.png` in the output folder. Open it to verify that the bars are solid (filled).

## Step 4: Create a generator for an empty Planet barcode

An **empty planet barcode** displays the same data but with unfilled (white) bars. This is useful for visual designs that overlay the barcode on colored backgrounds.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

The constructor call is identical to the filled version; the difference lies in the parameter we’ll change next.

## Step 5: Reuse the same X‑dimension

To keep the visual size consistent, apply the same bar width to the empty barcode.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Reusing the **barcode generator parameters** guarantees that both images align perfectly when placed side‑by‑side.

## Step 6: Switch to unfilled bars

The `FilledBars` flag determines whether the bars are rendered as solid black (default) or transparent white.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Why this matters:* Setting `FilledBars = false` flips the rendering mode, which is the key distinction between a filled and an empty Planet barcode.

## Step 7: Save the empty Planet barcode

Finally, export the empty version to PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

When you run the program, two files appear:

* `PostalPlanetFilledBars.png` – solid black bars.
* `PostalPlanetEmptyBars.png` – transparent (unfilled) bars.

Both images contain the same data (`123456`) and share the same X‑dimension, making them interchangeable in most UI scenarios.

## Full, runnable example

Putting everything together, here’s the complete source file you can copy‑paste into a new console project:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Expected output**

Running the program creates two PNG files in the executable’s working directory. Open them with any image viewer:

* **Filled version** – dark, solid bars that are easily readable by standard scanners.
* **Empty version** – bars appear as white gaps on a black background, useful for overlay effects.

## Common pitfalls and pro tips

| Issue | Why it happens | How to fix it |
|-------|----------------|---------------|
| Bars look too thin | X‑dimension left at default (1 pixel) | Set `XDimension.Pixels` to 3‑5 pixels for on‑screen use; increase for high‑resolution prints. |
| Empty barcode appears completely black | `FilledBars` not set to `false` | Ensure `emptyPlanet.Parameters.Barcode.FilledBars = false;` is executed **after** setting the X‑dimension. |
| PNG file is missing | Output path is incorrect or directory does not exist | Provide a full path (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) or create the directory beforehand with `Directory.CreateDirectory`. |
| Barcode fails to scan | Data string contains illegal characters for Planet symbology | Planet barcodes accept numeric payloads only; validate input with `int.TryParse`. |

**Pro tip:** If you need to embed the barcode in a PDF, you can load the generated PNG into a `PdfDocument` using Aspose.PDF, or directly add the barcode as an image stream without writing to disk.

## Next steps

Now that you can **create planet barcode** images, consider exploring these related topics:

* **Planet barcode C#** – customizing colors, adding human‑readable text, or embedding the barcode in a PDF.
* **Barcode generator parameters** – tweaking error correction level, quiet zone, or rotation.
* **Batch generation** – loop over a list of postal codes to produce a zip file of PNGs.
* **Alternative formats** – export to SVG or JPEG for web‑friendly delivery.

Experiment with different `XDimension` values and the `FilledBars` flag to see how they affect scanning reliability and visual style. When you’re ready, integrate the generation code into your web API or desktop application to automate postal barcode creation on the fly.

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}