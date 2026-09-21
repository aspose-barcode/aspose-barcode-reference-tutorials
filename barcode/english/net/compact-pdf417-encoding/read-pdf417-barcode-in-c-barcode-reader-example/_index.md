---
category: general
date: 2026-08-03
description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
  barcode reader example that also shows how to read multiple barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: en
lastmod: 2026-08-03
og_description: Read PDF417 barcode quickly with a C# BarCodeReader example. Follow
  this step‑by‑step guide to decode macro PDF417 and read multiple barcodes from an
  image.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Read PDF417 barcode in C# – complete barcode reader example
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Read PDF417 barcode in C# – barcode reader example
url: /net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read PDF417 barcode in C# – barcode reader example

If you need to read PDF417 barcode data from an image, this guide shows you how to do it with the **BarCodeReader** class in C#. You’ll learn a barcode reader example that also handles macro PDF417 and can read multiple barcodes in a single image.

Working with barcodes often means dealing with different image sources, varying lighting conditions, and sometimes composite data such as macro PDF417 segments. This tutorial covers everything you need to decode a PDF417 barcode, extract its extended fields, and process several barcodes from the same picture. By the end you will have a runnable console program that reads barcodes from an image file and prints detailed information to the console.

## What you’ll need

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A recent version of the **Aspose.BarCode for .NET** NuGet package (or any compatible library that provides `BarCodeReader` and `DecodeType.MacroPdf417`)  
* An image file that contains a PDF417 or macro PDF417 barcode (the sample uses `ExtPDF417Meta.png`)  
* A code editor or IDE such as Visual Studio 2022  

No additional services or external APIs are required.

## Setting up the project for barcode reading

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Place `ExtPDF417Meta.png` (or any image that contains a PDF417 barcode) into the project folder.  
   For this tutorial we assume the file resides at `YOUR_DIRECTORY/ExtPDF417Meta.png`.

The project is now ready to compile and run the barcode reader example.

## How to read PDF417 barcode with BarCodeReader

The core of the solution is a `using` block that creates a `BarCodeReader` instance, specifies `DecodeType.MacroPdf417`, and iterates over every detected barcode. The following code is a complete, self‑contained program that you can paste into `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Why this works**:  

* `DecodeType.MacroPdf417` tells the reader to look for the macro extension of PDF417, which carries additional metadata such as file ID, segment count, and timestamps.  
* The `using` statement guarantees that unmanaged resources (file handles, native decoding buffers) are released promptly.  
* The `foreach` loop automatically processes **all** barcodes that the image contains, satisfying the *read multiple barcodes* requirement.  

When you run the program (`dotnet run`), you should see output similar to the following:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

If the image contains more than one PDF417 barcode, the loop prints a separate block for each barcode, thereby demonstrating how to **read multiple barcodes** from a single picture.

## Reading multiple barcodes from an image

The same `BarCodeReader` instance can decode several barcode types at once. To broaden the scope from only macro PDF417 to any PDF417 (or even QR, Code128, etc.), adjust the `DecodeType` flag:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* is a bitmask, so you can combine any number of supported formats. This flexibility makes the snippet a **barcode reader example** that works for a wide variety of use cases, such as scanning product labels, tickets, or ID cards.

## Accessing macro PDF417 fields safely

Macro PDF417 adds a rich set of extended properties. However, not every barcode includes every field. Accessing a missing property can throw a `NullReferenceException`. The safest approach is to verify each property before printing:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Why this matters*: In real‑world deployments you may receive plain PDF417 barcodes that lack macro data. The defensive check ensures your application continues to run without crashing.

## Common pitfalls and best practices

| Issue | Why it happens | Recommended fix |
|-------|----------------|-----------------|
| Image path is incorrect | `BarCodeReader` throws a file‑not‑found exception before any decoding occurs | Use `Path.Combine` and validate the file exists with `File.Exists` |
| Low‑resolution image | The decoder cannot locate barcode edges, resulting in zero detections | Provide a minimum resolution of 300 dpi for reliable results |
| Barcode rotated > 45° | Many libraries assume upright orientation | Enable `reader.RecognitionOptions.RotateImage = true` if the


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}