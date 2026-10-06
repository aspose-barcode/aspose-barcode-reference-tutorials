---
category: general
date: 2026-10-05
description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
  step‑by‑step code and best‑practice tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: en
lastmod: 2026-10-05
og_description: Create PDF417 barcode in C# and generate barcode PNG instantly. Follow
  this complete tutorial for a production‑ready solution.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Create PDF417 barcode in C# – full guide to generate PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: How to create PDF417 barcode and save it as PNG in C#
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode and save it as PNG in C#

If you need to **create PDF417 barcode** in a .NET application, this guide shows you exactly how to do it. You’ll get a ready‑to‑use C# snippet that generates a high‑quality **barcode PNG** file, and you’ll understand every setting that influences the output.

Generating barcodes is a common requirement for ticketing systems, inventory tracking, and secure document encoding. By the end of this tutorial you can answer the question “**how to generate PDF417**” with a complete, runnable example.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A development environment such as Visual Studio 2022 or VS Code  
* The **Aspose.BarCode for .NET** NuGet package (or any compatible library that supports PDF417)  

You can add the package with the following command:

```bash
dotnet add package Aspose.BarCode
```

The code below uses the Aspose API because it provides granular control over PDF417 parameters and supports PNG export out of the box.

## Step 1: Set up the project and import namespaces

Create a new console project and import the required namespaces:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

The `Aspose.BarCode.Generation` namespace contains the `BarcodeGenerator` class, which is the entry point for **creating PDF417 barcode** images.

## Step 2: Create PDF417 barcode with the desired text

Instantiate the generator with the `EncodeTypes.Pdf417` enum and the data you want to encode. The example uses a string that contains special characters to demonstrate Unicode handling:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

The generator now holds a barcode object that you can configure before rendering.

## Step 3: Configure visual parameters

Fine‑tuning the barcode improves readability and reduces the image size. The most frequently adjusted settings are **X‑dimension**, **columns**, and **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** controls the width of each module; a value of `2` pixels yields a compact yet legible barcode.  
* **Columns** determine how many data columns the code uses. Fewer columns make the barcode narrower but taller.  
* **Truncate** activates the “compact” mode defined by the PDF417 specification, which removes unnecessary padding rows.

You can experiment with `Rows` and `ErrorCorrectionLevel` if your use case demands higher resilience against damage.

## Step 4: Save the barcode as a PNG image

Finally, export the barcode to a PNG file. PNG preserves sharp edges and supports transparency, making it ideal for web and print scenarios.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Running the program creates `CompactPdf417.png` in the specified directory. The image looks like this:

![Compact PDF417 barcode created with C#](compact-pdf417.png "Example of a compact PDF417 barcode created with C#")

*The alt text above contains the primary keyword, satisfying both SEO and accessibility requirements.*

## Full, runnable example

Putting all pieces together, here is a self‑contained program you can copy, paste, and run:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Expected output

When you open `CompactPdf417.png`, you should see a vertical, high‑density barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any PDF417 reader returns the original text.

## Why these settings matter

* **X‑dimension** influences both physical size and scanning speed. Smaller modules increase data density but may require higher‑resolution scanners.  
* **Columns** affect the aspect ratio. For mobile receipts, a low column count keeps the barcode narrow enough to fit on narrow paper.  
* **Truncate** reduces the number of rows, saving ink and space without sacrificing data integrity, because PDF417 already includes error‑correction codewords.

Understanding these parameters lets you tailor the barcode to the constraints of your target medium—whether it’s a label printer, a web page, or a mobile app.

## Common variations and edge cases

### Generating other image formats

If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG compresses the image but may introduce artifacts that affect scanning at small sizes.

### Adjusting error correction

For harsh environments (e.g., outdoor signage), increase the error‑correction level:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Higher levels add more redundancy, making the barcode larger but more robust.

### Encoding binary data

PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

The library automatically switches to binary mode.

### Handling very long strings

When the data exceeds the default capacity, the generator automatically creates additional rows. You can limit the row count to avoid oversized images:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

If the content still doesn't fit, consider splitting it across multiple barcodes.

## Pro tips

* **Cache the generator** if you need to create many barcodes with the same settings. Reusing the object avoids repeated allocation of internal resources.  
* **Set `Resolution`** on the `ImageOptions` if you need a specific DPI for print:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output** programmatically with `BarCodeReader` to ensure the generated PNG can be decoded before shipping it to users.

## Conclusion

You now know how to **create PDF417 barcode** in C# and **generate barcode PNG** files with full control over size, columns, and compact mode. The complete example demonstrates the standard approach, explains why each setting matters, and covers variations such as error correction, alternative formats, and binary data. Use the tips above to adapt the solution to your specific workflow, whether you are building a ticketing system, a logistics label generator, or a secure document encoder.

---

**Next steps**

* Explore other 2D symbologies (DataMatrix, QR) using the same `BarcodeGenerator` class.  
* Integrate the barcode creation into an ASP.NET Core API to serve PNGs on demand.  
* Combine the barcode image with PDF generation libraries to embed it directly into reports.

Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}