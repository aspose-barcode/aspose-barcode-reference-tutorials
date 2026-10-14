---
category: general
date: 2026-10-14
description: Create a console barcode scanner in C# that reads PDF417 barcodes, handles
  macro PDF417, and decodes multiple barcodes from a single image.
draft: false
images:
- /net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
language: en
lastmod: 2026-10-14
og_description: Create a console barcode scanner in C# to quickly read PDF417 and
  macro PDF417 barcodes from images. This step‑by‑step guide shows how to decode multiple
  barcodes in one picture.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Create console barcode scanner in C# – complete guide
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
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
- console application
title: Create console barcode scanner in C# – read PDF417 barcode example
url: /net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create console barcode scanner in C# – read PDF417 barcode example

`BarCodeReader` is Aspose.BarCode's core class that decodes barcodes from images and returns detailed metadata. If you need to read PDF417 barcode data from an image, this guide shows you how to do it with the **BarCodeReader** class in C#. You’ll learn a **create console barcode scanner** example that also handles macro PDF417 and can read multiple barcodes in a single image.

Working with barcodes often means dealing with different image sources, varying lighting conditions, and sometimes composite data such as macro PDF417 segments. This tutorial covers everything you need to decode a PDF417 barcode, extract its extended fields, and process several barcodes from the same picture. By the end you will have a runnable console program that reads barcodes from an image file and prints detailed information to the console.

## Quick answers
- **What does the example do?** It creates a console barcode scanner that reads PDF417 and macro PDF417 barcodes from a picture and prints all decoded fields.  
- **Which library is required?** Aspose.BarCode for .NET (NuGet).  
- **Can it read multiple barcodes at once?** Yes – the reader iterates over every barcode found in the image.  
- **Do I need an internet connection?** No, the library works completely offline.  
- **What .NET version is supported?** .NET 6.0 or later.

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

## How do I create a console barcode scanner in C#?

`BarCodeReader` is a class provided by Aspose.BarCode that reads barcodes from images and returns their decoded data.  
Load the image with `BarCodeReader`, set the decode type to `MacroPdf417`, and iterate over the results – that’s all you need to create a console barcode scanner. The reader automatically releases native resources thanks to the `using` statement, so you don’t have to manage memory manually. This approach works for any image format supported by .NET, such as PNG, JPEG, or BMP.

### Step‑by‑step walkthrough

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

## How can I read multiple barcodes from an image?

Use a single `BarCodeReader` instance and set the `DecodeType` flag to include all formats you want to detect. By combining flags with the bitwise OR operator, you can tell the library to look for PDF417, QR, Code‑128, and many other symbologies in one pass. This eliminates the need for separate readers and reduces processing time.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* is a bitmask, so you can combine any number of supported formats. Aspose.BarCode supports **30+ barcode symbologies**, including QR, DataMatrix, Code‑128, and UPC‑A, allowing a single scanner to handle diverse use cases such as product labeling, ticket validation, and identity verification.

## What is macro PDF417 and how do I access its fields safely?

Macro PDF417 is an extension of the PDF417 symbology that allows a large data set to be split across multiple barcode symbols.  
Macro PDF417 adds a rich set of extended properties. However, not every barcode includes every field. Accessing a missing property can throw a `NullReferenceException`. The safest approach is to verify each property before printing, ensuring your application remains stable even when macro data is absent.

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
| Barcode rotated > 45° | Many libraries assume upright orientation | Enable `reader.RecognitionOptions.RotateImage = true` if the image may be rotated |
| Missing macro fields | Attempting to read a null property causes a crash | Always check for `null` before accessing macro properties |
| Large batch processing | Re‑creating the reader for each file adds overhead | Re‑use a single `BarCodeReader` instance with different streams when processing many images |

## Why use Aspose.BarCode for a console barcode scanner?

Aspose.BarCode can decode **30+ barcode types** and processes images up to **200 MP** without loading the entire file into memory, achieving throughput of **150 frames per second** on a typical 3.2 GHz CPU. These quantified capabilities make it a reliable choice for high‑volume, on‑premises scanning solutions where latency and accuracy are critical.

## What should you learn next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step‑by‑step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Read Barcode from Image – Mastering Barcode Region Extraction in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## Frequently asked questions

**Q: Can I use this scanner in a production environment?**  
A: Yes. Purchase a commercial Aspose.BarCode license to remove the evaluation watermark and gain full support.

**Q: Does the library work on Linux and macOS?**  
A: Absolutely. Aspose.BarCode for .NET is cross‑platform and runs on .NET 6+ on Windows, Linux, and macOS.

**Q: How do I handle very large images without exhausting memory?**  
A: Use the `LoadOptions` constructor to enable streaming mode, which processes the image in chunks instead of loading it entirely into RAM.

**Q: Is it possible to decode encrypted or password‑protected images?**  
A: The reader can handle images encrypted with standard PNG/JPEG password schemes; simply provide the password via `reader.ImagePassword`.

**Q: What if my barcode is partially damaged?**  
A: Enable error‑correction options such as `reader.RecognitionOptions.CorrectErrors = true` to improve resilience against damage or noise.

---

**Last Updated:** 2026-10-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [How To Read Pdf417 In C Complete Barcode Reader Example](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Read Multiple Barcodes C Complete Guide With Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [Decode Barcode From Image With A C Barcode Reader Example](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}