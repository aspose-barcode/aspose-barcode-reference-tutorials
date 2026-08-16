---
category: general
date: 2026-08-15
description: Read barcode from image in C# using BarCodeReader. Learn how to read
  multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: en
lastmod: 2026-08-15
og_description: Read barcode from image in C# with a step‑by‑step guide. Discover
  how to read multiple barcodes C#, decode PDF417 symbols, and run a complete C# BarCodeReader
  example.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Read barcode from image in C# – BarCodeReader tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Read barcode from image in C# – BarCodeReader tutorial
url: /net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read barcode from image in C# – BarCodeReader tutorial

If you need to **read barcode from image** in a .NET application, this guide shows you exactly how to do it with the `BarCodeReader` class. You’ll also see how to **read multiple barcodes C#**, decode a PDF417 symbol, and get a complete **C# BarCodeReader example** you can copy into your project.

The tutorial covers every step—from adding the required NuGet package to printing extended PDF417 fields—so you finish with a runnable console program. No external documentation is needed; all code and explanations are included.

## What you’ll need

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code works with .NET Core and .NET Framework)
* Visual Studio 2022 or any C#‑compatible editor
* The `Aspose.BarCode` NuGet package (or the equivalent library that provides `BarCodeReader`)
* An image file that contains a Macro PDF417 barcode (e.g., `ExtPDF417Meta.png`)

Having these prerequisites ensures the sample compiles without additional configuration.

## Read barcode from image with BarCodeReader

The first step is to create a `BarCodeReader` instance that points at the image file and tells the library which barcode type to look for.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Why this works:**  
`BarCodeReader` opens the image, scans for the specified `DecodeType`, and returns a collection of `BarCodeResult` objects. Each result contains the generic barcode data (`CodeTypeName`, `CodeText`) and, for Macro PDF417, an `Extended.Pdf417` object that exposes all additional fields defined by the standard.

## Read multiple barcodes C# in a single image

Sometimes an image contains more than one barcode (e.g., QR code beside a PDF417). To handle that scenario, simply omit the explicit `DecodeType` or pass `DecodeType.AllSupported` and loop through the results.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Why you need this:**  
Specifying `AllSupported` tells the engine to try every barcode format it knows, which guarantees that you capture every symbol in the image. This is the recommended approach when you cannot predict the barcode types ahead of time.

## How to read PDF417 barcode using C#

If you only care about the classic PDF417 (non‑macro) format, change the `DecodeType` to `Pdf417`. The rest of the code stays identical, except the extended fields are not available.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Why this matters:**  
Classic PDF417 does not expose the macro‑specific properties, so the `Extended.Pdf417` block is unnecessary. Using the precise `DecodeType` also speeds up scanning because the library skips unsupported algorithms.

## Full C# BarCodeReader example you can copy

Below is the complete program that combines the three scenarios into a single, easy‑to‑run console application. Replace `YOUR_DIRECTORY/ExtPDF417Meta.png` with the actual path to your image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Expected output

When the sample image contains a Macro PDF417 barcode, the console prints something similar to:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

If the image contains only a regular PDF417, the “Macro PDF417” section will be empty, and the “Classic PDF417” section will display the decoded text.

## Conclusion

You now know how to **read barcode from image** in C# using `BarCodeReader`, how to **read multiple barcodes C#** in a single file, and the exact steps to **read PDF417 barcode**—both macro and classic variants. The full **C# BarCodeReader example** is ready to paste into any .NET project, and you can extend it to handle other formats or integrate it into a larger image‑processing pipeline.

**Next steps**

* Explore error‑handling patterns such as `try / catch` around the reader block.  
* Experiment with the `ReaderParameters` object to tune detection speed and accuracy.  
* Combine barcode reading with image preprocessing libraries (


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}