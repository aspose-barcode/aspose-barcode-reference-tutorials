---
category: general
date: 2026-10-02
description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
  PDF417 barcode and see how to generate PDF417 barcode in compact mode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: en
lastmod: 2026-10-02
og_description: Create barcode from text in C# with Aspose.BarCode. This guide shows
  how to generate PDF417 barcode and how to generate PDF417 barcode in compact mode.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Create barcode from text in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: How to create barcode from text in C# with Aspose.BarCode
url: /net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode from text in C# with Aspose.BarCode

If you need to **create barcode from text** in a .NET application, this guide walks you through the complete process. You’ll see a ready‑to‑run example that **generates PDF417 barcode** and also answers **how to generate PDF417 barcode** in a compact layout.

Generating a barcode programmatically removes manual steps and guarantees consistency across all documents. By the end of this tutorial you will have a PNG file containing a PDF417 barcode that you can embed in invoices, tickets, or identity cards.

## What you’ll need

- .NET 6.0 SDK or later (the code also works with .NET Framework 4.7.2+)
- Visual Studio 2022 or any editor that supports C#
- A NuGet license for **Aspose.BarCode for .NET** (a free trial works for testing)

> **Pro tip:** Add the NuGet package via the CLI to keep the project clean:  
> `dotnet add package Aspose.BarCode`

## Step 1: Set up a console project

Create a new console application and reference the Aspose.BarCode library.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

The `dotnet new console` command generates a `Program.cs` file that we will replace with the full example below.

## Step 2: How to create barcode from text – core code

Open `Program.cs` and replace its contents with the following code. Every line is commented to explain why it exists.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Why each setting matters

| Setting | Purpose |
|--------|----------|
| `EncodeTypes.Pdf417` | Selects the PDF417 symbology, which can store large amounts of data in a two‑dimensional matrix. |
| `XDimension.Pixels = 2` | Controls the width of each module; a value of 2 pixels balances readability and file size. |
| `Pdf417.Columns = 3` | Reduces the number of columns, making the barcode more compact without losing data. |
| `Pdf417.Truncate = true` | Activates compact mode, removing unnecessary padding and shortening the barcode. |
| `BarCodeImageFormat.Png` | PNG preserves lossless quality, ideal for further processing or printing. |

## Step 3: Generate PDF417 barcode – running the example

Build and run the project:

```bash
dotnet run
```

When execution finishes you will see:

```
Barcode saved to CompactPdf417.png
```

Open `CompactPdf417.png` to view the result. The image contains a PDF417 barcode that encodes the string **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: create barcode from text – PDF417 barcode saved as PNG*

## Step 4: How to generate PDF417 barcode with custom error correction (optional)

If your scanning environment is noisy, you can increase error correction level:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Increasing the error level makes the barcode larger but improves resilience against damage.

## Step 5: Common pitfalls and edge‑case handling

1. **Invalid characters** – PDF417 supports Unicode, but some older scanners may reject non‑ASCII symbols. Test with your target hardware.
2. **File path permissions** – Ensure the directory you write to is writable; otherwise `Save` throws an `UnauthorizedAccessException`.
3. **Image size** – Very high `XDimension` values produce large PNG files. Keep the pixel size between 1 and 4 for most screen‑display scenarios.

## Recap

You now know how to **create barcode from text** in C# using Aspose.BarCode, how to **generate PDF417 barcode** with a compact layout, and the exact steps for **how to generate PDF417 barcode** with custom settings. The complete, runnable code above can be copied into any .NET project and adapted to different text inputs or output formats (e.g., JPEG, BMP).

## Next steps

- Explore other symbologies such as QR Code or Code128 by changing `EncodeTypes`.
- Integrate the generated PNG into a PDF using Aspose.PDF for end‑to‑end document creation.
- Experiment with `generator.Parameters.Barcode.Pdf417.Rows` to control vertical density.

Feel free to modify the example, embed the barcode in your own applications, and share your results with the community. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# – compact example](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}