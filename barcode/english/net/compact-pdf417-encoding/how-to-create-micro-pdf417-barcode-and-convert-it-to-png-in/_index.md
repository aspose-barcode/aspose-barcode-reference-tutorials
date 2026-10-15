---
category: general
date: 2026-10-12
description: Learn to create micro PDF417 barcode and convert barcode to PNG using
  C#. Step‑by‑step guide with full code and tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: en
lastmod: 2026-10-12
og_description: Create micro PDF417 barcode and convert barcode to PNG with C#. Follow
  this complete guide to generate both standard and GS1 versions.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Create micro PDF417 barcode and convert it to PNG – C# tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: How to create micro PDF417 barcode and convert it to PNG in C#
url: /net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create micro PDF417 barcode and convert it to PNG in C#

If you need to **create micro PDF417 barcode** in a .NET application, this tutorial shows you exactly how. You’ll see a complete, runnable example that generates both a standard Micro PDF417 barcode and a GS1‑compliant version, then **convert barcode to PNG** for downstream use such as printing or web display.

Generating a barcode is more than just calling a single method—choosing the right module size, column count, and encoding format determines scan reliability. By the end of this guide you’ll understand why each setting matters and how to adjust them for your own projects.

## Prerequisites

Before you start, make sure you have:

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Provides the runtime for the C# console app |
| Visual Studio 2022 (or any C# IDE) | Makes editing and debugging easier |
| **Aspose.BarCode for .NET** NuGet package | Supplies `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat` classes |
| Write permission to the output folder | Required for `Save` calls that create PNG files |

You can add the Aspose.BarCode package via the CLI:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up a minimal console project

Create a new console project and reference the barcode library. The following `Program.cs` contains all the code you need; no external files are required.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Why each line matters

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – The first creates a plain Micro PDF417 barcode, while the second follows GS1 standards, embedding Application Identifiers (AIs). Choose based on whether your downstream system expects GS1 data.
* **`XDimension.Pixels = 2`** – Controls the module width. Smaller values create a denser image but may become unreadable on low‑resolution scanners. Two pixels is a safe default for most label printers.
* **`Pdf417.Columns = 4`** – Micro PDF417 allows you to limit columns, reducing overall width. Four columns keep the barcode compact without sacrificing data capacity for short payloads.
* **`BarCodeImageFormat.Png`** – PNG preserves lossless quality, essential for barcode clarity. That’s why we **convert barcode to PNG** rather than JPEG.

## Step 2: Run the program and verify the output

1. Build the project: `dotnet build`.
2. Execute: `dotnet run`.

You should see console messages similar to:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Open the generated PNG files with any image viewer. Both images display a crisp, high‑contrast barcode ready for scanning.

### Expected visual result

| Barcode type | Appearance |
|--------------|------------|
| **Micro PDF417** | Small rectangular pattern with 4 columns, readable by most 2‑D barcode scanners. |
| **GS1 Micro PDF417** | Same size but encodes GS1 AIs; a scanner that understands GS1 will return the GTIN and serial number. |

If a scanner fails to read the image, try increasing `XDimension.Pixels` to **3** or **4**, or reduce the column count for the standard Micro PDF417.

## Common pitfalls and how to avoid them

| Issue | Cause | Fix |
|-------|-------|-----|
| Blurry barcode after printing | Low DPI printer settings | Export PNG at 300 dpi or higher, or let the printer driver handle scaling. |
| Scanner returns “invalid data” | Missing or malformed GS1 AI format | Ensure every AI is wrapped in parentheses and follows the GS1 specification (e.g., `(01)` for GTIN‑14). |
| Image file not created | Output folder lacks write permission | Run the program with elevated rights or choose a folder like `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Barcode too large for label | Default column count too high | Reduce `Pdf417.Columns` (e.g., to **3**) or increase `XDimension` to shrink overall size. |

## Extending the example

* **Different image formats** – Replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` if your workflow requires them. PNG remains the best choice for lossless quality.
* **Dynamic data** – Pass user input or database values to the `BarcodeGenerator` constructor to create barcodes on the fly.
* **Batch generation** – Wrap the creation logic in a loop that reads rows from a CSV file and saves each barcode with a unique filename.

## Conclusion

You now know how to **create micro PDF417 barcode** in C# and **convert barcode to PNG** for both standard and GS1‑compliant scenarios. The complete, runnable code demonstrates the essential settings—X dimension, column count, and encoding type—so you can adapt the solution to any .NET project that needs compact, high‑quality 2‑D barcodes.

*Next steps*: explore other symbologies supported by Aspose.BarCode (e.g., QR, DataMatrix), experiment with different `XDimension` values for high‑resolution printing, or integrate the generated PNGs into a web API that serves barcodes on demand.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create micro pdf417 barcode in C# and save it as PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Generate Micro PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}