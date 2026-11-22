---
category: general
date: 2026-11-20
description: Generate a PDF417 barcode image in C# using Aspose.BarCode. Learn how to customize layout and save it as PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: en
lastmod: 2026-11-20
og_description: Generate a PDF417 barcode image in C# with Aspose.BarCode. This guide shows how to customize layout and export to PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Generate PDF417 barcode image with Aspose.BarCode in C# – complete tutorial
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Generate a PDF417 barcode image in C# using Aspose.BarCode. Learn how to customize layout and save it as PNG.
  headline: Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate a PDF417 barcode image in C# using Aspose.BarCode. Learn how to customize layout and save it as PNG.
  name: Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode image with PDF417 in C# – step‑by‑step guide

If you need to **create barcode image** in a .NET application, this guide shows you exactly **how to generate PDF417 barcode** with a custom layout and save it as a PNG file. You’ll see the complete, runnable code, understand why each setting matters, and learn common pitfalls so your barcode works reliably in production.

In this tutorial you will:

* Initialize the Aspose.BarCode generator for PDF417.
* Configure column and row counts to control the barcode’s shape.
* Export the result as a high‑quality PNG image.
* Explore optional settings for error correction and data length.

The only prerequisite is a recent .NET SDK (.NET 6 or later) and a license or free trial of **Aspose.BarCode for .NET**.

---

## Prerequisites and setup

Before you start, make sure you have:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6 SDK or newer | Provides the runtime for the C# console app. |
| Visual Studio 2022 (or VS Code) | Gives you an IDE with IntelliSense for the Aspose API. |
| Aspose.BarCode for .NET NuGet package | Supplies `BarcodeGenerator`, `EncodeTypes`, and image‑export helpers. |
| Write permission to the output folder | The generator writes the PNG file to disk. |

You can add the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

---

## Step 1: Create a new console project

First, scaffold a simple console application that will host the barcode‑generation logic.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Why this code works

* **`BarcodeGenerator`** is the entry point for all barcode types. By passing `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol.
* **Columns and rows** are the primary levers for layout. Fewer columns produce a taller barcode; more columns make it wider. Adjust these values to fit the space where the image will be displayed (e.g., a label printer vs. a web page).
* **Error correction** improves scan reliability when the barcode may be smudged or printed on low‑quality media. The default level is 0; raising it slightly (2–4) is a good trade‑off between size and robustness.
* **`Save`** writes the image to disk in PNG format, which preserves sharp edges and works across browsers and mobile devices.

When you run the program (`dotnet run`), it creates `CustomPdf417.png` in the project folder. The PNG looks like this:

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Alt text:* **create barcode image** – PDF417 barcode generated in C# and saved as PNG.

---

## Step 2: Fine‑tune the barcode for real‑world scenarios

### Adjusting data length

PDF417 can encode up to 1,850 characters. If you need to encode longer strings, consider splitting the data across multiple barcodes or using the **compact mode**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Compact mode reduces the number of rows but may increase the visual density, so test with your scanner.

### Controlling image size

The default image size is calculated from the module size (the smallest square in the barcode). You can explicitly set the DPI or scale the image after generation:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Or, after saving, resize with System.Drawing if you need a thumbnail.

### Handling special characters

PDF417 supports the full ASCII set. If your data contains Unicode characters, ensure you encode the string as UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Step 3: Common pitfalls and how to avoid them

| Pitfall | Symptom | Fix |
|---------|---------|-----|
| Too many columns for the given data | Barcode appears truncated or throws an exception. | Reduce `Columns` or let the library auto‑size by omitting the setting. |
| Low error correction on a noisy printer | Scanners fail to read the barcode intermittently. | Increase `ErrorCorrectionLevel` to at least 2. |
| Saving to a read‑only directory | `UnauthorizedAccessException` at runtime. | Use a writable folder such as `Environment.CurrentDirectory` or `Path.GetTempPath()`. |
| Using an outdated Aspose.BarCode version | Missing properties like `CompactMode`. | Update the NuGet package to the latest stable release. |

---

## Step 4: Verify the result

To confirm that the barcode was generated correctly, you can:

1. Open `CustomPdf417.png` in any image viewer – the barcode should be crisp, with clear black modules on a white background.
2. Use a free PDF417 scanner app (available on iOS and Android) to scan the image. The app should display **“Sample data for PDF417 barcode”**.
3. (Optional) Load the image in a unit test using `System.Drawing.Bitmap` and assert that the pixel at `(0,0)` is black, confirming that the image is not empty.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

If the assertion passes, you’ve successfully **create barcode image** and **generate PDF417 barcode** programmatically.

---

## Conclusion

You now know how to **create barcode image** in C# by **generating PDF417 barcode** with a custom layout, adjusting error correction, and exporting to PNG. The complete example demonstrates every required step—from initializing `BarcodeGenerator` to saving the final image—so you can copy, paste, and run it in your own project.

Next, you might explore:

* **Embedding the PNG in a web API** so clients can request barcodes on demand (`generate pdf417` as a service).
* **Batch generation** for large data sets—loop over a list of strings and store each PNG in a database.
* **Alternative output formats** (SVG, JPEG) by changing `BarCodeImageFormat`.

Feel free to experiment with column/row ratios, error‑correction levels, and image resolution to meet the exact requirements of your scanner hardware or UI design. Happy coding!


## What should you learn next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}