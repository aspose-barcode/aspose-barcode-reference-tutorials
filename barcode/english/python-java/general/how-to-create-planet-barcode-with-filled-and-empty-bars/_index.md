---
category: general
date: 2026-09-29
description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
  guide using Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: en
lastmod: 2026-09-29
og_description: Create planet barcode in C# quickly. Learn how to render filled bars,
  switch to empty bars, and adjust X‑dimension with Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Create planet barcode with filled and empty bars – C# tutorial
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: How to create planet barcode with filled and empty bars
url: /python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create planet barcode with filled and empty bars

If you need to **create planet barcode** images in C#, this guide shows you exactly how to generate both filled‑bar and empty‑bar versions. You’ll see how to set the bar width (X‑dimension), toggle the `FilledBars` property, and save the results as PNG files—all with the Aspose.Barcode library.

Generating postal barcodes is a common requirement for shipping systems, mailing‑list applications, and logistics dashboards. By the end of this tutorial you’ll have two ready‑to‑use PNG files that you can embed in reports, emails, or print‑outs.

## Prerequisites

Before you start, make sure you have:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 or later | Provides the runtime for the C# example. |
| Visual Studio 2022 (or any C# IDE) | Lets you compile and run the code. |
| **Aspose.Barcode for .NET** NuGet package | Supplies the `BarcodeGenerator` class and `EncodeTypes.Planet`. Install it with `dotnet add package Aspose.Barcode`. |
| Write permission to a folder on disk | The `Save` method writes PNG files to the path you specify. |

## Step 1: Set up the project and import namespaces

Create a new console project (or add the code to an existing one) and reference the Aspose.Barcode namespace.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

These `using` directives give you access to the `BarcodeGenerator`, `EncodeTypes`, and image‑format enums needed for the tutorial.

## Step 2: Create a Planet barcode with default (filled) bars

The first barcode uses the library’s default rendering, which fills the bars.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Why this works:**  
`EncodeTypes.Planet` tells Aspose.Barcode to use the **Planet** symbology, which is a postal barcode used by the United States Postal Service. The `XDimension` property controls the width of each bar; setting it to 4 pixels produces a barcode that prints well on standard label printers. By default, `FilledBars` is `true`, so the bars appear solid.

## Step 3: Create a Planet barcode with empty bars

To generate the same data with *empty* bars, you only need to flip the `FilledBars` flag while keeping the other settings identical.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Why this matters:**  
Some mailing systems require the **empty‑bars** style to improve readability when the barcode is printed on dark backgrounds or when a contrasting color scheme is used. By setting `FilledBars = false`, the generator draws only the outlines of the bars, leaving the interior transparent.

## Expected output

After running the program, the folder `C:\Barcodes` (or the path you chose) contains two PNG files:

| File | Visual description |
|------|---------------------|
| `PlanetFilledBars.png` | Bars are solid black rectangles on a white background. |
| `PlanetEmptyBars.png`  | Bars are black outlines; the interior of each bar is transparent (shows the background). |

Both images encode the same numeric string `"123456"` and share a 4‑pixel bar width, ensuring they look consistent except for the fill style.

## Common variations and edge cases

### Changing the bar width

If your label printer expects a different bar width, modify the `XDimension.Pixels` value. For high‑resolution printers, a value of **2** or **3** pixels may be preferable; for low‑resolution printers, **5** or **6** pixels can improve scan reliability.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Using a different image format

Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png` with another enum value to match your downstream workflow.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Generating multiple barcodes in a loop

When you need a batch of Planet barcodes (e.g., for a mailing list), wrap the generator logic in a `foreach` loop and change the data string each iteration.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Handling invalid input

The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying an invalid value throws an `ArgumentException`. Guard against this with a simple validation method.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Pro tip: Verify the barcode with a scanner emulator

Aspose.Barcode includes a `BarcodeReader` class you can use to confirm that the generated image decodes back to the original data.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

If the output shows `"123456"` for both files, the barcode was generated correctly.

## Conclusion

You now know how to **create planet barcode** images in C# with both filled and empty bar styles, control the **Planet barcode XDimension**, and save the results in PNG format using the **Aspose.Barcode** library. Adjust the bar width, switch image formats, or loop over a collection of values to fit any postal‑code workflow.

Next, you might explore:

* **Adding human‑readable text** beneath the barcode (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Embedding barcodes in PDF documents** with Aspose.PDF.
* **Generating other postal symbologies** such as **USPS POSTNET** or **Intelligent Mail**.

Feel free to experiment with the parameters and integrate the code into your shipping or mailing system. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Create planet barcode in C# – complete programming guide](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Barcode generator C# – create Planet barcode and RM4SCC example](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}