---
category: general
date: 2026-09-22
description: Learn how to read PDF417 barcodes in C# with a full barcode reader example.
  This tutorial shows you how to read barcode image C# quickly and reliably.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: en
lastmod: 2026-09-22
og_description: How to read PDF417 barcodes in C# using a concise barcode reader example.
  Follow the guide to decode Macro PDF417 images and extract metadata.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: How to read PDF417 barcodes in C# – full barcode reader example
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: How to read PDF417 barcodes in C# – complete step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 barcodes in C# – complete step‑by‑step guide

If you need to **how to read pdf417** in a .NET application, this guide shows you the exact code and reasoning you need. By the end of the first two sentences you’ll know how to read barcode image C# using the popular `BarCodeReader` class, and you’ll have a ready‑to‑run example that extracts every piece of Macro PDF417 metadata.

Reading PDF417 barcodes is a common requirement when processing shipping labels, boarding passes, or secure documents. This tutorial covers everything from setting up the reader to handling edge cases, so you can integrate barcode scanning with confidence.

## What you’ll achieve

- Decode a Macro PDF417 image file.
- Print basic barcode information (type and text).
- Access all Macro PDF417 extended fields such as file ID, segment count, and timestamp.
- Understand common pitfalls when working with multi‑segment PDF417 codes.

**Prerequisites**

- .NET 6.0 or later (the code also works with .NET Framework 4.7+).
- A reference to the barcode SDK that provides `BarCodeReader`, `DecodeType`, and `BarCodeResult` (e.g., Aspose.BarCode, Dynamsoft, or any library exposing the same API).
- An image file (`ExtPDF417Meta.png`) that contains a Macro PDF417 barcode.

> **Pro tip:** Place the image in a folder relative to your project root and set its **Copy to Output Directory** property to *Copy if newer* so the path works during debugging.

![How to read PDF417 barcode using C#](https://example.com/placeholder-image.png)

## How to read PDF417 barcode in C# – the complete code

Below is a self‑contained program you can paste into a console application. It creates a barcode reader, iterates over every decoded result, and prints both standard and extended Macro PDF417 fields.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
```

### Why each step matters

1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417 is a special variant that can carry file‑level metadata. Specifying the decode type ensures the SDK parses those extra fields instead of treating the code as a plain PDF417.
2. **Iterating over `ReadBarCodes()`** – An image can contain more than one barcode (e.g., a QR code next to a PDF417). The loop guarantees you capture every result.
3. **Printing `CodeTypeName` and `CodeText`** – These are the most frequently used properties; they give you the symbology name and the human‑readable payload.
4. **Accessing `Extended.Pdf417`** – The `Extended` object only appears for PDF417‑related decode types. Each property maps directly to the Macro PDF417 specification, allowing you to rebuild the original file or validate segment order.

## Common variations and edge cases

### Reading a non‑macro PDF417 barcode

If your source images contain regular PDF417 codes (no macro metadata), replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code stays identical, but the `Extended.Pdf417` block will be empty because those fields simply don’t exist.

### Handling multi‑segment PDFs

Macro PDF417 can split a large document across several barcode segments. To reassemble the original file you must:

1. Collect each segment’s `Pdf417MacroSegmentID`.
2. Sort segments by their ID.
3. Verify `Pdf417MacroSegmentsCount` matches the number of received segments.
4. Concatenate the `CodeText` of each segment in order.
5. Optionally validate `Pdf417MacroChecksum`.

Below is a concise snippet that demonstrates the reassembly logic:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Dealing with corrupted images

- **Low contrast** – Increase image preprocessing (e.g., histogram equalization) before passing it to `BarCodeReader`.
- **Rotation** – Use `barcodeReader.SetRotateAngle(90)` or enable auto‑rotate if the SDK supports it.
- **Partial scans** – Ensure the image resolution is at least 300 dpi; otherwise the SDK may miss small segments.

## c# barcode reader example – best practices

| Practice | Reason |
|----------|--------|
| **Dispose the reader with `using`** | Guarantees native resources are released promptly, preventing memory leaks. |
| **Validate `result.Extended` is not null** | Some SDKs return `null` for non‑macro codes; checking avoids a `NullReferenceException`. |
| **Log the `Pdf417MacroFileID`** | This identifier is unique per file and useful for audit trails. |
| **Wrap decoding in a try/catch** | I/O errors (missing file) or unsupported formats raise exceptions that should be handled gracefully. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Expected output

Running the full program against a correctly formatted `ExtPDF417Meta.png` yields output similar to:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

If the image contains multiple segments, the loop will print each segment’s metadata sequentially.

## Conclusion

You now know **how to read pdf417** barcodes in C# and have a **c# barcode reader example** that extracts every Macro PDF417 field. The solution covers basic decoding, metadata extraction, multi‑segment reassembly, and error handling, giving you a production‑ready foundation for any document‑processing workflow.

### Next steps

- Explore **read barcode image C#** techniques for other symbologies (QR, DataMatrix) using the same `BarCodeReader` API.
- Integrate the barcode decoder into an ASP.NET Core service to process uploads on the fly.
- Experiment with image preprocessing libraries (e.g., `OpenCvSharp`) to boost success rates on low‑quality scans.

Happy coding, and feel free to adapt the example to fit your specific use case!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}