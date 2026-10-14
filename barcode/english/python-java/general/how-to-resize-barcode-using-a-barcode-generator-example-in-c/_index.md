---
category: general
date: 2026-10-08
description: Learn how to resize barcode images with a C# barcode generator example,
  adjusting bar height from 30 px to 60 px in just a few lines of code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: en
lastmod: 2026-10-08
og_description: How to resize barcode quickly with a C# barcode generator example.
  Adjust bar height, save PNG files, and avoid common pitfalls.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: How to resize barcode in C# – step‑by‑step generator example
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: How to resize barcode using a barcode generator example in C#
url: /python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to resize barcode using a barcode generator example in C#

If you need to **how to resize barcode** images in a .NET project, this guide shows the complete solution. You’ll see a concise **barcode generator example C#** that changes the bar height from 30 px to 60 px and saves each version as a PNG file.

Resizing a barcode is often required when the same data must appear on receipts, labels, or product pages at different visual scales. Rather than editing the raster image with an external editor, you can adjust the barcode dimensions programmatically, keeping the data integrity intact.

In this tutorial you will:

* Set up a DataBar Omni‑Directional barcode generator.
* Modify the X‑dimension and bar height parameters.
* Save two images with distinct heights.
* Understand why changing the bar height works and what edge cases to watch for.

> **Prerequisite** – You have a .NET development environment (Visual Studio 2022 or later) and the barcode library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`. The code works with the latest version of the library as of October 2026.

## Prerequisites for the barcode generator example C#

Before you start, make sure you have:

| Item | Reason |
|------|--------|
| .NET 6.0 SDK or newer | Provides the runtime and language features used in the sample. |
| Barcode library (e.g., Aspose.BarCode, Dynamsoft, or any library exposing `BarcodeGenerator`) | Supplies the `EncodeTypes.DatabarOmniDirectional` enum and image export methods. |
| A folder you can write to (e.g., `C:\Temp\Barcodes\`) | The sample saves PNG files to this location. |
| Basic C# knowledge | The tutorial assumes familiarity with classes, properties, and string interpolation. |

Install the library via NuGet if you haven’t already:

```bash
dotnet add package Aspose.BarCode
```

Replace the package name with the one you actually use; the API surface shown below is common across most barcode SDKs.

## How to resize barcode – step 1: create the generator

The first step is to instantiate a `BarcodeGenerator` with the desired symbology and data payload. In this example we generate a **DataBar Omni‑Directional** barcode that encodes a GTIN‑14 value.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Why this matters:** The `EncodeTypes.DatabarOmniDirectional` enum tells the library which barcode standard to use. The data string follows the GS1 Application Identifier `(01)` for a 14‑digit GTIN, ensuring the barcode complies with global trade standards.

## How to resize barcode – step 2: define the module width and initial bar height

The visual size of a barcode depends on two parameters:

* **X‑dimension** – the width of the smallest bar (module). Measured in pixels or millimetres.
* **Bar height** – the vertical length of the bars.

Setting these values before saving guarantees that the rendered image matches the dimensions you need.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explanation:** An X‑dimension of 2 px yields a compact barcode that still scans reliably. The 30 px height is a common default for small labels. You can adjust the X‑dimension independently of the height if you need a denser or more spaced‑out pattern.

## How to resize barcode – step 3: save the first image (30 px height)

Now export the barcode to a PNG file. The `Save` method accepts a file path and an image format enum.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Result:** `DatabarBarHeight30Pixels.png` contains a 30 px tall barcode. You can open the file in any image viewer to verify the dimensions.

## How to resize barcode – step 4: change the bar height to 60 px

To create a larger version, simply modify the `BarHeight` property. The generator reuses the same data and X‑dimension, so the barcode’s pattern stays identical—only the visual size changes.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Why this works:** The barcode rendering engine calculates each bar’s geometry on demand. Updating the height property before the next `Save` call triggers a fresh rasterization with the new dimensions.

## How to resize barcode – step 5: save the second image (60 px height)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

You now have two PNG files, one small (30 px) and one larger (60 px), ready for use on different label sizes.

## Full source code for the barcode generator example C#

Below is the complete, runnable program. Copy it into a new console project to test immediately.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Expected output in the console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

After running, open the two PNG files to see the visual difference. Both barcodes encode the same GTIN‑14 value and will scan identically, regardless of height.

## Why adjusting bar height is safe for scanning

Barcode scanners read the pattern of light and dark modules, not the absolute pixel count. As long as the **X‑dimension** remains within the scanner’s tolerance (usually 0.5 mm to 2 mm in physical units), changing the height does not affect readability. The library automatically scales the modules, preserving the required quiet zones and alignment patterns.

## Common pitfalls and how to avoid them

| Pitfall | How to fix |
|---------|------------|
| **Output folder does not exist** | Call `Directory.CreateDirectory(outputPath)` before saving. |
| **Incorrect X‑dimension causing blurry scans** | Keep `XDimension.Pixels` between 1 px and 4 px for most printers; test with a physical scanner. |
| **Using a raster format for very large barcodes** | Switch to `BarCodeImageFormat.Svg` for infinite scalability without pixelation. |
| **Forgetting to reset `BarHeight` before the second save** | Ensure you assign the new height **before** calling `Save` again. |

## Pro tip: generate multiple sizes in a loop

If you need a range of heights (e.g., 30 px, 45 px, 60 px), a simple `foreach` loop reduces duplication:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

This pattern scales well for batch processing of product catalogs.

## Edge cases: different image formats and DPI settings

* **SVG output** – Use `BarCodeImageFormat.Svg` to produce a vector file that can be resized without quality loss.
* **High‑DPI PNG** – Set `generator.Parameters.Image.DpiX` and `DpiY` to 300 or 600 for print‑ready images; the bar height will still be measured in pixels, so increase it proportionally.
* **Non‑standard symbologies** – Some barcode types (e.g., QR Code) have a separate `Size` property rather than `BarHeight`. Consult the library docs for those cases.

## Testing the resized barcode

1. Open each PNG in an image viewer and verify the pixel dimensions (e.g., 150 × 30 px vs. 150 × 60 px).  
2. Print the images at 100 % scale.  
3. Scan with a handheld barcode scanner or a mobile app. The decoded data should be


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}