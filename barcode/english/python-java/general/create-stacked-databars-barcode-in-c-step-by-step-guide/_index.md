---
category: general
date: 2026-10-02
description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
  adjust aspect ratio, and export PNG images with a barcode generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: en
lastmod: 2026-10-02
og_description: Create stacked databars barcode in C# with a full code example. Adjust
  XDimension, change aspect ratio, and save PNG files in just a few lines.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Create stacked databars barcode in C# – quick tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Create stacked databars barcode in C# – step‑by‑step guide
url: /python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create stacked databars barcode in C# – step‑by‑step guide

If you need to **create stacked databars barcode** in a .NET project, this tutorial shows you exactly how. You’ll see how to configure the X‑dimension, switch aspect ratios, and save the result as PNG files—all with the Aspose.BarCode library.

Generating a stacked DataBar barcode doesn’t require a complex graphics pipeline. By the end of this guide you’ll have two ready‑to‑use PNG images that illustrate different aspect ratios, and you’ll understand why those parameters matter for scanning reliability.

## What you’ll need

- .NET 6.0 or later (the code also works with .NET Framework 4.6+)
- Visual Studio 2022 or any C# IDE
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Write permission to a folder where the PNG files will be saved

## Step 1: Set up the project and import namespaces

Create a new console application (or add the code to an existing project) and import the required namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Why this matters:** `Aspose.BarCode.Generation` provides the `BarcodeGenerator` class, while `Aspose.BarCode` contains the `BarCodeImageFormat` enumeration used for saving images.

## Step 2: Initialise the generator for a stacked omnidirectional DataBar

The `EncodeTypes.DatabarStackedOmniDirectional` value selects the stacked DataBar symbology. The data string must follow the GS1 Application Identifier (AI) format; here we use a dummy GTIN‑14 value.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Why this matters:** The chosen encode type tells the library to render a *stacked* barcode, which is essential for high‑density labels where vertical space is limited.

## Step 3: Define the module (X‑dimension) size in pixels

The X‑dimension controls the width of the smallest bar (the “module”). A value of 2 pixels works well for most screen‑resolution outputs.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why this matters:** Scanners interpret the module width as the basic unit of measurement. Too small a value can cause blurry prints; too large wastes space.

## Step 4: Save the first image with an aspect ratio of 15

The `AspectRatio` property influences the height‑to‑width relationship of each stacked segment. An aspect ratio of 15 is a common default for retail applications.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Why this matters:** A lower aspect ratio yields a flatter barcode, which may be easier to scan on certain label materials. The PNG format preserves lossless quality for testing.

## Step 5: Change the aspect ratio to 30 and save the second image

Increasing the aspect ratio makes each stacked segment taller, which can improve scan reliability on low‑contrast backgrounds.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Why this matters:** Different retailers or logistics partners may require specific barcode dimensions. Providing both versions lets you compare scan performance quickly.

## Full, runnable example

Below is the complete program you can copy‑paste into `Program.cs`. It compiles and runs without modification after installing the Aspose.BarCode NuGet package.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Expected output

Running the program creates two files in the execution folder:

| File name                     | Aspect ratio | Visual description |
|-------------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png`    | 15           | Shorter, flatter stacked barcode |
| `DatabarAspectRatio30.png`    | 30           | Taller, more elongated stacked barcode |

You can open the PNG files with any image viewer to verify that the barcode renders correctly.

![Create stacked databars barcode example](placeholder-image.png){alt="Create stacked databars barcode example"}

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| **Can I use a different X‑dimension?** | Yes. Typical values range from 1 to 4 pixels. Larger values increase barcode size but may improve readability on low‑resolution printers. |
| **What if I need a different symbology?** | Replace `EncodeTypes.DatabarStackedOmniDirectional` with another `EncodeTypes` value, such as `DatabarStacked` (non‑omnidirectional) or `DatabarLimited`. |
| **How do I change the output format?** | Use `BarCodeImageFormat.Jpeg`, `Gif`, or `Bmp` in the `Save` call. |
| **Is the GTIN‑14 format mandatory?** | The DataBar symbology expects a numeric string prefixed with an appropriate AI (e.g., `(01)` for GTIN‑14). Adjust the data according to your use case. |
| **What about DPI settings?** | The generator respects the `Resolution` property. For high‑resolution prints, set `barcodeGen.Parameters.ImageResolution.DpiX` and `DpiY` accordingly. |

## Pro tips

- **Batch generation:** Wrap the save logic in a loop and feed it a list of GTINs to produce thousands of barcodes automatically.
- **Validation:** Use `barcodeGen.Validate()` before saving to catch malformed data early.
- **Performance:** Re‑using the same `BarcodeGenerator` instance (only changing parameters) is faster than creating a new object for each image.

## Next steps

Now that you can **create stacked databars barcode** with custom aspect ratios, consider exploring:

- Adding human‑readable text beneath the barcode (`barcodeGen.Parameters.Barcode.CodeText`).
- Exporting to **PDF** for printable label sheets (`BarCodeImageFormat.Pdf`).
- Integrating the generator into a web API to serve barcodes on demand.
- Experimenting with other **secondary keywords** such as *C# barcode generator* and *barcode aspect ratio* to fine‑tune your implementation for specific hardware.

Happy coding, and enjoy the flexibility that Aspose.BarCode brings to your C# barcode projects!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}