---
category: general
date: 2026-08-03
description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
  images. Follow this complete example with code and tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: en
lastmod: 2026-08-03
og_description: Create barcode PNG in C# and see how to change aspect ratio for DataBar
  barcodes. This guide gives you ready‑to‑run code and practical tips.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Create barcode PNG in C# – full example with aspect‑ratio control
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Create barcode PNG in C# – step‑by‑step guide
url: /python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode PNG in C# – step‑by‑step guide

If you need to **create barcode PNG** in C#, this tutorial shows you exactly how. You will generate a stacked omnidirectional DataBar barcode, save it as a PNG file, and learn **how to change aspect ratio** to suit different scanning environments.

The guide covers everything you need: required packages, a complete, runnable program, and explanations of why each setting matters. By the end you will have two PNG files—one with an aspect ratio of 15 and another with 30—ready for testing or production use.

## Prerequisites

Before you start, ensure you have:

- .NET 6.0 SDK or later installed
- Visual Studio 2022 (or any C# IDE)
- A NuGet reference to **Aspose.BarCode** (the library that provides `BarcodeGenerator`)
- Write permission to the directory where the PNG files will be saved

You can add the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the project and import namespaces

Create a new console application and import the namespaces required for barcode generation and file I/O.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Why this matters:** Importing `Aspose.BarCode.Generation` gives you access to `BarcodeGenerator`. Keeping the code inside `Main` makes the example self‑contained and easy to run.

## Step 2: Create a barcode generator for a stacked omnidirectional DataBar

Instantiate `BarcodeGenerator` with the `EncodeTypes.DatabarStackedOmniDirectional` type and a sample GS1‑128 data string.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Why this matters:** The chosen encode type produces a high‑density DataBar that can be read by most modern scanners. The data string follows the GS1 Application Identifier (01) format, which is common for product identifiers.

## Step 3: Define the X‑dimension (module width) in pixels

Set the module width to control the barcode's overall size without affecting its readability.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** An X‑dimension of 2 pixels yields a barcode that is neither too small for scanners nor too large for typical label spaces.

## Step 4: Save the first PNG with an aspect ratio of 15

Adjust the DataBar aspect ratio, then save the image as a PNG file.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Why this matters:** The aspect ratio controls the height‑to‑width relationship of the stacked DataBar. A ratio of 15 is a common default that balances readability and label height.

## Step 5: Change the aspect ratio to 30 and save a second PNG

Modify the same generator instance to use a larger aspect ratio, then save the second image.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Why this matters:** Increasing the aspect ratio stretches the barcode vertically, which can improve scan reliability on low‑resolution devices or when the label is printed on narrow media.

## Expected output

Running the program creates two PNG files:

| File                               | Aspect Ratio | Approximate dimensions (pixels) |
|------------------------------------|--------------|---------------------------------|
| `DatabarAspectRatio15.png`         | 15           | 200 × 300 (width × height)      |
| `DatabarAspectRatio30.png`         | 30           | 200 × 600 (width × height)      |

Both images contain a clear, scannable DataBar barcode that encodes the GS1 identifier `(01)12345678901231`.

## Common questions and edge cases

### How to change other visual properties?

You can adjust foreground color, background color, or add human‑readable text through the `generator.Parameters.Barcode` object. For example:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### What if I need a different image format?

Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG remains the best choice for lossless barcode images.

### Does the aspect ratio affect scanning speed?

Higher aspect ratios increase the barcode’s height, which can improve scan reliability on devices that struggle with short stacked symbols. However, extremely tall barcodes may not fit on small labels, so test with your target hardware.

### Can I generate multiple barcodes in a loop?

Yes. Create a new `BarcodeGenerator` instance for each data string or reuse the same instance while updating `CodeText` and `DataBar.AspectRatio`. This approach reduces object allocation overhead.

## Pro tips

- **Reuse the generator**: Changing only the `CodeText` or `AspectRatio` avoids re‑instantiating the object, which speeds up batch processing.
- **Validate the output**: Use a handheld scanner or a mobile app to confirm the generated PNG reads correctly before deploying to production.
- **File naming**: Include the aspect ratio in the file name (as shown) to keep track of variations during testing.

## Conclusion

You now know how to **create barcode PNG** files in C# and precisely **how to change aspect ratio** for stacked omnidirectional DataBar symbols. The complete example demonstrates initialization, X‑dimension setting, aspect‑ratio manipulation, and image saving—all in a single, runnable program.

From here you can explore additional barcode types, experiment with colors, or integrate the generator into a larger reporting or inventory system. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}