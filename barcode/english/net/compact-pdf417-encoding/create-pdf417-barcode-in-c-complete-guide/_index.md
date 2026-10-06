---
category: general
date: 2026-09-22
description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
  PDF417 barcode images, set columns/rows, and save as PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
language: en
lastmod: 2026-09-22
og_description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
  PDF417 barcode images, customize layout, and export to PNG.
og_image_alt: Screenshot of a generated PDF417 barcode saved as PNG
og_title: Create PDF417 barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create PDF417 barcode in C# with Aspose.BarCode. Learn how to generate
    PDF417 barcode images, set columns/rows, and save as PNG.
  headline: Create PDF417 barcode in C# – complete guide
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
- image generation
title: Create PDF417 barcode in C# – complete guide
url: /net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PDF417 barcode in C# – complete guide

If you need to **create PDF417 barcode** in a .NET application, this tutorial shows you exactly how. You’ll see a full, runnable example that generates a PDF417 barcode, customizes its column and row layout, and saves the result as a PNG image.

Generating barcodes is a common requirement for inventory systems, ticketing platforms, and document automation. By the end of this guide you’ll be able to answer the question *how to generate PDF417 barcode* programmatically, without leaving your IDE.

## Prerequisites

Before you start, make sure you have:

- .NET 6.0 or later installed (the code also works with .NET Framework 4.8)
- A recent version of **Aspose.BarCode for .NET** (the free trial works for development)
- An IDE such as Visual Studio 2022 or Visual Studio Code
- Basic familiarity with C# syntax

> **Pro tip:** If you are using a CI/CD pipeline, add the NuGet package `Aspose.BarCode` to your project file so the build restores it automatically.

## Step 1: Install the Aspose.BarCode NuGet package

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version of the library to your project and updates the `.csproj` file accordingly.

## Step 2: Create a PDF417 barcode generator

The generator object is the entry point for all barcode operations. You specify the symbology (`EncodeTypes.Pdf417`) and the text you want to encode.

```csharp
using Aspose.BarCode.Generation;

// ...

// Step 2: Instantiate the generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

The `BarcodeGenerator` class abstracts the encoding algorithm, so you don’t have to deal with low‑level bit manipulation.

## Step 3: Adjust the PDF417 layout – columns and rows

PDF417 lets you control the number of columns (horizontal modules) and rows (vertical modules). Adjusting these values changes the barcode’s density and physical size.

```csharp
// Step 3: Configure layout
generator.Parameters.Barcode.Pdf417.Columns = 4; // supported range: 2‑10
generator.Parameters.Barcode.Pdf417.Rows = 9;    // optional; if omitted, rows are auto‑calculated
```

- **Columns**: Determines how many data columns the barcode will contain. Fewer columns produce a taller barcode.
- **Rows**: Allows you to force a specific height. Leaving it at `0` lets the engine choose the optimal count.

## Step 4: Save the barcode image as PNG

Finally, export the barcode to an image format that fits most UI frameworks.

```csharp
using Aspose.BarCode;

// ...

// Step 4: Save as PNG
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417_4x9.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

The `BarCodeImageFormat.Png` enum ensures lossless compression, which is ideal for further processing or printing.

## Full working example

Put everything together in a console app called `Pdf417Demo`.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Install Aspose.BarCode via NuGet before running this code

            // 2️⃣ Create the generator
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 3️⃣ Set layout – 4 columns, 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;

            // 4️⃣ Define output path
            string outputPath = Path.Combine(
                Environment.CurrentDirectory, "Pdf417_4x9.png");

            // 5️⃣ Save the barcode
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created at: {outputPath}");
        }
    }
}
```

### Expected output

Running the program prints a confirmation line and creates a file similar to the screenshot below:

![Generated PDF417 barcode](/images/pdf417-example.png "Create PDF417 barcode – PNG output")

The saved `Pdf417_4x9.png` contains a clear, scannable PDF417 symbol that encodes the text **“Sample”**.

## How to generate PDF417 barcode with custom data

If you need to encode more than a single word, simply replace the second argument of `BarcodeGenerator` with any string (including line breaks). The library automatically splits the data across rows and columns according to the layout you defined.

```csharp
var generator = new BarcodeGenerator(
    EncodeTypes.Pdf417,
    "OrderID: 12345\nDate: 2026-09-22\nCustomer: John Doe");
```

The same layout settings (columns = 4, rows = 9) still apply, but the barcode will grow vertically if the data exceeds the available space.

## Edge cases and troubleshooting

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| Barcode appears too small on screen | DPI of the saved PNG | Pass a `Resolution` object: `generator.Save(path, BarCodeImageFormat.Png, new Resolution(300))` |
| Rows are ignored | `Rows` set to `0` or left unset | Explicitly assign a positive integer (e.g., `Rows = 9`) |
| Text is truncated | Column count too low for data length | Increase `Columns` (max 10) or let the engine auto‑size by setting `Columns = 0` |
| Scan fails on mobile | Insufficient contrast | Use `generator.Parameters.Barcode.ForegroundColor = Color.Black` and `BackgroundColor = Color.White` |

These tips help you fine‑tune the barcode for real‑world scanning devices.

## Why you should use Aspose.BarCode for PDF417

- **Full control** over layout (columns, rows, error correction)
- **Zero‑dependency** image generation – no external graphics libraries needed
- **Cross‑platform** support (Windows, Linux, macOS) because it targets .NET Standard
- **Extensive documentation** and sample code directly from the vendor

Choosing this library ensures that the **create PDF417 barcode** task stays maintainable and future‑proof.

## Conclusion

You now know how to **create PDF417 barcode** in C# using Aspose.BarCode, adjust its columns and rows, and export the result as a PNG file. This complete solution answers *how to generate PDF417 barcode* for any .NET project, and you can extend it by changing the encoded text, image format, or resolution.

**Next steps**

- Experiment with other image formats such as `Jpeg` or `Bmp`.
- Combine the barcode with a PDF document using `Aspose.PDF` for end‑to‑end report generation.
- Explore error‑correction levels (`generator.Parameters.Barcode.Pdf417.ErrorLevel`) to improve scan reliability in noisy environments.

Happy coding, and enjoy embedding robust PDF417 symbols in your applications!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Generate PDF417 barcode C# – complete guide with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}