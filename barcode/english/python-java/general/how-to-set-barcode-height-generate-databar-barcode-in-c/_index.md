---
category: general
date: 2026-10-12
description: How to set barcode height and generate a DataBar barcode in C# using
  Aspose.BarCode. Follow a step‑by‑step guide with complete code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: en
lastmod: 2026-10-12
og_description: How to set barcode height in C# and generate a DataBar barcode with
  Aspose.BarCode. Learn the full code, why each step matters, and how to change barcode
  height.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: How to set barcode height and generate DataBar barcode in C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to set barcode height, generate DataBar barcode in C#
url: /python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set barcode height, generate DataBar barcode in C#

If you need to **how to set barcode** dimensions programmatically, this guide shows you the exact steps. You’ll learn how to generate a DataBar Omni‑directional barcode, adjust its height, and save both versions as PNG files.

Changing a barcode’s bar height is a common requirement when you integrate barcodes into receipts, product labels, or mobile screens. The example below uses the Aspose.BarCode library, which supports the full range of GS1 DataBar symbologies.

## What you’ll achieve

By the end of this tutorial you will be able to:

* **how to set barcode** height for a DataBar Omni‑directional barcode  
* **generate barcode c#** code that creates two images with different heights  
* understand **how to create databar** symbols and why the bar height matters  
* apply **change barcode height** logic without recreating the generator  

No external tools are required beyond the Aspose.BarCode NuGet package and a .NET 6+ runtime.

## Prerequisites

* .NET 6 SDK or later installed  
* Visual Studio 2022 (or any C# editor)  
* Aspose.BarCode for .NET – install via `dotnet add package Aspose.BarCode`  

> **Pro tip:** Use the free trial license from Aspose if you don’t have a commercial key; the API works the same way.

## Step 1: Install the Aspose.BarCode package

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `Aspose.BarCode` namespace, which contains the `BarcodeGenerator` class we’ll use to **generate barcode c#** images.

## Step 2: Create a DataBar barcode generator

The first concrete action for **how to set barcode** parameters is to instantiate `BarcodeGenerator` with the desired symbology and data string.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` produces a compact, omnidirectional DataBar that can be scanned from any angle—ideal for small labels.

## Step 3: Set common barcode parameters (including the initial bar height)

Now we answer **how to set barcode** X‑dimension and bar height before saving the first image.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

The X‑dimension controls the overall width of each bar; a 2‑pixel setting yields a readable, sharp image on most screens. The **change barcode height** step later will reuse the same generator, saving time and memory.

## Step 4: Save the first barcode image (30‑pixel height)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

The file `DatabarHeight30.png` now contains a DataBar barcode with a 30‑pixel bar height.

## Step 5: Change only the bar height to 60 pixels

To demonstrate **change barcode height**, we modify just the `BarHeight` property. All other settings remain unchanged, which is the most efficient way to produce multiple sizes from a single generator.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Step 6: Save the second barcode image (60‑pixel height)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

You now have two PNG files, each with a different bar height but identical data and X‑dimension.

## Full, runnable example

Below is the complete program you can copy‑paste into a new console application (`dotnet new console`) and run immediately.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Expected output

Running the program produces two files in the executable’s working directory:

* `DatabarHeight30.png` – a DataBar barcode with 30‑pixel tall bars.  
* `DatabarHeight60.png` – the same barcode, but each bar is twice as tall.

Both images can be opened in any image viewer or embedded directly into PDFs, HTML pages, or printed labels.

## Why adjusting bar height matters

* **Scanning reliability:** Some scanners struggle with very short bars on low‑resolution media; increasing the height improves detection.  
* **Design constraints:** A mobile app may need a compact barcode (30 px) while a printed receipt may require a larger one (60 px).  
* **Regulatory compliance:** Certain industries mandate a minimum bar height for GS1 DataBar symbols.

By reusing the same `BarcodeGenerator` instance, you avoid the overhead of re‑parsing the data string, which is especially beneficial in high‑throughput environments.

## Common variations and edge cases

| Situation | Recommended tweak |
|-----------|-------------------|
| Need a different X‑dimension | Change `XDimension.Pixels` before the first `Save`. |
| Want a different symbology (e.g., DataBar Stacked) | Use `EncodeTypes.DatabarStacked` when constructing `BarcodeGenerator`. |
| Must embed the barcode in a PDF | Use `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` and add the stream to a PDF library. |
| Running on .NET Framework 4.6 | The same code works; just reference the appropriate Aspose.BarCode assembly. |

## Pro tips for reliable barcode generation

* **Cache the generator** when you generate many barcodes with the same data but different sizes.  
* **


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}