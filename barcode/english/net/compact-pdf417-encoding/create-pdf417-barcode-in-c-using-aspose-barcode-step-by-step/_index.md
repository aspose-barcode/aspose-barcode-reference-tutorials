---
category: general
date: 2026-10-18
description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This tutorial
  covers basic, compact, macro and micro PDF417 generation with full code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: en
lastmod: 2026-10-18
og_description: Create PDF417 barcode in C# with Aspose.BarCode. Follow this guide
  to generate basic, compact, macro and micro PDF417 barcodes step by step.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Create PDF417 barcode in C# – complete Aspose.BarCode tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
url: /net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide

If you need to **create PDF417 barcode** in a .NET application, this tutorial walks you through the complete process. You’ll see how to generate a basic barcode, enable compact mode, add macro metadata, and produce a micro variant—all with clear explanations and runnable code.

Generating PDF417 barcodes is common in logistics, ticketing, and document management. By the end of this guide you’ll be able to integrate barcode creation into any C# project without external tools.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later (the code also works with .NET Framework 4.7+)
* Visual Studio 2022 or any C# IDE
* **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Write permission to a folder where the generated PNG files will be saved

No additional configuration is required; the library handles all low‑level encoding details.

## Step 1: Create a basic PDF417 barcode

The first step establishes a regular PDF417 barcode with custom size and column count.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Why these settings matter**

* `XDimension.Pixels` controls the physical size of each barcode element. A value of 2 produces a clear image on most screens and printers.
* `Pdf417.Columns` determines how many data columns the barcode contains. Fewer columns reduce width; more columns increase data capacity.

Running the code creates `Pdf417Basic.png`, which looks like a typical PDF417 symbol with three data columns and a full metadata column on the right side.

## Step 2: Enable compact (truncated) mode

Compact mode removes the right‑hand metadata column, making the barcode narrower. This is useful when space is limited but the data can be reconstructed from the remaining rows.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Why truncate?**  
When `Truncate` is `true`, the generator omits the optional right‑hand column that stores error‑correction and file‑level metadata. The resulting barcode occupies fewer columns while still being scannable by most PDF417 readers.

## Step 3: Create a Macro PDF417 barcode with file‑level metadata

Macro PDF417 extends the standard format with segment identifiers, allowing a large document to be split into multiple barcodes. This is handy for encoding long strings or multi‑page files.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Explanation of macro fields**

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | Unique identifier for the whole file; all segments share this value. |
| `MacroPdf417SegmentID` | Index of the current segment (starts at 1). |
| `MacroPdf417SegmentsCount` | Total number of segments that compose the complete data set. |

A scanner that understands Macro PDF417 can reassemble the original data by reading all segments and using these identifiers.

## Step 4: Create a Micro PDF417 barcode for short data

Micro PDF417 is a compact version designed for small payloads (up to 90 characters). It limits the column range to 1‑4, making the barcode suitable for tiny labels or devices with limited display area.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**When to use Micro PDF417**  
Use this variant when the data payload is short and you need the smallest possible barcode. It is ideal for inventory tags, access cards, or any scenario where screen real estate is at a premium.

## Full working example

Below is a self‑contained console application that generates all four barcode types in one run. Copy the code into a new C# project, replace `YOUR_DIRECTORY` with an existing folder path, and run it.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Expected output**

Running the program creates four PNG files in the specified folder:

* `Pdf417Basic.png` – standard barcode with three columns
* `CompactPdf417.png` – same data, truncated right‑hand column
* `MacroPdf417.png` – macro barcode containing segment metadata
* `MicroPdf417.png` – compact micro barcode for short strings

Open any image with an image viewer; you’ll see the distinct PDF417 patterns. Scanning them with a mobile barcode reader (e.g., ZXing, Scandit) returns the original text strings.

## Common questions and tips

* **What if the barcode looks blurry?**  
  Increase `XDimension.Pixels` to 3 or 4. Larger module sizes produce higher‑resolution images, at the cost of a bigger file.

* **Can I output SVG instead of PNG?**  
  Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Svg` in the `Save` calls.

* **Do I need to set error‑correction level manually?**  
  Aspose.BarCode chooses an optimal level automatically. For specialized use‑cases you can adjust `Pdf417.ErrorCorrectionLevel`.

* **How to embed the barcode in a PDF document?**  
  Use `Aspose.Pdf` to add the generated PNG or SVG as an image element on a PDF page.

* **Is the library thread‑safe?**  
  Each `BarcodeGenerator` instance is independent; you can create generators on multiple threads without shared state.

## Conclusion

You now know how to **create PDF417 barcode** in C# using Aspose.BarCode, covering basic, compact, macro, and micro variants


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}