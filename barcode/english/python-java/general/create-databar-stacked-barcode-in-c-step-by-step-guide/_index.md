---
category: general
date: 2026-08-06
description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
  adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
  generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: en
lastmod: 2026-08-06
og_description: Create databar stacked barcode in C# with Aspose.BarCode. This tutorial
  shows how to configure X dimension, change aspect ratio, and save PNG images.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Create databar stacked barcode in C# – complete programming guide
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Create databar stacked barcode in C# – step‑by‑step guide
url: /python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create databar stacked barcode in C# – step‑by‑step guide

If you need to **create databar stacked barcode** images in C#, this guide shows you exactly how to do it using the Aspose.BarCode library. You’ll learn to set the X dimension, change the barcode aspect ratio, and save the result as PNG files—all in a few concise steps.

Generating a DataBar Stacked barcode is common when you must encode GS1‑128 data for retail scanning or logistics tracking. In the sections that follow we cover everything from project setup to verifying the output, so you can integrate the solution into any .NET application without missing a detail.

## Prerequisites

Before you start, make sure you have:

* **.NET 6.0** (or later) installed – the code targets the modern SDK.
* A **licensed** copy of **Aspose.BarCode for .NET**. The free evaluation works for testing but adds a watermark.
* An IDE such as **Visual Studio 2022** or **VS Code** with the C# extension.
* Basic familiarity with **C#** syntax and the concept of GS1 Application Identifiers.

> **Pro tip:** If you use the NuGet package manager, the command `dotnet add package Aspose.BarCode` resolves all dependencies automatically.

## Step 1: Create a new console project

Open a terminal or the Package Manager Console and run:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

The `dotnet new console` command scaffolds a minimal **Program.cs** file. Adding the **Aspose.BarCode** package makes the `BarcodeGenerator` class available.

## Step 2: Initialize the DataBar Stacked Omnidirectional generator

Open **Program.cs** and replace the default content with the following code. The first line creates a **BarcodeGenerator** configured for the **DataBar Stacked Omnidirectional** symbology and supplies a GS1‑128 payload.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Why this matters:** The `EncodeTypes.DatabarStackedOmniDirectional` enum value tells the library to produce a **databar stacked barcode**, which is the stacked variant of the omnidirectional DataBar family. This symbology can hold up to 14 numeric characters, making it ideal for GTIN‑14 codes.

## Step 3: Set the X dimension (module width)

The X dimension controls the width of the smallest bar (the module). A value that’s too small may render poorly on low‑resolution printers, while a value that’s too large can exceed label space.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** The `Pixels` property is convenient for screen‑based testing. For print‑focused scenarios, use `generator.Parameters.Barcode.XDimension.Millimeters` instead.

## Step 4: Adjust the aspect ratio and save the first image

The **aspect ratio** influences the height‑to‑width relationship of the stacked barcode. The DataBar Stacked Omnidirectional type supports ratios from 10 to 30. We’ll generate two images to illustrate the visual impact.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The call to `generator.Save` writes a **PNG** file to the current working directory. The `BarCodeImageFormat.Png` enum ensures lossless compression, which is ideal for further processing or embedding in PDFs.

## Step 5: Change the aspect ratio to 30 and save the second image

Now we increase the height of the stacked bars by changing the aspect ratio to **30**. This makes the barcode taller without altering the X dimension.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Running the program now produces two PNG files:

* **DatabarAspectRatio15.png** – a compact barcode suitable for small labels.
* **DatabarAspectRatio30.png** – a taller barcode that improves scan reliability on low‑contrast surfaces.

You can open the images in any viewer to verify that the bars are correctly stacked and that the encoded data matches the original GS1 string.

## Step 6: Verify the encoded value (optional)

If you need to confirm that the barcode truly represents the input string, you can decode it with the same library:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

The decoder should output `(01)12345678901231`, proving that the **create databar stacked barcode** process preserved the data.

## Common pitfalls and how to avoid them

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode appears blurry | X dimension set too low for the output resolution | Increase `XDimension.Pixels` or use `Millimeters` for print |
| Scanner reports “symbol not found” | Aspect ratio outside the supported 10‑30 range | Keep the ratio between 10 and 30; 15 and 30 are safe defaults |
| PNG contains a watermark | Using the free evaluation license of Aspose.BarCode | Purchase a full license or use the trial for testing only |
| Decoding fails on the second image | The decoder was configured for the wrong symbology | Use `DecodeType.DatabarStackedOmniDirectional` when reading stacked barcodes |

## Next steps

Now that you can **create databar stacked barcode** images, you might want to:

* **Embed the PNGs into PDF invoices** using a PDF library such as **Aspose.PDF**.
* **Generate barcodes on the fly in a web API** – return the PNG bytes directly from an ASP.NET Core controller.
* **Experiment with other DataBar variants** (e.g., `DatabarExpanded`, `DatabarLimited`) by changing the `EncodeTypes` enum.
* **Adjust colors** by setting `generator.Parameters.Barcode.ForeColor` and `BackColor` for brand‑specific designs.

Each of these topics builds on the same core concepts covered here: initializing `BarcodeGenerator`, configuring visual parameters, and saving the result with `BarCodeImageFormat`.

---

### Conclusion

This tutorial demonstrated how to **create databar stacked barcode** images in C# using Aspose.BarCode. You learned to set the **X dimension**, modify the **barcode aspect ratio**, and export the result as **PNG** files with `BarcodeGenerator`. With the optional decoding step, you can also verify that the encoded GS1 data is accurate. Apply these patterns to your own inventory, shipping, or point‑of‑sale applications, and explore the many customization options the library provides. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}