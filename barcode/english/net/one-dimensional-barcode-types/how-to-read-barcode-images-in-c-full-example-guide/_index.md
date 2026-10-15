---
category: general
date: 2026-10-15
description: How to read barcode images in C# quickly using BarCodeReader. Learn to
  read multiple barcodes and see a c# barcode reader example that works with Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: en
lastmod: 2026-10-15
og_description: How to read barcode in C# using BarCodeReader. This tutorial shows
  a complete c# barcode reader example that handles multiple barcodes and extracts
  Macro‑PDF417 metadata.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: How to read barcode in C# – step‑by‑step example
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: How to read barcode images in C# – full example guide
url: /net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to read barcode images in C# – full example guide

If you need to **how to read barcode** data from an image in a .NET application, this guide gives you a ready‑to‑run solution. You’ll see a complete **c# barcode reader example** that works with Macro‑PDF417 symbols and can **read multiple barcodes** from a single picture.

Reading barcodes is a common requirement for inventory systems, ticket validation, and document processing. By the end of this tutorial you will be able to:

* Initialize the `BarCodeReader` for any supported format.  
* Extract basic information such as code type and decoded text.  
* Retrieve Macro‑PDF417‑specific metadata (file ID, segment, checksum, …).  
* Handle images that contain several barcodes without extra code.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed.  
* A development environment (Visual Studio 2022, VS Code, or Rider).  
* The **Aspose.BarCode for .NET** NuGet package (`Aspose.BarCode`) – it provides the `BarCodeReader` class used in the example.  
* An image file that contains a Macro‑PDF417 barcode (e.g., `MacroPdf417.png`).  

You can install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## How to read barcode with BarCodeReader in C#

The core of the solution lives in four concise steps. Each step is wrapped in a `using` block to guarantee that unmanaged resources are released promptly.

### Step 1: Initialise the `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Why this matters:**  
`BarCodeReader` accepts a file path and a `DecodeType`. Specifying `DecodeType.MacroPdf417` tells the library to look for Macro‑PDF417 symbols only, which improves detection speed and reduces false positives.

### Step 2: Read all barcodes present in the image

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Why this matters:**  
The `ReadBarCodes()` method returns an array that can contain one or many `BarCodeResult` objects. This is the point where the **read multiple barcodes** capability shines – you don’t need a separate loop for each possible barcode.

### Step 3: Display basic barcode details

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Why this matters:**  
`CodeTypeName` tells you which symbology was detected (e.g., “MacroPDF417”), while `CodeText` holds the decoded payload. These two fields are the most frequently used in downstream logic.

### Step 4: Retrieve and show Macro‑PDF417 specific metadata

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Why this matters:**  
Macro‑PDF417 extends the regular PDF417 format with document‑level metadata. Accessing the `Extended.Pdf417` property gives you everything you need to reconstruct the original file, validate integrity, or route the data to the proper recipient.

### Full runnable program

Below is a self‑contained console application that puts all four steps together. Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Expected console output

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

If the image contains more than one Macro‑PDF417 symbol, the program prints a separate block for each barcode, demonstrating the **read multiple barcodes** capability without any extra code.

## Handling common edge cases

| Situation | What to do | Reason |
|-----------|------------|--------|
| **File not found** | Wrap the `BarCodeReader` construction in a `try/catch (FileNotFoundException)` block and display a friendly message. | Prevents the application from crashing and informs the user about the missing asset. |
| **No barcode detected** | Check `results.Length == 0` (as shown in the full program) and handle it gracefully. | Gives clear feedback when the image does not contain any supported symbology. |
| **Different barcode type** | Change `DecodeType.MacroPdf417` to `DecodeType.AllSupportedTypes` or another specific enum value. | Allows the same code base to work with QR, Code128, DataMatrix, etc., while still supporting **read multiple barcodes**. |
| **Large images** | Set `reader.AutoSize = true` or down‑scale the image before feeding it to the reader. | Improves performance and reduces memory pressure on the CLR. |
| **Thread‑safe usage** | Create a separate `BarCodeReader` instance per thread; the class is not thread‑safe. | Avoids race conditions in multi‑threaded scanners or web services. |

## Pro tips for production code

* **Dispose early:** The `using` statement ensures that native resources (e.g., image buffers) are released promptly. In long‑running services, release the reader as soon as you finish processing each image.  
* **Batch processing


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}