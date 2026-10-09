---
category: general
date: 2026-09-29
description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
  Adjust X‑dimension, set aspect ratio, and save PNG images.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: en
lastmod: 2026-09-29
og_description: Create omnidirectional Databar barcode in C# using Aspose.BarCode.
  Learn to set X‑dimension, adjust aspect ratio, and export PNG files.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Create omnidirectional Databar barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: How to create omnidirectional Databar barcode in C#
url: /python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create omnidirectional Databar barcode in C#

If you need to **create omnidirectional Databar barcode** in a .NET application, this guide shows you the exact steps. You’ll see how to initialise a DataBar stacked omnidirectional barcode, configure its X‑dimension, change the aspect ratio, and generate PNG images with Aspose.BarCode.

Generating a **DataBar stacked omnidirectional barcode** is common when you must encode product identifiers for retail scanners. In this tutorial you’ll learn to **set barcode aspect ratio**, control module size, and export the result without leaving the IDE.

## Prerequisites

Before you start, make sure you have:

- .NET 6.0 or later installed
- Visual Studio 2022 (or any C#‑compatible IDE)
- The **Aspose.BarCode for .NET** NuGet package (version 23.12 or newer)

You can add the package via the NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Initialise the omnidirectional Databar barcode

The first step is to create a `BarcodeGenerator` instance that targets the **DataBar stacked omnidirectional** symbology. The constructor receives the encode type and the data string.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Why this matters:** The `EncodeTypes.DatabarStackedOmniDirectional` value tells Aspose.BarCode to render the specific omnidirectional Databar format, which is required for scanning in both directions.

## Step 2: Define the X‑dimension (module size)

The X‑dimension controls the width of a single barcode module in pixels. A value of `2` pixels works well for on‑screen rendering and most printers.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** A consistent X‑dimension ensures the barcode meets the minimum size specifications for retail scanners while keeping the image file size manageable.

## Step 3: Set the first aspect ratio and save the image

The **aspect ratio** determines the height‑to‑width relationship of the DataBar. An aspect ratio of `15` yields a compact, tall barcode ideal for narrow label spaces.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Why this matters:** Adjusting the aspect ratio lets you fit the barcode into different label layouts without sacrificing readability. The saved PNG can be inspected in any image viewer.

## Step 4: Change the aspect ratio and generate a second image

Sometimes a wider barcode is needed—for example, when the label has more horizontal space. Changing the ratio to `30` creates a flatter appearance.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Why this matters:** By exposing the **set barcode aspect ratio** property, you can produce multiple barcode variations from a single code base, simplifying automated label generation pipelines.

## Expected output

Running the program produces two PNG files in the application’s output folder:

| File name                | Aspect Ratio | Visual description |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | Tall, narrow barcode suited for narrow labels |
| `DatabarAspectRatio30.png` | 30           | Wider barcode that fills more horizontal space |

You can embed these images in reports, print them on product packaging, or send them to a web service for further processing.

![Create omnidirectional Databar barcode example](databar-example.png "Create omnidirectional Databar barcode example")

*The screenshot shows the two generated PNG files side‑by‑side.*

## Common questions and edge cases

### What if I need a different X‑dimension?

You can assign any integer value to `XDimension.Pixels`. Values below `1` are ignored, and values above `10` may produce oversized modules that exceed printer margins. Test the visual output after each change.

### How do I encode other AI‑generated data (e.g., UPC, EAN)?

Replace the data string in the `BarcodeGenerator` constructor with the appropriate Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without an AI prefix.

### Can I export to formats other than PNG?

Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that matches your downstream workflow.

## Pro tip: reuse the generator for batch processing

If you need to generate dozens of barcodes with varying aspect ratios, keep the `BarcodeGenerator` instance alive and only modify `DataBar.AspectRatio` before each `Save`. This avoids the overhead of re‑instantiating the generator for every image.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusion

You now know how to **create omnidirectional Databar barcode** in C# using Aspose.BarCode. By initialising a `BarcodeGenerator`, setting the X‑dimension, adjusting the **set barcode aspect ratio**, and saving PNG files, you can produce barcode images that meet diverse label requirements.  

Next, explore related topics such as **generate barcode image** for QR codes, **DataBar stacked omnidirectional barcode** validation, or integrating the generated PNGs into PDF invoices with Aspose.PDF. Experiment with different aspect ratios and module sizes to find the optimal configuration for your specific printing hardware.

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to generate barcode in C# – create barcode image c# with DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}