---
category: general
date: 2026-10-21
description: How to read PDF417 barcode in C# using a barcode reader from image. Follow
  this step‑by‑step C# barcode reader example for reliable decoding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: en
lastmod: 2026-10-21
og_description: How to read PDF417 barcode in C# with a complete barcode reader example.
  Learn to decode Macro PDF417 images and access all extended fields.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: How to read PDF417 barcode in C# – detailed guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: How to read PDF417 barcode in C# – full barcode reader guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 barcode in C# – full barcode reader guide

If you need to **how to read PDF417 barcode** in a .NET application, this guide shows you a ready‑to‑run solution. You’ll see how to **read barcode from image C#** using a popular barcode library and get every Macro PDF417 attribute without extra tooling.

The tutorial covers everything required for a **C# barcode reader example**: project setup, code walkthrough, and tips for handling edge cases. By the end you can paste the code into a console project and start decoding PDF417 images instantly.

## What you’ll need

Before you begin, confirm the following prerequisites:

| Prerequisite | Reason |
|--------------|--------|
| .NET 6.0 SDK or later | Provides the runtime for the C# console app |
| Visual Studio 2022 (or any C# IDE) | Enables easy project creation and debugging |
| Aspose.BarCode for .NET (NuGet package) | Supplies `BarCodeReader` and `DecodeType` classes |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | Serves as the input for decoding |

You can install the library with the dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## How to read PDF417 barcode from an image in C#

The core of the **read barcode from image C#** workflow consists of three actions:

1. Initialise the `BarCodeReader` for the specific `DecodeType`.
2. Iterate through the returned `BarCodeResult` collection.
3. Access both basic and extended PDF417 fields.

Below is the complete, runnable code. Save it as `Program.cs` inside a console project.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Explanation of each step

* **Step 1 – Initialise the reader**  
  The `BarCodeReader` constructor receives the image file path and a `DecodeType`. `DecodeType.MacroPdf417` tells the library to look for Macro PDF417 symbols, which contain additional metadata beyond ordinary PDF417 barcodes.

* **Step 2 – ReadBarCodes()**  
  This method returns an `IEnumerable<BarCodeResult>` that may contain multiple barcodes if the image holds more than one. The `foreach` loop guarantees that every detected symbol is processed.

* **Step 3 – Basic information**  
  `CodeTypeName` identifies the barcode format (e.g., “MacroPDF417”). `CodeText` holds the raw data string encoded in the symbol.

* **Step 4 – Extended fields**  
  Macro PDF417 adds a set of extended properties under `barcodeResult.Extended.Pdf417`. These fields expose file‑level data such as `FileID`, `SegmentID`, and `FileName`. Accessing them directly lets you rebuild multi‑segment documents or verify integrity.

#### Expected console output

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

The exact values reflect the content encoded in your `MacroPdf417.png`. If the image contains a single segment, `SegmentsCount` will be 1 and `SegmentID` will be 0.

## Set up the C# barcode reader environment

A reliable **C# barcode reader example** depends on a clean project configuration:

1. **Create a new console project**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Add the Aspose.BarCode package** (as shown earlier).  
3. **Copy the image file** into the project folder or reference it with an absolute path.  
4. **Build and run**  
   ```bash
   dotnet run
   ```

If the build fails with a missing reference error, verify that the `using Aspose.BarCode;` statements match the installed package version. The library’s API is stable across .NET 6 and .NET 8, so you can upgrade the runtime without code changes.

## Decode the Macro PDF417 barcode

When you call `ReadBarCodes()`, the library performs the following internally:

* **Image preprocessing** – converts the bitmap to a binary matrix, correcting rotation and noise.  
* **Pattern detection** – scans for PDF417 start/stop patterns and extracts the module width.  
* **Error correction** – applies Reed‑Solomon codes to recover damaged codewords.  
* **Macro extraction** – parses the extended PDF417 segment header and populates the `Extended.Pdf417` object.

Understanding this pipeline helps you decide when to tweak decoder options. For example, if your images are low‑contrast, you can enable the `BarCodeReader` property `ReadQuality` (available in later versions) to improve detection rates.

## Interpret the extended PDF417 fields

The extended fields map directly to the Macro PDF417 specification:

| Field | Meaning |
|-------|---------|
| `MacroPdf417FileID` | Unique identifier for the whole file across all segments |
| `MacroPdf417SegmentID` | Zero‑based index of the current segment |
| `MacroPdf417SegmentsCount` | Total number of segments that comprise the file |
| `MacroPdf417FileName` | Original file name stored during encoding |
| `MacroPdf417Checksum` | 16‑bit checksum for integrity verification |
| `MacroPdf417FileSize` | Size of the original file in bytes |
| `MacroPdf417TimeStamp` | UTC timestamp when the barcode was generated |
| `MacroPdf417Addressee` | Intended recipient of the document |
| `MacroPdf417Sender` | Originator of the document |
| `MacroPdf417Terminator` | Literal string “END” marking the last segment |

You can use these values to reconstruct a multi‑segment PDF, verify that no segment is missing, or log audit information for compliance purposes.

## Common pitfalls and troubleshooting

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| No output appears | Image path incorrect or unsupported format | Use an absolute path and ensure the file is a PNG/JPEG supported by Aspose.BarCode |
| `CodeType` shows “PDF417” instead of “MacroPDF417” | Image contains a regular PDF417 symbol, not a macro variant | Verify the source barcode is encoded with Macro PDF417 extensions |
| Some fields are empty | The barcode was generated without those macro fields | Encode the barcode with a full macro payload, or handle null values in code |
| Decoder throws `ArgumentException` | Wrong `DecodeType` specified | Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417` if you only need standard PDF417 data |

**Pro tip:** Wrap the field access in null‑checks if you anticipate non‑macro barcodes. The `Extended.Pdf417` object returns default values (e.g., `0` for numeric fields) when the data is absent.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Full working example recap

Putting everything together, the final program consists of the using directives, the `Main` method, and the four‑step loop shown earlier. No additional configuration files are required. Compile and run the project to see the console output with all Macro PDF417 properties.

## Conclusion

You now know **how to read PDF417 barcode** in C# using a concise **C# barcode reader example**. The guide walked you through environment setup, code implementation, and interpretation of every extended Macro PDF417 field. With this foundation you can integrate barcode scanning into inventory systems, document management workflows, or mobile back‑ends.

### Next


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to read PDF417 in C# – complete barcode reader guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}