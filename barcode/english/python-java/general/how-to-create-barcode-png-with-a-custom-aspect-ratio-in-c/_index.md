---
category: general
date: 2026-10-05
description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
  DataBar omnidirectional barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: en
lastmod: 2026-10-05
og_description: Create barcode PNG in C# and discover how to set aspect ratio 15 for
  stacked DataBar omnidirectional barcodes in a few steps.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Create barcode PNG in C# – set aspect ratio 15 tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: How to create barcode PNG with a custom aspect ratio in C#
url: /python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode PNG with a custom aspect ratio in C#

If you need to **create barcode PNG** in C#, this guide shows you **how to set aspect ratio** 15 for a stacked DataBar omnidirectional barcode. We'll walk through each API call, explain why the aspect ratio matters, and give you a complete, runnable example you can drop into any .NET project.

Generating a barcode image is a common requirement for inventory systems, shipping labels, and retail point‑of‑sale applications. By the end of this tutorial you will have a PNG file that meets the exact visual specifications required by your business partner. No external tools, no manual image editing—just code.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later (the example uses .NET 6 but works with .NET 5+)
* Visual Studio 2022 (or any IDE that supports .NET)
* The **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Write permission to the folder where you want to save the PNG file

These requirements are minimal; the same code works in .NET Core, .NET Framework, or a console application.

## Create barcode PNG with Aspose.BarCode

The first step is to instantiate the `BarcodeGenerator` class with the correct barcode type. In this case we use `EncodeTypes.DatabarStackedOmniDirectional`, which produces a stacked DataBar that can be read from any direction.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Why this matters:* The constructor takes two arguments—**the barcode symbology** and **the data string**. The DataBar format expects a GS1 application identifier, which is why the sample data starts with `(01)`.

## How to set aspect ratio for a stacked DataBar

The visual width of a DataBar is controlled by the **aspect ratio** property. A higher ratio makes the bars wider, which can improve scan reliability on low‑resolution printers.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

The `XDimension` defines the size of a single module (the smallest bar or space). Keeping this at 2 px gives a crisp, high‑density image suitable for most label printers.

## Set aspect ratio 15 – code walkthrough

Now we apply the **set aspect ratio 15** requirement. This is the core of the tutorial and demonstrates the exact API call you need.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Why 15?* The default aspect ratio for stacked DataBar is 12. Raising it to 15 expands the width of each bar by 25 %, which often matches the specifications of logistics providers that require a broader barcode for faster scanning.

## Save the barcode as PNG

With the generator configured, the final step is to write the image to disk. The `Save` method accepts a file path and an image format enum.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

The PNG format preserves lossless quality, ensuring that the barcode renders exactly as designed on any display or printer.

## Complete example and expected output

Below is the full program you can copy into a console app's `Main` method. It includes all the steps described above, plus a small verification message.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Expected output**

Running the program creates a file named `DatabarAspectRatio15.png` containing a clear, wide stacked DataBar barcode. When you open the PNG, you should see a horizontally stretched barcode that still complies with the GS1 DataBar specifications.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **create barcode PNG showing a stacked DataBar with aspect ratio 15**

### Tips and common pitfalls

| Situation | Recommendation |
|-----------|----------------|
| **Image looks blurry** | Increase `XDimension.Pixels` to 3 px or higher, but keep the overall image size under 500 px to avoid oversized files. |
| **Scanner cannot read the code** | Verify the data string follows the GS1 format (`(01)` prefix). Also, ensure the printer resolution is at least 300 dpi. |
| **Need a different file format** | Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`—the API supports all major raster formats. |
| **Running in a web application** | Use `generator.Save(Stream, BarCodeImageFormat.Png)` to write directly to the HTTP response without touching the file system. |

### Extending the example

* **Multiple barcodes in one image:** Create additional `BarcodeGenerator` instances and draw them on a single `Bitmap` using `Graphics`.  
* **Adding human‑readable text:** Set `generator.Parameters.Caption.Visible = true` and customize the font via `generator.Parameters.Caption.Font`.  
* **Dynamic aspect ratio:** Pull the ratio value from a configuration file or database to generate barcodes with varying widths on the fly.

## Conclusion

In this tutorial you learned how to **create barcode PNG** in C# and precisely **set aspect ratio** 15 for a stacked DataBar omnidirectional barcode. The complete, runnable code demonstrates every required API call, explains why each setting matters, and provides practical tips for real‑world deployments.  

Next, you might explore **how to set aspect ratio** for other barcode types (e.g., QR Code or Code 128) or integrate the generator into an ASP .NET Core service that returns barcode images on demand. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}