---
category: general
date: 2026-10-21
description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417 barcode
  with custom layout, columns, rows, and PNG output.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: en
lastmod: 2026-10-21
og_description: Generate pdf417 barcode in C#. Follow this tutorial to learn how to
  generate pdf417 barcode with custom columns, rows, and PNG output.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generate pdf417 barcode in C# – full step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Generate pdf417 barcode in C# with custom columns and rows
url: /net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate pdf417 barcode in C# – complete programming guide

If you need to **generate pdf417 barcode** in a .NET application, this guide shows you how to do it with a few lines of code. You’ll see a practical example that configures the number of columns and rows, then saves the result as a PNG image. The same approach works for any text you want to encode, so you can adapt it to invoices, tickets, or ID cards.

Generating a **pdf417 barcode** often feels like a separate task from the rest of your codebase. By the end of this tutorial you’ll understand why layout parameters matter, how to control image quality, and which library calls are required to **generate pdf417 barcode** reliably.

## What you’ll need

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A C#‑compatible IDE (Visual Studio, VS Code, Rider, etc.)  
* The **Aspose.BarCode for .NET** NuGet package (or any compatible barcode library)  

You can add the library with the following command:

```bash
dotnet add package Aspose.BarCode
```

The library provides the `BarcodeGenerator` class used throughout this tutorial.

## Step 1: Create a barcode generator instance

The first line creates an object that knows how to **generate pdf417 barcode**. You must specify the encoding type (`EncodeTypes.Pdf417`) and the text you want to encode.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Why this step matters* – The `BarcodeGenerator` encapsulates all settings for the barcode. Instantiating it with the correct `EncodeTypes` tells the engine to use the PDF417 symbology instead of QR, Code128, or other formats.

## Step 2: Configure the PDF417 layout

PDF417 lets you control the number of columns and rows, which directly influences the barcode’s size and density. Adjusting these values is the core of **how to generate pdf417 barcode** with a custom layout.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Why you might change these values* – More columns reduce the barcode height, while more rows increase width. Choose values that fit the target scanning device and the available print area.

> **Pro tip:** If you omit rows, the library automatically calculates the optimal count based on the data length. Explicitly setting rows is useful when you need a fixed image size for UI layouts.

## Step 3: Choose an image format and save the file

After configuring the layout, you can render the barcode to an image. The example below saves the barcode as a PNG file, but you can also select JPEG, BMP, or TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

When the code runs, `CustomLayout.png` will contain a clear **pdf417 barcode** that matches the column/row settings you provided.

### Expected output

Opening `CustomLayout.png` shows a rectangular barcode with four data columns and nine rows. Scanning the image with any PDF417 reader returns the original text **“Sample Text”**.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Generated pdf417 barcode saved as a PNG file"}

## Step 4: Full, runnable example

Below is a self‑contained console application that puts all the pieces together. Copy the code into a new `.csproj` project and run it—no additional files are required.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Running the program prints a confirmation line and creates the PNG file under an `output` subfolder. The image can be embedded in reports, printed on labels, or sent to a mobile device for scanning.

## Common variations and edge cases

| Scenario | What to change | Why it matters |
|----------|----------------|----------------|
| **Encode a long string** | Increase `Rows` or let the library auto‑calculate by omitting the `Rows` assignment | PDF417 can hold up to 1,850 characters; insufficient rows cause truncation |
| **Higher visual quality** | Set `generator.Parameters.ImageResolution` to 600 DPI | Useful for printing on high‑resolution printers |
| **Different image format** | Replace `BarCodeImageFormat.Png` with `Jpeg` or `Tiff` | JPEG reduces file size; TIFF preserves lossless data for archival |
| **Add a quiet zone** | `generator.Parameters.Barcode.XDimension = 2;` (or adjust `Margins`) | Quiet zones improve scanner reliability in noisy environments |
| **Dynamic text from user input** | Replace the hard‑coded string with `Console.ReadLine()` | Enables runtime generation based on user data |

### How to generate pdf417 barcode in a web API

If you need to expose barcode generation through an ASP.NET Core endpoint, return the image as a byte array:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

This snippet answers **how to generate pdf417 barcode** on the fly without writing to disk, which is ideal for microservices or mobile back‑ends.

## Testing the generated barcode

To verify that the barcode was created correctly:

1. Open the PNG file in any image viewer.  
2. Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the image.  
3. Confirm that the decoded text matches the original input.

If the scanner reports errors, double‑check the column/row values and ensure the image resolution is high enough for your device.

## Conclusion

You now know how to **generate pdf417 barcode** in C# with full control over columns, rows, and output format. The complete example demonstrates the entire workflow—from creating the `BarcodeGenerator` to saving a PNG file—so you can integrate barcode creation into any .NET project.

Next, explore related topics such as **pdf417 barcode layout** optimization, embedding barcodes in PDF reports, or decoding barcodes on mobile devices. Adjusting error‑correction levels and experimenting with different image resolutions will help you fine‑tune the solution for your specific use case. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}