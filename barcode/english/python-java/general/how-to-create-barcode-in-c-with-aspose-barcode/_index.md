---
category: general
date: 2026-09-26
description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
  guide includes a barcode generator example and shows how to adjust bar height.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: en
lastmod: 2026-09-26
og_description: Create barcode in C# with Aspose.BarCode. Follow this guide to generate
  a barcode, adjust its bar height, and save PNG images.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Create barcode in C# with Aspose.BarCode – full guide
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: How to create barcode in C# with Aspose.BarCode
url: /python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode in C# with Aspose.BarCode  

If you need to **create barcode c#** projects quickly, Aspose.BarCode provides a fluent API that handles the heavy lifting. In this tutorial you’ll see a complete **barcode generator example**, learn **how to adjust bar height**, and export the result as PNG files.  

Whether you are building a retail checkout system, generating inventory tags, or automating shipping labels, the ability to programmatically change the visual size of a barcode is essential. This guide assumes you have a basic understanding of C# and a development environment such as Visual Studio 2022.  

## Prerequisites  

Before you start, make sure you have:  

* .NET 6.0 SDK or later installed.  
* Visual Studio 2022 (or any C# IDE).  
* An active Aspose.BarCode license (the free trial works for learning).  

You will also need to add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** If you plan to generate many barcodes in a loop, reuse a single `BarcodeGenerator` instance and only modify the parameters that change. This reduces memory allocations and improves performance.

## How to create barcode in C# with Aspose.BarCode  

The following sections walk through each step of the **barcode generator example**. The code is self‑contained; copy it into a new console application and run it.

### Step 1: Import required namespaces  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

These namespaces give you access to the `BarcodeGenerator` class and the `EncodeTypes` enumeration.

### Step 2: Initialise the barcode generator  

We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14 value. The constructor takes the symbology and the raw data string.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

The `EncodeTypes.DatabarOmniDirectional` value tells Aspose.BarCode which barcode standard to use. The data string follows the GS1 Application Identifier format, which is common for retail barcodes.

### Step 3: Set common barcode parameters  

Two visual parameters are most often tweaked: the X‑dimension (the narrow bar width) and the overall bar height.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

The **X‑dimension** controls the barcode’s density, while **BarHeight** determines the vertical size of each bar. Adjusting **BarHeight** is exactly what you need when you want to **change barcode height** for different print media.

### Step 4: Save the first image (30‑pixel height)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

The `Save` method writes the rendered image to disk. The file name clearly indicates the height used, which helps when you compare different outputs.

### Step 5: Change the bar height to 60 pixels  

Now we demonstrate **how to adjust bar height** at runtime. The same `generator` instance is reused; only the `BarHeight` property changes.

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Because the generator retains all other settings (symbology, data, X‑dimension), the only visual difference between the two PNG files is the vertical size of the bars.

### Full source code  

Putting everything together yields a concise, runnable program:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Expected output**  

Running the program creates two PNG files in the executable’s working directory:

* `DatabarBarHeight30Pixels.png` – a barcode with 30 px bar height.  
* `DatabarBarHeight60Pixels.png` – the same barcode, but each bar is twice as tall.

Open the images in any viewer; you’ll see that the overall pattern remains identical while the vertical dimension changes, confirming that the **change barcode height** operation succeeded.

## Advanced variations  

### Switching to a different symbology  

If you need a QR code instead of a Databar, replace the `EncodeTypes` value:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

All other parameter settings (X‑dimension, BarHeight) still apply where they make sense.

### Using `BarHeight` in millimetres  

Aspose.BarCode also supports physical units. To set a height of 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

This is handy when you generate barcodes for print layouts that require exact measurements.

### Handling errors  

If the data string does not conform to the selected symbology, `BarcodeGenerator` throws an `ArgumentException`. Wrap the generation logic in a try‑catch block to provide a friendly message:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Common questions answered  

* **Does changing BarHeight affect scanability?**  
  The barcode remains scannable as long as the X‑dimension and the overall quiet zone meet the symbology’s specifications. Increasing height only makes the bars longer; it never reduces contrast.

* **Can I set different heights for individual bars?**  
  No. The `BarHeight` property applies uniformly to the entire symbol. For variable‑height designs you would need a custom rendering routine outside the scope of Aspose.BarCode.

* **Is PNG the best format for printing?**  
  PNG preserves lossless pixel data, making it ideal for screen display. For high‑resolution print jobs, consider `BarCodeImageFormat.Tiff` or `Pdf` to retain vector information.

## Conclusion  

You now know how to **create barcode c#** applications with Aspose.BarCode, see a complete **barcode generator example**, and understand **how to adjust bar height** to meet different layout requirements. By reusing the same generator instance and only modifying `BarHeight`, you can efficiently **change barcode height** without rebuilding the entire object.

From here you might explore:

* Generating other symbologies (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Exporting to SVG or PDF for scalable graphics.  
* Embedding barcodes directly into Word or Excel documents using Aspose.Words or Aspose.Cells.

Happy coding, and enjoy the flexibility that Aspose.BarCode brings to your C# barcode projects!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}