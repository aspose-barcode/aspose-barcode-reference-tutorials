---
category: general
date: 2026-11-23
description: Learn how to use BarCodeReader in C# to read barcodes from an image,
  including Macro PDF417 decoding, with a complete code example and clear explanations.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: en
lastmod: 2026-11-23
og_description: How to use BarCodeReader in C# to read barcodes from an image. Follow
  this step‑by‑step guide to decode Macro PDF417 and other formats with ready‑to‑run
  code.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: How to use BarCodeReader in C# – read barcodes from images quickly
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: How to use BarCodeReader in C# to read barcodes from images
url: /net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use BarCodeReader in C# to read barcodes from images

If you need to **how to use BarCodeReader** for a quick barcode scan, this guide shows you exactly that. Whether you are building a point‑of‑sale system or automating document intake, you’ll learn how to read barcodes from image C# projects with just a few lines of code.

In this tutorial you’ll see a complete, runnable example that decodes a Macro PDF417 barcode, extracts its extended properties, and prints useful information to the console. No external documentation is required – everything you need is right here.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 (or later) installed – the code targets the latest LTS version.
* A reference to the **Aspose.BarCode** (or any compatible) NuGet package that provides `BarCodeReader`.
* An image file containing a Macro PDF417 barcode (the example uses `ExtPDF417Meta.png`).

> **Pro tip:** If you’re using Visual Studio, add the package via `dotnet add package Aspose.BarCode` or the NuGet Package Manager UI.

## Step 1: Create a BarCodeReader instance

The first thing you do when working with a barcode library is instantiate a reader that points to the source image and tells the API which barcode type(s) to look for.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Why this step matters:*  
`BarCodeReader` opens the image, allocates native memory, and prepares decoding algorithms for the specified `DecodeType`. By limiting the type to `MacroPdf417`, you reduce CPU overhead and improve detection accuracy.

## Step 2: Read all barcodes found in the image

A single image can contain multiple barcodes, especially when dealing with macro‑encoded data. The `ReadBarCodes` method returns an enumerable of `BarCodeResult` objects, each representing one detected code.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Why this step matters:*  
Iterating over the collection ensures you capture every instance, which is essential for batch processing scenarios or when a document embeds several codes.

## Step 3: Access the extended Macro PDF417 properties

Macro PDF417 stores extra metadata such as file identifiers, segment numbers, and total segment count. These values are exposed through the `Extended.Pdf417` property of `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Why this step matters:*  
The extended fields let you reconstruct multi‑segment documents or validate that all parts belong to the same source. Skipping this step would give you only the raw text, losing valuable context.

## Step 4: Output the most useful information

Finally, write the data to the console (or any logger) so you can verify the read operation. The example prints the code type, decoded text, and several macro fields.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Expected console output**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Note:** If the image does not contain a Macro PDF417 barcode, `ReadBarCodes()` returns an empty collection and the loop body never executes. Always check for an empty result in production code.

## Read barcodes from image in C# – handling common scenarios

### 1. Decoding multiple barcode formats

If you need to detect more than one format, pass a combined `DecodeType` flag:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Managing large images

Large images can cause high memory usage. Downscale the image before passing it to the reader:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Error handling

Wrap the reading logic in a try‑catch block to surface decoding failures:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Full working example

Below is the complete program you can copy, paste, and run. It includes all the steps, necessary `using` directives, and a simple error‑handling scaffold.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Running the program** prints each detected Macro PDF417 barcode and its extended fields, or informs you that no barcodes were found.

## Conclusion

You now know **how to use BarCodeReader** to read barcodes from image C# applications, including extracting Macro PDF417 metadata. The solution covers initialization, iteration, extended property access, and practical tips for handling multiple formats, large images, and errors.

Next, you might explore:

* **Reading QR codes** – replace `DecodeType.MacroPdf417` with `DecodeType.QR`.
* **Saving decoded data** to a database or JSON file for downstream processing.
* **Integrating with ASP.NET Core** to accept uploaded images via a web API.

Feel free to experiment with different barcode types and image sources. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [c# barcode reader tutorial – read Macro PDF417 barcodes step by step using GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [How to use a barcode generator C# for Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}