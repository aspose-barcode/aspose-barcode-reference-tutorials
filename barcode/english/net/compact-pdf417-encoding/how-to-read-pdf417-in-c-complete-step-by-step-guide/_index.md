---
category: general
date: 2026-09-28
description: Read PDF417 barcode c# quickly with Aspose.BarCode. Decode multiple barcodes
  from one image, extract Macro‑PDF417 fields, and handle rotation or batch processing.
draft: false
images:
- /net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
language: en
lastmod: 2026-09-28
og_description: Read PDF417 barcode c# quickly with Aspose.BarCode. This guide shows
  how to decode multiple barcodes from a single image, extract all Macro‑PDF417 properties,
  and handle rotated or batch images.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Read PDF417 barcode c# – full code sample & guide
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: How to read PDF417 barcode c# – complete step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read PDF417 barcode c# – complete step‑by‑step guide

Ever wondered **how to read PDF417** from an image using C#? You’re not the only one. Most developers hit a wall when they need to pull out the extended Macro‑PDF417 fields from a scanned document. The good news? With just a few lines of code you can **read PDF417 barcode c#**, decode multiple barcodes in the same picture, and grab every hidden property the spec offers.

## Quick answers
- **Can Aspose.BarCode decode Macro‑PDF417?** Yes – just enable `DecodeType.MacroPdf417` and the library returns all extended fields.  
- **How many barcodes can be read from one image?** Unlimited; the API returns a collection of `BarCodeResult` objects.  
- **Do I need a license for production?** A commercial license is required for production use; a free trial works for evaluation.  
- **Will rotated barcodes be detected?** Built‑in rotation compensation works for barcodes covering at least 30 % of the image width.  
- **Is batch processing supported?** Absolutely – wrap the reader in a `foreach` loop and dispose each instance with `using`.

## What is read PDF417 barcode c#?
`read pdf417 barcode c#` refers to the process of using a .NET library to decode PDF417 (including Macro‑PDF417) symbols from image files directly in C# code. The Aspose.BarCode SDK provides a single‑call API that handles image loading, barcode detection, and extraction of all ISO‑defined fields.

## Why use Aspose.BarCode for PDF417 decoding?
Aspose.BarCode supports **30+ barcode symbologies** and can process images up to **5000 × 5000 px** in under **0.1 s** on typical server hardware. It also offers out‑of‑the‑box rotation, distortion, and inverted‑barcode handling, eliminating the need for custom image‑preprocessing. Additionally, the library includes built‑in support for reading Macro‑PDF417 extended fields, making it a one‑stop solution for complex scanning scenarios.

## Prerequisites

Before we dive in, make sure you have:

* .NET 6.0 SDK or later (the code works with .NET Core and .NET Framework as well).  
* Visual Studio 2022 (or any editor you prefer).  
* The **Aspose.BarCode for .NET** NuGet package – this is the library that actually parses PDF417.  
* A sample image that contains a Macro‑PDF417 barcode (for example `ExtPDF417Meta.png`).  

No extra configuration is required; the library ships with all the decoders you need.

## How to read PDF417 barcode c#?

Load the image with `BarCodeReader`, specify `DecodeType.MacroPdf417`, and iterate the returned `BarCodeResult` collection – that’s the complete solution in under ten lines of code. The reader automatically extracts both plain PDF417 symbols and Macro‑PDF417 extended data, so you get file identifiers, segment numbers, timestamps, and checksums without extra parsing.

### Step 1: install Aspose.BarCode

Open your project folder in a terminal and run:

```bash
dotnet add package Aspose.BarCode
```

That command pulls the latest stable version (as of July 2026 it’s 23.12). If you prefer the Package Manager Console inside Visual Studio, use:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** lock the version (`23.12.0`) in your `.csproj` to avoid accidental breaking changes later.

### Step 2: create a console app skeleton

Create a new console project if you don’t already have one:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Replace the autogenerated `Program.cs` with the code below. We’ll explain each block in the next sections.

