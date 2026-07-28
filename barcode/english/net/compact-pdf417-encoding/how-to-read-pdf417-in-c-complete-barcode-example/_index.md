---
category: general
date: 2026-07-27
description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
  decode images, and get Macro PDF417 metadata in a full C# barcode example.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: en
lastmod: 2026-07-27
og_description: How to read PDF417 barcode in C# with this step‑by‑step guide. Decode
  images, handle multiple barcodes, and extract Macro PDF417 metadata in a ready‑to‑run
  example.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: How to Read PDF417 in C# – Full Barcode Example
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: How to Read PDF417 in C# – Complete Barcode Example
url: /net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Read PDF417 in C# – Complete Barcode Example

Ever wondered **how to read PDF417** barcode in a C# application without pulling your hair out? You're not the only one. Whether you're building a logistics scanner, a ticket validator, or just need to pull data from a PDF417‑encoded ID, the process can feel a bit mysterious at first.  

In this tutorial we’ll walk through a **c# barcode example** that reads a PDF417 image, handles **read multiple barcodes** if they’re present, and extracts all the handy Macro PDF417 metadata you might need.

## What You’ll Build

By the end of this guide you’ll have a small console program that:

1. Loads a barcode image from disk.  
2. Decodes **PDF417** (including Macro PDF417) barcodes.  
3. Prints basic information such as code type and text.  
4. Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum, etc.).  

No external services, just a single NuGet package and a few lines of C#.

## Prerequisites – What You Need Before Starting

- **.NET 6.0** or later (the code works on .NET Framework 4.6+ as well).  
- A recent version of the **Aspose.BarCode for .NET** library – install it via NuGet (`Install-Package Aspose.BarCode`).  
- An image file that contains a PDF417 barcode (the demo uses `ExtPDF417Meta.png`).  
- A basic understanding of C# console apps (if you’ve written “Hello World”, you’re good).

> **Pro tip:** If you don’t have a PDF417 sample handy, generate one on the Aspose demo site or use a smartphone app that can create PDF417 tags.

## Step 1: Set Up the Project and Install the Library

First, create a new console project:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

This pulls in the **c# barcode example** dependencies we need. Open `Program.cs` and replace the default code with the skeleton below:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Step 2: Initialize the Barcode Reader for PDF417

The heart of the solution is the `BarCodeReader` class. We tell it which file to scan and which barcode type we care about—in this case `DecodeType.Pdf417` or the macro variant `DecodeType.MacroPdf417`. Using the macro type ensures we capture the extended fields.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Why use `MacroPdf417` instead of plain `Pdf417`? Macro PDF417 carries extra metadata (file ID, segment count, timestamps, etc.) that many real‑world applications rely on—think of shipping manifests split across several pages.

## Step 3: Read All Barcodes Found in the Image

A single image can contain **read multiple barcodes**—perhaps a QR code next to a PDF417. The `ReadBarCodes()` method returns an `IEnumerable<BarCodeResult>` that we can iterate over.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

If the image only holds one PDF417, the loop still runs once, keeping the code flexible for future scenarios where you might need to **read multiple barcodes** from the same scan.

## Step 4: Display Basic Barcode Information

Before diving into the macro fields, it’s useful to show the barcode type and the decoded text. This helps you verify that the reader actually recognized a PDF417 and not some other symbology.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

The `CodeTypeName` will read *MacroPdf417* (or *Pdf417* if the macro flag isn’t set), while `CodeText` contains the raw data encoded in the barcode.

## Step 5: Extract Macro PDF417 Metadata

The `Extended` property gives you a deep dive into the PDF417-specific structure. Every field we print below maps directly to the PDF417 macro specification.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Each line pulls a different piece of the macro payload:

- **FileID** – a unique identifier for the whole document set.  
- **SegmentID** – which part of the multi‑segment file you’re looking at.  
- **SegmentsCount** – total number of segments expected.  
- **FileName, Checksum, FileSize** – useful for validating the integrity of the transferred file.  
- **TimeStamp, Addressee, Sender** – optional fields that many logistics systems embed.  

If any of these fields are missing in the source barcode, the library returns `null` or `0`, which you can handle as needed.

## Step 6: Run the Complete Example

Putting it all together, here’s the full, ready‑to‑run program:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Expected Output

When you run the program against a valid `ExtPDF417Meta.png`, you should see something akin to:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

If the image contains more than one barcode,


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}