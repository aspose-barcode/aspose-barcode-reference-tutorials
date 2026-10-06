---
category: general
date: 2026-09-19
description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
  PDF417 barcode settings and create a barcode image C# developers can use instantly.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: en
lastmod: 2026-09-19
og_description: How to generate barcode in C# with detailed instructions. Customize
  PDF417 barcode parameters and create a barcode image C# projects can use today.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: How to generate barcode and customize PDF417 barcode in C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: How to generate barcode and customize PDF417 barcode in C#
url: /net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode and customize PDF417 barcode in C#

If you need to **how to generate barcode** in a .NET application, this tutorial shows you a complete, ready‑to‑run solution. You’ll learn how to customize PDF417 barcode dimensions, choose the number of columns, and finally **create barcode image C#** projects can embed directly.

Generating a barcode doesn’t require a complex build pipeline. By the end of this guide you will have a PNG file containing a MicroPDF417 barcode that matches the exact size and resolution you need.

## Prerequisites

You should have the following installed before you start:

* .NET 6.0 SDK or later (the code also works with .NET Framework 4.6+)
* Visual Studio 2022 (or any C# editor you prefer)
* Aspose.BarCode for .NET NuGet package – install with  
  `dotnet add package Aspose.BarCode`

No additional external tools are required.

## Step 1: Set up the project and import namespaces

Create a new console project and add the Aspose.BarCode reference.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Open `Program.cs` and add the required `using` directives:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

These namespaces expose the classes that let you **how to generate barcode** and control PDF417‑specific options.

## Step 2: Initialise the MicroPDF417 generator with the desired text

The first line creates a `BarcodeGenerator` instance configured for the MicroPDF417 symbology. The constructor takes the encoding type and the data string you want to encode.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Why this matters:** MicroPDF417 is a compact variant of the full PDF417 standard, ideal for small labels or mobile screens. Initialising the generator with the correct `EncodeTypes` ensures the library uses the right encoding algorithm.

## Step 3: Customize the X‑dimension (module width) for finer resolution

The X‑dimension controls the width of a single barcode module (the smallest black or white bar). Setting it to a low pixel value yields a higher‑resolution image.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** A larger X‑dimension makes the barcode easier for low‑resolution scanners to read, while a smaller value packs more data into a limited space. Adjust this value based on the scanning environment.

## Step 4: Define the number of columns to control barcode size

MicroPDF417 allows 1‑4 columns. More columns produce a shorter, wider barcode; fewer columns create a taller, narrower one.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Why this matters:** Choosing the right column count lets you fit the barcode into a specific UI element or printed label without manual scaling.

## Step 5: Save the barcode as a PNG image

Finally, write the generated barcode to disk. PNG preserves lossless quality, which is important for crisp scanning.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

If the target directory does not exist, the `Save` method throws an `ArgumentException`. You can guard against this with a simple check:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Full source code

Putting the pieces together, here is the complete, runnable program:

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
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Running this program produces a file named **MicroPdf417.png** that looks like the screenshot below (image omitted for brevity). The barcode encodes the text *Sample* and respects the X‑dimension and column settings you defined.

## Customizing other PDF417 options

While this guide focuses on **customize pdf417 barcode** parameters that affect size, Aspose.BarCode offers many additional settings you might need:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Controls the number of rows (height) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Sets error‑correction level (higher = more tolerant) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Generates a truncated barcode (no stop pattern) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Chooses numeric, text, or byte compaction | `CompactionModes.Numeric`, etc. |

**Pro tip:** When you need a barcode that fits a fixed width, start by increasing `Columns` and decreasing `XDimension`. If the scanner reports missed symbols, raise the `ErrorLevel` to improve redundancy.

## Handling edge cases

* **Text too long for MicroPDF417:** The Micro variant supports up to 1 KB of data. If your string exceeds this limit, switch to the full `Pdf417` symbology by changing `EncodeTypes.MicroPdf417` to `EncodeTypes.Pdf417`.
* **Unsupported image format:** `BarCodeImageFormat` also supports `Jpeg`, `Bmp`, and `Gif`. Choose a format that matches your downstream processing pipeline.
* **Cross‑platform paths:** Use `Path.Combine` instead of hard‑coded backslashes when targeting Linux or macOS.

## Verifying the barcode

You can verify the generated image with any standard barcode scanner app (mobile or desktop). The scanner should return the original text **Sample**. If it fails:

1. Check that the X‑dimension is not set below 1 pixel (some scanners cannot resolve sub‑pixel modules).
2. Ensure the output file is not corrupted—re‑run the program and compare file sizes.
3. Increase `ErrorLevel` to improve tolerance.

## Conclusion

You now know **how to generate barcode** in C# using Aspose.BarCode, how to **customize pdf417 barcode** dimensions and column count, and how to **create barcode image C#** projects can embed directly. The complete example demonstrates a practical workflow from project setup to final PNG output.

Next, explore other symbologies such as QR, Code128, or DataMatrix by swapping the `EncodeTypes` enum value. Adjusting additional parameters like `Resolution` or `Margin` lets you fine‑tune every barcode for your specific application.

Happy coding, and let your barcodes empower your next automation project!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}