---
category: general
date: 2026-08-09
description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
  PNG files, handle multiple barcodes, and extract extended metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: en
lastmod: 2026-08-09
og_description: How to read PDF417 in C# with Aspose.BarCode. This tutorial shows
  you how to read barcode PNG files, process multiple barcodes in one image, and retrieve
  extended PDF417 metadata.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: How to read PDF417 in C# – barcode reader tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: How to read PDF417 in C# – complete barcode reader guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 in C# – complete barcode reader guide

If you need to **how to read PDF417** in a .NET application, this guide gives you a ready‑to‑run solution. You’ll see how to read a barcode PNG, process several barcodes in the same image, and pull the extended PDF417 fields that many scanners hide.

Reading PDF417 barcodes is common in logistics, ticketing, and document management. By the end of this tutorial you can decode a Macro PDF417 image, display every result, and use the extra information (file ID, segment count, timestamps, etc.) in your own business logic.

## Prerequisites

- .NET 6.0 or later (the code also works with .NET Framework 4.7+)
- Visual Studio 2022 or any C# IDE
- **Aspose.BarCode for .NET** (free trial or licensed NuGet package)
- A PNG image that contains a Macro PDF417 barcode (the sample file is named `ExtPDF417Meta.png`)

> **Pro tip:** Install the library with the NuGet console:  
> `dotnet add package Aspose.BarCode`

## How to read PDF417 with BarCodeReader in C#

The core of the solution is the `BarCodeReader` class. It accepts an image path and a `DecodeType` enum that tells the engine which symbology to look for.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
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
        }
    }
}
```

### Why this works

- **`DecodeType.MacroPdf417`** tells the reader to look for the Macro PDF417 variant, which stores the extra fields you see in step 4.
- The `using` block disposes the reader automatically, releasing file handles.
- `ReadBarCodes()` returns **all** barcodes that match the requested type, which satisfies the *read multiple barcodes* requirement even if the image contains just one.

Running the program prints output similar to:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Using C# barcode reader to read multiple barcodes

If an image contains several Macro PDF417 symbols (for example, a scanned page with a batch of tickets), the same `foreach` loop processes each one. No extra code is required; the reader aggregates results internally.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Common pitfalls

- **Image format:** The reader supports PNG, JPEG, BMP, and TIFF. If you try a format it cannot decode, you’ll get an empty collection. That’s why the tutorial highlights *read barcode PNG*.
- **Resolution:** Low‑resolution images (< 300 dpi) may cause missed segments. Upscale or request a higher‑quality scan when possible.
- **Macro flag:** Forgetting `DecodeType.MacroPdf417` limits the engine to plain PDF417 and discards the extended data. Always specify the macro type when you need *read barcode extended* fields.

## Reading barcode PNG files – best practices

Working with PNG files is straightforward because the format preserves lossless pixel data. Here’s a quick checklist:

1. Verify the file exists before creating the reader.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The `BarCodeReader` can open the file directly, which avoids extra memory allocation.
3. If the PNG contains transparency, the reader still works because the barcode is rendered on opaque pixels.

## Accessing extended PDF417 metadata

The `Extended.Pdf417` object exposes every optional field defined by the PDF417 specification. You can map these fields to a domain model, store them in a database, or use them for validation.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Populate the model:

```csharp
Pdf417Metadata meta = new Pdf417Metadata
{
    FileID = result.Extended.Pdf417.MacroPdf417FileID,
    SegmentID = result.Extended.Pdf417.MacroPdf417SegmentID


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}