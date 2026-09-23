---
category: general
date: 2026-09-23
description: c# barcode generator tutorial shows how to generate barcode images with
  custom aspect ratios using the Aspose.BarCode library.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: en
lastmod: 2026-09-23
og_description: c# barcode generator guide walks you through how to generate barcode
  images, adjust aspect ratios, and export PNG files using Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Create high‑quality barcodes with a C# barcode generator
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: How to use a C# barcode generator for DataBar codes
url: /python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use a C# barcode generator for DataBar codes

If you need a **c# barcode generator** that can produce DataBar stacked Omni‑Directional symbols, this guide gives you a complete, ready‑to‑run solution. You’ll see how to generate barcode images, control the X‑dimension, and change the aspect ratio without leaving the IDE.

Generating barcodes is a common requirement for inventory systems, shipping labels, and point‑of‑sale applications. By the end of this tutorial you can create PNG files with any aspect ratio you choose, and you’ll understand how to adapt the code for other barcode types.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any C# editor you prefer)  
* A NuGet reference to **Aspose.BarCode** – the library that powers the `BarcodeGenerator` class  

You do not need a separate graphics library; Aspose.BarCode handles image encoding internally.

## Step 1: Install the Aspose.BarCode NuGet package

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version of the library to your project file, making the `BarcodeGenerator` class available for use.

## Step 2: Define the output folder

Choose a folder where the generated PNG files will be saved. Using an absolute or relative path works the same way, but a relative path keeps the project portable.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Creating the directory programmatically prevents runtime errors if the folder is missing.

## Step 3: Instantiate the C# barcode generator with sample data

The `BarcodeGenerator` constructor requires two arguments: the barcode type and the data string. For a DataBar stacked Omni‑Directional symbol you use `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

The data string follows the GS1 Application Identifier format. The `EncodeTypes` enum contains over 150 barcode standards; you can switch to another type by changing the enum value.

## Step 4: Set the X‑dimension (pixel size) for the barcode

The X‑dimension controls the width of the narrowest bar. A pixel value of 2 yields a crisp, high‑resolution image suitable for most screens.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Adjusting the X‑dimension is optional, but it gives you fine‑grained control over the visual density of the barcode.

## Step 5: Generate a barcode with an aspect ratio of 15 and save it as PNG

The `AspectRatio` property belongs to the `DataBar` sub‑object. Changing this value stretches or compresses the barcode vertically while preserving the encoded data.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The `Save` method writes the barcode to the specified file path. The `BarCodeImageFormat.Png` enum ensures lossless compression.

![c# barcode generator output example](generated_barcode_example.png)

*Image: barcode generated with an aspect ratio of 15.*

## Step 6: Change the aspect ratio to 30 and generate a second image

Reusing the same `BarcodeGenerator` instance avoids allocating a new object. Simply update the `AspectRatio` and call `Save` again.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Now you have two PNG files that differ only in vertical scaling. This technique is useful when you need the same data rendered for different label sizes.

## Common variations and edge cases

### Switching to another barcode type

If you need a QR code, Code 128, or PDF417, replace the enum value in the constructor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

All other configuration steps (X‑dimension, saving) remain identical.

### Handling unsupported characters

The `BarcodeGenerator` validates the input string against the selected symbology. Supplying an illegal character throws an `ArgumentException`. Wrap the creation in a try‑catch block to provide a friendly error message:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exporting to other image formats

Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument of `Save` accordingly:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### High‑resolution output for printing

When printing on high‑DPI printers, increase the X‑dimension and optionally set the `Resolution` property:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

These settings produce larger files but maintain crisp edges on physical media.

## Expected output

Running the complete program creates the following files inside `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – a standard‑height DataBar code  
* `DatabarAspectRatio30.png` – a vertically stretched version  

Both images contain the same encoded GS1 data, and you can verify them with any barcode scanner app.

## Full source code

Copy the code below into a new console project (`dotnet new console`) and run it. The program prints status messages to the console and writes the PNG files to disk.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Running the program produces console output similar to:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusion

You now have a **c# barcode generator** that can create DataBar stacked Omni‑Directional symbols, adjust the X‑dimension, and export PNG files with custom aspect ratios. The same pattern works for any other barcode symbology supported by Aspose.BarCode, making it easy to integrate barcode creation into inventory, shipping, or point‑of‑sale solutions.

If you want to explore further, try:

* Generating QR codes or PDF417 symbols (`how to generate barcode` for mobile apps)  
* Exporting to SVG for scalable web graphics  
* Embedding the generated images directly into PDF invoices using Aspose.PDF  

Experiment with different `AspectRatio` values, X‑dimension sizes, and output formats to match the exact


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}