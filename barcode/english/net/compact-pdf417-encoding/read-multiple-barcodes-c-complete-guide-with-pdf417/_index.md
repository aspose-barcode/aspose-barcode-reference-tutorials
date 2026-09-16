---
category: general
date: 2026-07-30
description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step how
  to decode PDF417, detect compact mode, and handle many barcodes in one image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read multiple barcodes c#
- BarCodeReader C#
- PDF417 decoding
- barcode compact mode
- C# barcode library
language: en
lastmod: 2026-07-30
og_description: Read multiple barcodes C# with Aspose.BarCode. This guide shows you
  how to decode all barcodes in an image, check compact mode, and integrate into .NET
  apps.
og_image_alt: Screenshot of C# console output showing compact mode status for PDF417
  barcodes
og_title: Read Multiple Barcodes C# – Full Tutorial for PDF417
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  headline: Read Multiple Barcodes C# – Complete Guide with PDF417
  type: TechArticle
- description: Read multiple barcodes C# using Aspose.BarCode. Learn step‑by‑step
    how to decode PDF417, detect compact mode, and handle many barcodes in one image.
  name: Read Multiple Barcodes C# – Complete Guide with PDF417
  steps:
  - name: Why This Code Works
    text: '- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API.
      It opens the image, applies pre‑processing, and searches for symbols of the
      type you specify. - **`ReadBarCodes()`** returns an array, not just a single
      result. That’s the key to **reading multiple barcodes C#**—the method aut'
  - name: 1️⃣ No Barcodes Detected
    text: 'If `ReadBarCodes()` returns an empty array, the most common culprits are:'
  - name: 2️⃣ Extremely Large Images
    text: 'Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:'
  - name: 3️⃣ Thread‑Safety
    text: '`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin
      up separate instances per thread if you need parallel processing.'
  - name: 4️⃣ Licensing
    text: 'Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark
      on the output image. For production, set the license early:'
  - name: 5️⃣ Logging
    text: When you integrate this into a larger service, replace `Console.WriteLine`
      with a structured logger (Serilog, NLog). That way you can capture `CodeText`,
      `CodeType`, and `IsTruncated` as fields for downstream analytics.
  type: HowTo
tags:
- C#
- BarCode
- PDF417
- Aspose
- Barcode Decoding
title: Read Multiple Barcodes C# – Complete Guide with PDF417
url: /net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Multiple Barcodes C# – Complete Guide with PDF417

Ever wondered how to **read multiple barcodes C#** from a single image? Maybe you have a batch of shipping labels, a ticket collage, or a PDF417 document that packs several codes into one picture. In my day‑to‑day work, I’ve hit exactly that wall—until I discovered Aspose.BarCode’s `BarCodeReader`. This tutorial will walk you through decoding every barcode in an image, figuring out whether each PDF417 is in compact (truncated) mode, and handling the results cleanly.

We'll also sprinkle in a few extra tips—like what to do when the image contains different barcode symbologies, or when a scan returns no results at all. By the end you’ll have a ready‑to‑run console app that **reads multiple barcodes C#** like a pro.

## What You’ll Need

Before we dive, make sure you have the following on your machine:

- **.NET 6.0** SDK or newer (the code works with .NET Framework 4.6+ as well, but .NET 6 is the sweet spot).
- **Aspose.BarCode for .NET** NuGet package (`Install-Package Aspose.BarCode`).
- A sample image that contains **PDF417** barcodes—preferably one that mixes compact and full‑size symbols. The tutorial uses `CompactPdf417.png`, but any PNG/JPEG will do.
- Your favorite IDE (Visual Studio, Rider, or VS Code).  

That’s it—no extra DLLs, no native dependencies. Aspose.BarCode is pure managed code, so you can drop it into any .NET project.

