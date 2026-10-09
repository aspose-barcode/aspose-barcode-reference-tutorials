---
category: general
date: 2026-09-13
description: Learn how to create pdf417 barcode in C# and generate pdf417 barcode
  images quickly with a complete, runnable example.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- generate pdf417 barcode
- create barcode image c#
language: en
lastmod: 2026-09-13
og_description: Create pdf417 barcode in C# and generate pdf417 barcode images with
  this concise tutorial. Follow the full example and get a PNG file instantly.
og_image_alt: Screenshot of a PDF417 barcode generated in C#
og_title: Create pdf417 barcode in C# – complete programming guide
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create pdf417 barcode in C# and generate pdf417 barcode
    images quickly with a complete, runnable example.
  headline: How to create pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: How to create pdf417 barcode in C# – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create pdf417 barcode in C# – step‑by‑step guide

If you need to **create pdf417 barcode** in a .NET application, this tutorial shows you exactly how to do it. You’ll see how to generate pdf417 barcode images in C# using the Aspose.BarCode library, and you’ll end up with a ready‑to‑use PNG file.

Creating a barcode is a common requirement for inventory systems, ticketing solutions, or document verification. By the end of this guide you will be able to **create pdf417 barcode** images programmatically, customize key parameters such as module width, columns, and rows, and save the result as a PNG without any external tools.

## What you’ll need

- .NET 6.0 or later (the code also works on .NET Framework 4.7+)
- A reference to the **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Basic knowledge of C# syntax and a development environment (Visual Studio, VS Code, or Rider)

## Step 1: Set up the project and import namespaces

Create a new console project (or add the code to an existing one) and import the required namespaces. This step prepares the environment for barcode generation.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enumeration
```

**Why this matters:** Importing `Aspose.BarCode.Generation` gives you access to `BarcodeGenerator`, the class that actually creates the barcode. The `Aspose.BarCode` namespace contains the image format enum you’ll use when you **save the barcode image**.

## Step 2: Initialise the BarcodeGenerator with PDF417 settings

The `BarcodeGenerator` constructor takes two arguments: the barcode symbology (`EncodeTypes.Pdf417`) and the text you want to encode. Here we encode the string `"Layout demo"`.

```csharp
// Step 2: Initialise generator for PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
{
    // All further configuration goes inside this block
```

**Why this matters:** Selecting `EncodeTypes.Pdf417` tells the library to use the PDF417 2‑D symbology, which is ideal for storing large amounts of data and is widely supported in logistics and ID cards.

## Step 3: Configure the X‑dimension (module width)

The X‑dimension controls the width of each individual module (the smallest black or white element). Setting it in pixels gives you precise control over the final image size.

```csharp
    // Step 3: Set module width to 2 pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** A smaller X‑dimension yields a more compact barcode, while a larger value makes the barcode easier to scan at a distance. Adjust this value based on the scanning environment of your application.

## Step 4: Define the layout – columns and rows

PDF417 allows you to specify how many columns and rows the barcode should use. This influences both size and data capacity.

```csharp
    // Step 4: Define layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // Number of data columns
    barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // Number of rows (height)
```

**Why this matters:** Controlling columns and rows lets you fine‑tune the barcode for specific label dimensions or printing constraints. Too many rows can make the barcode too tall; too few columns may reduce data capacity.

## Step 5: Save the barcode as a PNG image

Finally, write the generated barcode to disk. The `Save` method accepts the output path and the desired image format.

```csharp
    // Step 5: Save as PNG
    barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
}
```

When you run the program, a file named **LayoutPdf417.png** appears in the output directory. Opening the file shows a clean PDF417 barcode that encodes the text `"Layout demo"`.

### Expected output

![Screenshot of a PDF417 barcode generated in C#](placeholder-image.png "PDF417 barcode created with C#")

*Image alt text:* **Screenshot of a PDF417 barcode generated in C#** (matches `og_image_alt` for accessibility).

## Full, runnable example

Putting all the pieces together, here is a self‑contained console application you can copy, paste, and run.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise generator for PDF417 with the desired text
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo"))
            {
                // Set the X‑dimension (module width) in pixels
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Define layout: 4 columns and 9 rows
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
                barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

                // Save the generated barcode as a PNG image
                barcodeGenerator.Save("LayoutPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode created successfully: LayoutPdf417.png");
        }
    }
}
```

**How to verify:** After running the program, navigate to the folder containing the compiled binary. You should see `LayoutPdf417.png`. Open it with any image viewer; the barcode should be clearly visible and scannable with standard PDF417 readers.

## Common variations and edge cases

| Situation | What to change | Why |
|-----------|----------------|-----|
| **Higher data density** | Increase `Columns` (e.g., to 6) and optionally reduce `Rows` | More columns pack more data horizontally, useful for narrow labels. |
| **Large print area** | Increase `XDimension.Pixels` (e.g., to 4) | Larger modules make the barcode easier to scan from a distance. |
| **Different image format** | Use `BarCodeImageFormat.Jpeg` or `Bmp` in the `Save` call | Choose a format that matches your downstream processing pipeline. |
| **Custom foreground/background colors** | Set `barcodeGenerator.Parameters.Barcode.ForeColor` and `BackColor` | Improves readability on colored backgrounds or when printing on dark media. |
| **Encoding Unicode characters** | Pass a Unicode string (e.g., `"Пример"`). PDF417 supports Unicode out‑of‑the‑box. | Allows international text without extra configuration. |

**Pro tip:** Always test the generated barcode with the actual scanner hardware you plan to use. Some scanners have minimum module size requirements; adjusting `XDimension` accordingly prevents read errors.

## Frequently asked questions

**Q: Does this work with .NET Core?**  
Yes. The `Aspose.BarCode` package targets .NET Standard 2.0, which is compatible with .NET Core, .NET 5+, and .NET Framework.

**Q: Can I generate multiple barcodes in a loop?**  
Absolutely. Place the `using` block inside a `foreach` loop and change the text or layout parameters for each iteration.

**Q: What if I need to embed the barcode in a PDF?**  
After generating the PNG, you can load it into a PDF library (e.g., iText7 or Aspose.PDF) and place it on a page. The barcode generation step remains the same.

## Conclusion

You now know how to **create pdf417 barcode** images in C# using Aspose.BarCode. The tutorial covered initializing the generator, configuring the X‑dimension, setting columns and rows, and saving the result as a PNG file. With this foundation you can **generate pdf417 barcode** graphics for inventory tags, boarding passes, or any scenario that requires compact, high‑capacity 2‑D barcodes.

Next, try **create barcode image c#** for other symbologies such as QR, Code‑128, or DataMatrix by swapping `EncodeTypes.Pdf417` with the desired type. Experiment with colors, error correction levels, and embedding the image directly into PDFs or reports to extend the solution further.

Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Create PDF417 Barcode in C# – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}