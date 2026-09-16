---
category: general
date: 2026-09-16
description: Learn how to set barcode columns in C# using BarcodeGenerator and also
  set barcode rows for DataBar Expanded Stacked barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: en
lastmod: 2026-09-16
og_description: Set barcode columns in C# quickly. This guide shows you how to configure
  columns, rows, and image format with BarcodeGenerator.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Set barcode columns and rows in C# – complete BarcodeGenerator guide
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to set barcode columns and rows with C# BarcodeGenerator
url: /python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set barcode columns and rows with C# BarcodeGenerator

If you need to set barcode columns in a C# application, this tutorial shows the exact steps required. You’ll see how to configure both columns and rows for a DataBar Expanded Stacked barcode, then save the result as a PNG image.

Generating barcodes programmatically saves you from manual design work and guarantees consistency across reports, invoices, and product labels. The example below covers the full workflow, from installing the library to producing two images—one with a custom column count and another with a custom row count.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed.
* A reference to the **Aspose.BarCode for .NET** NuGet package. Install it with:

```bash
dotnet add package Aspose.BarCode
```

* Write access to a folder where the generated PNG files will be saved.

These requirements ensure the code compiles and runs without additional configuration.

## How to set barcode columns in C#

The first major step is creating a `BarcodeGenerator` instance for the **DataBar Expanded Stacked** symbology and assigning the desired column count.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
`EncodeTypes.DatabarExpandedStacked` tells the library which symbology to render. Setting `Parameters.Barcode.DataBar.Columns` changes the internal module layout, which directly influences the visual width of the barcode. The `Save` method writes the image to disk in the requested `BarCodeImageFormat`.

### Expected result
Open `C:\Barcodes\DatabarCols4.png` in any image viewer. You should see a DataBar Expanded Stacked barcode that is wider than the default because it uses four columns.

## How to set barcode rows in C#

After you have saved the column‑based image, you may want a barcode that varies in height by adjusting rows. The process mirrors the column configuration but uses the `Rows` property instead.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
Re‑initializing the generator ensures that the previous column setting does not interfere with the row configuration. Changing `Parameters.Barcode.DataBar.Rows` modifies the barcode’s height, producing a taller image when the row count exceeds the default.

### Expected result
Open `C:\Barcodes\DatabarRows3.png`. The barcode will appear taller, reflecting the three‑row configuration.

## Full end‑to‑end example

Below is a single program that creates both images in one execution. Keeping the code in one file demonstrates how you can switch between column and row configurations without restarting the application.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Running the program produces two PNG files:

* **DatabarCols4.png** – barcode with four columns.  
* **DatabarRows3.png** – barcode with three rows.

Both files use the **barcode image format** PNG, which preserves sharp edges and supports lossless compression—ideal for printing and digital display.

## Common questions and tips

| Question | Answer |
|----------|--------|
| *Can I use JPEG instead of PNG?* | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is smaller but introduces compression artifacts, which may affect scanner reliability. |
| *What is the maximum number of columns or rows?* | The library validates the values against the DataBar specification. Values outside the allowed range throw an `ArgumentException`. Check the Aspose.BarCode documentation for the exact limits. |
| *Do I need to dispose the `BarcodeGenerator`?* | The class implements `IDisposable`. Wrap the generator in a `using` block if you create many instances in a loop to free unmanaged resources promptly. |
| *How do I change the barcode size without altering columns/rows?* | Use `barcodeGenerator.Parameters.Image.Width` and `Height` to scale the output image while keeping the module layout unchanged. |

**Pro tip:** When you generate barcodes for high‑resolution printing, increase the output image dimensions (`Width`/`Height`) rather than the column or row count. This approach maintains the standard module size defined by the symbology while giving you a sharper image.

## Conclusion

You now know how to set barcode columns and rows in C# using the **BarcodeGenerator** class. The guide covered initializing the generator, configuring column and row counts, saving the barcode in PNG format, and handling common variations such as image format changes and resource disposal.

Next, explore related topics such as **customizing barcode colors**, **adding human‑readable text**, and **embedding barcodes into PDF documents**. All of these extensions build on the same configuration pattern demonstrated here, allowing you to create fully featured barcode solutions for any .NET application.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}