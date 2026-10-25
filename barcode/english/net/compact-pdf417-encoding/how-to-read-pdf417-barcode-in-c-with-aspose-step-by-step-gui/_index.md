---
category: general
date: 2026-10-24
description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
  covers reading a barcode image, extracting Macro PDF417 fields, and handling common
  scenarios.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: en
lastmod: 2026-10-24
og_description: How to read PDF417 barcode in C# using Aspose.BarCode. Follow this
  complete tutorial to decode images, retrieve Macro PDF417 metadata, and avoid common
  pitfalls.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: How to read PDF417 barcode in C# with Aspose – complete guide
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 barcode in C# with Aspose – step‑by‑step guide

If you need to **how to read PDF417 barcode** in a .NET application, this guide shows you exactly how to read PDF417 barcode in C# using the Aspose.BarCode library. Whether you are processing scanned documents, mobile captures, or batch‑imported images, the code below decodes the barcode and extracts every Macro PDF417 property you might need.

Reading a barcode image in C# can feel daunting, especially when the barcode contains extended metadata. This tutorial eliminates the guesswork by providing a complete, runnable example, explaining each line, and covering edge cases such as missing macro segments or corrupted images. By the end, you’ll be able to integrate PDF417 decoding into any C# project with confidence.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports .NET)  
* A license or free evaluation of **Aspose.BarCode for .NET** – you can obtain a temporary key from the Aspose website  
* An image file that contains a Macro PDF417 barcode (e.g., `ExtPDF417Meta.png`)

> **Pro tip:** If you only need to experiment, Aspose offers a 30‑day trial that includes full functionality for barcode reading.

## Step 1: Install the Aspose.BarCode NuGet package

Open your project folder in a terminal and run:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `Aspose.BarCode.ReadRecognition` namespace, which contains the `BarCodeReader` class used to decode images.

## Step 2: Create a BarCodeReader for a PDF417 image

The `BarCodeReader` constructor takes two arguments: the path to the image file and the `DecodeType` you want to target. Specifying `DecodeType.MacroPdf417` tells Aspose to look for Macro PDF417 symbols and to populate the extended properties automatically.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Why use `DecodeType.MacroPdf417`?

* **Macro PDF417** stores additional fields (file ID, segment count, timestamps, etc.) that are not present in standard PDF417.  
* The `Extended` property of `BarCodeResult` is populated only when you request the macro type, saving you a separate parsing step.

## Step 3: Iterate through all detected barcodes

A single image can contain multiple PDF417 symbols (for example, when a document is split across several pages). The `ReadBarCodes()` method returns an `IEnumerable<BarCodeResult>` that you can loop over.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

If the image does not contain any barcode, the loop simply never executes, and the program exits gracefully. This behavior makes the code safe for batch processing where some files might be barcode‑free.

## Step 4: Output Macro PDF417 extended properties

The `Extended.Pdf417` property groups all macro‑specific fields. Each field maps directly to the PDF417 specification, so you can store them in a database, log them, or use them for further validation.

```csharp
        // Macro PDF417 extended properties
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
    }
}
```

### What each property means

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | Unique identifier for the whole multi‑segment document. |
| **MacroPdf417SegmentID** | Index of the current segment (starting at 0). |
| **MacroPdf417SegmentsCount** | Total number of segments that belong to the file. |
| **MacroPdf417FileName** | Optional file name embedded in the barcode. |
| **MacroPdf417Checksum** | CRC‑16 checksum for the macro data block. |
| **MacroPdf417FileSize** | Original file size in bytes. |
| **MacroPdf417TimeStamp** | Timestamp when the macro barcode was generated. |
| **MacroPdf417Addressee** | Intended recipient of the document. |
| **MacroPdf417Sender** | Originator of the document. |
| **MacroPdf417Terminator** | Terminator flag indicating the end of the macro sequence. |

These fields are especially useful when you are reconstructing a large PDF or image that was split into several PDF417 symbols for printing on low‑resolution media.

## Step 5: Handle common edge cases

### Missing macro fields

Sometimes a PDF417 barcode is generated without the optional macro fields. Accessing a missing property returns `null` or `0`. Guard against this if you plan to store the values:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Corrupted or low‑quality images

If the image is blurry, you can improve detection by enabling the `BarCodeReader` quality options:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

These settings are optional but can dramatically increase the success rate for scanned documents.

### Multiple barcode formats in one image

If you suspect other barcode types might be present, use `DecodeType.AllSupported` and filter results:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Complete runnable example

Copy the following program into a new console project (`dotnet new console`) and run it. Replace the `imagePath` variable with the location of your own Macro PDF417 image.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Expected output** (values will differ based on your image):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

If the image contains no Macro PDF417 symbols, the program writes nothing and exits silently—perfect for batch jobs that process many files.

## Frequently asked questions

**Q: Can I read a standard PDF417 (non‑macro) with the same code?**  
A: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended` property will be empty, but `CodeText` and `CodeTypeName` remain available.

**Q: Does Aspose.BarCode support reading from a stream instead of a file path?**  
A: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and pass a `FileStream` or `MemoryStream`. This is useful when the image comes from a web API.

**Q: How do I validate the checksum?**  
A: The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can recompute the checksum on the reconstructed file and compare it to ensure data integrity.

## Next steps and related topics

* **Write PDF417 barcodes** – explore `BarCodeGenerator` to create macro barcodes for testing.  
* **Combine multiple segments** – after reading all segments, order them by `MacroPdf417SegmentID` and concatenate `CodeText` to reconstruct the original payload.  
* **Performance tuning** – for high‑throughput scenarios, reuse a single `BarCodeReader` instance across many images and


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}