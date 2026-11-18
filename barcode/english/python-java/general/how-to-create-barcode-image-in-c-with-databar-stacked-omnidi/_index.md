---
category: general
date: 2026-11-17
description: Create barcode image in C# using the Barcode Generator library. Follow
  this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: en
lastmod: 2026-11-17
og_description: Create barcode image in C# with a concise example. Learn how to generate
  DataBar stacked omnidirectional barcodes using the Barcode Generator library.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Create barcode image in C# – complete guide for DataBar codes
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to create barcode image in C# with DataBar stacked omnidirectional
url: /python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode image in C# with DataBar stacked omnidirectional

If you need to **create barcode image** in a .NET application, this tutorial shows you a complete, ready‑to‑run solution. You’ll see exactly how to use the **Barcode Generator C#** API to produce a stacked omnidirectional DataBar, which is the format covered by the *how to generate databar* query.

The guide walks through every required step—from installing the library to fine‑tuning the aspect ratio—so you can copy the code, run it, and immediately obtain a PNG file. No external documentation lookup is necessary.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed (the sample also works with .NET Framework 4.7+)
* A development environment such as Visual Studio 2022 or VS Code
* The **Aspose.BarCode for .NET** NuGet package (the library that provides `BarcodeGenerator`)

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Use the `--version` flag to lock the package to the latest stable release, e.g., `dotnet add package Aspose.BarCode --version 23.9`.

## Step 1: Set up the project and import namespaces

Create a new console project and reference the required namespaces. This step prepares the environment for the **barcode generator c#** code that follows.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

The `Aspose.BarCode.Generation` namespace contains the `BarcodeGenerator` class, which is the core of the **create barcode image** workflow.

## Step 2: Initialize the BarcodeGenerator for a stacked omnidirectional DataBar

The generator needs two pieces of information: the barcode type and the data to encode. The `EncodeTypes.DatabarStackedOmniDirectional` enum value selects the exact DataBar variant required by *how to generate databar* scenarios.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Why this matters:* Selecting the correct `EncodeTypes` value ensures the resulting image complies with industry specifications for retail scanning.

## Step 3: Define the module size (X‑dimension) in pixels

A barcode’s visual density is controlled by the X‑dimension. Setting it to a sensible pixel value guarantees that the image is readable on both screen and print.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

If you need a larger barcode for low‑resolution printing, increase the pixel value accordingly.

## Step 4: Adjust the DataBar aspect ratio to make rows taller

The stacked omnidirectional DataBar consists of two rows. Modifying the `AspectRatio` lets you control the height of each row, which can be useful when the default size looks cramped.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

An aspect ratio of `15` is a common choice for retail labels; you can experiment with values between `10` and `20` to meet specific layout requirements.

## Step 5: Save the generated barcode as a PNG image

Finally, write the image to disk. PNG is lossless, making it ideal for later processing or embedding in PDFs.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Running the program produces a file named **DatabarAspectRatio15.png** in the project’s output directory. Opening the file shows a clean, high‑contrast barcode ready for scanning.

### Expected output

The saved image looks similar to the illustration below (the actual visual is omitted for brevity).

*Alt text for the example image:* **create barcode image** – a PNG file displaying a stacked omnidirectional DataBar with an aspect ratio of 15.

## Common variations and edge cases

| Situation | Adjustment |
|-----------|------------|
| **Different payload length** | Replace the GTIN string with any valid DataBar content (e.g., `(01)01234567890123`). |
| **Higher resolution for large prints** | Increase `XDimension.Pixels` to 4 or 5 and optionally set `Resolution` in `Parameters.Image`. |
| **Other DataBar formats** | Use `EncodeTypes.DatabarStacked` for a two‑row stacked variant without omnidirectional capability. |
| **Saving as JPEG** | Change `BarCodeImageFormat.Png` to `BarCodeImageFormat.Jpeg` and optionally set `Quality`. |

These variations answer the broader *how to generate databar* question by showing that the same generator can be re‑configured for multiple DataBar families.

## Full source code recap

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Copy the code into `Program.cs`, restore NuGet packages, and execute `dotnet run`. The console will confirm the image location, and you can open the PNG to verify the **create barcode image** result.

## Conclusion

You now know how to **create barcode image** in C# using the Barcode Generator library and how to **generate DataBar** codes with precise control over size and aspect ratio. The complete example demonstrates every required setting—from initializing `BarcodeGenerator` to exporting a PNG file—so you can integrate barcode creation into any .NET application without further research.

### What’s next?

* Explore other barcode symbologies with `EncodeTypes` (e.g., QR, Code128) – a natural extension of the **barcode generator c#** workflow.
* Combine the generated image with PDF or Excel reports using Aspose.PDF or Aspose.Cells.
* Adjust color, add margins, or embed the barcode in a web API for on‑demand generation.

Feel free to experiment with the parameters, and let the code serve as a reliable foundation for all your future barcode‑related projects. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}