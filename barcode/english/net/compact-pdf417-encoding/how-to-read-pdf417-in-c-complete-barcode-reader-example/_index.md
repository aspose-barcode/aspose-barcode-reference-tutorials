---
category: general
date: 2026-07-21
description: How to read PDF417 barcode in C# using a concise barcode reader example.
  Quickly learn how to read barcode from image with step‑by‑step code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: en
lastmod: 2026-07-21
og_description: How to read PDF417 barcode in C# with a practical example. Discover
  how to read barcode from image and integrate the c# barcode reader example instantly.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: How to Read PDF417 in C# – Full Barcode Reader Walkthrough
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: How to Read PDF417 in C# – Complete Barcode Reader Example
url: /net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read PDF417 in C# – Complete Barcode Reader Example

Ever wondered **how to read PDF417** in a .NET project without hunting through endless docs? You're not the only one. Whether you're scanning driver licenses, boarding passes, or custom inventory tags, extracting that data reliably is a real‑world need.  

In this guide we'll walk through a **c# barcode reader example** that pulls every piece of Macro PDF417 metadata from a single image file. By the end you’ll have a ready‑to‑run console app that **reads barcode from image** and prints out all the extended fields you might need.

## What You’ll Need

- .NET 6.0 SDK or later (you can also target .NET Framework 4.7+ – the code works the same)
- Visual Studio 2022, VS Code, or any C# editor you like
- The **Aspose.BarCode for .NET** NuGet package (the `BarCodeReader` class comes from this library)
- An image file that contains a Macro PDF417 barcode (for demo we’ll use `ExtPDF417Meta.png`)

> **Pro tip:** If you don’t have a PDF417 sample handy, Aspose ships a few test images in their GitHub repo – just download one and drop it into your project folder.

## Step 1: Install the Barcode Library

Open a terminal at your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `BarCodeReader`, `DecodeType`, and the `Extended` property we’ll need later. No extra configuration is required; the library works out‑of‑the‑box for most image formats (PNG, JPEG, BMP, etc.).

## Step 2: Create a Minimal Console App

Create a new console project if you haven’t already:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Replace the generated `Program.cs` with the code below. Notice how each section is commented so you can follow the logic even if you’re new to barcode processing.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Why This Works

- **`DecodeType.MacroPdf417`** tells the reader to expect the extended Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps, etc.).
- The **`Extended.Pdf417`** object is only populated for Macro PDF417 barcodes, so accessing those properties is safe after the `ReadBarCodes()` call.
- Using a **`using`** block guarantees that file handles are released, preventing file‑lock issues on Windows.

## Step 3: Run the Application

Compile and execute:

```bash
dotnet run
```

If the image contains a valid Macro PDF417 barcode, you should see output similar to:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

If nothing prints, double‑check that the image path is correct and that the barcode is indeed a Macro PDF417 variant. Regular PDF417 (without the macro extension) will still decode, but the `Extended` properties will be empty.

## Handling Edge Cases

### Multiple Barcodes in One Image

Sometimes a single scan contains more than one PDF417 segment (think of a multi‑page document encoded across several symbols). The `foreach` loop already enumerates *all* detected barcodes, so you don’t need extra logic—just collect the segments and reassemble them later if required.

### Missing Extended Data

Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417` will be instantiated but its fields will be default values (zero, empty string, or `false`). You can guard against it like this:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Performance Tips

- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader` creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`. This reduces allocation overhead.
- **Parallelism:** For large workloads, consider `Parallel.ForEach` on the file list, but remember that the Aspose reader is thread‑safe only when each thread uses its own `BarCodeReader` instance.

## Full Source Listing (Copy‑Paste Ready)

Below is the entire program again, ready to drop into `Program.cs`. No extra files needed besides the image.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Recap: How to Read PDF417 in C# Quickly

- Install **Aspose.BarCode** via NuGet.
- Point a `BarCodeReader` at your image with `DecodeType.MacroPdf417`.
- Loop through `ReadBarCodes()` and pull both basic and extended fields.
- Handle missing macro data gracefully and consider performance tweaks for bulk scans.

## Next Steps & Related Topics

- **Read barcode from image** using other formats (QR, DataMatrix) – just swap `DecodeType` enum.
- **Encode PDF417** with `BarCodeGenerator` if you need to create barcodes programmatically.
- Explore **error correction levels** and how they affect scan reliability.
- Integrate this logic into an ASP.NET Core API to expose barcode reading as a web service.

Feel free to experiment: change the image, play with the `DecodeType` flag, or feed the macro data into a database. The core pattern stays the same, and now you have a solid **c# barcode reader example** in your toolbox.

Happy coding, and may your scans always be clean!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}