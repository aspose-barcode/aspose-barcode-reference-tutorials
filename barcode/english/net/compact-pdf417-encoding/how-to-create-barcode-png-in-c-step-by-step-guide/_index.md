---
category: general
date: 2026-10-15
description: Create barcode PNG in C# with a compact PDF417 example – learn how to
  set columns, adjust dimensions, and generate the image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: en
lastmod: 2026-10-15
og_description: Create barcode PNG in C# with a compact PDF417 example. This guide
  shows how to set columns, adjust dimensions, and save the image.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Create barcode PNG in C# – complete programming tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: How to create barcode PNG in C# – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode PNG in C# – step‑by‑step guide

If you need to **create barcode PNG** files from C# code, this tutorial shows you a complete solution in just a few lines. You’ll see how to set columns, adjust the module size, and save a compact PDF417 barcode as a PNG image—all with a single, easy‑to‑read example.

Generating barcodes programmatically removes the manual step of using a graphics editor, and it lets you embed barcodes directly into invoices, tickets, or inventory labels. In the sections that follow we’ll cover everything you need to know to **how to create barcode** images, why each configuration matters, and how to adapt the code for different use‑cases.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later (the code also works with .NET Framework 4.7+)
* A reference to a barcode library that supports PDF417, such as **Aspose.BarCode for .NET** or **IronBarcode**. The example uses Aspose.BarCode, which you can install via NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Basic familiarity with C# syntax and Visual Studio (or any IDE you prefer).

> **Pro tip:** If you prefer a free alternative, the open‑source **ZXing.Net** library also supports PDF417, but the property names differ slightly. The concepts shown here remain the same.

## How to create barcode PNG in C# (primary step)

The core of the solution is a `BarcodeGenerator` object configured for PDF417 encoding. The following sections break down each line of code, explain **how to set columns**, and show why the settings affect the final PNG size.

### Step 1: Initialise the barcode generator with the desired text

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Why this matters*: The `EncodeTypes.Pdf417` enum tells the library to produce a 2‑dimensional stacked barcode. The constructor also accepts the data you want to encode, so you don’t need a separate `SetData` call.

### Step 2: Set the module (X) dimension in pixels

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

The **X dimension** controls the visual density of the barcode. A smaller value yields a tighter image, which is useful when you need a compact PNG for mobile screens or limited print space.

### Step 3: Define the number of columns for the PDF417 barcode

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

This line demonstrates **how to set columns**. PDF417 can automatically choose the optimal column count, but explicitly setting it gives you predictable width, especially when you embed the PNG in a fixed‑size layout.

### Step 4: Enable the compact layout by truncating the barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

When `Truncate` is true, the library removes trailing rows that contain no data, reducing the overall height of the image without losing information.

### Step 5: Save the barcode image as PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

The `Save` method writes the barcode to disk in the format you specify. PNG is loss‑less, making it ideal for scanning applications that require precise edge detection.

### Full, runnable example

Putting everything together, here is a self‑contained program you can copy, paste, and run:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Expected output** – After running the program, you’ll find `CompactPdf417.png` in the execution folder. The image contains a three‑column PDF417 barcode that is compact enough to fit on a standard 2 × 2 cm label while remaining fully scannable.

![Create barcode PNG example](placeholder.png){alt="Create barcode PNG using C#"}

## How to set columns for different data sizes (secondary keyword)

The number of columns influences both the width and the readability of the barcode:

| Columns | Approx. width (px) | Typical use‑case |
|--------|-------------------|------------------|
| 1‑2    | Narrow, tall      | Small tags, RFID‑like prints |
| 3‑5    | Balanced          | General‑purpose labels |
| 6‑9    | Wide, short       | Large posters or packaging |

If your data string grows, the library may automatically increase the row count to keep the barcode within the column limit. However, forcing a column count that is too low can cause the barcode to become excessively tall, which may not fit on a receipt printer. Adjust the column count based on the physical constraints of your output medium.

## How to create barcode images in other formats (secondary keyword)

While PNG is the most common format for web and mobile, you might need **how to create barcode** images in JPEG, BMP, or SVG for specialized workflows:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Choosing the right format depends on the downstream consumer:

* **PNG** – lossless, ideal for scanners.
* **JPEG** – smaller file size, acceptable when slight compression artifacts are tolerable.
* **SVG** – perfect for high‑resolution print or UI scaling.

## C# barcode example: handling errors and edge cases

A robust **c# barcode example** should anticipate runtime issues:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Why wrap in `try/catch`?* Invalid characters in the text, unsupported dimensions, or write‑permission problems will throw exceptions. Handling them gracefully prevents your application from crashing during batch processing.

## Extending the example: adding a logo or background

Many real‑world scenarios require a logo overlay or a colored background. The Aspose.BarCode API lets you combine the barcode with a bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

This technique keeps the **create barcode PNG** workflow intact while enriching the visual branding of the final image.

## Summary

In this guide we demonstrated how to **create barcode PNG** files in C# using a compact PDF417 configuration. You learned:

* The exact code needed to initialise a `BarcodeGenerator`.
* **How to set columns** and why column count matters for size and readability.
* How to adjust the X‑dimension and enable truncation for a tighter PNG.
* Ways to save the image in PNG, JPEG, or SVG.
* Error handling patterns for a production‑ready **c# barcode example**.
* Optional extensions such as logo overlay and background customization.

You now have a ready‑to‑run snippet that you can integrate into invoice generators, ticketing systems, or inventory management tools. Experiment with different column values, module sizes, or barcode types (e.g., QR, Code128) to see how the image changes.

## Next steps

* Explore other encoding types (`EncodeTypes.QR`, `EncodeTypes.Code128`) to cover more use‑cases.
* Combine barcode generation with PDF creation libraries (e.g., **iTextSharp**) to embed the PNG directly into documents.
* Investigate dynamic sizing: calculate the optimal column count based on the length of the input string and the target label dimensions.

Happy coding, and enjoy the simplicity of programmatically generating crisp barcode PNGs in C#!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}