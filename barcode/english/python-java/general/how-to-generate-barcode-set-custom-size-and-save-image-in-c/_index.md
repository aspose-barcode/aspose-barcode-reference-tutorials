---
category: general
date: 2026-09-13
description: Learn how to generate barcode in C#, customize barcode size, and save
  barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: en
lastmod: 2026-09-13
og_description: How to generate barcode in C# with custom barcode size and save barcode
  image as PNG. Follow this complete guide for Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: How to generate barcode, set custom size, and save image in C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: How to generate barcode set custom size and save image in C#
url: /python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode set custom size and save image in C#

If you need to **how to generate barcode** in a .NET application, this tutorial shows you a complete solution. You’ll see how to adjust the **custom barcode size** and **save barcode image** files with just a few lines of C# code.

Generating barcodes is a common requirement for inventory systems, shipping labels, and point‑of‑sale applications. By the end of this guide you will have a runnable program that creates two DataBar‑Stacked‑Omnidirectional barcodes, each with a different aspect ratio, and writes them to PNG files on disk.

**Prerequisites**

- .NET 6.0 or later (the code also works with .NET Framework 4.7+)
- Visual Studio 2022 or any C# IDE
- Aspose.BarCode for .NET (free trial or licensed NuGet package)

---

## How to generate barcode with Aspose.BarCode

The Aspose.BarCode library abstracts the low‑level details of barcode standards, letting you focus on the data you want to encode and the visual appearance you need.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Why each line matters

| Step | Explanation |
|------|-------------|
| **1️⃣ Create a generator** | The `EncodeTypes.DatabarStackedOmniDirectional` enum tells Aspose which barcode symbology to use. The string `"(01)12345678901231"` follows the GS1‑128 data format, where `(01)` is the Application Identifier for a GTIN. |
| **2️⃣ Set X‑dimension** | `XDimension.Pixels` defines the width of a single barcode module (the smallest bar). Changing this value is the primary way to achieve a **custom barcode size** without altering the encoded data. |
| **3️⃣ Set aspect ratio & save** | `DataBar.AspectRatio` controls the height‑to‑width ratio of DataBar symbols. An aspect ratio of 15 produces a relatively short, wide barcode, while 30 makes it taller. `Save` writes the visual representation to a PNG file, satisfying the **save barcode image** requirement. |
| **4️⃣ Change aspect ratio & save again** | Re‑using the same generator instance lets you produce multiple images with different visual characteristics while keeping the data constant. |

---

## Adjusting custom barcode size beyond X‑dimension

While `XDimension.Pixels` sets the module width, you can also fine‑tune the barcode’s overall dimensions by combining two properties:

1. **`BarHeight`** – explicit height in pixels.  
2. **`BarWidth`** – explicit width in pixels (overrides X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** When printing barcodes, always test the generated image at the final print size. A module width of 2 px works for on‑screen display, but printed labels often need at least 4 px to stay scannable.

---

## Choosing the right image format for saving barcode image

Aspose.BarCode supports PNG, JPEG, BMP, GIF, and TIFF. PNG is lossless and preserves crisp edges, making it the safest choice for most applications. If you need a smaller file for web use, JPEG with a quality setting of 90 works well, but be aware that compression artifacts can affect scan reliability.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Full, runnable example

Below is a self‑contained console application that you can copy, paste, and run. It demonstrates **how to generate barcode**, modify **custom barcode size**, and **save barcode image** in two different formats.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Expected output on the console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

The four image files will appear in the program


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}