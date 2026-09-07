---
category: general
date: 2026-09-07
description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
  for precise control. Follow this step‑by‑step guide to create a PNG image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: en
lastmod: 2026-09-07
og_description: Generate PDF417 barcode in C# and learn how to set barcode dimensions.
  This tutorial shows a complete, runnable example.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Generate PDF417 barcode in C# – full guide with dimensions
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: How to generate PDF417 barcode in C# with custom dimensions
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode in C# with custom dimensions

If you need to **generate PDF417 barcode** in a .NET application, this guide shows you exactly how to do it. You’ll see a complete, runnable example that creates a PNG image while letting you control the barcode dimensions.

Generating a PDF417 barcode is a common requirement for inventory systems, boarding passes, and secure documents. In this tutorial you’ll also learn **how to set barcode dimensions** so the output matches your layout needs.

## Prerequisites

Before you start, make sure you have:

- .NET 6.0 SDK or later installed  
- Visual Studio 2022 (or any C#‑compatible IDE)  
- The **Aspose.BarCode for .NET** NuGet package (or any compatible library that supports PDF417)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a PDF417 barcode generator

The first step is to instantiate a `BarcodeGenerator` with the `EncodeTypes.Pdf417` type and the text you want to encode. The generator object holds all settings for the barcode.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Why this matters:** The `EncodeTypes.Pdf417` enum tells the library to use the PDF417 symbology, which supports large data payloads and error correction. The text string can contain Unicode characters, so you can encode international symbols without extra work.

## Step 2: How to set barcode dimensions

Controlling the size of each module (the smallest black/white square) determines the overall image resolution. The `XDimension.Pixels` property sets the pixel width of one module.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Why this matters:** A larger `XDimension` yields a higher‑resolution image, which is useful for printing or scanning from a distance. Conversely, a smaller value reduces file size for web use.

## Step 3: Define the PDF417 layout (columns and rows)

PDF417 allows you to influence the matrix shape by specifying the number of columns and rows. This can affect readability and the physical size of the barcode.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Why this matters:** Adjusting columns and rows lets you fit the barcode into a specific space or meet a scanner’s aspect‑ratio requirements. The library automatically adds padding if the data does not fill the matrix completely.

## Step 4: Save the barcode as a PNG image

Finally, write the generated barcode to a file. PNG preserves lossless quality, making it ideal for further processing.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

When you run the program, `Pdf417Layout.png` appears in the project’s output folder. The image looks like this:

![Generated PDF417 barcode image with custom dimensions](og_image_placeholder.png)

*Image alt text: Generated PDF417 barcode image with custom dimensions*  

**Why this matters:** Saving as PNG ensures that the exact module dimensions you set are retained, which is crucial for downstream scanning applications.

## Complete example in one block

Below is the full program you can copy, paste, and run without modifications (apart from the output path if desired).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Expected output

- **File:** `Pdf417Layout.png` (PNG, lossless)  
- **Dimensions:** Determined by `XDimension` (2 px) × (columns × rows) matrix  
- **Content:** A scannable PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`

## Common questions and edge cases

### What if I need a larger image for printing?

Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution barcode but also increase file size.

### Can I encode more data than the example string?

Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity, the library automatically adds extra rows.

### How does error correction work?

PDF417 includes built‑in error correction. You can adjust its level via:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Higher levels increase robustness at the cost of larger barcodes.

### What if the barcode appears blurry on screen?

Make sure the output image’s DPI matches the display environment. You can set DPI when saving:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Pro tips

- **Pro tip:** Always test the generated barcode with the actual scanner you plan to use. Different devices have varying tolerance for module size and quiet zones.  
- **Watch out for:** Very small `XDimension` values (< 1 px) may render as invisible lines on high‑DPI screens.  
- **Tip for web apps:** Serve the PNG with `Cache-Control: public, max-age=86400` to reduce repeated generation overhead.

## Conclusion

You now know how to **generate PDF417 barcode** in C# and precisely **set barcode dimensions** to fit any requirement. The complete, runnable example demonstrates creating a PNG image with custom column/row layout and module size, ready for printing or digital distribution.

### Next steps

- Explore **how to generate PDF417 barcode** with different image formats (JPEG, BMP).  
- Learn **how to set barcode dimensions** dynamically based on user input or device DPI.  
- Integrate the barcode generation into an ASP.NET Core API to serve barcodes on demand.

Feel free to experiment with other PDF417 settings such as error correction, margins, and color. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Generate PDF417 Barcode in C# – Complete Guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}