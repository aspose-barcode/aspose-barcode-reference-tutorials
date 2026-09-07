---
category: general
date: 2026-09-07
description: barcode generator C# tutorial that shows you how to generate barcode
  PNG files and create DataBar barcodes with customizable rows and columns
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: en
lastmod: 2026-09-07
og_description: 'barcode generator C# tutorial: learn to generate barcode PNG files
  and create DataBar barcodes with custom rows and columns in just minutes'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: barcode generator C# – create DataBar barcodes and PNG images
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: How to use a barcode generator C# to create DataBar barcodes
url: /python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use a barcode generator C# to create DataBar barcodes

If you need a **barcode generator C#** for creating high‑quality barcodes, this guide shows you how to **generate barcode PNG** files and **create DataBar barcodes** with custom rows and columns. Whether you’re building a retail inventory system or a ticketing platform, the steps below let you produce a DataBar Expanded Stacked barcode in a single, self‑contained example.

In this tutorial you will learn:

* How to instantiate the `BarcodeGenerator` for the DataBar Expanded Stacked symbology.  
* How to adjust column and row settings to meet the ISO / GS1 specifications.  
* How to save the output as a PNG image that can be embedded in web pages or printed on labels.  

No external services are required—just the Aspose.BarCode for .NET library (or any compatible library that follows the same API). The code runs on .NET 6+ and works in Visual Studio, Rider, or any IDE that supports C#.

## Prerequisites

Before you start, make sure you have:

* .NET 6 SDK or later installed.  
* A reference to the `Aspose.BarCode` NuGet package (or an equivalent library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`).  
* Basic familiarity with C# syntax and project structure.  

You can add the package via the command line:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Initialize the barcode generator C# for DataBar Expanded Stacked

The first step is to create a `BarcodeGenerator` instance that targets the **DataBar Expanded Stacked** symbology. This object holds all rendering parameters, including the text to encode.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Why this matters:** The `EncodeTypes.DatabarExpandedStacked` enum value tells the library which barcode standard to apply. Using the correct enum ensures the generated image complies with GS1 DataBar specifications.

## Step 2: Configure the number of columns (default rows are used)

DataBar Expanded Stacked can be split into multiple columns. Adjusting the column count changes the visual density and can help fit longer data strings into limited space.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Pro tip:** The default column count is 1. Setting it to 4 creates four stacked columns, which is ideal for longer numeric strings while keeping the barcode height manageable.

## Step 3: Generate barcode PNG with the column setting applied

Now save the barcode as a PNG image. PNG preserves the crisp edges needed for scanners and works well on both web and print media.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

The file `DatabarCols4.png` contains a **barcode PNG** that you can embed directly in HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Step 4: Create a separate generator instance for row configuration

If you need to control the number of rows instead of columns, instantiate a new `BarcodeGenerator`. Re‑using the same instance after changing a dimension can lead to unexpected layout artifacts, so a fresh object is the safest approach.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Step 5: Set the number of rows (default columns are used)

Rows affect the vertical stacking of the barcode modules. Increasing rows can make the barcode taller, which may be required for certain label sizes.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Why rows vs. columns:** Columns split the barcode horizontally, while rows extend it vertically. Choose the orientation that best fits your label layout.

## Step 6: Generate barcode PNG with the row setting applied

Finally, save the row‑adjusted barcode as a PNG file.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

You now have two distinct PNG files:

* `DatabarCols4.png` – 4 columns, 1 row.  
* `DatabarRows3.png` – 1 column, 3 rows.

Both images are ready for immediate use in applications, reports, or printed labels.

## How to generate barcode PNG files in C# with custom dimensions

The pattern shown above can be reused for any DataBar variant or other symbologies supported by the library. Here’s a compact template you can copy‑paste into a utility class:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Call the method like this:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Edge cases to consider**

* **Data length** – DataBar Expanded Stacked can encode up to 74 numeric characters. Exceeding this limit throws an exception. Validate input length before calling the generator.  
* **Invalid dimensions** – The library restricts columns to 1‑4 and rows to 1‑3 for this symbology. Supplying values outside these ranges will be ignored or cause an error.  
* **Image DPI** – If you need higher resolution for printing, set `generator.Parameters.ImageResolution` before saving.

## Expected output

When you open `DatabarCols4.png` or `DatabarRows3.png` you should see a clear, high‑contrast DataBar barcode. Scanning the image with a GS1‑compatible scanner returns the original text `"Databar Expanded Stacked long"`.

![Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#](image.png)

*Alt text: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#*

## Conclusion

This tutorial demonstrated how a **barcode generator C#** can be used to **create DataBar barcodes** and **generate barcode PNG** files with custom row and column settings. By following the six steps—initializing the generator, configuring columns or rows, and saving as PNG—you obtain production‑ready images suitable for inventory systems, ticketing, or any scenario that requires reliable barcode rendering.

Next, you might explore:

* Adding color or background images to the PNG (still compatible with most scanners).  
* Using other symbologies such as QR, Code 128, or PDF417 via the same `BarcodeGenerator` API.  
* Embedding the generated PNG directly into ASP.NET Core MVC views or Blazor components.

Feel free to experiment with different data strings, dimensions, and image formats (e.g., JPEG, BMP). The same pattern applies, making the **barcode generator C#** a versatile tool in any .NET developer’s toolbox. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode C# – Create DataBar barcode](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}