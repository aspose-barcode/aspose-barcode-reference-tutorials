---
category: general
date: 2026-10-15
description: Create barcode PNG quickly using C#. Learn how to generate barcode, change
  rows, configure barcode settings, and generate PDF417 barcode in a single tutorial.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to generate barcode
- how to change rows
- how to configure barcode
- generate pdf417 barcode
language: en
lastmod: 2026-10-15
og_description: Create barcode PNG in C# fast. This tutorial shows how to generate
  barcode, change rows, configure barcode, and generate PDF417 barcode with clear
  code.
og_image_alt: Generated PDF417 barcode saved as a PNG file
og_title: Create barcode PNG with PDF417 in C# – step-by-step guide
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG quickly using C#. Learn how to generate barcode,
    change rows, configure barcode settings, and generate PDF417 barcode in a single
    tutorial.
  headline: Create barcode PNG with PDF417 in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Create barcode PNG with PDF417 in C# – complete guide
url: /net/compact-pdf417-encoding/create-barcode-png-with-pdf417-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode PNG with PDF417 in C# – complete guide

If you need to **create barcode PNG** from C# code, this guide shows you exactly how to do it. We'll walk through generating a PDF417 barcode, changing rows, and configuring all the key parameters before saving the result as a PNG image.

You’ll learn how to **generate barcode** images programmatically, adjust the layout to match your design, and understand the options for configuring a barcode’s appearance. No external tools are required—just the Aspose.BarCode library (or any compatible .NET barcode package) and a few lines of code.

## What you’ll need

- .NET 6.0 or later (the sample uses .NET 6, but any recent .NET version works)
- A reference to the `Aspose.BarCode` NuGet package (`Install-Package Aspose.BarCode`)
- Basic familiarity with C# and Visual Studio (or your preferred IDE)

> **Pro tip:** If you prefer a free alternative, the same API surface is available in the open‑source `ZXing.Net` library; however, the code snippets below target Aspose.BarCode because it provides direct PDF417 layout controls.

## Step 1: Set up the project and add the barcode library

Create a new console app and add the NuGet package:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Then open `Program.cs` and add the required `using` directives:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

These namespaces expose the `BarcodeGenerator` class and the `EncodeTypes` enumeration you’ll use to **generate PDF417 barcode** images.

## Step 2: Create barcode PNG – basic generator

The first actionable line creates a `BarcodeGenerator` instance configured for PDF417 encoding. This is the core of **how to generate barcode** images.

```csharp
// Step 2: Initialize the generator with PDF417 and the data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
{
    // The rest of the configuration goes here
}
```

> **Why this matters:** The `EncodeTypes.Pdf417` flag tells the library which symbology to use. The second argument (`"Layout test"`) is the raw text that will be encoded into the barcode.

## Step 3: How to configure barcode – set module size

A module (or X dimension) defines the smallest printable element of the barcode. Adjusting it changes the overall image size without affecting data density.

```csharp
// Step 3: Set the module size (X dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Setting `Pixels = 2` gives a compact, high‑resolution **create barcode PNG** result that works well for web thumbnails and print.

## Step 4: How to change rows – customize the PDF417 layout

PDF417 allows you to explicitly control the number of columns and rows. This is the step that answers **how to change rows** in a barcode.

```csharp
// Step 4: Define a custom layout – 4 columns and 9 rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // number of data columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // number of rows (the focus of “how to change rows”)
```

> **Edge case:** If you request more rows than the data requires, the library will automatically add padding rows. Conversely, requesting too few rows may cause an exception because the data cannot fit.

## Step 5: Save the generated barcode as a PNG file

Finally, write the image to disk. This completes the **create barcode PNG** workflow.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode PNG saved to: {outputPath}");
```

When you run the program, you’ll see a file named `Pdf417_4x9.png` in the project folder. The image contains a PDF417 barcode with exactly 4 columns and 9 rows, rendered at 2‑pixel modules.

### Full runnable example

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for PDF417
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test"))
        {
            // Configure module size
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Custom layout: 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save as PNG
            string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Expected output** (console):

```
Barcode PNG saved to: C:\Path\To\BarcodeDemo\Pdf417_4x9.png
```

Open the PNG file and you’ll see a clean PDF417 barcode ready for scanning.

## How to generate barcode with different data

If you need to **generate barcode** for another string, simply replace the second argument of the `BarcodeGenerator` constructor:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "New data payload"))
{
    // Keep the same configuration or adjust as needed
}
```

The same configuration steps (module size, rows, columns) apply, allowing you to reuse the code for multiple payloads.

## How to change rows dynamically based on content length

Sometimes the number of rows must adapt to the length of the encoded text. You can calculate a safe row count before creating the generator:

```csharp
int estimatedRows = (int)Math.Ceiling(text.Length / (double)(columns * 2)); // rough estimate
generator.Parameters.Barcode.Pdf417.Rows = Math.Max(3, estimatedRows);
```

This snippet ensures you never request fewer than three rows (the library’s minimum) while scaling up for longer data.

## How to configure barcode for different image formats

Although the tutorial focuses on PNG, you can switch to JPEG, BMP, or TIFF by changing the `BarCodeImageFormat` enum:

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

PNG remains the best choice for loss‑less quality, especially when the barcode will be printed.

## Common pitfalls and troubleshooting

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Barcode appears blurry | X dimension too large or image scaling after save | Keep `XDimension.Pixels` ≤ 3 for on‑screen use, or upscale with a vector format (PDF) |
| Scanner cannot read barcode | Too few rows for the data length | Increase `Pdf417.Rows` or let the library auto‑size by omitting the explicit row setting |
| `ArgumentOutOfRangeException` on save | Output directory does not exist | Ensure `outputPath` points to a valid folder or create it with `Directory.CreateDirectory` |

## Summary

This tutorial demonstrated how to **create barcode PNG** files in C# using the PDF417 symbology. You learned:

- **How to generate barcode** with the `BarcodeGenerator` class  
- **How to change rows** and columns to control layout  
- **How to configure barcode** settings such as module size and image format  
- How to **generate PDF417 barcode** and save it as a PNG image

You now have a reusable code block that you can adapt for different data payloads, image formats, or layout requirements.

## Next steps

- Experiment with `Pdf417.ErrorCorrectionLevel` to improve scan reliability in low‑quality prints.  
- Combine multiple barcodes into a single PDF using Aspose.PDF for batch label generation.  
- Explore other symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) by swapping the enum value—this aligns with the secondary keyword **generate pdf417 barcode** while showing broader capabilities.

Happy coding, and enjoy creating crisp barcode PNGs for every application!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to create barcode PNG with a custom aspect ratio in C#](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}