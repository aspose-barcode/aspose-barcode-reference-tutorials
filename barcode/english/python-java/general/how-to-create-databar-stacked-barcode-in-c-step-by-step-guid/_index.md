---
category: general
date: 2026-10-21
description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
  adjust aspect ratio, and save PNG images in this complete tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: en
lastmod: 2026-10-21
og_description: create databar stacked barcode in C# with Aspose.BarCode. Follow this
  guide to configure X‑dimension, change aspect ratio, and export PNG files.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Create databar stacked barcode in C# – full programming guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: How to create databar stacked barcode in C# – step‑by‑step guide
url: /python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create databar stacked barcode in C# – step‑by‑step guide

If you need to **create databar stacked barcode** in a .NET application, this guide shows you exactly how. You will see how to configure the X‑dimension, change the aspect ratio, and save the barcode as PNG files.

Generating a DataBar stacked barcode does not require a complex build pipeline. This tutorial covers everything you need: required packages, code‑by‑code explanation, and tips for common pitfalls. By the end you can produce multiple barcode images with different aspect ratios in a single method.

## What you’ll need

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports C#)  
* **Aspose.BarCode for .NET** NuGet package – the library that provides `BarcodeGenerator` and `EncodeTypes`  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the project and import namespaces

Create a new console project or add the code to an existing one. Import the required namespaces so the compiler recognises the barcode classes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

These `using` statements expose `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat` used later in the example.

## Step 2: Define the output folder

Choose a folder where the generated PNG files will be written. Using an absolute or relative path works the same way; the example uses a relative folder called `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Creating the folder programmatically prevents runtime errors when the directory is missing.

## Step 3: Initialize the **create databar stacked barcode** generator

Create a `BarcodeGenerator` instance with `EncodeTypes.DatabarStackedOmniDirectional`. The sample data `(01)12345678901231` follows the GS1‑128 format required by DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

The generator object holds all parameters that affect the visual appearance of the barcode.

## Step 4: Set the X‑dimension (pixel width of the smallest bar)

The X‑dimension controls the overall size of the barcode without altering the encoded data. A value of `2` pixels provides a clear, scannable image for most screen resolutions.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Adjust this value if you need a larger or smaller barcode; keep the ratio between width and height consistent.

## Step 5: Configure the aspect ratio and save the first image

The aspect ratio determines the height‑to‑width relationship of a DataBar stacked barcode. An aspect ratio of `15` is a common default that yields a compact visual.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The `Save` method writes a PNG file to the folder defined earlier. The file name clearly indicates the used aspect ratio.

### Expected output for aspect ratio 15

The generated `DatabarAspectRatio15.png` looks similar to the illustration below.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Alt text:* `create databar stacked barcode image saved with aspect ratio 15`

## Step 6: Change the aspect ratio and save a second image

You can reuse the same `BarcodeGenerator` instance to produce variations. Changing the `AspectRatio` to `30` doubles the height of each bar stack, which may be required for high‑resolution printing.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Expected output for aspect ratio 30

The `DatabarAspectRatio30.png` image is taller, preserving the same width while increasing readability for distant scanners.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Alt text:* `create databar stacked barcode image saved with aspect ratio 30`

## Full source code

Putting all steps together results in a self‑contained program you can run immediately.

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
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Compile and run the program. After execution, the `Barcodes` directory contains two PNG files, each representing a **create databar stacked barcode** with a different aspect ratio.

## Pro tips and common pitfalls

* **Pro tip:** Keep the X‑dimension between 1 px and 4 px for most screen‑based use cases. Larger values increase file size without improving scan reliability.
* **Pitfall:** Changing the `EncodeTypes` value after the generator is created does not update the internal encoding. Always specify the correct `EncodeTypes` in the constructor.
* **Pro tip:** When you need more than two aspect ratios, loop over an array of integer values and call `Save` inside the loop. This reduces code duplication.
* **Pitfall:** Saving to a path without write permission throws an `UnauthorizedAccessException`. Ensure the application runs with appropriate file‑system rights.

## Conclusion

You now know how to **create databar stacked barcode** in C# using Aspose.BarCode. The guide covered setting up the environment, configuring X‑dimension, adjusting the aspect ratio, and saving PNG files. With this foundation you can generate additional variations, integrate barcode creation into web APIs, or embed the images into PDF reports.

Next, explore related topics such as **DataBar Stacked Omnidirectional** scanning best practices, embedding barcodes in **ASP.NET Core** responses, or generating **QR codes** with the same library. Experiment with different `EncodeTypes` and image formats to fit the needs of your application.

Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}