### Step 3: write the full “how to read PDF417” code

`BarCodeReader` is the core class that streams the image, detects barcodes, and returns a collection of `BarCodeResult` objects.

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
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — the primary class responsible for reading and decoding barcodes from images.  
* `DecodeType.MacroPdf417` — a flag that tells the SDK to treat Macro‑PDF417 specially while still returning plain PDF417 symbols.  
* `Extended.Pdf417.MacroPdf417` — the object that holds every optional field defined by ISO/IEC 15438, such as `FileID`, `SegmentID`, and `Checksum`.

The `using` block guarantees the native resources are released, preventing memory leaks in long‑running services.

### Step 4: run the application and verify output

From the terminal:

```bash
dotnet run
```

You should see something like:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

If the image contains more than one barcode, the loop prints a separator line (`----------------------------------------`) and continues with the next result—exactly what **read multiple barcodes** looks like in practice.

## Common questions & edge cases

### What if the image has both Macro‑PDF417 and regular PDF417 symbols?

The same `BarCodeReader` call will return both. You can differentiate them by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents a `NullReferenceException`.

### My barcode is rotated or skewed—will the reader still work?

Aspose.BarCode includes built‑in rotation and distortion compensation. As long as the barcode is at least 30 % of the image width, the decoder will usually succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes = true;` before calling `ReadBarCodes()`.

### How do I handle large batches of images?

Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder, "*.png"))` loop. The `using` pattern ensures each image’s native resources are freed before the next iteration, keeping memory usage low.

## Full source listing (copy‑paste ready)

Below is the entire program in one block for quick copy‑paste. No hidden dependencies—just the Aspose.BarCode NuGet package.

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
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Recap – what we covered

* **How to read PDF417 barcode c#** using Aspose.BarCode.  
* The exact steps to **read multiple barcodes** from a single image.  
* How to **read barcode image c#** and extract every Macro‑PDF417 field.  
* Tips for rotation, batch processing, and handling missing extended data.

## Next steps & related topics

* **Encode PDF417** – generate your own Macro‑PDF417 barcodes with `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – using the same `BarCodeReader` class.  
* **Integrate with ASP.NET Core** – expose a web endpoint that accepts an uploaded image and returns JSON with the decoded fields.  

### Additional useful links
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Feel free to experiment: change the image path, drop a plain PDF417 into the same folder, or tweak the `DecodeType` flags to see how the library behaves. The more you play, the more comfortable you’ll become with **read barcode image c#** scenarios.

Got a tricky image that refuses to decode? Drop a comment below or open an issue on the GitHub repo of the sample project. Happy coding!

## Frequently asked questions

**Q: Can I use this in a commercial application?**  
A: Yes, you can use Aspose.BarCode in commercial projects as long as you have a valid license; a free trial is available for evaluation.

**Q: Does the reader support password‑protected images?**  
A: The SDK works with any standard image format; password protection is not applicable to raster images, only to PDFs, which are handled by a separate Aspose.PDF component.

**Q: What .NET versions are supported?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, and .NET 6+ are all fully supported by the current Aspose.BarCode release.

**Q: How can I improve performance for very large image batches?**  
A: Enable `reader.Options.Quality = QualityMode.HighPerformance` and process images in parallel using `Parallel.ForEach` while still wrapping each `BarCodeReader` in a `using` block.

**Q: Is there a way to get only the Macro‑PDF417 fields without iterating all results?**  
A: Yes – after calling `ReadBarCodes()`, filter the collection with `result => result.CodeType == DecodeType.MacroPdf417` and then access the `Extended.Pdf417.MacroPdf417` property.

---

**Last updated:** 2026-09-28  
**Tested with:** Aspose.BarCode 23.12 for .NET  
**Author:** Aspose

## Related Tutorials

- [How To Generate Pdf417 Barcode Image In C With Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Create Pdf417 Barcode With Aspose Barcode Step By Step Guide](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Read Multiple Barcodes C Complete Guide With Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}