![Read multiple barcodes C# console output](image.png "Read multiple barcodes C# console output")

*Image alt text: Read multiple barcodes C# – screenshot of console displaying compact mode status for PDF417 barcodes.*

## Step 1 – Install and Reference the BarCodeReader C# Library

First things first, you need the **BarCodeReader C#** class that powers the decoding. Open your terminal (or Package Manager Console) and run:

```powershell
dotnet add package Aspose.BarCode
```

Or, if you’re inside Visual Studio’s NuGet manager, just search for *Aspose.BarCode* and hit **Install**. This pulls in the latest stable version (as of July 2026 it’s 23.9), which supports PDF417, QR, DataMatrix, and dozens of other symbologies.

Why this matters: the library abstracts away the heavy lifting of image processing, error correction, and symbol recognition. You could write your own scanner, but you’d spend weeks chasing edge‑cases. Aspose gives you a battle‑tested, **C# barcode library** that’s been updated for modern .NET runtimes.

## Step 2 – Set Up a Minimal Console Project

Create a fresh console app so we can focus on the barcode logic without any UI noise:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Replace the generated `Program.cs` with the full example below. Feel free to keep the default namespace or rename it—nothing special is required.

## Step 3 – Write the Full “Read Multiple Barcodes C#” Implementation

Below is a **complete, runnable** code sample. It covers all four steps from the original snippet, adds error handling, and prints useful diagnostics.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // ---------------------------------------------------------
            // 1️⃣  Initialize the BarCodeReader for the target image.
            // ---------------------------------------------------------
            // Replace the path with your own image location.
            const string imagePath = "YOUR_DIRECTORY/CompactPdf417.png";

            // The DecodeType.Pdf417 tells the reader to look for PDF417 symbols.
            // You could pass DecodeType.AllSupported to scan every possible barcode.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
            {
                // ---------------------------------------------------------
                // 2️⃣  Iterate over every barcode found in the picture.
                // ---------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes detected – double‑check the image path and content.");
                    return;
                }

                // ---------------------------------------------------------
                // 3️⃣  Process each result: check compact mode and output data.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    // The Extended property gives us PDF417‑specific info.
                    bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;

                    // Display the raw text and the compact‑mode flag.
                    Console.WriteLine($"Code Text   : {result.CodeText}");
                    Console.WriteLine($"Compact mode: {isCompact}");
                    Console.WriteLine(new string('-', 30));
                }
            }

            // ---------------------------------------------------------
            // 4️⃣  Keep the console window open when debugging.
            // ---------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Why This Code Works

- **`BarCodeReader`** is the workhorse from the **BarCodeReader C#** API. It opens the image, applies pre‑processing, and searches for symbols of the type you specify.
- **`ReadBarCodes()`** returns an array, not just a single result. That’s the key to **reading multiple barcodes C#**—the method automatically collects every match it finds.
- **`result.Extended.Pdf417.IsTruncated`** tells us whether the PDF417 is in *compact* (a.k.a. truncated) mode. This flag only exists for PDF417, so we guard with the null‑conditional operator (`?.`) to avoid exceptions if another symbology sneaks in.
- The `foreach` loop prints both the decoded text and the compact status, giving you a quick sanity check.

## Step 4 – Handling Different Barcode Types (Optional)

If your image might contain more than just PDF417, simply change the second argument of `BarCodeReader` to `DecodeType.AllSupported`. The loop stays the same, but you’ll need to guard against `result.Extended` being null for non‑PDF417 symbols:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Symbology : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // PDF417‑specific check only when applicable.
        if (result.CodeType == DecodeType.Pdf417)
        {
            bool isCompact = result.Extended?.Pdf417?.IsTruncated ?? false;
            Console.WriteLine($"Compact mode: {isCompact}");
        }

        Console.WriteLine(new string('=', 30));
    }
}
```

This small tweak turns your **C# barcode library** into a universal scanner, perfect for mixed‑symbology batches.

## Step 5 – Edge Cases and Best‑Practice Tips

### 1️⃣ No Barcodes Detected  
If `ReadBarCodes()` returns an empty array, the most common culprits are:

- Wrong file path or missing read permissions.
- Image quality too low (blur, low contrast). Consider pre‑processing with `reader.ImagePreprocessingOptions` (e.g., `reader.ImagePreprocessingOptions.Denoise = true;`).

### 2️⃣ Extremely Large Images  
Processing a 10 MP photo can be memory‑hungry. You can limit the scan area:

```csharp
reader.SetRegionOfInterest(0, 0, 2000, 2000); // left, top, width, height
```

### 3️⃣ Thread‑Safety  
`BarCodeReader` implements `IDisposable` and is **not** thread‑safe. Spin up separate instances per thread if you need parallel processing.

### 4️⃣ Licensing  
Aspose.BarCode works in trial mode out of the box, but you’ll see a watermark on the output image. For production, set the license early:

```csharp
License license = new License();
license.SetLicense("Aspose.BarCode.lic");
```

### 5️⃣ Logging  
When you integrate this into a larger service, replace `Console.WriteLine` with a structured logger (Serilog, NLog). That way you can capture `CodeText`, `CodeType`, and `IsTruncated` as fields for downstream analytics.

## Full Working Example Recap

Putting it all together, here’s the *entire* program you can copy‑paste into `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            const string imagePath = "YOUR_DIRECTORY


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}