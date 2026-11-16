---
category: general
date: 2026-11-14
description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
  how to generate PDF417 and how to customize PDF417 settings for precise control.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: en
lastmod: 2026-11-14
og_description: Create PDF417 barcode in C# with step‑by‑step instructions. Learn
  how to generate PDF417 and how to customize PDF417 parameters for exact results.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Create PDF417 barcode in C# – full guide with custom layout
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Create a PDF417 barcode with custom layout in C# using Aspose.BarCode
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode with custom layout in C#

If you need to **create pdf417 barcode** for a ticketing system, inventory tag, or mobile‑app scan, this tutorial shows the complete process. You’ll see how to generate PDF417 quickly and how to customize PDF417 settings such as columns and rows, so the barcode fits your design constraints.

Generating a barcode doesn’t require a complex graphics library—just the Aspose.BarCode for .NET (or any compatible API). By the end of this guide you’ll have a ready‑to‑use PNG file that you can embed in PDFs, web pages, or print directly from your application.

## Prerequisites

- .NET 6.0 or later (the code also works with .NET Framework 4.7+)
- Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`)
- Basic familiarity with C# and Visual Studio (or any IDE)

> **Pro tip:** If you’re using a CI/CD pipeline, add the NuGet package reference in your project file so builds stay reproducible.

## Step 1: Install the barcode library

Open your project folder in a terminal and run:

```bash
dotnet add package Aspose.BarCode
```

The package includes the `BarcodeGenerator` class used throughout this tutorial. No additional native dependencies are required.

## Step 2: Create a basic PDF417 barcode

The first goal is to **create pdf417 barcode** with default settings. The following program sets up the generator, encodes a sample string, and saves the result as a PNG image.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Why this works:**  
`EncodeTypes.Pdf417` tells the library to use the PDF417 symbology. The constructor automatically creates a `Barcode` object with default column/row values that guarantee scannability for most use cases.

Run the program (`dotnet run`). You’ll find `Pdf417Default.png` in the project folder. Opening the image shows a standard PDF417 barcode ready for scanning.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Create PDF417 barcode example showing default layout"}

## Step 3: How to generate PDF417 with custom dimensions

Sometimes a fixed‑size label or a UI component requires a specific barcode footprint. That’s where **how to generate pdf417** with custom columns and rows becomes essential.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Why you might want this:**  
- **Limited width:** Reducing columns and increasing rows creates a wider but shorter barcode, perfect for narrow labels.  
- **Limited height:** Increasing columns and decreasing rows yields a taller, narrower barcode, useful when you have vertical space.

Both `Columns` and `Rows` accept only values inside the documented ranges (2‑30 for columns, 1‑90 for rows). Supplying an out‑of‑range value throws an `ArgumentOutOfRangeException`, so always validate user input if you expose these settings in a UI.

## Step 4: How to customize PDF417 further

Beyond columns and rows, the PDF417 symbology offers many optional parameters:

| Property | Purpose | Typical values |
|----------|---------|----------------|
| `ErrorLevel` | Controls error‑correction capability | 0‑8 (higher = more robust) |
| `MacroPdf417` | Enables macro PDF417 for multi‑segment data | `true`/`false` |
| `CompactPdf417` | Produces a more compact barcode at the cost of reduced error correction | `true`/`false` |
| `SecurityLevel` | Adds a security check digit | 0‑2 |

Here’s a quick example that also sets the error level to the maximum (8) for a noisy environment:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Why it matters:**  
Higher error correction allows scanners to recover data even if part of the barcode is damaged. However, it also increases the barcode size, so balance the setting against your layout constraints.

## Step 5: Verify the barcode works

After generating the PNG, test it with any barcode scanner app (most smartphones have free PDF417 readers). If the scanner returns the original text (`Custom layout text`), the barcode is valid.

If you encounter scanning issues:

1. **Check dimensions:** Ensure columns/rows stay within the allowed range.  
2. **Adjust error level:** Increase `ErrorLevel` for damaged media.  
3. **Review image quality:** Save with a higher DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) if you plan to print.

## Full source code for a reusable helper

Below is a compact, reusable class you can drop into any .NET project. It encapsulates **how to generate pdf417** and **how to customize pdf417** in a single method.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

You can call this helper like:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

The method abstracts away the repetitive boiler‑plate, letting you focus on business logic.

## Common pitfalls and how to avoid them

- **Out‑of‑range values:** Always validate `columns` and `rows` before assigning them.  
- **Incorrect image format:** Some legacy scanners only accept BMP or JPEG. Use `BarCodeImageFormat.Bmp` if needed.  
- **Low DPI for print:** The default DPI is 96. For high‑quality prints, explicitly set a higher DPI (e.g., 300) when calling `Save`.  
- **Missing font support:** PDF417 encodes binary data, so you generally don’t need to specify a font. However, if you overlay text on the image, ensure the font is installed on the target machine.

## Conclusion

You now know how to **create pdf417 barcode** from start to finish, how to **generate pdf417** with custom column/row settings, and how to **customize pdf417** for error correction and compactness. By following the reusable helper pattern you can generate barcodes on demand, adapt them to any layout constraint, and guarantee reliable scanning in production environments.

**Next steps**

- Explore other symbologies such as QR or Code128 using the same `BarcodeGenerator` class.  
- Combine the PNG output with a PDF generation library (e.g., iText7) to embed barcodes in invoices.  
- Experiment with `MacroPdf417` for multi‑segment data transmission, a feature useful in logistics and transport applications.

Happy coding, and may your barcodes always scan on the first try!


## What should you learn next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}