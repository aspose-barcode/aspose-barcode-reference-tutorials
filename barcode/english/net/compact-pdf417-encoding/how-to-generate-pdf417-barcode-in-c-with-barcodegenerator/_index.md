---
category: general
date: 2026-11-20
description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator. This
  step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: en
lastmod: 2026-11-20
og_description: Generate PDF417 barcode in C# quickly. Follow this guide to set dimensions,
  columns, and export the barcode as a PNG image.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Generate PDF417 barcode in C# – complete step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: How to generate PDF417 barcode in C# with BarcodeGenerator
url: /net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate PDF417 barcode in C# with BarcodeGenerator

If you need to **generate PDF417 barcode** in a .NET application, this guide shows you exactly how to do it. You’ll see a complete, runnable example that sets the X‑Dimension, chooses the number of columns, and saves the result as a PNG image.

Generating a PDF417 barcode is common when you have to encode a lot of data—such as a driver's license, boarding pass, or inventory record—into a compact, machine‑readable image. In this tutorial we use the **BarcodeGenerator** class from the Aspose.BarCode library, but the concepts apply to any library that supports PDF417.

By the end of this article you will be able to:

* Initialize a `BarcodeGenerator` for PDF417 encoding.  
* Adjust the module size with **set XDimension pixels**.  
* Control the layout using **configure PDF417 columns**.  
* **Save barcode as PNG** for use in web pages, mobile apps, or printed material.  

> **Prerequisites**  
> * .NET 6.0 or later (the code also works with .NET Framework 4.7+).  
> * A reference to the **Aspose.BarCode** NuGet package (`Install-Package Aspose.BarCode`).  
> * Basic familiarity with C# and Visual Studio (or any IDE you prefer).

---

## How to generate PDF417 barcode in C#

The core of the solution is a short four‑step process. Each step is wrapped in a dedicated method so you can reuse the logic in larger projects.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Why these four steps matter

1. **Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you cannot access any further configuration.  
2. **Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing `XDimension.Pixels` lets you control the barcode’s visual density, which is crucial for readability on low‑resolution displays or printers.  
3. **Configure columns** – PDF417 can arrange its codewords in a variable number of columns. Fewer columns produce a taller barcode, while more columns flatten it. Adjust this to fit the space where the image will be placed.  
4. **Save as PNG** – PNG is a loss‑less format, preserving the sharp edges required for accurate scanning. You could also choose JPEG or BMP, but PNG is the safest default.

---

## Configure barcode dimensions (X‑Dimension)

The **set XDimension pixels** step directly influences how scanners interpret the barcode. If the module is too small, low‑quality cameras may miss individual bars; if it’s too large, the barcode can become unnecessarily big.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Test the generated image at the intended print size. For high‑density printing (300 dpi or more), a value of `1` or `2` works well. For on‑screen display at 96 dpi, `2`–`3` gives a clear visual.

---

## Set PDF417 columns

The **configure PDF417 columns** step lets you decide the barcode’s shape.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### When to change the column count

| Columns | Resulting shape | Typical use case |
|---------|----------------|------------------|
| 1–3     | Tall, narrow   | Labels with limited width |
| 4–9     | Balanced       | General purpose scanning |
| 10+     | Wide, short    | Large signage or web graphics |

If your data payload exceeds the default capacity, the library automatically adds extra rows, but you can still influence the aspect ratio by tweaking the column count.

---

## Export barcode to PNG

Saving the barcode as a PNG image is straightforward:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Why PNG?**  
* Lossless compression retains the crisp edges needed for barcode readers.  
* PNG supports transparency, which can be useful if you overlay the barcode on a colored background later.

If you need a different format, replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`—the API handles the conversion automatically.

---

## Common pitfalls and troubleshooting

| Issue | Likely cause | Fix |
|-------|--------------|-----|
| Barcode appears blurry | X‑Dimension too small for the output resolution | Increase `XDimension.Pixels` to 3 or 4. |
| Scanner cannot read the code | Unicode characters not supported by the chosen font | Ensure the library’s font supports the characters, or replace them with ASCII equivalents. |
| Output file not created | Invalid path or missing write permissions | Use an absolute path and verify folder write access. |
| Too many rows, barcode becomes tall | Column count too low for the data length | Raise `Pdf417.Columns` to a higher number (e.g., 6). |

---

## Full working example recap

Below is the **complete program** you can copy‑paste into a new console project. No additional code is required beyond the `using` statements and the Aspose.BarCode package.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Expected output:** A file named `Pdf417Basic.png` containing a clear PDF417 barcode that encodes the string `Åspóse.Barcóde©`. When opened, the image should show a series of stacked rectangular bars with a higher‑density left side (due to the three‑column layout).

---

## Conclusion

You now know how to **generate PDF417 barcode** in C# using the `BarcodeGenerator` class. The tutorial covered initializing the generator, **set XDimension pixels**, **configure PDF417 columns**, and **save barcode as PNG**—the essential steps for any production‑ready barcode workflow.

From here you can:

* Experiment with different `EncodeTypes` (e.g., QR, Code128).  
* Add error‑correction levels via `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Render the barcode directly to a `MemoryStream` for web APIs.  

Feel free to adapt the code to your own project, and share your results in the comments or on Stack Overflow using the `#pdf417` tag. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate PDF417 barcode as PNG in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}