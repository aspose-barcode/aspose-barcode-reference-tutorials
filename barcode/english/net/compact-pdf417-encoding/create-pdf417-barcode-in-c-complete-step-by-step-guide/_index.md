---
category: general
date: 2026-07-18
description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
  set parameters, and save image files – includes AI 10 handling.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: en
lastmod: 2026-07-18
og_description: Create PDF417 barcode in C# with a full walkthrough. Discover how
  to generate barcode, adjust settings, and save images while handling AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Create PDF417 Barcode in C# – Fast, Flexible, Full‑Code Example
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
url: /net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide

Ever needed to **create pdf417 barcode** but weren’t sure which library or settings to pick? You’re not alone—many developers hit that wall when they first dabble with GS1‑Micro‑PDF417. The good news is that with a few lines of C# you can spin up a perfectly‑formatted barcode, tweak its appearance, and drop the image straight to disk.

In this tutorial we’ll walk through **how to generate barcode** using the Aspose.BarCode library, show **how to set parameters** like X‑dimension and column count, and demonstrate **how to save image** files for both AI 10 and AI 21 variations. By the end you’ll have a reusable snippet that you can drop into any .NET project.

## Prerequisites

Before we dive in, make sure you have:

- .NET 6+ or .NET Framework 4.7.2 (any recent runtime works)
- Visual Studio 2022 or your favorite C# editor
- The **Aspose.BarCode for .NET** NuGet package (`Install-Package Aspose.BarCode`)
- A writable folder on disk where the PNG files will land

That’s it—no extra tools, no complex configuration. Ready? Let’s roll.

## Step 1: Create PDF417 Barcode with GS1‑Micro Format

The first thing we do is **create pdf417 barcode** object and feed it the initial AI data. In GS1‑Micro‑PDF417 the AI 10 (batch/lot number) is often the starting point, so we’ll encode it right away.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Why this matters:** The `EncodeTypes.GS1MicroPdf417` tells the library to follow the GS1‑Micro spec, which automatically prefixes the AI brackets. If you skip this, you’ll end up with a generic PDF417 that may not be scannable in retail environments.

## Step 2: How to Set Parameters for the Barcode

Now that we have a barcode instance, we need to fine‑tune its visual characteristics. This is where **how to set parameters** comes into play. We’ll adjust three common settings:

1. **X‑dimension** – controls the width of the smallest bar (in pixels)
2. **Column count** – influences the overall shape; fewer columns = taller barcode
3. **IsLinked** – enables the optional link module that ties the barcode to the data string

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Pro tip:** If you’re targeting mobile scanning, bump the X‑dimension up to 3‑4 pixels; larger modules survive low‑resolution cameras better.

## Step 3: How to Save Image – First Version (AI 10)

With the generator configured, we can finally **how to save image**. The `Save` method writes the barcode to a file in the format you specify. Here we use PNG because it preserves crisp edges without compression artifacts.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

At this point you should see a file named `GS1MicroPdf417_AI10.png` in your `outputDir`. Open it with any image viewer—you’ll see a clean, high‑contrast PDF417 ready for printing.

## Step 4: Switch to a Different AI (AI 21) and Save Again

Often you need to encode a different application identifier, such as AI 21 (serial number). Changing the `CodeText` property is all that’s required. This demonstrates **barcode ai 10** versus **barcode ai 21** handling in one go.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **What if you need more AIs?** Just concatenate them in the same string, e.g., `"(10)ABCD(21)12345(240)XYZ"`. The library parses the brackets automatically.

## Full Working Example

Putting it all together, here’s a self‑contained program you can copy‑paste into a console app:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Expected output:** Two PNG files appear in `C:\Barcodes\`—`GS1MicroPdf417_AI10.png` and `GS1MicroPdf417_AI21.png`. Both contain a scannable PDF417; the first encodes AI 10, the second AI 21.

## Common Pitfalls & How to Avoid Them

- **Missing folder permissions:** If `Save` throws an `UnauthorizedAccessException`, double‑check that the path exists and your app has write rights.
- **Incorrect AI formatting:** Forgetting the parentheses (`(10)`) will cause the barcode to be treated as plain data, breaking GS1 validation.
- **Too small X‑dimension:** Bars thinner than 1 pixel may disappear when the image is resized. Stick to at least 2 pixels for screen display.

## Next Steps & Related Topics

Now that you know **how to generate barcode**, **how to set parameters**, and **how to save image**, you might want to explore:

- Adding **human‑readable text** below the barcode (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Exporting to **PDF** instead of PNG (`BarCodeImageFormat.Pdf`)
- Integrating the barcode generation into an **ASP.NET Core API** for on‑the‑fly image creation

Each of those topics builds directly on the foundation we laid out in this guide.

---

### Quick Recap

- **Create pdf417 barcode** using `BarcodeGenerator` with `EncodeTypes.GS1MicroPdf417`
- **How to set parameters** like X‑dimension, columns, and linking
- **How to save image** as PNG for both AI 10 and AI 21 variants
- Handled **barcode ai 10** and swapped to **barcode ai 21** with a single property change

Give it a spin, tweak the settings, and you’ll have a robust barcode engine ready for production. Got questions or need a deeper dive? Drop a comment below—happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}