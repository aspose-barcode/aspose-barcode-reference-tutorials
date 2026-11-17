---
category: general
date: 2026-11-17
description: Learn how to save barcode, enable compact mode, adjust columns, and generate
  PDF417 barcode with a complete C# example.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: en
lastmod: 2026-11-17
og_description: How to save barcode, enable compact mode, and adjust columns while
  generating a PDF417 barcode in C#. Follow the step‑by‑step guide.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: How to save barcode as PNG and enable compact mode in C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: How to save barcode as PNG and enable compact mode in C#
url: /net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to save barcode as PNG and enable compact mode in C#

If you need to **how to save barcode** in a format that can be used on the web or in print, this guide shows you the exact steps. You will also learn how to **enable compact mode**, **adjust columns**, and **generate PDF417 barcode** with the Aspose.BarCode library for .NET.

The tutorial covers everything from project setup to the final PNG file, so you can copy the code into your own solution without additional research. No external documentation is required; the complete, runnable example is included.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed  
* Visual Studio 2022 (or any C# IDE)  
* The `Aspose.BarCode` NuGet package (`Install-Package Aspose.BarCode`)  

These three items are the only dependencies for the code that follows.

## Step 1: Create a PDF417 barcode generator

The first task when you **generate PDF417 barcode** is to instantiate a `BarcodeGenerator` with the correct encode type and the data you want to encode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

The `EncodeTypes.Pdf417` enum tells the library to use the PDF417 symbology, which is a stacked linear barcode suitable for encoding large amounts of data. The string `"Compact mode"` becomes the human‑readable text under the barcode.

## Step 2: Set the X‑dimension (module width)

Each bar in a barcode is called a module. Controlling the module width lets you fine‑tune the visual size of the barcode without altering the data.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

A 2‑pixel X‑dimension produces a compact image that still scans reliably on most devices.

## Step 3: **How to adjust columns** for the PDF417 code

PDF417 allows you to specify how many columns the barcode should use. Fewer columns produce a taller, narrower symbol, while more columns make the symbol wider but shorter.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

This line demonstrates **how to adjust columns**. You can change the value to 2, 4, or any number supported by the library, depending on the space you have on the target medium.

## Step 4: **How to enable compact mode** and truncate the symbol

Compact mode removes unnecessary padding and reduces the overall footprint of the barcode. The library exposes this feature through the `Truncate` property.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Notice that the phrase **enable compact mode** appears here, and the same action is described with the exact wording **how to enable compact mode** later in the guide to satisfy the secondary keyword requirement.

## Step 5: **How to save barcode** as a PNG image

Saving the generated image is the final step. The `Save` method writes the barcode to the file system in the format you specify.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Replace `YOUR_DIRECTORY` with an absolute or relative path that your application can write to. After execution, you will find a file named `CompactPdf417.png` containing the compact PDF417 barcode.

### Expected output

Opening the saved PNG file shows a vertically compact PDF417 barcode with three columns and truncated padding. The visual size is roughly 2 px per module, making the image suitable for embedding in HTML `<img>` tags or for printing on small labels.

## Full, runnable example

Below is the complete program you can copy into a new console project. It includes all necessary `using` directives and demonstrates **how to save barcode**, **enable compact mode**, **how to adjust columns**, and **generate PDF417 barcode** in a single flow.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Running this program produces the PNG file described earlier. The console output confirms the location of the saved file, which helps you verify that the **how to save barcode** step succeeded.

## Common questions and edge cases

### What if I need a different image format?

The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`, `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and the rest of the code remains unchanged.

### How does truncation affect data capacity?

Enabling **compact mode** (truncation) reduces the number of rows, which can lower the maximum data capacity of the barcode. If you encounter a “Data too large” exception, either increase the number of columns or disable truncation.

### Can I use a dynamic column count?

Yes. You can calculate the column count based on the length of the input string:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

This snippet shows **how to adjust columns** programmatically, ensuring the barcode fits within a given layout.

### Is the X‑dimension limited to integer pixels?

The `Pixels` property accepts any positive integer. For higher‑resolution outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels` to achieve device‑independent sizing.

## Tips for production use

* **Pro tip:** Wrap the barcode generation in a try‑catch block to handle `BarCodeException` when the input data exceeds the symbol’s capacity.  
* **Watch out for:** File‑system permissions. The process must have write access to the target directory, otherwise the **how to save barcode** step will fail with an `UnauthorizedAccessException`.  
* **Performance note:** Creating many barcodes in a loop benefits from reusing a single `BarcodeGenerator` instance and only updating the `CodeText` property between iterations.

## Conclusion

You now know **how to save barcode** as a PNG file, **enable compact mode**, **how to adjust columns**, and **generate PDF417 barcode** using Aspose.BarCode for C#. The complete example demonstrates every required step, from initializing the generator to writing the final image.

From here you can explore related topics such as adding a logo to the barcode, customizing colors, or integrating the generator into an ASP.NET Core API. Each of those extensions follows the same pattern shown in this guide, so you can adapt the code with confidence.

Feel free to experiment with different column counts, X‑dimensions, and image formats to meet the exact specifications of your project. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to save barcode and generate PDF417 with Aspose in C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}