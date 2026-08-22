---
category: general
date: 2026-08-22
description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set barcode
  size, adjust columns, and enable compact mode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: en
lastmod: 2026-08-22
og_description: Generate PDF417 barcode in C# with Aspose.BarCode. This guide shows
  how to set barcode size, control columns, and enable compact mode for a smaller
  image.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Generate PDF417 barcode in C# – set size, columns, and compact mode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: How to generate PDF417 barcode in C# and set barcode size
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode in C# and set barcode size

If you need to **generate PDF417 barcode** in a .NET application, this guide walks you through the complete process. You’ll see exactly **how to generate PDF417** with Aspose.BarCode, adjust the **set barcode size**, and produce a compact PNG that can be embedded in reports or mobile apps.

Creating a barcode doesn’t require a separate graphics editor. By the end of this tutorial you will have a fully functional C# method that produces a PDF417 image with the exact dimensions you need, ready for downstream processing.

## What you’ll learn

* Install and reference the Aspose.BarCode library.
* Create a PDF417 barcode generator and specify the encoded text.
* **Set barcode size** by configuring X‑dimension and column count.
* Enable compact (truncated) mode to shrink the symbol.
* Save the result as a PNG file.
* Troubleshoot common issues such as unreadable codes and oversized images.

### Prerequisites

* .NET 6.0 or later (the API works with .NET Framework 4.6+ as well).
* Basic familiarity with C# and Visual Studio (or any C# IDE).
* A valid Aspose.BarCode license (the free evaluation works for testing).

> **Pro tip:** If you plan to generate many barcodes in a loop, reuse a single `BarcodeGenerator` instance and only change the `CodeText` property. This reduces memory allocations.

## Generate PDF417 barcode with Aspose.BarCode

The first step is to instantiate the `BarcodeGenerator` for the PDF417 symbology. This object is the entry point for all barcode operations.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Why this matters*: `EncodeTypes.Pdf417` tells the library to use the PDF417 standard, which supports large data volumes and error correction. The constructor also accepts the data you want to encode, eliminating the need for a separate `CodeText` assignment later.

## Set barcode size and column count

PDF417 symbols consist of rows and columns of small rectangular modules. Controlling the module width (X‑dimension) and the number of columns lets you fine‑tune the overall dimensions.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explanation*:  
* **X‑dimension** (`Pixels`) determines how wide each module is. Smaller values produce a tighter barcode, while larger values increase readability on low‑resolution scanners.  
* **Columns** control the horizontal layout. Fewer columns make the barcode taller; more columns make it wider. Adjust these two settings together to achieve the exact **set barcode size** you need.

## Enable compact mode for a smaller barcode

PDF417 includes a “compact” (or truncated) mode that removes unnecessary padding and reduces the overall footprint. This is especially useful when you have limited screen real estate.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Why enable truncation?*  
When `Truncate` is `true`, the generator omits the stop pattern and some error‑correction codewords that are not required for most scanning scenarios. The resulting image is roughly 15‑20 % smaller without sacrificing data integrity for typical use cases.

## Save the barcode as a PNG image

After configuring size and mode, write the barcode to disk. PNG is lossless, ensuring that the module edges remain sharp.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

The file `CompactPdf417.png` will contain a crisp PDF417 symbol that matches the dimensions you set in the previous steps.

### Expected output

Opening the saved PNG should display a vertical‑oriented PDF417 barcode consisting of three columns, each module 2 px wide, and a total size of roughly **120 × 240 px** (width × height). Scanning the image with any standard PDF417 reader returns the original text “Sample text for PDF417”.

## Common pitfalls and how to avoid them

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Barcode is unreadable | X‑dimension too small for the scanner | Increase `XDimension.Pixels` to 3 or 4 |
| Image is too wide for UI | Too many columns set | Reduce `Pdf417.Columns` or enable `Truncate` |
| Exception `ArgumentOutOfRangeException` | Negative or zero column count | Ensure `Columns` is a positive integer (minimum 1) |
| PNG file is empty | Output path does not exist or lacks write permission | Verify the directory exists and the app has write rights |

> **Pro tip:** Use `barcodeGenerator.ValidateParameters()` before calling `Save()` to catch configuration errors early.

## Full, runnable example

Below is a self‑contained console program that incorporates all the steps above. Copy it into a new C# project, restore the Aspose.BarCode NuGet package, and run it to see the result.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Running the program** produces `CompactPdf417.png` in the executable’s working directory. Scan the image with a mobile app (e.g., “Barcode Scanner”) to verify that the encoded text matches the source string.

## Next steps and related topics

* **Increase error correction level** – adjust `Pdf417.ErrorLevel` for environments with noisy scans.  
* **Change orientation** – set `Pdf417.Rotate` to `RotationAngle.Rotate90` if you need a horizontal layout.  
* **Embed the barcode in a PDF** – combine Aspose.PDF with Aspose.BarCode to place the image directly into a document.  
* **Generate other 2‑D barcodes** – the same `BarcodeGenerator` class supports DataMatrix, QR, and Aztec codes; just swap `EncodeTypes.Pdf417` for the desired symbology.

By mastering **generate PDF417 barcode** techniques, you can automate ticketing, inventory labeling, and secure data transmission across a wide range of .NET applications.

## Conclusion

You now know how to **generate PDF417 barcode** in C#, precisely **set barcode size**, configure columns, enable compact mode, and save the result as a PNG. Apply these settings to fit any UI constraint or scanning requirement, and extend the approach to other barcode formats as needed. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}