---
category: general
date: 2026-11-14
description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
  barcodes, set X‑dimension, and adjust bar height in pixels.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: en
lastmod: 2026-11-14
og_description: Barcode generator C# tutorial explains step‑by‑step how to generate
  a DataBar Omnidirectional barcode, define XDimension in pixels, and change bar height
  for PNG output.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Barcode generator C# tutorial – create DataBar barcodes
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Barcode generator C# tutorial: DataBar Omnidirectional'
url: /python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# tutorial – create DataBar Omnidirectional barcodes

If you are looking for a **barcode generator C# tutorial**, you have landed in the right place. This guide walks you through creating a DataBar Omnidirectional barcode, configuring the XDimension in pixels, and adjusting the bar height to produce PNG images.

You’ll see a complete, runnable example that covers everything from initializing the generator to saving multiple images with different bar heights. No external documentation is required—just copy the code, run it, and you’ll have two barcode files ready to use.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed  
* A reference to the barcode library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat` (for example, Aspose.BarCode for .NET)  
* Basic familiarity with C# syntax and Visual Studio or your preferred IDE  

> **Pro tip:** If you are using Aspose.BarCode, add the NuGet package `Aspose.BarCode` to your project.

## Barcode generator C# tutorial – step 1: create the generator

The first step is to instantiate a `BarcodeGenerator` with the `DatabarOmniDirectional` encode type and the data you want to encode.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Why this matters:* `EncodeTypes.DatabarOmniDirectional` tells the library to produce a barcode that can be read from any direction, which is ideal for retail packaging and logistics.

## Set XDimension pixels for the barcode

The X‑dimension defines the width of the smallest module (the “pixel”) in the barcode. Setting it in pixels gives you precise control over the barcode’s visual density.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Explanation:* A value of `2` pixels yields a barcode that is sharp enough for most scanners while keeping the image file size modest.

## Adjust bar height and save images

Bar height determines how tall the bars appear. You can generate multiple images with different heights by changing the `BarHeight.Pixels` property and calling `Save` again.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

The `BarCodeImageFormat.Png` enum value ensures the output is a loss‑less PNG file, which is the recommended format for barcode graphics because it preserves exact dimensions.

## Change bar height to create multiple images

You often need the same barcode at different sizes—for example, one for a small label and another for a large poster. Change the bar height and reuse the same generator instance:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Edge case:* If the bar height is set too low (e.g., below 10 px), some scanners may struggle to read the code. Always test the generated images with your target scanner hardware.

## Full source code

Below is the complete program you can copy‑paste into a new console project. It includes all required `using` directives and demonstrates both bar‑height variations.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Run the program, replace `YOUR_DIRECTORY` with a valid folder path, and you’ll find two PNG files:

* `DatabarBarHeight30Pixels.png` – 30 px tall bars  
* `DatabarBarHeight60Pixels.png` – 60 px tall bars  

![barcode generator C# tutorial output](images/databar-example.png "Barcode generator C# tutorial showing two DataBar images")

## Common questions

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed. PNG is preferred for lossless quality. |
| **What if I need a different XDimension?** | Adjust `generator.Parameters.Barcode.XDimension.Pixels` to any integer. Larger values increase overall barcode width. |
| **Is the DataBar Omnidirectional suitable for mobile scanning?** | It is, provided the printed size meets the scanner’s minimum module size (usually 0.33 mm). The pixel‑based XDimension helps you meet that requirement. |
| **How do I embed the barcode in a PDF?** | After saving the PNG, use a PDF library (e.g., iTextSharp) to insert the image into a PDF page. |

## Conclusion

This **barcode generator C# tutorial** showed you how to create a DataBar Omnidirectional barcode, set the XDimension in pixels, and generate PNG files with different bar heights. You now have a reusable code snippet that you can adapt for any C# project that requires barcode creation.

### What’s next?

* Explore other `EncodeTypes` such as `Code128` or `QR` to broaden your barcode repertoire.  
* Combine the generated PNG with a PDF generation library to produce printable invoices.  
* Experiment with `generator.Parameters.Barcode.Color` to add custom colors while staying within scanner specifications.

Feel free to modify the example, try additional bar heights, or switch the output format. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}