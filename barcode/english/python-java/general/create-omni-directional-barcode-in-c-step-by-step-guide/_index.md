---
category: general
date: 2026-07-15
description: create omni-directional barcode in C# quickly with Aspose.BarCode – learn
  how to generate barcode C# with adjustable bar height and X‑dimension.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: en
lastmod: 2026-07-15
og_description: create omni-directional barcode in C# with Aspose.BarCode. Master
  how to generate barcode C# by tweaking XDimension and BarHeight for perfect results.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: create omni-directional barcode in C# – Complete Programming Walkthrough
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: create omni-directional barcode in C# – Step‑by‑Step Guide
url: /python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create omni-directional barcode in C# – Step‑by‑Step Guide

Ever wondered how to generate a barcode C# that complies with the GS1 DataBar Omni‑Directional symbology? You’re not alone. In this tutorial we’ll **create omni-directional barcode** images from scratch, tweak the X‑dimension, and play with bar height—all using the Aspose.BarCode library.

We’ll walk through a real‑world scenario: you need a compact, high‑density barcode for a retail label, and you want total control over its visual size. By the end you’ll have two PNG files—one with a 30 px bar height and another with 60 px—ready to drop into any printing workflow.

## Prerequisites

- .NET 6 (or any recent .NET runtime) installed on your machine.  
- Visual Studio 2022 or VS Code—your favorite IDE will do.  
- A free Aspose.BarCode for .NET NuGet package (`Aspose.BarCode`).

No other dependencies are required. If you’ve never touched NuGet before, just open the Package Manager Console and run:

```powershell
Install-Package Aspose.BarCode
```

## create omni-directional barcode – Understanding the Basics

The **GS1 DataBar Omni‑Directional** symbology is designed for scanning on any orientation, making it perfect for shelf‑edge labels. When you call `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, the library does the heavy lifting: it encodes the data, applies the symbology rules, and prepares a raster image.

> **Pro tip:** Always wrap the raw data in the appropriate Application Identifier (AI) format, e.g. `"(01)12345678901231"` for a GTIN‑14. This tells the scanner what the digits represent.

## Step 1 – Set Up the Barcode Generator (how to generate barcode c#)

First we create the generator object. This is the cornerstone of **how to generate barcode c#** with Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

The `EncodeTypes.DatabarOmniDirectional` enum value tells the engine which symbology to use. The second argument is the raw data string, already wrapped in the GTIN AI.

## Step 2 – Adjust the X‑Dimension (barcode XDimension)

The **barcode XDimension** controls the width of the smallest bar. A value of 2 px is a good balance between readability and compactness for most label printers.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

If you need a finer or coarser look, just change the number. Remember: the X‑dimension is the fundamental unit; all other bar widths are multiples of this value.

## Step 3 – Create the First Image with a 30 px Bar Height (barcode BarHeight)

Now we set the **barcode BarHeight** to 30 px and save the image. This produces a modest‑sized barcode that fits nicely on a standard label.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

The `Save` method writes a PNG file to disk. You can swap `BarCodeImageFormat.Jpeg` if you prefer JPEG output.

## Step 4 – Increase Bar Height to 60 px for Larger Labels (barcode BarHeight)

Sometimes a larger barcode is required—perhaps for a shelf label that sits further from the scanner. Let’s double the height.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Notice we **don’t** need to recreate the generator; we just tweak the parameter and reuse the same object. This saves memory and keeps the code tidy.

## Step 5 – Save the Second Image (how to generate barcode c#)

Finally, we save the second PNG. You now have two files that differ only in bar height.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Expected output

- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.  
- `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.

Open the files in any image viewer; you’ll see crisp, scannable bars that respect the GS1 DataBar Omni‑Directional specification.

## Common Questions & Edge Cases

### What if I need a different X‑dimension?

Simply assign a new value before calling `Save`. For ultra‑high‑density printing you might go down to 1 px, but test with your scanner first—some devices struggle with sub‑2 px bars.

### Can I add human‑readable text below the barcode?

Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`. This is handy for retail environments where the numeric GTIN must be visible.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Is PNG the best format for printing?

PNG is lossless, which preserves the sharp edges needed for barcode scanners. If your downstream system expects a different format (TIFF, BMP), just change the `BarCodeImageFormat` enum.

## Full Working Example (create omni-directional barcode)

Below is the complete, ready‑to‑run program. Copy‑paste it into a new console project and hit **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Run the program, check the output folder, and you’ll see the two PNG files exactly as described.

## Recap

We’ve shown **how to generate barcode C#** code that creates a **create omni-directional barcode** using Aspose.BarCode. By adjusting the **barcode XDimension** and **barcode BarHeight**, you gain fine‑grained control over the visual size without sacrificing scan reliability.

## What’s Next?

- Experiment with other **GS1 DataBar Omni-Directional** settings like `Color` or `Margin`.  
- Combine multiple barcodes on a single canvas using `Graphics` for complex label designs.  
- Integrate the generator into a web API so your e‑commerce platform can emit barcodes on demand.

Got a twist you’d like to share? Drop a comment, and let’s keep the conversation going. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}