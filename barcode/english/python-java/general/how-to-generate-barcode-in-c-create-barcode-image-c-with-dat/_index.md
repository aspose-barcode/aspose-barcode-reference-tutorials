---
category: general
date: 2026-08-22
description: How to generate barcode in C# using Aspose.BarCode. Learn to create barcode
  image c# step‑by‑step, disable the 2‑D component, and save PNG files.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: en
lastmod: 2026-08-22
og_description: How to generate barcode in C# with Aspose.BarCode. This tutorial shows
  you how to create barcode image c# using DataBar Expanded, toggle the 2‑D component,
  and save PNG files.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: How to generate barcode in C# – complete guide to create barcode image c#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: How to generate barcode in C# – create barcode image c# with DataBar Expanded
url: /python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode in C# – create barcode image c# with DataBar Expanded

How to generate barcode in C# is a frequent requirement when you need to embed machine‑readable data into your applications. This guide shows you how to create barcode image c# using the Aspose.BarCode library, disable the 2‑D composite component, and save the result as PNG files.

You will see a complete, runnable program, an explanation of every configuration option, and tips for customizing the output. No external documentation is required—just the code below and a .NET development environment.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports .NET)  
* Aspose.BarCode for .NET NuGet package (`Aspose.BarCode`)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

The library provides the `BarcodeGenerator` class used throughout this tutorial.

## Step 1: Set up the project and import namespaces

Create a new console application and import the required namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

The `Aspose.BarCode.Generation` namespace contains all classes needed to configure and render barcodes.

## Step 2: Initialize the DataBar Expanded barcode generator

The first functional line creates a `BarcodeGenerator` for the **DataBar Expanded** symbology and supplies the raw data string. The data string follows the GS1 Application Identifier format `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Creating the generator allocates the internal bitmap canvas, so you can adjust size and appearance before rendering.

## Step 3: Define the module width (X‑dimension)

The X‑dimension controls the width of the smallest barcode element. Setting it in pixels gives you precise control over the final image size.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A value of `2` pixels works well for screen display; increase it for higher‑resolution prints.

## Step 4: Disable the 2‑D composite component

DataBar Expanded can optionally include a 2‑D component that carries additional information. To generate a barcode **without** this component, set the flag to `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Disabling the component reduces the visual complexity and produces a smaller PNG file.

## Step 5: Save the barcode image without the 2‑D component

Choose an output directory and write the image to disk. The `BarCodeImageFormat.Png` enum ensures a lossless PNG file.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

After this call, `Databar2DComponentDisabled.png` contains a clean DataBar Expanded barcode.

## Step 6: Enable the 2‑D composite component

If you need the extra data layer, re‑enable the flag. The same generator instance can be reused, which avoids creating a second object.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Step 7: Save the barcode image with the 2‑D component enabled

Render the second image using the same settings, except for the 2‑D flag.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Now `Databar2DComponentEnabled.png` shows the barcode with the additional 2‑D pattern.

## Full source code

Copy the entire snippet below into `Program.cs` and run the project. The program creates both PNG files in the folder you specify.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Expected output

Running the program prints:

```
Barcode images generated successfully.
```

and creates two files:

* `Databar2DComponentDisabled.png` – barcode without the 2‑D component  
* `Databar2DComponentEnabled.png` – barcode with the 2‑D component  

Open the PNGs in any image viewer to verify the visual difference.

## Common variations and edge cases

| Situation | Adjustment |
|-----------|------------|
| **Different symbology** | Replace `EncodeTypes.DatabarExpanded` with another value, e.g., `EncodeTypes.Code128`. |
| **Higher resolution** | Increase `XDimension.Pixels` to 4 or 5, or set `Resolution` in `barcodeGenerator.Parameters.Image`. |
| **Other image formats** | Use `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, or `BarCodeImageFormat.Svg`. |
| **Running in a web app** | Stream the image bytes directly to the HTTP response instead of saving to disk. |
| **Memory management** | Wrap the generator in a `using` block if you target .NET Framework to ensure unmanaged resources are released. |

## Pro tips

* **Reuse the generator** – Changing only the 2‑D flag avoids re‑instantiating the object, which saves CPU cycles.  
* **Validate data** – GS1 data must follow the exact length and checksum rules; invalid input throws `ArgumentException`.  
* **Batch processing** – Loop over a collection of data strings, toggle the 2‑D flag as needed, and save each image with a unique filename.  

## Conclusion

You now know how to generate barcode in C# and create barcode image c# with full control over the 2‑D composite component. The example demonstrates initializing the generator, configuring the X‑dimension, toggling the component, and saving PNG files. From here you can explore other symbologies, embed the images in PDFs, or integrate barcode generation into ASP.NET Core services.

--- 

*Next steps*: try generating QR codes, experiment with different image resolutions, or embed the generated PNGs into a PDF using Aspose.PDF. These extensions build on the same `BarcodeGenerator` API and keep your workflow consistent.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}