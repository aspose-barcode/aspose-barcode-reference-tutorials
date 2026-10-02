---
category: general
date: 2026-10-02
description: Create barcode image in C# using a barcode generator, control barcode
  pixel size and adjust barcode height for custom barcode dimensions.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: en
lastmod: 2026-10-02
og_description: Create barcode image in C# with a barcode generator. Learn to set
  barcode pixel size, adjust barcode height, and define custom barcode dimensions.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Create barcode image in C# – guide to barcode generator and custom dimensions
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: How to create barcode image in C# with a barcode generator
url: /python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create barcode image in C# with a barcode generator

If you need to **create barcode image** files programmatically, this guide shows you a complete, ready‑to‑run solution in C#. By using a barcode generator you can control the **barcode pixel size**, **adjust barcode height**, and define **custom barcode dimensions** without leaving your IDE.

You’ll learn how to generate two PNG files—one with a 30 px bar height and another with 60 px—while keeping the module width constant. The steps work with any barcode type supported by the library, so you can adapt them to QR codes, Code 128, or other symbologies.

## What you’ll need

- .NET 6.0 or later (the code also compiles with .NET Framework 4.8)
- A reference to the barcode library (e.g., Aspose.BarCode for .NET or any compatible `BarcodeGenerator` class)
- Basic C# knowledge
- Write permission to a folder where the PNG files will be saved

## Step 1: Initialize the barcode generator to **create barcode image**

First, import the required namespaces and instantiate a `BarcodeGenerator`. The constructor receives the barcode type (`EncodeTypes.DatabarOmniDirectional`) and the data string you want to encode.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Creating the generator is the foundation for any **barcode generator c#** workflow. It allocates the internal drawing canvas and prepares the data for rendering.

## Step 2: Define **barcode pixel size** and initial bar height

The visual quality of the final image depends on two parameters:

| Parameter | Meaning |
|-----------|---------|
| `XDimension.Pixels` | Width of a single module (the smallest black/white element). |
| `BarHeight.Pixels` | Height of the bars for the current image. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Keeping the **barcode pixel size** constant while changing the height lets you create **custom barcode dimensions** that match branding guidelines or scanning requirements.

## Step 3: Save the first PNG file (30 px height)

Now write the image to disk. The `Save` method accepts the file path and the desired image format.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

The resulting file is a **barcode image** with a 30 px bar height and a 2 px module width, perfect for compact labels.

## Step 4: **Adjust barcode height** for a larger version

To generate a second image with a different visual size, only the `BarHeight.Pixels` property needs to change. This demonstrates how easy it is to **adjust barcode height** without recreating the generator.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Changing the height while preserving the **barcode pixel size** ensures the bars stay crisp and the overall aspect ratio remains consistent.

## Step 5: Save the second PNG file (60 px height)

Finally, persist the larger version.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

You now have two **custom barcode dimensions** saved side by side:

- `DatabarBarHeight30Pixels.png` – 30 px bar height
- `DatabarBarHeight60Pixels.png` – 60 px bar height

Both images share the same **barcode pixel size** of 2 px, guaranteeing visual consistency across different sizes.

## Why these settings matter

- **Barcode pixel size** (`XDimension`) influences scanner readability. A width of 2 px is a common default that balances file size and scan reliability.
- **Bar height** determines how tall the barcode appears on a label. Some retail scanners require a minimum height; others allow taller bars for aesthetic reasons.
- Keeping the generator instance alive while only tweaking `BarHeight` reduces memory allocations and speeds up batch processing.

## Edge cases and best‑practice tips

| Situation | Recommended approach |
|-----------|----------------------|
| **Different image formats** (JPEG, BMP) | Change `BarCodeImageFormat.Jpeg` or `.Bmp` in the `Save` call. JPEG is smaller but may introduce compression artifacts. |
| **High‑resolution output** (e.g., 300 DPI) | Increase `XDimension.Pixels` proportionally (e.g., 4 px) and adjust `BarHeight.Pixels` to maintain the same physical size. |
| **Dynamic data strings** | Wrap the generator creation in a method that accepts the data string as a parameter, then reuse the same `barcode` instance for multiple saves. |
| **Thread‑safe batch generation** | Instantiate a separate `BarcodeGenerator` per thread or use a thread‑local pool to avoid race conditions. |
| **File‑system permission errors** | Verify that `outputFolder` exists and the process has write access; handle `IOException` gracefully. |

## Full source listing

Below is the complete, self‑contained program you can copy, paste, and run.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Expected output

After running the program, the `YOUR_DIRECTORY` folder contains two PNG files:

- **DatabarBarHeight30Pixels.png** – a compact barcode suitable for small labels.
- **DatabarBarHeight60Pixels.png** – a larger version ideal for high‑visibility applications.

Both files can be opened in any image viewer, printed, or embedded in PDFs.

## Conclusion

You now know how to **create barcode image** files in C# with a **barcode generator c#**, control the **barcode pixel size**, **adjust barcode height**, and produce **custom barcode dimensions** that meet specific scanning or branding requirements. The example demonstrates a clean, repeatable pattern that scales to batch processing or different symbologies.

### What to explore next

- Swap `EncodeTypes.DatabarOmniDirectional` for other types such as `EncodeTypes.Code128` or `EncodeTypes.QR`.
- Apply foreground/background colors via `barcode.Parameters.Barcode.ForeColor` and `BackColor`.
- Generate SVG or PDF outputs for vector‑based printing.
- Combine multiple barcodes into a single image using `Graphics` for composite labels.

Feel free to experiment with the parameters, and integrate this pattern into your inventory, ticketing, or any system that needs programmatic barcode creation. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create barcode image in C# with adjustable height](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Create barcode image C# with barcode generator example](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}