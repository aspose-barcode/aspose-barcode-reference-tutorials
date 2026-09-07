---
category: general
date: 2026-09-07
description: Create planet barcode PNG in C# quickly. Learn how to generate planet
  barcode images using Aspose.BarCode with filled and empty bars.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: en
lastmod: 2026-09-07
og_description: Create planet barcode PNG in C# fast. Follow this guide to learn how
  to generate planet barcode images with filled and empty bars using Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Create planet barcode PNG in C# – complete coding tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: How to create planet barcode PNG with C# – step‑by‑step guide
url: /python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create planet barcode PNG with C# – step‑by‑step guide

If you need to **create planet barcode PNG** files in C#, this guide shows you the exact steps. Whether you’re building a postal‑service integration or a logistics dashboard, you’ll learn **how to generate planet barcode** images with both filled and empty bars using the Aspose.BarCode library.

In this tutorial you will:

* Set up the output folder for your images.  
* Configure a `BarcodeGenerator` for the Planet symbology.  
* Produce a PNG with the default filled‑bars style.  
* Produce a PNG with empty bars for visual contrast.  

No external services are required—everything runs locally on .NET 6 or later.

## Prerequisites

Before you start, make sure you have:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6 SDK (or newer) | Provides the runtime for the C# console app. |
| Visual Studio 2022 or VS Code | Any IDE that can compile C# projects. |
| Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`) | Supplies the `BarcodeGenerator` class used to render Planet barcodes. |
| Write permission to a folder on disk | The PNG files will be saved to this location. |

Install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a new console project

Open a terminal and run:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

This scaffolds a minimal C# console application named **PlanetBarcodeDemo**.

## Step 2: Define the output directory

The first piece of code determines where the generated PNG files will be stored. Using an absolute or relative path works; just ensure the folder exists or let the program create it.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Why this step?* Separating output from source code keeps your project tidy and avoids accidental overwrites.

## Step 3: Generate a filled‑bars Planet barcode

A Planet barcode consists of concentric circles (filled by default). We configure the X‑dimension (pixel width of each bar) and then save the image as PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Explanation**

* `EncodeTypes.Planet` tells Aspose to use the Planet symbology, which is common for postal services.  
* `XDimension.Pixels = 4` yields a clear, printable size without manual scaling.  
* The `Save` method writes a PNG file; you could also choose JPEG or BMP by changing the `BarCodeImageFormat`.

## Step 4: Generate an empty‑bars Planet barcode

Sometimes a visual with empty (transparent) bars is required—for example, when the barcode is overlaid on a colored background. Setting `FilledBars` to `false` produces this style.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Explanation**

* `FilledBars = false` disables the solid circles, leaving only the outlines.  
* All other settings (X‑dimension, data string) stay identical, guaranteeing that both images represent the same data.

## Step 5: Run the program and verify the output

Compile and execute:

```bash
dotnet run
```

You should see console messages confirming the saved files, and the `Barcodes` folder will contain:

* `PostalPlanetFilledBars.png` – a classic filled‑bars Planet barcode.  
* `PostalPlanetEmptyBars.png` – the same data rendered with empty bars.

Open the PNGs in any image viewer. Both images encode the numeric string **123456** and can be scanned by standard postal barcode readers.

## Common questions and edge‑case handling

### What if I need a different data format?

Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric value, Aspose throws an `ArgumentException`. Validate the input before creating the generator:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### How do I change the image size without altering bar thickness?

Use the `Resolution` property or scale the resulting bitmap after saving:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Can I generate other image formats?

Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`, or `Gif`. The API supports all common raster formats.

### What about color customization?

Set `BarColor` and `BackColor` on the `Barcode` parameters:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

These options work for both filled and empty‑bars versions.

## Pro tips for production use

* **Cache the generator** when you need to render many barcodes with the same settings—initializing the object repeatedly adds overhead.  
* **Dispose** of `BarcodeGenerator` objects if you create many in a loop (they implement `IDisposable`).  
* **Validate the output folder** early to avoid runtime exceptions on write‑protected directories.  

## Conclusion

You now know how to **create planet barcode PNG** files in C# and understand **how to generate planet barcode** images with both filled and empty bar styles. The complete, runnable example demonstrates setting up the output directory, configuring the `BarcodeGenerator`, and saving the results as PNG files.

Next, you might explore:

* Adding **human‑readable text** below the barcode (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrating the generated PNGs into a **PDF invoice** using Aspose.PDF.  
* Switching to other postal symbologies such as **IMB** or **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Feel free to experiment with bar thickness, colors, and image resolutions to match your specific application requirements. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}