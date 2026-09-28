---
category: general
date: 2026-08-09
description: Create barcode image in C# with this step-by-step guide. Learn how to
  generate barcode, adjust barcode height pixels, and create multiple barcodes efficiently.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: en
lastmod: 2026-08-09
og_description: Create barcode image in C# quickly. Follow this tutorial to learn
  how to generate barcode, set barcode height pixels, and produce multiple barcodes.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Create barcode image in C# – full guide for developers
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Create barcode image in C# – complete programming guide
url: /python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode image in C# – complete programming guide

If you need to **create barcode image** in a .NET application, this guide shows you exactly **how to generate barcode** using the Aspose.BarCode library. You’ll see how to control the **barcode height pixels**, save the image, and produce **multiple barcodes** without duplicating code.

The tutorial covers everything from installing the package to customizing dimensions, so you can copy‑paste a ready‑to‑run example into your project today.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any C# IDE)  
* NuGet package `Aspose.BarCode` – install with  

```bash
dotnet add package Aspose.BarCode
```

No additional dependencies are required.

## How to generate barcode image with BarcodeGenerator C#

The core class for creating a barcode image is `BarcodeGenerator`. It encapsulates the encoding type, the data string, and all rendering parameters.

### Step 1: Define the output folder

Choose a folder where the generated PNG files will be stored. Using an absolute path avoids permission surprises.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Why?** Creating the folder programmatically guarantees that the subsequent `Save` calls succeed even on a fresh machine.

### Step 2: Instantiate the barcode generator

For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional` and the GS1‑128 data string.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Note:** The `BarcodeGenerator` object is reusable; you can change its parameters between saves to **create multiple barcodes** from the same data.

### Step 3: Set common barcode parameters

The most common visual tweaks are the X‑dimension (module width) and the bar height. Both are expressed in pixels.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Why set X‑dimension?** A smaller X‑dimension yields higher resolution, which is important when the image will be printed or displayed on high‑DPI screens.

### Step 4: Save the first barcode image

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

The file `DatabarBarHeight30Pixels.png` now contains a 30‑pixel‑high DataBar Omnidirectional barcode.

### Step 5: Adjust the barcode height pixels

Changing the height does not require a new `BarcodeGenerator` instance—just modify the parameter.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Step 6: Save the second barcode image

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Now you have two PNG files with different **barcode height pixels**, demonstrating how easy it is to **create barcode image** variations.

## Setting barcode height pixels dynamically

Often you need a series of barcodes with heights that match UI elements or printed labels. The following helper method abstracts the height change:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

You can now call `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` to **create barcode image** with a 45‑pixel height in a single line.

## Creating multiple barcodes in a loop

When you have a collection of product identifiers, a `foreach` loop eliminates repetitive code. This example shows how to **create multiple barcodes** from an array of GTINs.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

The loop produces three PNG files, each with a distinct **barcode height pixels** value. Because the `SaveBarcodeWithHeight` helper encapsulates the height change, the main loop stays clean and focused on data.

### Expected output

After running the full sample, the `Barcodes` folder contains:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Opening any PNG shows a crisp DataBar Omnidirectional barcode that can be scanned by standard mobile apps.

## Common pitfalls and pro tips

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Wrong EncodeTypes** | Using a 1D type for a DataBar will produce an unreadable image. | Always pick `EncodeTypes.DatabarOmniDirectional` (or another DataBar variant) for GS1‑128 payloads. |
| **Insufficient X‑dimension** | Very low X‑dimension can make thin bars disappear on low‑resolution monitors. | Keep `XDimension.Pixels` ≥ 2 for screen display; increase to 3‑4 for printing. |
| **File path errors** | Relative paths may resolve to unexpected directories. | Use `Path.Combine` and `Environment.CurrentDirectory` to build absolute paths. |
| **Overwriting images** | Re‑using the same file name in a loop overwrites previous results. | Include unique identifiers (e.g., GTIN or timestamp) in the file name. |
| **Missing NuGet package** | Code compiles but throws `FileNotFoundException` at runtime. | Verify `Aspose.BarCode` is installed and the project references it. |

## Full working example

Below is the complete program you can copy into a console application. It includes all steps, helper methods, and error handling.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Running this program


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}