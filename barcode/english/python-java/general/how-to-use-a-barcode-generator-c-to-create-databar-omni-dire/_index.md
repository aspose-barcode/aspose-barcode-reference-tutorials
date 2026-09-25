---
category: general
date: 2026-08-22
description: barcode generator C# tutorial shows how to generate barcode PNG files,
  create DataBar barcodes, and adjust barcode height in just a few steps.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: en
lastmod: 2026-08-22
og_description: barcode generator C# guide walks you through how to generate barcode
  PNG, create DataBar barcodes, and adjust barcode height efficiently.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: barcode generator C# – create DataBar barcodes and adjust height
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
url: /python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use a barcode generator C# to create DataBar Omni‑directional barcodes

If you need a **barcode generator C#** that can produce high‑quality PNG images, this guide has you covered. You’ll learn how to generate barcode PNG files, create a DataBar Omni‑directional barcode, and adjust the barcode height without leaving your IDE.

Generating barcodes programmatically removes the manual step of using a graphic editor. By the end of this tutorial you’ll have two PNG files—one with a 30‑pixel bar height and another with a 60‑pixel bar height—ready for inclusion in invoices, labels, or inventory systems.

**Prerequisites**

- .NET 6.0 or later (the code also works with .NET Framework 4.7+)
- A reference to the `Aspose.BarCode` NuGet package (or any library that exposes a similar API)
- Basic familiarity with C# and Visual Studio or your preferred IDE

---

## Step 1: Set up the barcode generator C# project

Creating a **barcode generator C#** instance is the first thing you do. The constructor takes two arguments: the barcode type (`EncodeTypes.DatabarOmniDirectional`) and the data payload. In this example the payload follows the GS1 Application Identifier format for a 14‑digit GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Why this matters:** The `EncodeTypes.DatabarOmniDirectional` enum tells the library to render a DataBar that can be read from any direction, which is ideal for small retail labels.

---

## Step 2: Define the module dimension (X‑dimension)

The X‑dimension controls the width of a single barcode module. Setting it to 2 pixels gives a crisp, readable image while keeping file size low.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** If you need a tighter barcode for limited space, lower the value to 1 pixel, but test readability with a scanner.

---

## Step 3: Generate the first PNG with a 30‑pixel bar height

Bar height determines how tall the bars appear. A 30‑pixel height is a common default for standard labels.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

The file `DatabarBarHeight30Pixels.png` now contains a **generate barcode PNG** that can be used directly in web pages or printed on demand.

---

## Step 4: Adjust barcode height to 60 pixels and save a second PNG

Changing the bar height is as simple as assigning a new value to the same property. This demonstrates the **adjust barcode height** capability of the generator.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Now you have `DatabarBarHeight60Pixels.png`, which is ideal for larger packaging where the barcode must be scanned from a distance.

**Expected output**

- `DatabarBarHeight30Pixels.png` – a compact DataBar Omni‑directional barcode, 30 px tall.
- `DatabarBarHeight60Pixels.png` – the same barcode, doubled in height for better visibility.

Both images are PNG files, preserving lossless quality and supporting transparency if needed.

---

## How to generate barcode PNG files in different formats

While this tutorial focuses on PNG, the `Save` method accepts other formats such as `Jpeg`, `Bmp`, and `Svg`. To **how to generate barcode** files in another format, simply replace `BarCodeImageFormat.Png` with the desired enum value:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Choosing SVG is handy when you need a vector image that scales without pixelation.

---

## Common pitfalls when you **create DataBar barcode** images

| Issue | Cause | Fix |
|-------|-------|-----|
| Barcode appears blurry | X‑dimension too low for the target resolution | Increase `XDimension.Pixels` to 3 or 4 |
| Scanner cannot read the code | Bar height too short for the scanner’s optics | Use a minimum of 30 pixels or follow the scanner’s specifications |
| Data string is rejected | Incorrect GS1 formatting | Ensure the string starts with the proper Application Identifier, e.g., `(01)` for GTIN‑14 |

Addressing these points early saves time when integrating barcodes into production pipelines.

---

## Advanced tip: Reusing the same generator for multiple barcodes

If you need to **generate barcode PNG** files for a batch of products, reuse the same `BarcodeGenerator` instance and only update the `CodeText` property:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

This pattern minimizes object creation overhead and keeps your code concise.

---

## Conclusion

You now have a complete **barcode generator C#** workflow that **creates DataBar barcodes**, **generates barcode PNG** files, and lets you **adjust barcode height** with a single property change. The example covers everything from project setup to handling edge cases, so you can integrate barcode creation into any .NET application with confidence.

**Next steps**

- Explore other barcode symbologies (`EncodeTypes.QR`, `EncodeTypes.Code128`) to broaden your solution.
- Combine the generator with ASP.NET Core to serve barcodes on‑the‑fly via an API endpoint.
- Experiment with color options (`generator.Parameters.Barcode.ForeColor`) for branding purposes.

Happy coding, and may your scans always be swift!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}