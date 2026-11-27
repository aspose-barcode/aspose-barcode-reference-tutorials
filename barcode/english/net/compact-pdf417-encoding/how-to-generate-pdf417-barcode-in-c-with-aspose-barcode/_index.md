---
category: general
date: 2026-11-27
description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
  dimensions, set column count, and save as PNG in a few lines of code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: en
lastmod: 2026-11-27
og_description: Generate PDF417 barcode in C# instantly. This tutorial shows how to
  configure dimensions, column count, and save the result as a PNG image.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generate PDF417 barcode in C# – quick guide with Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: How to generate PDF417 barcode in C# with Aspose.BarCode
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode in C# with Aspose.BarCode

If you need to **generate PDF417 barcode** in a .NET application, this guide shows you a concise, end‑to‑end solution. You’ll see how to create the barcode, fine‑tune its size, and write the result to a PNG file—all with the Aspose.BarCode library.

Generating a PDF417 barcode is common when you have to encode large amounts of data for scanning on mobile devices, boarding passes, or inventory tags. By the end of this tutorial you’ll have a ready‑to‑run console program that produces a high‑quality PNG image.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A recent version of **Aspose.BarCode for .NET** (the NuGet package `Aspose.BarCode`)  
* An IDE or editor (Visual Studio, VS Code, Rider, etc.)  

The code works on Windows, Linux, and macOS because Aspose.BarCode is cross‑platform.

## Step 1: Create a new console project

Open a terminal and run:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

This creates a minimal C# project named **Pdf417Demo** and adds the `Aspose.BarCode` dependency.

## Step 2: Write the barcode generation code

Open **Program.cs** and replace its contents with the following:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Why each line matters

* **BarcodeGenerator** – the core class that creates a barcode image. Passing `EncodeTypes.Pdf417` selects the PDF417 symbology.
* **XDimension.Pixels** – determines the smallest bar width. Smaller values shrink the image; larger values improve readability on low‑resolution scanners.
* **Pdf417.Columns** – controls the number of data columns. More columns produce a shorter but taller barcode; fewer columns make it wider.
* **ErrorCorrectionLevel** – higher levels add redundant data, making the barcode tolerant to damage at the cost of size.
* **Save(..., BarCodeImageFormat.Png)** – writes the image to disk in PNG format, a loss‑less format ideal for further processing or embedding in documents.

## Step 3: Build and run the program

From the terminal, execute:

```bash
dotnet run
```

You should see:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

A file named **Pdf417Basic.png** appears in the project folder. Opening it shows a clear PDF417 barcode that encodes the text *“Sample text for PDF417 barcode”*.

![Generated PDF417 barcode saved as a PNG file](pdf417-barcode-example.png "Generated PDF417 barcode in PNG format")

*Image alt text: screenshot of a generated PDF417 barcode saved as a PNG file, demonstrating the result of the generate PDF417 barcode tutorial.*

## Step 4: Common variations and edge cases

### Changing the encoded data

Replace the second argument of `BarcodeGenerator` with any UTF‑8 string, e.g.:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

The generator automatically splits the data across rows and columns.

### Adjusting image size without losing quality

If you need a larger image for printing, increase `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Handling very long inputs

PDF417 can encode up to 1 850 characters. For extremely long strings, you may want to increase the column count:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

If the content exceeds the maximum capacity, Aspose.BarCode throws an `ArgumentException`. Wrap the generation code in a try‑catch block to present a friendly error message.

### Saving in other formats

Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like this:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Step 5: Verify the barcode

You can confirm that the barcode is valid by scanning it with any PDF417 reader app (e.g., smartphone camera apps that support barcode scanning). The decoded text should match the string you passed to the generator.

If the scan fails:

* Ensure the image is not compressed (use PNG or lossless SVG).  
* Verify that `ErrorCorrectionLevel` is high enough for the intended environment.  
* Check that the barcode dimensions are appropriate for the scanner’s resolution.

## Conclusion

You now know how to **generate PDF417 barcode** in C# using Aspose.BarCode, customize its dimensions, set the column count, and export the result as a PNG image. This approach works for a wide range of scenarios, from mobile ticketing to inventory management.

Next, you might explore:

* **Reading** a PDF417 barcode with `BarCodeReader`.  
* Generating other symbologies such as QR Code or DataMatrix.  
* Embedding the PNG into PDFs, reports, or web pages.  

Feel free to experiment with different error‑correction levels, image formats, and data payloads to suit your project’s needs. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# with Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [How to generate PDF417 barcode and render it as PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [How to generate PDF417 barcode in C# and set barcode size](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}