---
category: general
date: 2026-09-16
description: Learn how to set width, how to make empty bars, and how to fill bars
  when you generate Planet barcode using Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: en
lastmod: 2026-09-16
og_description: How to set width, make empty bars, and fill bars while you generate
  Planet barcode with Aspose.BarCode – complete step‑by‑step guide.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: How to set width and generate a Planet barcode in C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to set width and generate a Planet barcode in C#
url: /python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set width and generate a Planet barcode in C#

If you need to **how to set width** for a Planet barcode, this guide shows the complete process. You’ll also see **how to make empty** bars, **how to fill bars**, and the exact steps to **generate Planet barcode** with Aspose.BarCode for .NET.

Generating a postal‑style Planet barcode is common when building mailing‑label applications or postal‑service integrations. By the end of this tutorial you will have a ready‑to‑run console program that creates both a filled‑bars image and an empty‑bars image, each using the same data string.

## Prerequisites

- .NET 6.0 SDK or later (the code also works with .NET Framework 4.7+)
- Visual Studio 2022 or any C#‑compatible IDE
- Aspose.BarCode for .NET NuGet package (`Aspose.BarCode`)  
  Install with:

```bash
dotnet add package Aspose.BarCode
```

No additional configuration is required; the library handles image encoding internally.

## Step 1: Create a console project and add the library

Open a terminal and run:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

This creates a `Program.cs` file where we will write the barcode logic.

## Step 2: Write the code – how to set width and generate Planet barcode

Open `Program.cs` and replace its contents with the following complete example:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Why each step matters

- **How to set width**: The `XDimension.Pixels` property directly influences the physical size of each bar. Choosing a value between 2 and 6 pixels balances readability on screen and print quality.
- **How to make empty**: Setting `FilledBars = false` tells the generator to draw only the outlines of the bars. This style is useful for “light‑on‑dark” printing or when you want the underlying paper texture to show through.
- **How to fill bars**: The default `FilledBars = true` creates solid black bars, which is the standard for most postal scanners.
- **Generate Planet barcode**: Using `EncodeTypes.Planet` selects the specific encoding required by the United States Postal Service (USPS) for Planet barcodes.

## Step 3: Build and run the program

From the project folder execute:

```bash
dotnet run
```

You should see console output similar to:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Two PNG files appear in the project directory:

- `PostalPlanetFilledBars.png` – solid black bars (default style)
- `PostalPlanetEmptyBars.png` – outline bars (empty style)

Open them in any image viewer to verify that the bar width matches the 4‑pixel setting and that the empty version shows unfilled bars.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| *Can I use a different image format?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. |
| *What if the barcode becomes too wide for my label?* | Reduce `XDimension.Pixels` (e.g., to `2`) or increase the module width of the label printer. |
| *Do I need to set `Height` manually?* | The library automatically calculates height based on the encoding. You can override with `Parameters.Barcode.BarHeight`. |
| *Is the empty‑bars style supported on all printers?* | Most modern thermal printers handle both filled and empty styles, but verify with a test print if you use a legacy device. |
| *How to add a human‑readable caption under the barcode?* | Use `Parameters.Caption` to enable and style a caption; set `CaptionAbove` to `false` to place it below. |

## Pro tips

- **Reuse the same generator** only when you keep all parameters identical. Changing `FilledBars` after a save does not affect the already saved image, so re‑instantiating (as shown) guarantees a clean start.
- **Batch generation**: Wrap the code in a loop and change `data` each iteration to create a series of Planet barcodes for bulk mailing.
- **Performance**: For thousands of barcodes, create a single `BarcodeGenerator` instance, adjust `XDimension` and `FilledBars` as needed, and reuse the object to reduce memory allocations.

## Conclusion

You now know **how to set width**, **how to make empty**, **how to fill bars**, and the exact steps to **generate Planet barcode** with Aspose.BarCode in C#. The complete, runnable example produces both filled‑bars and empty‑bars PNG files, ready for integration into any mailing‑label workflow.

Next, explore related topics such as **how to add QR codes to the same label**, **customizing barcode colors**, or **embedding the barcode into a PDF document**. Each of these builds on the same fundamentals covered here. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [How to Create Code128 Barcode with Empty Bars in Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}