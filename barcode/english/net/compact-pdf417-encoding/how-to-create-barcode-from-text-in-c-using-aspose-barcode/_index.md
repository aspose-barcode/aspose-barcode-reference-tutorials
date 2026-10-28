---
category: general
date: 2026-10-28
description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
  PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: en
lastmod: 2026-10-28
og_description: Create barcode from text in C# using Aspose.BarCode. This tutorial
  shows how to generate a PDF417 barcode image, customize size, columns, and compact
  mode.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Create a barcode from text in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: How to create barcode from text in C# using Aspose.BarCode
url: /net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode from text in C# using Aspose.BarCode

If you need to **create barcode from text** in a .NET application, this guide provides a ready‑to‑run solution. You will see how to **generate PDF417 barcode** images, control module width, column count, and enable compact mode without leaving your IDE.

The tutorial covers everything required to **generate barcode C#** code, from library installation to saving the final PNG file. By the end you can embed a high‑density PDF417 barcode in reports, tickets, or inventory labels.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any editor that supports .NET)  
* Internet access to download the Aspose.BarCode for .NET NuGet package  

These items are sufficient to compile and run the example on Windows, Linux, or macOS.

## Step 1: Install the Aspose.BarCode NuGet package

The library that powers the barcode generation is **Aspose.BarCode for .NET**. Install it with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `Aspose.BarCode` namespace, which contains the `BarcodeGenerator` class used throughout this tutorial.

## Step 2: Create a console project and add the code

Create a new console project and replace the generated `Program.cs` with the following code. The program demonstrates how to **create barcode from text** and save it as a **PDF417 barcode image**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Why each line matters

* **`EncodeTypes.Pdf417`** selects the PDF417 symbology, which is ideal for encoding large amounts of data in a two‑dimensional format.  
* **`XDimension.Pixels = 2`** reduces the module width, making the barcode denser and more suitable for limited space.  
* **`Pdf417.Columns = 3`** controls the number of vertical data columns; a lower count yields a taller but narrower barcode.  
* **`Pdf417.Truncate = true`** activates compact mode, trimming unused columns on the right‑hand side. This is the key setting that turns a regular PDF417 into a **compact PDF417 barcode image**.  

## Step 3: Build and run the project

Execute the following commands in the project directory:

```bash
dotnet build
dotnet run
```

When the program finishes, you will see a console message confirming the file location. Open `CompactPdf417.png` with any image viewer to verify the result.

**Expected output** – a high‑contrast PNG showing a compact PDF417 barcode that encodes the string `Åspóse.Barcóde©`. Scanning the image with a standard barcode reader returns the original text, confirming that **generate pdf417 barcode** succeeded.

## Step 4: Customizing the barcode for different scenarios

While the example uses a fixed column count and X‑dimension, you can adapt the generator for other requirements:

| Scenario | Adjustment |
|----------|------------|
| Larger data payload | Increase `Pdf417.Columns` or set `Pdf417.Rows` manually |
| Higher scan reliability | Raise `XDimension.Pixels` to 3 or 4 |
| Different image format | Replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` |
| Transparent background | Set `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

These options let you **generate barcode C#** solutions that fit mobile apps, desktop reports, or web services.

## Step 5: Handling edge cases and best practices

* **Unicode support** – The generator automatically encodes Unicode characters, but ensure your source string is UTF‑8 encoded if you read it from a file.  
* **Large text** – PDF417 can encode up to 1,850 alphanumeric characters. If you exceed this limit, the library throws an exception; split the data into multiple barcodes or switch to a higher‑capacity symbology.  
* **Error handling** – Wrap the generation code in a `try/catch` block to capture `BarCodeException` and provide a friendly error message.  
* **Performance** – Generating many barcodes in a loop benefits from reusing a single `BarcodeGenerator` instance and only updating `CodeText` between iterations.

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Full source listing

Below is the complete, self‑contained program that you can copy into `Program.cs`. No additional files are required.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Running this program creates the **pdf417 barcode image** shown in the illustration below.

![Compact PDF417 barcode created from text using C#](/images/compact-pdf417.png){.img-fluid alt="create barcode from text example showing a compact PDF417 barcode image"}

*Image description: The PNG file displays a compact PDF417 barcode that encodes the string “Åspóse.Barcóde©”.*  

## Conclusion

You now know how to **create barcode from text** in C# and produce a **PDF417 barcode image** with custom dimensions and compact mode. The example demonstrates the essential steps to **generate barcode C#**, handle Unicode data, and adjust visual parameters for different deployment scenarios.

Next, explore related topics such as **generate QR code in C#**, **add barcode to PDF documents**, or **embed barcodes in ASP.NET Core APIs**. Each of these builds on the same `BarcodeGenerator` fundamentals covered here.

Happy coding, and enjoy integrating barcodes into your .NET solutions!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate PDF417 Barcode in C# – Create PDF417 Barcode C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [How to generate PDF417 barcode with Aspose.BarCode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}