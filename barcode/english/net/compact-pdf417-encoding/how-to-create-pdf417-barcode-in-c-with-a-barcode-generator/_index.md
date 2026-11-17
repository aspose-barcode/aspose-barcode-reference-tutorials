---
category: general
date: 2026-11-17
description: Learn how to create PDF417 barcode in C# – a complete guide on how to
  generate barcode from string using a C# barcode generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: en
lastmod: 2026-11-17
og_description: Create PDF417 barcode in C# quickly. This tutorial shows how to generate
  barcode from string with a C# barcode generator and includes full source code.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Create PDF417 barcode in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: How to create PDF417 barcode in C# with a barcode generator
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode in C# with a barcode generator

If you need to **create PDF417 barcode** in a .NET application, this guide shows exactly how to do it. You’ll learn **how to generate barcode** from a plain string, configure the symbol size, and save the result as a PNG file—all using a reliable C# barcode generator.

Generating barcodes programmatically removes manual steps and guarantees consistent quality. In this tutorial we’ll cover everything from project setup to the final image, so you can integrate barcode creation into any C# solution today.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code works with .NET Core and .NET Framework)
* Visual Studio 2022 (or any IDE that supports C#)
* A license or free trial of **Aspose.BarCode for .NET** – the library used in the examples
* Basic familiarity with C# syntax

No additional packages are required; the NuGet package `Aspose.BarCode` contains all the classes you’ll need.

## Step 1 – Set up the C# barcode generator

The first thing you do when you **create PDF417 barcode** is instantiate a `BarcodeGenerator` object. This object represents the **c# barcode generator** that will handle encoding, rendering, and saving.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Why this matters*: The `EncodeTypes.Pdf417` enum tells the library to use the PDF417 symbology, which is the same standard used for identification cards and transport labels. The string `"(01)12345678901234"` is a **generate barcode from string** example that also demonstrates how to **create GS1 barcode** data.

## Step 2 – Configure the X‑dimension (module width)

The X‑dimension controls the width of the smallest bar (module). A common value for on‑screen rendering is 2 units.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 (units)
        barcodeGenerator.Parameters.Barcode.XDimension = 2;
```

Setting the X‑dimension explicitly prevents the generator from using its default, which might produce a barcode that is too small for some scanners.

## Step 3 – Define the number of columns

PDF417 allows you to adjust the number of columns, affecting both the barcode’s shape and data capacity. For a compact label, four columns work well.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

If you need a taller barcode, increase the column count; the library will automatically calculate the required rows.

## Step 4 – Save the barcode as an image

Finally, export the barcode to a PNG file. PNG preserves crisp edges and supports transparency.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Running the program creates `output/Gs1Pdf417.png`. Open the file in any image viewer—you’ll see a clean **PDF417 barcode** that encodes the GS1 data you supplied.

### Expected output

![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}

*The image above demonstrates the result of the complete code sample. The barcode can be scanned by any PDF417‑compatible reader.*

## Additional options and common variations

### Changing the image format

If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.

### Adjusting error correction level

PDF417 supports error correction levels 0‑8. Higher levels increase redundancy but also enlarge the barcode.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Generating other GS1 barcodes

The same `BarcodeGenerator` can produce **create GS1 barcode** for other symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just swap the enum value:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Handling empty or null data

When you **generate barcode from string**, always validate the input:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

This prevents runtime exceptions and ensures the barcode complies with GS1 formatting rules.

## Complete, runnable example

Below is the full program you can copy‑paste into a new console project. It includes all necessary `using` directives, folder creation, and error handling.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Run the program** (`dotnet run`) and you’ll find `Gs1Pdf417.png` inside the *output* folder. Scan it with any PDF417 reader to verify that the GTIN `(01)12345678901234` is correctly encoded.

## Frequently asked questions

**Q: Can I use this code on .NET Framework 4.6?**  
A: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible with .NET Framework 4.6 and later.

**Q: What if I need a higher‑resolution image?**  
A: Set the `Resolution` property before saving:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**Q: Is the barcode still valid without the GS1 Application Identifier?**  
A: It will be a standard PDF417 barcode, but it won’t be recognized as a GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode** compliance.

## Conclusion

You now know how to **create PDF417 barcode** in C# using a robust **c# barcode generator**. The tutorial covered:

* Instantiating `BarcodeGenerator` with GS1 data  
* Configuring X‑dimension and column count  
* Saving the result as a PNG image  
* Extending the solution with error correction, different formats, and input validation  

With this foundation you can generate any PDF417 or GS1 barcode directly from a string, embed it in reports, or send it to printers. Explore the Aspose.BarCode API to add colors, add margins, or combine multiple barcodes into a single image.

**Next steps**: try generating a **create GS1 barcode** for DataMatrix, experiment with dynamic column calculations, or integrate the generator into an ASP.NET Core web service that returns barcode images on demand.

Happy coding!


## What should you learn next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}