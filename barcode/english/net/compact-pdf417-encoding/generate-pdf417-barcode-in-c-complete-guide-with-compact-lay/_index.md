---
category: general
date: 2026-08-19
description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
  C# using Aspose.BarCode with compact mode and custom settings.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: en
lastmod: 2026-08-19
og_description: Generate PDF417 barcode in C# with Aspose.BarCode. This tutorial shows
  how to generate PDF417 barcode C# in compact mode, set X‑dimension, and save as
  PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Generate PDF417 barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Generate PDF417 barcode in C# – complete guide with compact layout
url: /net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate PDF417 barcode in C# – complete guide

If you need to **generate PDF417 barcode** in a .NET application, this tutorial shows you exactly how to do it. You’ll see a concise, production‑ready example that creates a compact PDF417 barcode, customizes the X‑dimension, and saves the result as a PNG image.

Generating a PDF417 barcode is common when you have to encode large amounts of data—such as ticket information, shipping manifests, or identity documents—in a machine‑readable format. Using Aspose.BarCode makes the process straightforward, and the code works with .NET 6+ or .NET Framework 4.7.2 and later.

In this guide you will:

* Install the Aspose.BarCode NuGet package.
* Write a self‑contained C# program that **generates PDF417 barcode** with a small column count and compact (truncated) mode.
* Adjust the bar width (X‑dimension) for sharper rendering.
* Save the barcode as a PNG file.
* Explore variations, edge cases, and best‑practice tips.

## Prerequisites

Before you start, make sure you have:

* Visual Studio 2022 (or any C# IDE) with .NET 6 SDK installed.
* Internet access to download the **Aspose.BarCode** NuGet package.
* Write permission to a folder where the PNG file will be saved.

No additional libraries are required; Aspose.BarCode handles image encoding internally.

## Step 1: Add the Aspose.BarCode package

Open your project in Visual Studio, right‑click the solution, and select **Manage NuGet Packages**. Search for `Aspose.BarCode` and install the latest stable version.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Keep the package up to date. New releases often include performance improvements and support for the latest .NET runtimes.

## Step 2: Create a minimal console application

Create a new C# console project if you don’t already have one:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Replace the content of `Program.cs` with the full example below. This program demonstrates **how to generate PDF417 barcode C#** from start to finish.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Why each line matters

* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports up to ~1.1 KB of data.
* **`XDimension.Pixels = 2`** – sets the basic bar width. Smaller values make the barcode thinner; larger values improve readability on low‑resolution devices.
* **`Pdf417.Columns = 3`** – limits the number of columns, forcing the generator to use more rows, which results in a taller but narrower barcode.
* **`Pdf417.Truncate = true`** – activates compact mode, removing the stop pattern and shrinking the image without losing data integrity.
* **`Save(..., BarCodeImageFormat.Png)`** – writes a PNG file. You could also choose `Jpeg`, `Bmp`, or `Svg` depending on downstream needs.

Run the program:

```bash
dotnet run
```

You should see the console output confirming the file location, and the folder will contain `CompactPdf417.png`. Opening the PNG shows a clear, compact PDF417 barcode that encodes the Unicode string.

## Step 3: Verify the barcode (optional but recommended)

To ensure the barcode is readable, you can use any standard PDF417 scanner app on a smartphone or a desktop decoder library. The encoded text should match the original `data` string exactly, including the special characters.

If you encounter decoding issues:

* Increase the `XDimension` to 3 or 4 pixels.
* Reduce the number of columns (e.g., set `Columns = 2`).
* Disable `Truncate` (`Truncate = false`) to add the stop pattern.

These adjustments trade size for readability, which is useful for low‑resolution printers or scanners.

## Step 4: Explore common variations

### 4️⃣ Generate a high‑density PDF417 for printing

If you need a barcode that fits on a small label, increase the column count and lower the X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Change the output format to SVG for vector scaling

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG output scales without loss of quality, perfect for responsive web pages.

### 6️⃣ Encode binary data (e.g., a byte array)

If you need to embed binary payloads, convert them to a Base64 string first:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

The barcode now carries the binary information, and the decoder must reverse the Base64 step.

## Frequently asked questions

| Question | Answer |
|----------|--------|
| **Can I generate PDF417 without Aspose?** | Yes, other libraries like ZXing.Net or Dynamsoft exist, but Aspose.BarCode offers richer layout control (columns, truncation) and better Unicode handling. |
| **What is the maximum data length?** | PDF417 can encode up to 1,108 bytes (≈ 1 KB) of binary data. If you exceed this, consider splitting the data across multiple barcodes. |
| **Is compact mode compliant with standards?** | Truncated PDF417 is part of the ISO/IEC 15438 spec and is widely supported, but verify that your target scanner explicitly supports it. |
| **How do I change the background color?** | Set `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` and `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` before saving. |

## Conclusion

You now know **how to generate PDF417 barcode C#** using Aspose.BarCode, how to fine‑tune the X‑dimension, enable compact mode, and export the result as a PNG image. The complete, runnable example can be copied into any .NET project, and the variations shown let you adapt the barcode for printing, web, or binary payload scenarios.

Next steps you might explore:

* Integrate the barcode generation into an ASP.NET Core API that returns the image on demand.
* Combine PDF417 with QR codes on the same label for dual‑format scanning.
* Use the Aspose.BarCode `Reader` class to decode the generated image and verify data programmatically.

Happy coding, and enjoy the flexibility that **generate PDF417 barcode** solutions bring to your applications!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}