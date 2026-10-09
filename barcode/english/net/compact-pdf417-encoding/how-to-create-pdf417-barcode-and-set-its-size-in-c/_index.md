---
category: general
date: 2026-09-22
description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
  barcode image files with clear step‑by‑step code examples.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: en
lastmod: 2026-09-22
og_description: Create PDF417 barcode in C# quickly. This tutorial shows how to set
  barcode size, enable compact mode, and output PNG images for any .NET project.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Create PDF417 barcode in C# – step-by-step guide
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: How to create PDF417 barcode and set its size in C#
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode and set its size in C#

If you need to **create PDF417 barcode** in C#, this guide shows you how to generate the barcode, control its dimensions, and save the result as an image file. Whether you are building a ticketing system, a logistics label, or a secure credential, mastering the PDF417 format lets you encode large amounts of data in a compact visual form.

In this tutorial you will learn to:

* **Create PDF417 barcode** with the Aspose.BarCode (or any compatible) library.  
* **Set barcode size** by adjusting the X‑dimension and column count.  
* Generate a **barcode image in C#** for PNG, JPEG, or BMP output.  

The example uses the free community edition of Aspose.BarCode for .NET, but the same concepts apply to other libraries that expose similar properties.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed.  
* A C# IDE (Visual Studio, Visual Studio Code, Rider, etc.).  
* The `Aspose.BarCode` NuGet package (`dotnet add package Aspose.BarCode`).  

No additional configuration is required; the library works on Windows, Linux, and macOS.

## Step 1: Create a basic PDF417 barcode and set its size

The first step is to instantiate a `BarcodeGenerator` with the `EncodeTypes.Pdf417` enum and provide the text you want to encode. Then adjust the **X‑dimension** (module width) and the number of **columns** to control the overall size.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Why these settings matter**

* `XDimension.Pixels` determines the narrowest bar width. Smaller values produce a tighter barcode, while larger values increase readability on low‑resolution scanners.  
* `Pdf417.Columns` influences the barcode’s aspect ratio. Fewer columns make the barcode taller; more columns flatten it. Adjusting columns is the primary way to **set barcode size** without changing the encoded data.

After running the code, you will find `Pdf417Basic.png` in the specified folder. The image looks similar to the screenshot below:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Step 2: Create a compact PDF417 barcode (truncate mode) with the same size

Sometimes you need a shorter barcode for limited space. PDF417 offers a *truncate* (compact) mode that removes the stop pattern and reduces the overall height. The property `Truncate` toggles this behavior.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**What changes with `Truncate = true`?**

* The barcode becomes roughly 15‑20 % shorter vertically, which is useful for small labels or mobile screens.  
* The data remains fully recoverable; most modern scanners understand truncate mode automatically.

The resulting `CompactPdf417.png` appears as a slimmer version of the basic barcode.

## Step 3: Create a Micro PDF417 barcode, adjust columns, and save it

Micro PDF417 is a newer, high‑density variant designed for very small spaces (e.g., ID cards). It supports 1‑4 columns only, and the library exposes the same `XDimension` property for size control.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Key points for Micro PDF417**

* The `EncodeTypes.MicroPdf417` enum selects the micro variant automatically.  
* Because the symbol is denser, you may need a higher DPI printer (300 dpi or more) to keep the barcode readable.  
* Adjusting the column count is the only size knob available; the library still respects `XDimension`.

## How to set barcode size for different output formats

The examples above use PNG, but the same `Save` method works with JPEG, BMP, or TIFF. If you need a specific image dimension (e.g., 300 × 150 px), combine `XDimension` with `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Increasing `ImageResolution` while scaling `XDimension` preserves visual quality on high‑resolution prints.

## Common pitfalls and pro tips

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode appears blurry on screen | Low DPI combined with small `XDimension` | Increase `ImageResolution` and/or `XDimension.Pixels` |
| Scanner cannot read truncate mode | Older scanner firmware lacks support | Use the full (non‑truncated) mode for legacy hardware |
| Micro PDF417 is unreadable | Printed at < 300 dpi or with insufficient contrast | Print on matte paper at 300 dpi or higher, ensure dark foreground |
| Output file is corrupted | Missing write permission to the target folder | Verify `YOUR_DIRECTORY` exists and is writable |

**Pro tip:** Always generate the barcode as a PNG when you need lossless quality for further processing (e.g., embedding into PDFs). PNG preserves exact pixel values, whereas JPEG introduces compression artifacts that can affect barcode readability.

## Full, runnable example

Below is a complete console application that demonstrates all three barcode types in a single run. Copy the code into a new .NET console project and execute it.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Expected output**

Running the program creates three PNG files inside a `Barcodes` folder:

* `Pdf417Basic.png` – a standard PDF417 barcode with three columns.  
* `CompactPdf417.png` – the same data in truncate (compact) mode, slightly shorter.  
* `MicroPdf417.png` – a high‑density Micro PDF417 variant with four columns.

Open any image with an image viewer; you should see the distinctive stacked


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}