---
category: general
date: 2026-11-17
description: Learn how to generate PDF417 barcode, set barcode size, and render barcode
  to image using C#. Complete step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: en
lastmod: 2026-11-17
og_description: Generate PDF417 barcode in C# and render barcode to image. Follow
  this guide to set barcode size and save a PNG file.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: Generate PDF417 barcode and render as PNG – C# guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: How to generate PDF417 barcode and render it as PNG
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode and render it as PNG

If you need to **generate PDF417 barcode** in a .NET application, this tutorial shows you exactly how. You’ll see how to set the barcode size, configure the layout, and **render barcode to image** with just a few lines of C# code.

Generating a PDF417 barcode is common when you want to encode large amounts of data for scanning on mobile devices or printers. By the end of this guide you’ll have a ready‑to‑use PNG file that you can embed in reports, emails, or web pages.

## Prerequisites

Before you start, make sure you have:

- .NET 6.0 SDK or later installed  
- A C# IDE such as Visual Studio 2022 (any editor works)  
- The **Aspose.BarCode for .NET** NuGet package (or any compatible library that provides `BarcodeGenerator`)  

You can add the package with:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a C# console project

First, set up a minimal console application that will host the barcode generation code.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **Pro tip:** Keep the `Main` method short and delegate the heavy lifting to helper methods. This improves readability and makes unit testing easier.

## Step 2: Generate PDF417 barcode with custom size

Now we’ll **generate PDF417 barcode** and specify the module (X‑dimension) size. The X‑dimension controls how wide each tiny square of the barcode is, effectively setting the overall barcode size.

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(Aspose.BarCode.Generation.EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, Aspose.BarCode.Generation.BarCodeImageFormat.Png);
}
```

### Why set the X‑dimension?

The **how to set barcode size** step matters because a too‑small X‑dimension can make the barcode unreadable on low‑resolution scanners, while a too‑large value wastes space. A value of `2` pixels works well for most screen displays and printing scenarios.

## Step 3: Call the generation method from `Main`

Wire everything together by invoking `GeneratePdf417` with your desired text and output location.

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

Running the program creates `LayoutPdf417.png` containing the barcode:

![Generated PDF417 barcode](/images/layout-pdf417.png "PDF417 barcode generated by the tutorial code"){: .align-center alt="Generated PDF417 barcode saved as PNG"}

> **Expected output:** A PNG file of size roughly 200 × 100 px (depending on column/row settings) that displays a clear PDF417 pattern ready for scanning.

## Step 4: Verify the barcode works

To ensure the barcode is valid:

1. Open the PNG file in any image viewer.  
2. Use a smartphone barcode scanning app that supports PDF417 (e.g., Google Lens, QR & Barcode Scanner).  
3. Scan the image; the app should return the text *Layout demo*.

If the scan fails, double‑check the X‑dimension and column/row values—larger modules improve readability on low‑resolution cameras.

## Common variations and edge cases

| Scenario | Adjustment |
|----------|------------|
| **More data** (e.g., a URL) | Increase `Columns` or `Rows` to accommodate extra codewords. |
| **High‑resolution print** | Raise `XDimension.Pixels` to 3‑4 px for sharper bars. |
| **Transparent background** | Use `generator.Save(outputPath, Aspose.BarCode.Generation.BarCodeImageFormat.Png, new Aspose.BarCode.ImageOptions { BackgroundColor = System.Drawing.Color.Transparent })`. |
| **Different image format** | Replace `BarCodeImageFormat.Png` with `Jpeg` or `Bmp` as needed. |

These variations answer the **how to generate PDF417** question for different requirements while keeping the core logic identical.

## Conclusion

You now know how to **generate PDF417 barcode**, **set barcode size**, and **render barcode to image** using C#. The complete, runnable example creates a PNG file that can be embedded anywhere you need a machine‑readable barcode.

Next, explore related topics such as **embedding the PNG in a PDF** (look up *render barcode to PDF*), or **generating other 2‑D barcodes** like QR codes. Adjust the layout parameters to fit your UI design, and experiment with color options for branding.

Happy coding, and let your barcodes do the heavy lifting!


## What should you learn next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}