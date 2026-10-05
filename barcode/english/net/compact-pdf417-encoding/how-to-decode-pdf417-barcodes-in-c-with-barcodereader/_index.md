---
category: general
date: 2026-09-07
description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This step‑by‑step
  guide also explains how to read PDF417 data efficiently.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: en
lastmod: 2026-09-07
og_description: How to decode PDF417 barcodes in C# using BarCodeReader. Follow this
  tutorial to learn how to read PDF417 data and extract MacroPdf417 fields.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: How to decode PDF417 barcodes in C# – complete guide
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: How to decode PDF417 barcodes in C# with BarCodeReader
url: /net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to decode PDF417 barcodes in C# with BarCodeReader

If you need to **how to decode PDF417** barcodes in a .NET application, this guide walks you through the entire process. You’ll also discover **how to read PDF417** data such as MacroPdf417 file and segment identifiers, all with a few lines of C#.

Decoding PDF417 is common when working with transport tickets, driver's licenses, or shipping labels. By the end of this tutorial you will have a runnable console program that prints every MacroPdf417 field exposed by the GroupDocs.Barcode SDK.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code compiles with .NET Core and .NET Framework)
* Visual Studio 2022 or any IDE that supports C#
* The **GroupDocs.Barcode** NuGet package (`GroupDocs.Barcode` ≥ 23.3)
* An image file that contains a Macro PDF417 barcode (e.g., `ExtPDF417Meta.png`)

> **Pro tip:** Install the package via the CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## How to decode PDF417 barcodes in C#

The following sections break the solution into logical steps. Each step includes the exact code you need and a short explanation of why it matters.

### Step 1: Prepare the project and import namespaces

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Why?*  
`GroupDocs.Barcode` provides the `BarCodeReader` class, while `GroupDocs.Barcode.Common` contains the `DecodeType` enumeration needed for PDF417 decoding.

### Step 2: Define the image path

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Why?*  
The reader works with any image format supported by .NET (`.png`, `.jpg`, `.bmp`). Supplying the correct path ensures the SDK can locate the file.

### Step 3: Initialize the barcode reader for MacroPdf417 decoding

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Why?*  
`DecodeType.MacroPdf417` tells the SDK to look for the extended Macro PDF417 format, which carries additional metadata such as file and segment IDs. Using the `using` statement guarantees that unmanaged resources are released promptly.

### Step 4: Read every barcode found in the image

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Why?*  
An image may contain multiple barcodes. The `ReadBarCodes()` method returns a collection, allowing you to process each one individually.

### Step 5: Retrieve and display Macro PDF417 specific data

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Why?*  
The `Extended.Pdf417` object exposes all Macro PDF417 fields defined by the specification. Printing them lets you verify that the decode operation succeeded and gives you the data you need for downstream processing.

### Full runnable example

Combine the snippets above into a single `Program.cs` file:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Expected console output** (values will differ based on the barcode content):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

If the image does not contain a Macro PDF417 barcode, the `ReadBarCodes()` collection will be empty and nothing will be printed.

## Common variations and edge cases

| Situation | How to adapt the code |
|-----------|----------------------|
| **Standard (non‑macro) PDF417** | Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended.Pdf417` object will be `null`, so guard against null references. |
| **Multiple images** | Wrap the reader initialization in a `foreach (var path in imagePaths)` loop. |
| **Large images** | Set `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` to limit memory usage. |
| **Performance‑critical batch** | Reuse a single `BarCodeReader` instance with `reader.SetImage(path)` instead of creating a new object for each file. |

## Troubleshooting checklist

* **No output:** Verify that `imagePath` points to a valid file and that the image actually contains a PDF417 barcode. |
* **Null `Extended.Pdf417`:** You probably used `DecodeType.Pdf417` instead of `MacroPdf417`. |
* **Exception `FileNotFoundException`:** Ensure the working directory matches the path or use an absolute path. |
* **Low confidence score:** Increase image quality or adjust `reader.Options.Quality` settings.

## Conclusion

You now know **how to decode PDF417** barcodes in C# and **how to read PDF417** metadata such as Macro file IDs, segment IDs, and timestamps. The complete example demonstrates initializing `BarCodeReader`, selecting the correct decode type, iterating over results, and extracting every available MacroPdf417 field.

From here you can:

* Integrate the extracted data into a logistics or ticket‑validation system.
* Extend the console app to write results to a database or JSON file.
* Explore other barcode formats supported by GroupDocs.Barcode (QR, DataMatrix, Code128, etc.) by swapping the `DecodeType` enumeration.

Happy coding, and feel free to experiment with different images and barcode settings to master PDF417 decoding in your .NET projects!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}