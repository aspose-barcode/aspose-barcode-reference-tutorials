---
category: general
date: 2026-09-10
description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
  set columns, and generate a PNG with BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- enable compact mode
- barcode generator C#
- how to generate barcode
- how to set columns
language: en
lastmod: 2026-09-10
og_description: Create PDF417 barcode in C# by enabling compact mode, setting columns,
  and saving as PNG. Follow the complete step‑by‑step guide.
og_image_alt: Screenshot of a compact PDF417 barcode generated with C#
og_title: Create PDF417 barcode in C# – compact mode tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create PDF417 barcode in C# quickly. Learn how to enable compact mode,
    set columns, and generate a PNG with BarcodeGenerator.
  headline: How to create PDF417 barcode in C# with compact mode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: How to create PDF417 barcode in C# with compact mode
url: /net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create PDF417 barcode in C# with compact mode

If you need to **create PDF417 barcode** in a .NET application, this guide shows you exactly how to do it. You’ll see how to **enable compact mode**, set the number of columns, and save the result as a PNG image using the BarcodeGenerator C# library.

Generating a barcode is a common requirement for inventory tracking, ticketing systems, and mobile scanning apps. By the end of this tutorial you will have a self‑contained, runnable example that produces a compact PDF417 barcode ready for production use.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed (the code also works with .NET Framework 4.7+)
* A recent version of the **BarcodeGenerator** library (e.g., Aspose.BarCode for .NET)
* An IDE or editor such as Visual Studio 2022 or VS Code
* Write permission to a folder where the PNG will be saved

No additional NuGet packages are required beyond the barcode library itself.

## Step 1: Create a PDF417 barcode generator

The first step is to instantiate a `BarcodeGenerator` object with the `EncodeTypes.Pdf417` enum and the text you want to encode. This object drives the whole generation process.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

*Why this matters*: The `EncodeTypes.Pdf417` value tells the library to use the PDF417 symbology, while the second argument supplies the payload. You can replace `"Compact mode"` with any alphanumeric string you need to encode.

## Step 2: Set the X dimension (module width)

The X dimension controls the width of each tiny square (module) in the barcode. Smaller values produce a tighter image, which is useful when space is limited.

```csharp
// Step 2: Set the X dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

A value of `2` pixels is a good balance between readability and compactness for most screen‑based scanners.

## Step 3: Define the number of columns

PDF417 can arrange data in a grid of rows and columns. Adjusting the column count changes the barcode’s aspect ratio.

```csharp
// Step 3: Define the number of columns for the PDF417 barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

Setting **how to set columns** to `3` yields a short, wide barcode that fits nicely on a label. You can experiment with values from `1` to `30` depending on the amount of data and the target scanner.

## Step 4: Enable compact mode

Compact mode removes unnecessary padding rows, making the barcode smaller without losing data integrity. This is the key step for a **compact PDF417**.

```csharp
// Step 4: Enable compact mode by truncating the barcode
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

When `Truncate` is `true`, the library automatically calculates the minimal number of rows required to store the data, which is why the final image looks “tight”.

## Step 5: Save the generated barcode as a PNG image

Finally, write the barcode to a file. PNG preserves the crisp edges needed for reliable scanning.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Replace `YOUR_DIRECTORY` with an absolute or relative path that your application can write to. After execution, you will find a `CompactPdf417.png` file that contains the barcode.

### Full source code

Putting all the steps together gives you a single, ready‑to‑run program:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

        // Set the X dimension (module width) in pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the number of columns for the PDF417 barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;

        // Enable compact mode by truncating the barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("CompactPdf417.png", BarCodeImageFormat.Png);

        Console.WriteLine("PDF417 barcode created successfully.");
    }
}
```

Running this program produces `CompactPdf417.png` in the same folder as the executable. Open the image with any viewer; you should see a dense, high‑contrast PDF417 barcode ready for scanning.

## How to enable compact mode in other scenarios

* **Batch generation** – When creating many barcodes, set `Truncate` once on the generator and reuse it for each new payload.
* **Different image formats** – The same `Save` method works with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp` if you need a different file type.
* **Dynamic column count** – If the length of the encoded string varies, calculate an optimal column count based on the string length and the scanner’s resolution.

## How to set columns for specific use‑cases

* **Label printing** – Use a low column count (e.g., `2`‑`5`) to keep the barcode short enough to fit on narrow labels.
* **Mobile scanning** – Higher column counts (`10`‑`15`) produce taller barcodes that are easier for phone cameras to focus on.
* **Error‑correction trade‑off** – More columns reduce the number of rows, which can affect the barcode’s built‑in error correction. Test with your target scanner to find the sweet spot.

## Common pitfalls and pro tips

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Barcode is unreadable | X dimension too low (e.g., `1` pixel) | Increase `XDimension.Pixels` to at least `2` |
| Image is too large | Columns set too high for a short payload | Reduce `Pdf417.Columns` or enable `Truncate` |
| PNG file is blank | Output folder does not exist or lacks write permission | Ensure the directory exists and the process has write rights |
| Scanner reports “data corrupted” | Truncate disabled while using many columns | Enable `Truncate` or lower column count |

## Verifying the result

You can verify the barcode with any PDF417 scanner app (many free Android/iOS apps exist). Open `CompactPdf417.png` in the app and confirm that the decoded text matches the original payload (“Compact mode”). If the text differs, double‑check the `Truncate` flag and column settings.

## Next steps

* **Integrate with ASP.NET Core** – Return the PNG directly from a controller action instead of saving to disk.
* **Add human‑readable text** – Use `barcodeGenerator.Parameters.Barcode.CodeTextParameters` to display the encoded string beneath the barcode.
* **Explore other symbologies** – The same `BarcodeGenerator` class supports QR, Code128, DataMatrix, and more. Switch `EncodeTypes` to try them out.

---

### Conclusion

You now know how to **create PDF417 barcode** in C# while **enabling compact mode**, controlling **how to set columns**, and using the **barcode generator C#** API to **generate a barcode** that meets real‑world size constraints. Apply these steps to any .NET project that needs compact, high‑density barcodes, and extend the pattern to other barcode formats as required. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}