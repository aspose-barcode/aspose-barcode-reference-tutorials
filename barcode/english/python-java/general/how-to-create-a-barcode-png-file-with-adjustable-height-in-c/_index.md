---
category: general
date: 2026-08-19
description: Learn how to generate a barcode PNG file in C# and adjust its height,
  covering how to generate barcode images and change barcode height easily.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: en
lastmod: 2026-08-19
og_description: Create a barcode PNG file in C# and learn how to generate barcode
  images, adjust barcode height, and change barcode height for optimal scans.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Create a barcode PNG file in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: How to create a barcode PNG file with adjustable height in C#
url: /python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create a barcode PNG file with adjustable height in C#

If you need to create a **barcode PNG file** in C#, this guide shows you exactly how. You’ll see a complete, runnable example that demonstrates **how to generate barcode** images and how to **adjust barcode height** for different use‑cases.

Generating a barcode PNG file is a common requirement for inventory systems, point‑of‑sale terminals, and any application that must print or display machine‑readable data. By the end of this tutorial you will be able to change the barcode height, save multiple PNG files, and understand the impact of height on scan reliability.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports .NET)  
* The **Aspose.BarCode for .NET** NuGet package (the code sample uses this library)  

You can add the package from the command line:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** The free evaluation version of Aspose.BarCode works for development and testing. For production, obtain a licensed key.

## Install the barcode library

The first step is to reference the library in your project. Add the following `using` directives at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

These namespaces give you access to `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`.

## Create the barcode PNG file

Now we create a `BarcodeGenerator` instance that will output a **barcode PNG file**. The example uses the Databar OmniDirectional symbology, but you can replace `EncodeTypes.DatabarOmniDirectional` with any supported type.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

The string `"(01)12345678901231"` follows the GS1 Application Identifier format for a 14‑digit GTIN. Adjust the data to match your own product identifiers.

## Set the X‑dimension (optional)

The X‑dimension defines the width of a single barcode module. A pixel‑based value gives you precise control over image size.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A value of `2` pixels works well for most screen displays. Increase it if you need a larger barcode when printed.

## Adjust barcode height and save the barcode PNG file

The **BarHeight** property controls the vertical size of the bars. Changing this value lets you **adjust barcode height** without affecting the encoded data.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

The file `DatabarBarHeight30Pixels.png` is now a **barcode PNG file** that is 30 pixels tall.  

To **change barcode height** and create a second image, simply assign a new value and call `Save` again:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

You now have two PNG files—one at 30 px and another at 60 px—demonstrating how to **adjust barcode height** on the fly.

### Why bar height matters

* **Readability:** Scanners expect a minimum height for reliable detection. Too short a barcode may be missed, especially on low‑resolution cameras.
* **Aesthetics:** Matching the barcode height to surrounding design elements creates a cleaner UI.
* **Print constraints:** Some label printers have fixed height slots; adjusting the barcode height ensures it fits.

**Best practice:** Keep the height a multiple of the X‑dimension (e.g., 30 px when X‑dimension is 2 px) to maintain proportion and avoid distortion.

## Complete example

Below is the full, self‑contained program you can paste into a console application and run immediately.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Expected output**

Running the program creates two files in the executable’s working directory:

* `DatabarBarHeight30Pixels.png` – a 30‑pixel‑high barcode PNG file  
* `DatabarBarHeight60Pixels.png` – a 60‑pixel‑high barcode PNG file  

Open either PNG with any image viewer; you’ll see a clear Databar OmniDirectional barcode ready for scanning.

## Edge cases and troubleshooting

| Situation | What to check | Recommended fix |
|-----------|---------------|-----------------|
| Barcode appears blurry | X‑dimension too low for chosen height | Increase `XDimension.Pixels` (e.g., from 2 to 3) |
| Scanner fails on low‑height barcode | Height below scanner’s minimum | Set `BarHeight.Pixels` to at least 30 px (or per scanner specs) |
| PNG file is empty or corrupted | Output path invalid or write permission denied | Use an absolute path or ensure the app has write access |
| Need a different symbology | Current `EncodeTypes` not suitable | Replace `EncodeTypes.DatabarOmniDirectional` with another enum value (e.g., `EncodeTypes.Code128`) |

## Frequently asked questions

**Q: Can I generate other image formats (JPEG, BMP)?**  
A: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, etc.

**Q: How do I embed the PNG in a web page?**  
A: Serve the generated PNG via an HTTP endpoint or convert it to a Base64 string and place it in an `<img>` tag’s `src` attribute.

**Q: Is there a way to set the background color?**  
A: Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any `System.Drawing.Color`).

## Conclusion

You now know how to **generate a barcode PNG file** in C# and precisely **adjust barcode height** to meet scanning or design requirements. By changing the `BarHeight.Pixels` property you can **change barcode height** on the fly and produce multiple PNG assets from a single code base.

Next, explore other customization options such as foreground color, margins, and adding human‑readable text. You can also experiment with different symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) to broaden the range of data you can encode.

Happy coding, and may your barcodes always scan on the first try!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}