---
category: general
date: 2026-07-21
description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
  barcode, customize barcode size, and export barcode image in just a few steps.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- create databar barcode
- customize barcode size
- change barcode dimensions
- export barcode image
language: en
lastmod: 2026-07-21
og_description: Generate barcode C# using Aspose.BarCode. Create DataBar barcode,
  customize its size, and export the image instantly.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode saved as PNG
og_title: Generate barcode C# – Build DataBar Barcodes with Custom Size
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Generate barcode C# quickly with Aspose.BarCode. Learn to create DataBar
    barcode, customize barcode size, and export barcode image in just a few steps.
  headline: Generate barcode C# – Create DataBar barcode
  type: TechArticle
- questions:
  - answer: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`.
      The API handles the conversion automatically.
    question: What if I need a different image format?
  - answer: Technically you can set both, but Aspose will prioritize the last property
      you modify. It's safer to set *one* dimension and let the library compute the
      other for a valid DataBar.
    question: Can I change both rows and columns simultaneously?
  - answer: 'Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`.
      Example:'
    question: How do I apply a foreground/background color?
  - answer: DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric).
      Exceeding that throws an exception.
    question: Is there a size limit for the encoded data?
  type: FAQPage
tags:
- barcode
- csharp
- databar
- image-export
- aspnet
title: Generate barcode C# – Create DataBar barcode
url: /python-java/general/generate-barcode-c-create-databar-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode C# – Create DataBar barcode

Looking to **generate barcode C#** without wading through endless docs? You're in the right spot. In this guide we'll walk through creating a **DataBar barcode**, tweaking its dimensions, and finally **exporting the barcode image**—all with a handful of lines of C#.

Imagine you need a compact product label that fits on a tiny shelf tag. A DataBar Expanded Stacked symbology does the trick, and with Aspose.BarCode you can control exactly how many columns or rows it uses. Ready? Let’s dive in.

## What you'll accomplish

- **Create a DataBar barcode** (the “expanded stacked” variant) from scratch.  
- **Customize barcode size** by setting columns or rows directly.  
- **Change barcode dimensions** on the fly without rebuilding the generator.  
- **Export barcode image** to PNG (or any format Aspose supports).  

No external services, no messy configurations—just clean, runnable C# code.

## Prerequisites

- .NET 6.0 or later (the code also works on .NET Framework 4.7+).  
- A valid Aspose.BarCode for .NET license (or you can run in trial mode).  
- An IDE of your choice—Visual Studio, Rider, or VS Code will do.  

If you haven’t installed the NuGet package yet, run:

```bash
dotnet add package Aspose.BarCode
```

That’s it—no other dependencies.

## Step 1: Set up the barcode generator (How to **generate barcode C#**)

First, we need a `BarcodeGenerator` instance pointing at the **DataBar Expanded Stacked** symbology. This object is the engine that creates the image later on.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Initialize the generator with the desired symbology and data
BarcodeGenerator barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // Symbology
    "Databar Expanded Stacked long");    // Human‑readable text (optional)
```

*Why this matters*: The `EncodeTypes.DatabarExpandedStacked` enum tells Aspose we want the stacked version, which is ideal for narrow spaces. The text we pass becomes the encoded value; you can replace it with any numeric string your application requires.

## Step 2: **Customize barcode size** – set columns

DataBar barcodes let you influence the visual density by specifying either the number of **columns** *or* **rows**. Let’s start with columns. The row count will be auto‑calculated to keep the barcode valid.

```csharp
// Set the number of columns; rows are computed automatically
barcodeGen.Parameters.Barcode.DataBar.Columns = 4;
```

*Pro tip*: Columns affect the barcode’s width. More columns → wider barcode, which can improve scan reliability on low‑resolution printers.

## Step 3: **Export barcode image** with the column setting

Now we write the image to disk. You can pick PNG, JPEG, BMP, or even SVG. Here’s PNG for crisp, lossless output.

```csharp
// Save the barcode image using the current column configuration
barcodeGen.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

> **Expected result** – Open `DatabarCols4.png` and you should see a neatly stacked DataBar with four columns. It looks like a dense stack of vertical bars, perfect for a small label.

## Step 4: **Change barcode dimensions** – set rows instead

Sometimes you need a taller barcode rather than a wider one. Switch to row control; Aspose will recalculate columns automatically.

```csharp
// Switch to row control – columns will be derived automatically
barcodeGen.Parameters.Barcode.DataBar.Rows = 3;
```

*Why switch?* Rows affect the barcode’s height. More rows make the symbol taller, which can be handy when you have vertical space but limited width.

## Step 5: **Export barcode image** with the row setting

Save the second variation. Notice the filename reflects the change; you could also keep both images for comparison.

```csharp
// Save the barcode image using the new row configuration
barcodeGen.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

> **Result** – `DatabarRows3.png` now displays a taller version of the same data, still perfectly scannable.

## Full working example

Putting it all together, here’s a self‑contained console app you can copy‑paste and run immediately:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Expanded Stacked
        BarcodeGenerator barcodeGen = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Customize size – set columns (width)
        barcodeGen.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Export image with column setting
        string colPath = @"C:\Barcodes\DatabarCols4.png";
        barcodeGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column‑based barcode to {colPath}");

        // 4️⃣ Change dimensions – set rows (height)
        barcodeGen.Parameters.Barcode.DataBar.Rows = 3;

        // 5️⃣ Export image with row setting
        string rowPath = @"C:\Barcodes\DatabarRows3.png";
        barcodeGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row‑based barcode to {rowPath}");
    }
}
```

Run the program, then open the two PNG files. You’ve now **generated barcode C#**, **customized barcode size**, **changed barcode dimensions**, and **exported the barcode image**—all in under a minute.

## Common questions & edge cases

- **What if I need a different image format?**  
  Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, `Gif`, or `Svg`. The API handles the conversion automatically.

- **Can I change both rows and columns simultaneously?**  
  Technically you can set both, but Aspose will prioritize the last property you modify. It's safer to set *one* dimension and let the library compute the other for a valid DataBar.

- **How do I apply a foreground/background color?**  
  Use `barcodeGen.Parameters.Barcode.ForegroundColor` and `BackgroundColor`. Example:  
  ```csharp
  barcodeGen.Parameters.Barcode.ForegroundColor = Color.DarkBlue;
  barcodeGen.Parameters.Barcode.BackgroundColor = Color.White;
  ```

- **Is there a size limit for the encoded data?**  
  DataBar Expanded Stacked supports up to 74 numeric characters (or 30 alphanumeric). Exceeding that throws an exception.

## Next steps

Now that you’ve mastered **create databar barcode** basics, consider:

- Adding **text annotations** below the barcode (`barcodeGen.Parameters.CaptionAbove.Text`).
- Embedding the PNG directly into a PDF using Aspose.PDF.
- Generating barcodes in bulk by looping over a CSV of product IDs.

Each of these topics builds on the same `BarcodeGenerator` object, so you won’t need to start from scratch.

---

**Bottom line**: you now know how to **generate barcode C#**, **customize barcode size**, **change barcode dimensions**, and **export barcode image** with Aspose.BarCode. Play around with the column/row values, swap image formats, and integrate the code into your inventory or POS system. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}