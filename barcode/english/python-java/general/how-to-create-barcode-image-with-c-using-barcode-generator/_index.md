---
category: general
date: 2026-10-28
description: Create barcode image in C# quickly. Learn barcode generator c# usage,
  how to set pixel size, and how to change aspect ratio for DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to set pixel size
- how to change aspect ratio
- how to generate databar
language: en
lastmod: 2026-10-28
og_description: Create barcode image in C# with a Barcode Generator. Follow this guide
  to set pixel size, change aspect ratio, and generate DataBar barcodes.
og_image_alt: Screenshot of a generated barcode image created with C#
og_title: Create barcode image in C# – step‑by‑step guide
schemas:
- author: GroupDocs
  dateModified: '2026-10-28'
  description: Create barcode image in C# quickly. Learn barcode generator c# usage,
    how to set pixel size, and how to change aspect ratio for DataBar.
  headline: How to create barcode image with C# using Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- imaging
title: How to create barcode image with C# using Barcode Generator
url: /python-java/general/how-to-create-barcode-image-with-c-using-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode image with C# using Barcode Generator

If you need to **create barcode image** in a .NET application, this guide shows you exactly how. You’ll see a complete, runnable example that uses the Barcode Generator C# library to generate a DataBar stacked omnidirectional barcode, set the pixel size, and change the aspect ratio.

Generating barcodes programmatically removes the need for external tools and lets you embed the image directly into PDFs, reports, or UI controls. In the steps below we also cover **how to set pixel size** and **how to change aspect ratio**, two common requirements when you need a crisp, correctly‑scaled barcode.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A C#‑compatible IDE (Visual Studio, Rider, or VS Code)  
* The `BarcodeGenerator` NuGet package (e.g., `GroupDocs.Barcode` or `Aspose.Barcode`) installed in your project  

You can add the package with the following command:

```bash
dotnet add package GroupDocs.Barcode
```

> **Pro tip:** Verify the package version matches your target framework to avoid runtime incompatibilities.

## Create barcode image with Barcode Generator C#

The first step is to instantiate the generator with the desired barcode type and data. The example below creates a **DataBar stacked omnidirectional** barcode, which is ideal for retail scanning scenarios.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // Step 1: Create a BarcodeGenerator for DataBar stacked omnidirectional
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example data

        // Step 2: Set the pixel size of the X‑dimension (how to set pixel size)
        barcode.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Save an image with the first aspect ratio (how to generate databar)
        barcode.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcode.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // Step 4: Change the aspect ratio (how to change aspect ratio) and save a second image
        barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcode.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Why each line matters

* **Instantiate `BarcodeGenerator`** – The constructor takes a barcode symbology (`EncodeTypes.DatabarStackedOmniDirectional`) and the raw data string. Choosing the correct symbology ensures the scanner can read the code.
* **Set `XDimension.Pixels`** – This property controls the width of the smallest bar element. A value of `2` produces a fine‑grained image that remains readable on most screens. Adjust it higher if you need a larger barcode for low‑resolution printers.
* **Configure `AspectRatio`** – The DataBar family supports several aspect ratios that affect the height‑to‑width relationship. Values `15` and `30` are common; `15` yields a shorter barcode, while `30` produces a taller one.
* **`Save` method** – Saves the generated barcode to a PNG file. You can replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` if your downstream system requires a different format.

## How to set pixel size for different rendering contexts

Pixel size determines the visual density of the barcode. If a barcode will be displayed on a high‑DPI monitor, you might increase the pixel size to `3` or `4`. Conversely, for low‑resolution thermal printers, a smaller pixel size (e.g., `1`) reduces ink usage.

```csharp
// Example: increase pixel size for a high‑resolution display
barcode.Parameters.Barcode.XDimension.Pixels = 4;
```

**Edge case:** Setting the pixel size too low (< 1) throws an `ArgumentOutOfRangeException`. Always validate the value before assigning it.

## How to change aspect ratio without recreating the generator

Changing the aspect ratio is a simple property update; you do **not** need to recreate the `BarcodeGenerator` instance. This saves memory and improves performance when you need multiple images with different shapes.

```csharp
// Switch from a short to a tall barcode
barcode.Parameters.Barcode.DataBar.AspectRatio = 30;
barcode.Save("TallDatabar.png", BarCodeImageFormat.Png);
```

If you need more than two ratios, you can loop through an array:

```csharp
int[] ratios = { 15, 20, 25, 30 };
foreach (int ratio in ratios)
{
    barcode.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string fileName = $"DatabarAspectRatio{ratio}.png";
    barcode.Save(fileName, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {fileName}");
}
```

## Expected output

Running the program creates two PNG files (or more, if you use the loop). Open them in any image viewer; you should see a clean DataBar barcode:

* **DatabarAspectRatio15.png** – short, wide barcode suitable for narrow label spaces.  
* **DatabarAspectRatio30.png** – taller barcode that improves scan reliability on angled scanners.

Both images share the same pixel size (2 px per module) but differ only in height, demonstrating **how to change aspect ratio** while keeping other parameters constant.

## Common pitfalls and how to avoid them

| Symptom | Cause | Fix |
|---------|-------|-----|
| Barcode appears blurry | `XDimension.Pixels` set too low for the output resolution | Increase pixel size to at least `2` for screen display, `3` for print |
| Scanner cannot read the code | Wrong `EncodeTypes` for the data format | Verify that the GTIN‑14 data matches the chosen symbology |
| `ArgumentOutOfRangeException` on aspect ratio | Ratio value not supported by the library (valid range: 15‑30) | Use only values documented by the library, or catch the exception and fallback to a default |
| File not found after `Save` | Relative path points to a non‑existent directory | Use an absolute path or ensure `Directory.CreateDirectory` is called first |

```csharp
// Ensure the output folder exists
string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputDir);
barcode.Save(Path.Combine(outputDir, "DatabarAspectRatio15.png"), BarCodeImageFormat.Png);
```

## Next steps – extending the barcode workflow

Now that you can **create barcode image**, you might want to:

* **Embed the PNG into a PDF** using a library like `PdfSharp` or `iTextSharp`.  
* **Generate other symbologies** (QR, Code128, PDF417) by changing the `EncodeTypes` enum.  
* **Apply color transformations** by accessing `barcode.Parameters.Barcode.Image.Color`.  
* **Serve the image via an ASP.NET Core endpoint** for on‑the‑fly generation in web apps.

Each of these topics builds on the same core concepts covered in this tutorial, such as **barcode generator c#** usage, pixel‑size control, and aspect‑ratio manipulation.

## Conclusion

You now know how to **create barcode image** in C# with a Barcode Generator, how to set the pixel size, how to change the aspect ratio, and how to generate DataBar barcodes efficiently. The complete, runnable example can be copied into any .NET project, adapted for other symbologies, and extended to fit real‑world workflows.

Feel free to experiment with different `XDimension` values, aspect ratios, and output formats. If you run into issues, revisit the “Common pitfalls” table or consult the library’s official documentation for deeper configuration options. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create barcode image and adjust its aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-image-and-adjust-its-aspect-ratio-in-c/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}