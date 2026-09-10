---
category: general
date: 2026-09-10
description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417 and
  how to change barcode size with Aspose.BarCode in just a few lines.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: en
lastmod: 2026-09-10
og_description: Generate PDF417 barcode in C# instantly. This tutorial shows how to
  generate PDF417 and how to change barcode size using Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Generate PDF417 barcode in C# – complete programming guide
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: How to generate PDF417 barcode in C# – step‑by‑step guide
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode in C# – step‑by‑step guide

If you need to **generate PDF417 barcode** in a .NET application, this guide shows you exactly how to do it. You’ll see a concise, ready‑to‑run example that creates a PDF417 barcode, lets you control its size, and saves the result as a PNG image.

Generating a PDF417 barcode is a common requirement for inventory systems, boarding passes, and document tracking. In this tutorial we also cover **how to change barcode size** so the code adapts to different printing or screen‑display needs.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later (the code also works with .NET Framework 4.6+)
* Visual Studio 2022 or any C# IDE
* The **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Basic familiarity with C# console applications

## Project setup

1. Create a new console project:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Add the Aspose.BarCode reference (see prerequisites).  

3. Open `Program.cs` and replace its content with the full example below.

## Step 1: Generate PDF417 barcode

The first step is to create a `BarcodeGenerator` instance configured for the **PDF417** symbology. This object is the entry point for all barcode operations.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Why this matters* – The `EncodeTypes.Pdf417` enum value tells Aspose.BarCode to use the PDF417 standard, while the second argument supplies the data that will be encoded. The generator now holds a full barcode object that you can customize before saving.

## Step 2: How to change barcode size (module size)

PDF417 barcodes consist of small square modules. Adjusting the module size changes the overall dimensions of the image without altering the encoded data.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Why this matters* – A larger `XDimension` yields a bigger barcode suitable for high‑resolution printing; a smaller value is better for on‑screen display. The default is usually 1 px, which can look cramped on modern monitors.

## Step 3: Configure layout – columns and rows

PDF417 allows you to define the number of columns and rows, which influences both the barcode’s shape and its error‑correction capacity.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Why this matters* – More columns make the barcode wider, while more rows make it taller. Adjust these values to fit the available space in your UI or printed label.

## Step 4: Save the barcode image

Finally, write the barcode to a file. Here we use PNG because it preserves crisp edges and supports transparency.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Running the program creates `LayoutPdf417.png` in the project’s output folder. The image will look like this:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="generate PDF417 barcode example showing 4 columns and 9 rows"}

*Tip*: If you need a different image format (JPEG, BMP, TIFF), replace `BarCodeImageFormat.Png` with the appropriate enum value.

## How to generate PDF417 – alternative data sources

The code above uses a hard‑coded string `"Layout test"`. In real‑world scenarios you often pull data from a database, a file, or user input.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

The rest of the steps (size, layout, saving) remain unchanged. This demonstrates **how to generate PDF417** from dynamic sources without additional complexity.

## Common pitfalls and how to avoid them

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode appears blurry | `XDimension` set too low for the output resolution | Increase `XDimension.Pixels` or save as a vector format like SVG (`BarCodeImageFormat.Svg`) |
| Text does not fit in the chosen layout | Too many characters for the selected rows/columns | Reduce the number of rows/columns or split the data into multiple barcodes |
| Image file not created | Output folder does not exist or write permissions missing | Ensure the directory exists (`Directory.CreateDirectory`) and the app runs with proper rights |

## Verifying the barcode

After generating the image, you can verify it using any PDF417 scanner app (mobile phones have free scanners) or the built‑in Aspose.BarCode reader:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

If the output matches the original text, the **generate PDF417 barcode** process succeeded.

## Full, runnable example

Below is the complete program you can copy‑paste into `Program.cs`. It includes all using directives, error handling, and comments.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Running this program prints:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

You now have a **complete, self‑contained solution** for generating PDF417 barcodes and controlling their size.

## Conclusion

In this tutorial you learned how to **generate PDF417 barcode** in C# using Aspose.BarCode, how to **change barcode size** by adjusting the X‑dimension, and how to configure columns and rows for layout control. You also saw how to verify the result programmatically and how to adapt the code for dynamic data.

Next, you might explore:

* **How to generate PDF417** with error‑correction level tuning (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Exporting to **vector formats** (SVG, EPS) for infinite scaling
* Embedding the barcode in a PDF document with **Aspose.PDF**

Experiment with different module sizes and layout options to fit your specific UI or printing requirements. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}