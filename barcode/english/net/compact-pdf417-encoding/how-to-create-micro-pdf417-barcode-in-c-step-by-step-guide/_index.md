---
category: general
date: 2026-08-22
description: Learn how to create micro PDF417 barcode in C# and generate a barcode
  PNG image. Includes setting barcode dimensions and saving the file.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: en
lastmod: 2026-08-22
og_description: Create micro PDF417 barcode in C# and export it as a PNG. Follow this
  guide to set barcode dimensions and generate a barcode image quickly.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Create micro PDF417 barcode in C# – full coding tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: How to create micro PDF417 barcode in C# – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create micro PDF417 barcode in C# – step‑by‑step guide

If you need to **create micro PDF417 barcode** for a ticketing system, inventory label, or mobile scan, this tutorial shows you exactly how. You’ll see the complete C# program that generates a barcode PNG, learn how to set barcode dimensions, and understand each configuration option.

By the end of this guide you will be able to generate a high‑resolution barcode image, customize the X‑dimension, choose the column count, and save the result as a PNG file—all with a few lines of code.

## What you’ll need

- .NET 6.0 SDK or later (the code works with .NET Core and .NET Framework)
- Visual Studio 2022 or any C#‑compatible IDE
- The **Aspose.BarCode for .NET** NuGet package (or any library that supports `EncodeTypes.MicroPdf417`)
- Basic familiarity with C# syntax

> **Pro tip:** The free community edition of Aspose.BarCode is sufficient for development and testing. For production, obtain a license to remove evaluation watermarks.

## Step 1: Install the barcode library

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

This adds the `Aspose.BarCode` assembly, which provides the `BarcodeGenerator` class used to **create barcode image C#** applications.

## Step 2: Initialize the generator – create micro PDF417 barcode

The first actionable line creates a `BarcodeGenerator` instance configured for the Micro PDF417 symbology and supplies the data you want to encode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Why this matters*: The `EncodeTypes.MicroPdf417` enum tells the library to use the compact version of PDF417, which is ideal for small labels and mobile screens.

## Step 3: How to set barcode dimensions in C#

Fine‑tuning the module width (X‑dimension) controls the visual density of the barcode. A smaller value yields a sharper image, while a larger value makes the barcode easier to scan at a distance.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why you should set dimensions**: Without adjusting the X‑dimension, the default value may produce a barcode that looks blurry when rendered at high DPI. Setting it to 2 pixels is a good balance for most screen‑based scans.

## Step 4: Choose the number of columns – controlling barcode width

Micro PDF417 allows between 1 and 4 columns. More columns compress the data horizontally, reducing the overall image width.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Edge case*: If you request 5 columns the library throws an `ArgumentOutOfRangeException`. Always stay within the documented range.

## Step 5: How to generate barcode PNG – saving the image

Now you can export the generated barcode to a PNG file. PNG preserves lossless quality, which is essential for reliable scanning.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

When you run the program, you’ll see a console message confirming the file location. The resulting `MicroPdf417.png` looks like this:

![Screenshot showing a generated micro PDF417 barcode created with C#](micro-pdf417-example.png "Generated micro PDF417 barcode")

*Image alt text*: **micro PDF417 barcode generated in C#** – demonstrates the final output after applying the dimensions and column settings.

## Step 6: Run and verify the output

1. Build the project: `dotnet build`.
2. Execute: `dotnet run`.
3. Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode scanner app.

You should see the text **“Sample text”** decoded. If the scanner reports an error, double‑check the X‑dimension and column count – extreme values can make the barcode too dense for some devices.

## Common variations and troubleshooting

| Situation | Adjustment |
|-----------|------------|
| **Need a larger barcode for low‑resolution printers** | Increase `XDimension.Pixels` to 3 or 4. |
| **Want a taller barcode without changing width** | Set `generator.Parameters.Barcode.Pdf417.Rows` (rows range 3‑90). |
| **Generating multiple barcodes in a loop** | Re‑use the same `BarcodeGenerator` instance and only change `CodeText` before each `Save`. |
| **Saving as JPEG instead of PNG** | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. |
| **Running on .NET Framework 4.7** | The same code works; just reference the appropriate `Aspose.BarCode.dll`. |

## Full source listing (runnable)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Expected output** – a 200 × 100‑pixel PNG file containing a crisp Micro PDF417 barcode that decodes to “Sample text”.

## Conclusion

You now know how to **create micro PDF417 barcode** in C#, **set barcode dimensions**, and **generate a barcode PNG** image. The complete example demonstrates every required step—from library installation to saving the final file—so you can embed barcode generation directly into your own applications.

Next, explore related topics such as **creating QR codes with Aspose.BarCode**, **customizing colors**, or **embedding barcodes in PDF documents**. Each of those builds on the same `BarcodeGenerator` fundamentals covered here.

Feel free to experiment with different data strings, column counts, and X‑dimension values to suit your specific scanning environment. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}