---
category: general
date: 2026-08-19
description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
  databar images, configure databar parameters, and save PNG output.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: en
lastmod: 2026-08-19
og_description: Create databar PNG files in C# using Aspose.BarCode. This tutorial
  walks you through how to generate databar images, configure databar parameters such
  as X‑dimension and aspect ratio, and save high‑quality PNG files for printing or
  web use.
og_image_alt: create databar PNG example
og_title: Create databar PNG images in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: How to create databar PNG images with C# and Aspose.BarCode
url: /python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create databar PNG images with C# and Aspose.BarCode

If you need to **create databar PNG** files in a .NET application, this guide shows you exactly how. You’ll see a complete, runnable example that generates stacked omnidirectional DataBar codes, configures key parameters, and saves two PNG files with different aspect ratios.

Generating a DataBar image isn’t just about calling a single method. You also have to **configure databar parameters** like the X‑dimension (module width) and the aspect ratio to meet printing or scanning specifications. By the end of this tutorial you’ll understand **how to generate databar** graphics that work reliably in real‑world scenarios.

## Prerequisites

- .NET 6.0 or later (the code also works with .NET Framework 4.7+)
- Visual Studio 2022 or any C#‑compatible IDE
- A valid license for **Aspose.BarCode for .NET** (the free evaluation works for testing)
- Basic familiarity with C# syntax

> **Pro tip:** If you don’t have a license yet, you can request a temporary evaluation key from the Aspose portal. The API behaves the same; only the watermark changes.

## Step 1: Install the Aspose.BarCode NuGet package

Open your project in Visual Studio, right‑click the solution, and select **Manage NuGet Packages**. Search for `Aspose.BarCode` and install the latest stable version.

```bash
dotnet add package Aspose.BarCode
```

This command adds the `Aspose.BarCode` assembly to your project and makes the `BarcodeGenerator` class available.

## Step 2: Initialize the barcode generator for a stacked omnidirectional DataBar

The `BarcodeGenerator` constructor receives two arguments: the barcode type and the raw data string. For a stacked omnidirectional DataBar you use `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Why this matters:** The `EncodeTypes.DatabarStackedOmniDirectional` constant tells the library to produce a barcode that can be read from any orientation, which is ideal for retail shelf labels.

## Step 3: Configure the X‑dimension (module width) in pixels

The X‑dimension controls the size of the smallest bar element. Setting it in pixels gives you precise control over the final image size.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A value of **2 pixels** is a good balance between readability and compactness for most label printers. Adjust this value if you need larger or smaller modules.

## Step 4: Set the first aspect ratio and save the PNG

The aspect ratio influences the height of the stacked DataBar. An aspect ratio of **15** produces a relatively short barcode, while **30** makes it taller.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The `Save` method writes the generated barcode to a PNG file. PNG is lossless, which preserves the crisp edges required for barcode scanners.

## Step 5: Change the aspect ratio and save a second PNG

You can reuse the same `BarcodeGenerator` instance to produce variations simply by changing the aspect ratio.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Now you have two PNG files—`DatabarAspectRatio15.png` and `DatabarAspectRatio30.png`—each with a different visual density.

## Step 6: Verify the output

Open the generated PNG files in any image viewer. You should see a clean, high‑contrast DataBar barcode. Scanning the images with a smartphone barcode scanner confirms that both aspect ratios decode to the original GTIN value `12345678901231`.

![create databar PNG example](databar_example.png)

*The image above shows the two PNG files side by side. The left image uses aspect ratio 15, the right uses aspect ratio 30.*

## Common variations and edge cases

| Scenario | What to change | Reason |
|----------|----------------|--------|
| **Different data** | Replace the string `(01)12345678901231` with any valid GS1 Application Identifier and data | Allows you to encode product IDs, serial numbers, etc. |
| **Higher resolution** | Increase `XDimension.Pixels` to 3 or 4 | Needed when the barcode will be printed at large sizes or scanned from a distance. |
| **Other DataBar types** | Use `EncodeTypes.DatabarStacked` or `EncodeTypes.DatabarExpanded` | Choose the type that best fits your label layout. |
| **Transparent background** | Pass `BarCodeImageFormat.Png` with `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Useful for overlaying the barcode on colored labels. |

> **Watch out for:** Setting an X‑dimension that’s too small (< 1 pixel) can produce a barcode that looks blurry after


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}