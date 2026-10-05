---
category: general
date: 2026-08-22
description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
  how to read multiple barcodes from an image and extract MacroPdf417 details.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: en
lastmod: 2026-08-22
og_description: How to read PDF417 barcodes in C# quickly. This tutorial shows you
  how to read multiple barcodes from an image and retrieve MacroPdf417 extended information.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: How to read PDF417 barcodes in C# – full programming walkthrough
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to read PDF417 barcodes in C# – complete guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 barcodes in C# – complete guide

If you need to **how to read PDF417** bars in a .NET application, this tutorial gives you a ready‑to‑run solution. You’ll learn how to read multiple barcodes from a single image, extract the full MacroPdf417 data set, and display it in the console. The approach works with the Aspose.BarCode for .NET library and requires only a few lines of code.

Reading barcodes from an image is a common task in inventory systems, ticket validation, and document management. By the end of this guide you will be able to decode any PDF417 or MacroPdf417 barcode, handle several codes in one picture, and understand the extended fields that MacroPdf417 provides.

## Prerequisites

- .NET 6.0 SDK or later (the code also compiles with .NET Framework 4.7+)
- Visual Studio 2022 or any C# editor you prefer
- Aspose.BarCode for .NET NuGet package (`Install-Package Aspose.BarCode`)
- A sample image that contains a MacroPdf417 barcode (e.g., `MacroPdf417.png`)

No additional configuration is required; the library handles image loading and decoding internally.

## How to read PDF417 barcodes from an image in C#

The core of the solution is the `BarCodeReader` class. It opens the image, detects all barcodes of the specified type, and returns a collection of `BarCodeResult` objects. The following code shows a complete console program.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Why each line matters

| Step | Purpose |
|------|---------|
| **1️⃣ Initialize** | Creates a `BarCodeReader` bound to the image file and restricts detection to the MacroPdf417 symbology, which speeds up processing. |
| **2️⃣ Iterate** | `ReadBarCodes()` returns **all** barcodes that match the requested type, enabling you to **read multiple barcodes** without extra loops. |
| **3️⃣ Basic output** | Shows the generic `CodeTypeName` and the human‑readable `CodeText`. This is useful for logging or quick validation. |
| **4️⃣ Extended data** | MacroPdf417 carries additional metadata (file ID, segment count, timestamps, etc.). The `Extended.Pdf417` object exposes each field directly, so you can store or verify the whole data packet. |

Running the program against a valid MacroPdf417 image produces console output similar to the following:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

The output confirms that the library successfully read the barcode, extracted the text, and provided every MacroPdf417 field.

## Reading multiple barcodes from a single image

Many real‑world scenarios place several PDF417 symbols on one label—think of a shipping manifest that contains a carrier code, a tracking number, and a customs declaration. The same code block above already **read multiple barcodes** because `ReadBarCodes()` returns an enumerable of all matches. No additional configuration is needed; you only have to loop through the results, as demonstrated.

If you want to limit the reader to standard PDF417 (non‑macro) while still handling several codes, replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the logic stays unchanged.

## Understanding MacroPdf417 extended data

MacroPdf417 is an extension of the regular PDF417 specification. It splits large payloads into multiple segments and adds a small header that describes the whole file. The most relevant fields are:

- **MacroPdf417FileID** – a unique identifier shared by all segments of the same file.
- **MacroPdf417SegmentID** – the sequence number of the current segment.
- **MacroPdf417SegmentsCount** – total number of segments expected.
- **MacroPdf417FileName** – optional file name transmitted with the barcode.
- **MacroPdf417Checksum** – error‑checking value for the complete file.
- **MacroPdf417FileSize** – size of the original binary payload.
- **MacroPdf417TimeStamp** – ISO‑8601 timestamp when the barcode was generated.
- **MacroPdf417Addressee / Sender** – optional textual fields for routing.
- **MacroPdf417Terminator** – indicates whether this segment is the final one.

When you receive all segments, you can reconstruct the original file by ordering them by `MacroPdf417SegmentID` and concatenating the `CodeText` values. This logic is straightforward to implement once you have the fields available.

## Common pitfalls and pro tips

- **Image quality matters** – low‑resolution or heavily compressed PNG/JPEG files can cause missed detections. Use a DPI of at least 300 dpi for printed barcodes.
- **Mixed symbologies** – if the image contains both MacroPdf417 and regular PDF417, instantiate two readers (one for each `DecodeType`) or use `DecodeType.AllSupported` and filter results by `result.CodeTypeName`.
- **Memory usage** – the `using` statement disposes the `BarCodeReader` promptly, preventing large image buffers from staying in memory.
- **Thread safety** – `BarCodeReader` is not thread‑safe. Create a separate instance per thread if you decode images in parallel.
- **Error handling** – wrap the `ReadBarCodes()` call in a try/catch block to capture `BarCodeException` for corrupted images.

## Full working example recap

Below is the complete program you can copy into a new console project. It includes all `using` directives, a constant for the image path, and the disposal pattern.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compile with `dotnet build` and run with `dotnet run`. The console prints every barcode’s basic data and the full MacroPdf417 payload.

## Next steps

- **Reconstruct multipart files** – collect all segments, sort by `MacroPdf417SegmentID`, and concatenate `CodeText` to


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Read PDF417 Barcodes with Turkish Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [How to Use Aspose for PDF417 Barcode (Chinese) in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}