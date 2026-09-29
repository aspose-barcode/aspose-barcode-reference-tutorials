---
category: general
date: 2026-09-29
description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
  Follow a step‑by‑step guide to export barcode image efficiently.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: en
lastmod: 2026-09-29
og_description: Create barcode GS1 in C# and generate barcode PNG files with BarcodeGenerator.
  Follow this complete guide to export barcode image quickly.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Create barcode GS1 in C# – export as PNG in minutes
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Create barcode GS1 in C# and export it as PNG
url: /net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode GS1 in C# and export it as PNG

If you need to **create barcode GS1** in a .NET application, this guide shows you exactly how to do it. You’ll see a concise solution that generates a barcode PNG image and exports the barcode image to disk, all with the Aspose.BarCode `BarcodeGenerator` class.

Generating a GS1 barcode is a common requirement for inventory, shipping, and point‑of‑sale systems. By the end of this tutorial you’ll be able to write a small C# program that creates a GS1‑compliant MicroPDF417 barcode and saves it as a high‑quality PNG file.

## Prerequisites

Before you start, make sure you have:

* **.NET 6** (or any later .NET version) installed.
* **Visual Studio 2022** or any IDE that supports C#.
* The **Aspose.BarCode for .NET** NuGet package (`Aspose.BarCode`) – it provides the `BarcodeGenerator` API used in the examples.
* Basic familiarity with C# syntax.

> **Pro tip:** Use the free community edition of Aspose.BarCode when experimenting; the full version removes any evaluation watermarks.

## Step 1 – Create barcode GS1 with BarcodeGenerator

The first thing you need is to instantiate the `BarcodeGenerator` for the *MicroPDF417* format and feed it a GS1 data string. The GS1 Application Identifiers (AIs) are wrapped in parentheses, e.g. `(01)` for GTIN‑14 and `(21)` for a serial number.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Why this matters:**  
`EncodeTypes.MicroPdf417` automatically treats the input as GS1 data when the string contains valid AIs. This ensures the generated barcode complies with the GS1 specification without extra configuration.

## Step 2 – Set barcode dimensions for optimal size

A barcode’s visual size is controlled by its **X‑dimension** (the width of a single module). Adjusting `XDimension.Pixels` lets you fine‑tune the final image size while preserving readability.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **How to generate barcode PNG** – The X‑dimension does not affect the data encoded; it only changes the physical dimensions of the generated image. If you need a larger barcode for high‑resolution printing, increase this value (e.g., `3` or `4`).

## Step 3 – Generate barcode PNG and export barcode image

Now you can render the barcode and write it to a PNG file. The `Save` method takes the target path and the desired image format.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**What happens under the hood:**  
`BarcodeGenerator.Save` rasterizes the barcode into a bitmap, applies the X‑dimension you set earlier, and encodes the bitmap as a PNG file. The resulting file can be used directly in web pages, printed on labels, or embedded in PDFs.

## Full source code example

Below is a complete, self‑contained console application that you can copy, paste, and run. It demonstrates **how to generate barcode PNG** files, **export barcode image**, and includes basic error handling.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Expected output

When you run the program, you should see:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Opening the PNG file displays a clear **GS1 MicroPDF417** barcode that encodes the GTIN‑14 `12345678901234` and the serial number `ABC123`. Scanning it with any GS1‑compatible scanner will return the original data string.

## Common pitfalls and best practices

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Incorrect AI formatting** | Missing parentheses or wrong order makes the barcode non‑GS1. | Always wrap each AI in parentheses, e.g., `(01)`. |
| **Too small X‑dimension** | The barcode becomes unreadable on low‑resolution devices. | Keep `XDimension.Pixels` ≥ 2 for most printers; increase for high‑DPI output. |
| **Output folder does not exist** | `Save` throws `DirectoryNotFoundException`. | Use `Directory.CreateDirectory` before calling `Save`. |
| **Using the wrong EncodeType** | Some types (e.g., `Code128`) do not support GS1 data out of the box. | Choose `EncodeTypes.MicroPdf417` or any GS1‑compatible type. |
| **Missing NuGet reference** | Compile‑time errors like `The type or namespace name 'Aspose' could not be found`. | Install the `Aspose.BarCode` package via NuGet. |

## Extending the example

* **Different image formats** – Replace `BarCodeImageFormat.Png` with `Jpeg`, `Gif`, or `Bmp` if you need another format.
* **Higher‑resolution output** – Set `generator.Parameters.ImageResolution.DpiX` and `DpiY` before saving.
* **Embedding in PDF** – Use `Aspose.Pdf` to place the PNG into a PDF invoice or label.

## Conclusion

You now know how to **create barcode GS1** in C# using the Aspose.BarCode `BarcodeGenerator`, **generate barcode PNG**, and **export barcode image** to the file system. The guide covered every step—from initializing the generator with GS1 data, adjusting the X‑dimension, to saving the final PNG file—while addressing common errors and offering extension ideas.

Feel free to experiment with other GS1 Application Identifiers, different barcode symbologies, or higher‑resolution images. When you master these basics, generating compliant barcodes for inventory, shipping, or retail becomes a routine part of your .NET toolbox.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Create barcode PNG in C# – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Create barcode image in C# – complete programming guide](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}