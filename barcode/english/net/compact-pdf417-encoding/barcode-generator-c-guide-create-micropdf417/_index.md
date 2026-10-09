---
category: general
date: 2026-09-29
description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
  change dimensions, set columns, and customize barcode size in just a few lines.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: en
lastmod: 2026-09-29
og_description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
  change dimensions, set columns, and customize barcode size in just a few lines.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Barcode generator C# guide – create and customize MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Barcode generator C# guide: create MicroPdf417'
url: /net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# guide: create MicroPdf417

If you need a **barcode generator C#** for your .NET project, this tutorial walks you through creating a MicroPdf417 barcode from scratch. You’ll learn **how to generate barcode**, change dimensions, set columns, and **customize barcode size** effortlessly.

MicroPdf417 is a compact 2‑D symbology that works well for labeling small parts, tickets, or inventory tags. By the end of this guide you will have a complete, runnable console application that outputs a PNG image of the barcode, and you’ll understand how each parameter influences the final size.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later (the code also works with .NET Framework 4.7+)
* A C#‑compatible IDE (Visual Studio, VS Code, Rider, etc.)
* The **GroupDocs.Barcode** NuGet package – install it with  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

No additional external tools are required; the library handles encoding, rendering, and file saving.

## Barcode generator C#: initializing the generator

The first step is to create an instance of `BarcodeGenerator` and specify the symbology (`EncodeTypes.MicroPdf417`) together with the data you want to encode.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Why this matters:**  
`BarcodeGenerator` is the entry point for all barcode operations. The constructor binds the chosen **EncodeTypes** (MicroPdf417) to the raw data string. The library automatically handles Unicode characters like “Å” and “©”, so you don’t need extra encoding logic.

## How to change dimensions of the barcode

A barcode’s readability depends heavily on the module width (the X‑dimension). Setting it to a larger pixel count makes the bars wider and the image easier to scan, especially on low‑resolution displays.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Explanation:**  
`XDimension.Pixels` controls the width of a single barcode module. The default is 1 pixel, which can appear thin on high‑DPI monitors. Raising it to 2 pixels doubles the overall width without affecting the encoded data.

**Tip:** If you plan to print the barcode at 300 dpi, a value of 3 or 4 pixels often yields the best balance between size and scan reliability.

## How to set columns for size control

MicroPdf417 lets you specify the number of columns (up to 4). Fewer columns produce a taller barcode; more columns make it wider but shorter. Adjusting this value is the primary way to **customize barcode size**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Why this works:**  
The `Pdf417.Columns` property is shared across all PDF417‑based symbologies, including MicroPdf417. Setting it to the maximum (4) spreads the data across the widest possible layout, reducing overall height. If you need a more compact height, lower the column count to 2 or 3.

**Edge case:** When the data string is long, the library may automatically increase rows to accommodate the content, regardless of column count. Keep the payload under 50 characters for predictable sizing.

## Customize barcode size for different outputs

Beyond X‑dimension and columns, you can influence the final image size by selecting an appropriate image format and DPI. PNG is lossless, perfect for web display, while BMP or TIFF may be preferable for high‑quality printing.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

If you need a higher DPI, you can set it explicitly:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Result:** The saved PNG file contains a crisp MicroPdf417 barcode that respects the dimensions you configured. Open the file in any image viewer to verify the visual size.

### Expected output

Running the program produces a file named **MicroPdf417.png** (or **MicroPdf417_300dpi.png** if you set DPI). The barcode will look similar to the illustration below:

![Barcode generator C# output showing a MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *Barcode generator C# output showing a MicroPdf417 PNG*

Scanning the image with a standard 2‑D barcode reader returns the original string `Åspóse.Barcóde©`.

## Full source code for quick copy‑paste

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Copy the code into a new console project, restore NuGet packages, and run `dotnet run`. The console will confirm the image location, and you’ll see the generated barcode in your project folder.

## Common questions and troubleshooting

| Question | Answer |
|----------|--------|
| **What if the barcode looks blurry?** | Increase `XDimension.Pixels` or the DPI (`Parameters.Image.DpiX/Y`). Both enlarge the modules and improve visual fidelity. |
| **Can I use a different image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff`. PNG remains the safest choice for lossless quality. |
| **My data contains emojis—will they encode?** | MicroPdf417 supports UTF‑8, so most emojis encode correctly. If you encounter errors, verify that the string is properly normalized (`System.Text.Encoding.UTF8`). |
| **How do I generate other symbologies?** | Change `EncodeTypes.MicroPdf417` to any other value from `EncodeTypes` (


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}