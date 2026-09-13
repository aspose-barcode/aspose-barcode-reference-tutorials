---
category: general
date: 2026-09-13
description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
  and Macro PDF417 options. Step‑by‑step code, tips, and full example.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: en
lastmod: 2026-09-13
og_description: Create PDF417 barcode image in C# with BarcodeGenerator. Follow this
  detailed tutorial to configure Macro PDF417 options and save a PNG barcode.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Create PDF417 barcode image in C# – complete guide
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: How to create PDF417 barcode image in C# with Macro PDF417 options
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode image in C# with Macro PDF417 options

If you need to **create PDF417 barcode image** in C#, this guide shows you exactly how to do it using the **BarcodeGenerator class**. Whether you are building a document‑tracking system or encoding large files, the step‑by‑step instructions below cover everything from setting up Macro PDF417 options to saving the final PNG.

Generating a barcode is straightforward once you understand the key parameters. In this tutorial you will learn how to:

* Initialize a `BarcodeGenerator` for **Macro PDF417**.
* Adjust the barcode module size (`XDimension`).
* Configure segment‑specific settings such as file ID, segment ID, and checksum.
* Save the result as a **barcode image format** (PNG) that can be displayed in any UI.

The only prerequisite is a .NET development environment (Visual Studio 2022 or later) and the Aspose.BarCode for .NET NuGet package, which provides the `BarcodeGenerator` API used in the examples.

---

## How to create PDF417 barcode image in C# – overview

Creating a PDF417 barcode image consists of four logical steps:

1. **Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417` and the data you want to encode.  
2. **Define the module size** – set `XDimension.Pixels` to control the physical width of each barcode element.  
3. **Configure Macro PDF417 options** – specify columns, file identifiers, segment numbers, and optional checksum.  
4. **Save the barcode** – write the generated image to disk using a supported **barcode image format** such as PNG.

Each step is explained in detail below, with complete, runnable C# code.

---

## Step 1: Initialize the BarcodeGenerator for Macro PDF417

The first line creates a `BarcodeGenerator` object that knows it must produce a **Macro PDF417** barcode. The constructor takes two arguments: the encoding type and the raw data string.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Why this matters:**  
`EncodeTypes.MacroPdf417` tells the library to treat the barcode as a multi‑segment container, which is essential when you need to split a large file into several symbols. The `BarcodeGenerator` instance is disposable, so the `using` block guarantees that all unmanaged resources are released after the image is saved.

---

## Step 2: Set the barcode module size (XDimension)

`XDimension` controls the pixel width of a single barcode module (the smallest black or white bar). A value of **2 pixels** yields a compact yet readable image.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Practical tip:**  
If your target printer has a low DPI, increase the pixel count (e.g., `3` or `4`) to avoid smearing. Conversely, for on‑screen display you can keep it low to reduce file size.

---

## Step 3: Configure Macro PDF417 specific options

Macro PDF417 adds metadata that allows a scanner to reconstruct the original file from multiple barcode segments. The most common options are:

| Property | Meaning |
|----------|---------|
| `Columns` | Number of columns in each symbol (affects width). |
| `MacroPdf417FileID` | Unique identifier for the whole file. |
| `MacroPdf417SegmentID` | Index of the current segment (starts at 1). |
| `MacroPdf417SegmentsCount` | Total number of segments that make up the file. |
| `MacroPdf417FileName` | Original file name (optional, for display). |
| `MacroPdf417Checksum` | Optional 16‑bit checksum for integrity verification. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Why these settings are important:**  
- **Columns** affect readability and overall image dimensions.  
- **FileID** must be the same across all segments so the decoder knows they belong together.  
- **SegmentID** and **SegmentsCount** let the scanner order the pieces correctly.  
- **FileName** and **Checksum** are optional but improve user experience and data integrity.

**Edge case:** If you generate more than 999 segments, the `SegmentID` field overflows; split the data into multiple files instead.

---

## Step 4: Save the generated barcode as a PNG image

The final step writes the barcode to disk. `BarCodeImageFormat.Png` produces a loss‑less image that works with web, desktop, and mobile platforms.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Alternative formats:**  
You can replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` if your downstream system requires a specific format. Keep in mind that JPEG introduces compression artifacts that may reduce scan reliability.

**Expected output:**  
The file `MacroPdf417.png` will contain a high‑contrast, multi‑segment PDF417 barcode. When opened, it should look similar to the illustration below.

![Create PDF417 barcode image example](image.png){: .align-center alt="Create PDF417 barcode image example generated by C# code"}

---

## Full source code – ready to copy and run

Below is the complete, self‑contained program. It includes the necessary `using` directives, the `Main` method, and comments that explain each non‑obvious line.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Running the program:**  

1. Create a new .NET 6 (or later) console project.  
2. Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).  
3. Replace the generated `Program.cs` with the code above.  
4. Adjust `outputPath` to a folder you have write access to.  
5. Build and run – the console will confirm the image location.

---

## Common questions & troubleshooting

| Question | Answer |
|----------|--------|
| *What if the barcode is too wide for my label?* | Reduce `Columns` or increase `XDimension.Pixels` to balance width and readability. |
| *Do I need to set a checksum?* | The checksum is optional


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}