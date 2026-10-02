---
category: general
date: 2026-10-02
description: Learn how to set columns and rows in a C# barcode generator to create
  DataBar barcodes. Step‑by‑step guide with complete code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: en
lastmod: 2026-10-02
og_description: C# barcode generator guide – learn how to set columns and rows to
  create DataBar barcodes with full code examples.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'C# barcode generator: set columns & rows for DataBar barcodes'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: How to use a C# barcode generator to create DataBar barcodes with custom columns
  and rows
url: /python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use a C# barcode generator to create DataBar barcodes with custom columns and rows

If you need a **c# barcode generator** that can produce DataBar barcodes with precise column and row configurations, this tutorial shows you exactly how. You’ll see why adjusting columns and rows matters, and you’ll get a complete, ready‑to‑run example that creates both a 4‑column and a 3‑row DataBar Expanded Stacked barcode.

In the sections that follow we cover:

* The prerequisites for using the Aspose.BarCode for .NET library.
* How to set columns (`how to set columns`) and rows (`how to set rows`) on a DataBar barcode.
* A full C# console program that you can copy, compile, and execute.
* Expected output files and tips for troubleshooting.

By the end of this guide you’ll be able to **create databar barcode** images tailored to your layout requirements.

## Prerequisites

Before you start, make sure you have:

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK or later | Provides the runtime for the C# code. |
| Visual Studio 2022 (or any IDE that supports .NET) | Makes project creation and debugging easier. |
| Aspose.BarCode for .NET NuGet package | Supplies the `BarcodeGenerator` class used in the examples. |
| Write permission to a folder for the output PNG files | The generator writes the barcode images to disk. |

Install the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a basic DataBar Expanded Stacked barcode

The first step is to instantiate a **c# barcode generator** with the `EncodeTypes.DatabarExpandedStacked` format. This format is a two‑dimensional DataBar barcode that can encode up to 74 numeric characters.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

The constructor receives two arguments:

* `EncodeTypes.DatabarExpandedStacked` – tells the library which symbology to use.
* `"Databar Expanded Stacked long"` – the text that will be encoded.

## Step 2: How to set columns

Columns affect the horizontal density of the DataBar barcode. Increasing the column count makes the barcode wider, which can improve scan reliability on low‑resolution printers.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Why 4 columns?**  
Four columns give a good balance between size and readability for most retail applications. You can experiment with values from 1 to 8; the library will automatically adjust the module width.

## Step 3: Save the column‑configured barcode

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

The image is saved as a PNG file, which preserves the crisp edges required for barcode scanners.

## Step 4: Create a separate generator for row configuration

Row configuration works the same way but influences the vertical density. To avoid mixing column and row settings, we create a new generator instance.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: How to set rows

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**When to use more rows?**  
Adding rows makes the barcode taller, which can be useful when the printed space is limited horizontally but ample vertically (e.g., on a product label that is taller than it is wide).

## Step 6: Save the row‑configured barcode

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Both PNG files (`DatabarCols4.png` and `DatabarRows3.png`) will appear in the `C:\Barcodes` folder.

## Full, runnable example

Below is a self‑contained console application that incorporates every step described above. Copy the code into a new .NET console project and run it.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### What the code does

| Section | Purpose |
|---------|---------|
| **Namespace imports** | Pulls in `Aspose.BarCode` and `Aspose.BarCode.Generation`. |
| **Output directory** | Centralises the path so you only need to edit one line if you move the folder. |
| **Column generator** | Demonstrates **how to set columns** on a `c# barcode generator`. |
| **Row generator** | Demonstrates **how to set rows** on a `c# barcode generator`. |
| **Save calls** | Writes the PNG files to disk, making them ready for scanning or inclusion in reports. |
| **Console output** | Provides immediate feedback, useful during development. |

## Expected output

After running the program you should see two PNG files:

* **DatabarCols4.png** – a wider barcode reflecting four columns.
* **DatabarRows3.png** – a taller barcode reflecting three rows.

Both images contain the text *“Databar Expanded Stacked long”* encoded in the DataBar Expanded Stacked symbology. You can open them in any image viewer or feed them to a barcode scanner to verify readability.

## Common pitfalls and how to avoid them

| Issue | Reason | Fix |
|-------|--------|-----|
| **File‑access exception** | The output folder does not exist or you lack write permission. | Create the folder manually or run the program with elevated privileges. |
| **Incorrect column/row values** | The library only accepts values 1‑8 for columns and 1‑4 for rows. | Validate the values before assigning, e.g., `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | The generated image is too small for the scanner’s resolution. | Increase the `ImageHeight` or `ImageWidth` using `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | The encoded text exceeds the maximum length for the chosen DataBar variant. | Use a shorter string or switch to `EncodeTypes.DatabarExpanded` if you need more capacity. |

## Pro tips

* **Cache the generator** – If you need to create many barcodes with the same column/row settings, reuse the same `BarcodeGenerator` instance and only change the `CodeText` property.
* **Batch processing** – Loop over a collection of product identifiers, set `generator.CodeText` inside the loop, and call `Save` with a unique filename each iteration.
* **Performance** – For high‑volume scenarios, disable anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) to speed up image generation without affecting scan quality.

## Next steps

Now that you know **how to set columns** and **how to set rows** with a **c# barcode generator**, you might want to explore:

* **Adding human‑readable text** below the barcode (`generator.Parameters.Barcode.CodeTextLocation`).
* **Changing colors** (`generator.Parameters.Image.ForegroundColor` and `BackgroundColor`).
* **Generating other DataBar variants** such as `DatabarLimited` or `DatabarExpanded`.
* **Embedding barcodes in PDF reports** using Aspose.PDF.

Each of these topics builds on the foundation covered here and helps you create richer, production‑ready barcode solutions.

---

*Happy coding! If you run into any issues, feel free to leave a comment or check the Aspose.BarCode documentation for deeper API details.*


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set barcode columns and rows with C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}