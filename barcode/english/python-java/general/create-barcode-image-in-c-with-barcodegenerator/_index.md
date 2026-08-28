---
category: general
date: 2026-08-12
description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
  DataBar, control barcode image size, and create multiple barcodes efficiently.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: en
lastmod: 2026-08-12
og_description: Create barcode image in C# with BarCodeGenerator. This tutorial shows
  step‑by‑step how to generate DataBar codes, adjust barcode image size, and produce
  multiple barcodes.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Create barcode image in C# – complete BarCodeGenerator guide
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Create barcode image in C# with BarCodeGenerator
url: /python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode image in C# with BarCodeGenerator

If you need to **create barcode image** in a .NET application, this guide shows you exactly how to do it with the `BarCodeGenerator` class. Whether you are building a retail POS system or an inventory‑tracking tool, you’ll learn to generate DataBar symbols, control the barcode image size, and produce several barcodes in one run.

You’ll also discover how the **barcode generator c#** API lets you tweak dimensions, switch output formats, and handle edge cases such as invalid data strings. By the end of the tutorial you can confidently **create multiple barcodes** without writing repetitive code.

## Prerequisites

Before you start, make sure you have:

- .NET 6.0 or later installed  
- A development environment (Visual Studio, Rider, or VS Code)  
- The Aspose.BarCode for .NET NuGet package (or any compatible library that provides `BarCodeGenerator`)  

You can add the package with:

```bash
dotnet add package Aspose.BarCode
```

## What this tutorial covers

1. Setting up a **barcode generator c#** instance for DataBar Omni‑directional encoding.  
2. Adjusting **barcode image size** by changing X‑dimension and bar height.  
3. Using a loop to **create multiple barcodes** with different heights.  
4. Saving the images as PNG files and verifying the output.  

All code snippets are complete and ready to copy‑paste into a new console project.

![Create barcode image example](barcode-example.png){alt="Create barcode image example"}

## Step 1: Initialize the generator – create barcode image basics

The first step is to instantiate `BarCodeGenerator` with the desired symbology. For a DataBar Omni‑directional symbol you use `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Why this matters:** Instantiating the generator defines the encoding rules and the data payload. If you omit the correct `EncodeTypes` value, the library will produce an unsupported barcode or throw an exception.

## Step 2: Configure X‑dimension and bar height – control barcode image size

The visual size of a barcode is driven by two parameters:

| Parameter | What it controls | Typical range |
|-----------|------------------|---------------|
| `x_dimension.pixels` | Width of the smallest module (the “dot”) | 1 – 4 px |
| `bar_height.pixels`  | Height of the vertical bars                | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Pro tip:** A smaller X‑dimension yields a higher‑resolution image but may be harder to scan on low‑quality printers. Adjust the value based on your target scanning equipment.

## Step 3: Save the first barcode – create barcode image for 30 px height

Now you can generate the image and write it to disk. The `Save` method accepts a file path and an image format enum.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Expected result:** A PNG file named `Databar30.png` appears in `C:\Barcodes`. Opening the file shows a DataBar Omni‑directional symbol with a clear, high‑contrast pattern.

## Step 4: Change the height and generate additional images – create multiple barcodes

To **create multiple barcodes** with different dimensions you only need to modify the `BarHeight` property and call `Save` again. This avoids re‑instantiating the generator, which saves memory and CPU time.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Why this works:** The `BarCodeGenerator` object holds all configuration state. Changing a single property updates the rendering engine for the next `Save` call, allowing you to **create multiple barcodes** efficiently.

## Step 5: Advanced – how to generate DataBar with custom data

The example above uses a static GS1 payload. In real‑world scenarios you often need to embed variable product identifiers. The library accepts any string that matches the DataBar specification.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Key point:** Setting `generator.CodeText` updates the encoded data without recreating the object. This is the recommended **how to generate databar** pattern when handling large data sets.

## Step 6: Verify and troubleshoot – ensuring correct barcode image size

After generating the images, you may want to programmatically confirm that the dimensions match your expectations. The `Image` class from `System.Drawing` can read the file and report its size.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

If the height does not reflect the value you set, check:

- **X‑dimension**: A very small value may cause the renderer to round the height.
- **Image format**: Some formats (e.g., JPEG) apply compression that can alter pixel dimensions on saving. PNG preserves exact dimensions.

## Step 7: Best practices for barcode image size and performance

| Recommendation | Reason |
|----------------|--------|
| Keep `x_dimension.pixels` between 2 – 3 px for most scanners. | Balances readability and file size. |
| Use PNG for lossless output when the image will be printed. | Guarantees exact dimensions and sharp edges. |
| Reuse a single `BarCodeGenerator` instance when generating many barcodes. | Reduces object allocation overhead. |
| Validate the input string against the GS1 standard before assigning to `CodeText`. | Prevents runtime exceptions and invalid scans. |
| Store generated images in a dedicated folder with a clear naming convention (e.g., `Databar_{GTIN}.png`). | Simplifies downstream processing and audit trails. |

## Full working example

Below is the complete program that incorporates all steps from initialization through verification. Copy the code into a new console project and run it.

```csharp
using System;
using System.Drawing;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // Step 1: Create the generator (create barcode image basics)
            // -------------------------------------------------
            var generator = new BarCodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // -------------------------------------------------
            // Step 2: Set X‑dimension and initial bar height


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}