---
category: general
date: 2026-09-19
description: Create PDF417 barcode in C# and learn how to generate barcode image,
  set barcode dimensions, and save as PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: en
lastmod: 2026-09-19
og_description: Create PDF417 barcode in C# and discover how to generate barcode image,
  set barcode dimensions, and save it as a PNG file.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Create PDF417 barcode and export PNG in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: How to create PDF417 barcode and export PNG in C#
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode and export PNG in C#

If you need to **create PDF417 barcode** in a .NET application, this guide shows you how to generate a barcode image, adjust its dimensions, and save it as a PNG file. You’ll see a complete, runnable example that uses the Aspose.BarCode library, so you can copy the code directly into your own project.

Generating a barcode image is a common requirement for ticketing systems, inventory tracking, and mobile boarding passes. By the end of this tutorial you will understand **how to generate barcode image**, **how to set barcode dimensions**, and **how to create barcode PNG** files that meet your visual quality standards.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code also works with .NET Framework 4.7+).
* A development environment such as Visual Studio 2022 or VS Code.
* A valid license for the **Aspose.BarCode for .NET** library (the free trial works for this example).
* Basic familiarity with C# syntax.

Install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the project and import namespaces

Create a new console application or add the code to an existing project. Import the required namespaces at the top of the file:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

These namespaces give you access to the `BarcodeGenerator` class and the `EncodeTypes` enumeration.

## Step 2: How to create PDF417 barcode – basic generator configuration

The first operation is to instantiate a `BarcodeGenerator` with the `Pdf417` encode type and the text you want to encode. This object represents the barcode you will later render.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*Why this matters*: `EncodeTypes.Pdf417` tells the library to use the PDF417 symbology, which is a stacked linear barcode capable of storing large amounts of data. The second argument (“Sample”) is the payload that will appear when the barcode is scanned.

## Step 3: How to set barcode dimensions – fine‑tuning density and layout

A PDF417 barcode consists of rows and columns of modules. Adjusting the X‑dimension (module width) and the number of rows/columns lets you control the visual density and the overall size of the image.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*Why this matters*:  
* **X‑dimension** determines how wide each tiny square (module) is. A smaller value yields a more compact barcode but may be harder for low‑resolution scanners.  
* **Columns** and **Rows** affect the data capacity and the physical shape. Increasing columns makes the barcode wider; increasing rows makes it taller. You can experiment with values up to the limits shown in the comments.

**Pro tip**: If the barcode looks too dense on a high‑DPI screen, increase `XDimension.Pixels` to 3 or 4. Conversely, for a small label, you might set it to 1 pixel and reduce the column count.

## Step 4: How to generate barcode image – rendering to an in‑memory bitmap

After configuring the generator, you can render the barcode to an image object. This step is optional if you only need to save the file directly, but exposing the bitmap lets you apply further processing (e.g., adding a logo or drawing a border).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` returns a `System.Drawing.Image` that you can manipulate with GDI+ if desired.

## Step 5: How to create barcode PNG – saving the final image file

Finally, write the image to disk in PNG format. PNG preserves lossless quality, which is ideal for scanning applications.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*Why this matters*: The `Save` method handles the encoding and file I/O for you. Using `BarCodeImageFormat.Png` ensures the output is a portable, lossless image that works across browsers and mobile devices.

### Full runnable example

Below is the complete program that you can paste into `Program.cs` and run. Replace `YOUR_DIRECTORY` with an existing folder on your machine.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Running the program produces a PNG file that looks like this:

![Generated PDF417 barcode example](https://example.com/placeholder-image.png "PDF417 barcode generated with custom dimensions saved as PNG")

*Alt text*: **Sample PDF417 barcode generated with C# showing custom dimensions saved as PNG** – this satisfies the **create PDF417 barcode** requirement for image accessibility.

## Common variations and edge cases

| Situation | Recommended adjustment |
|-----------|------------------------|
| **Very small label** (e.g., 1 cm × 2 cm) | Set `XDimension.Pixels = 1` and reduce `Columns` to 2‑3. Verify scanner readability. |
| **High‑resolution print** (300 dpi or more) | Increase `XDimension.Pixels` to 3‑4 and optionally raise `Rows` for more data capacity. |
| **Need a different image format** (JPEG, BMP) | Change `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp`. |
| **Embedding in a PDF** | Use `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` instead of PNG. |
| **Dynamic data** (user input) | Replace the static `"Sample"` string with a variable, e.g., `userInput`. Ensure the text length does not exceed PDF417 limits (≈ 1 800 characters). |

## Troubleshooting checklist

* **Blank image** – Verify that the output directory exists and the application has write permission.  
* **Barcode not scannable** – Increase `XDimension.Pixels` or add more columns/rows; low contrast backgrounds can also cause failures.  
* **Unexpected size** – Double‑check the `Columns` and `Rows` values; the library respects the maximum limits shown in comments.  

## Next steps

Now that you can **create PDF417 barcode**, consider exploring these related topics:

* **How to generate barcode image** in other formats such as SVG for web‑scalable graphics.  
* **How to set barcode dimensions** for QR codes and DataMatrix symbologies.  
* **How to create barcode PNG** with custom colors or embedded logos using `System.Drawing`.  

These extensions let you build a full‑featured barcode generation service that can serve mobile apps, web portals, and desktop utilities alike.

---

*You have learned how to create a PDF417 barcode, customize its dimensions, render a barcode image, and save it as a PNG file using C#. Apply the patterns shown here to other barcode types and image formats to broaden your automation capabilities.*


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}