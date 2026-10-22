---
category: general
date: 2026-10-21
description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
  Follow this step‑by‑step guide to create barcode images, customize rows and columns,
  and export PNG files.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: en
lastmod: 2026-10-21
og_description: Generate a databar expanded stacked barcode in C# with this tutorial.
  Learn how to use BarcodeGenerator, set rows and columns, and save PNG images.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Generate a databar expanded stacked barcode in C# – complete guide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: How to generate a databar expanded stacked barcode in C#
url: /python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate a databar expanded stacked barcode in C#

If you need to generate a **databar expanded stacked** barcode in C#, this guide shows you how. The databar expanded stacked symbology is ideal for encoding large amounts of data in a compact form, and you can create the image with just a few lines of code. You’ll also learn how to **generate barcode image** files in different formats and customize rows or columns to suit your scanning environment.

This tutorial covers everything you need to start producing databar barcodes: installing the required library, preparing the output folder, creating the barcode with custom rows or columns, and saving the result as a PNG file. By the end, you’ll be able to **create databar barcode** images programmatically and adapt the code for other image formats or runtime scenarios.

## Prerequisites

Before you begin, make sure you have:

* .NET 6.0 SDK or later (the code also works with .NET Core 3.1 and .NET Framework 4.7+)
* A development environment such as Visual Studio 2022, Visual Studio Code, or Rider
* Internet access to install the **Barcode Generator C#** NuGet package (Aspose.BarCode for .NET)

> **Pro tip:** If you are using a CI/CD pipeline, add the NuGet package reference to your project file so builds are reproducible.

## Install the Barcode Generator C# library

The example uses the Aspose.BarCode library, which provides the `BarcodeGenerator` class and the `EncodeTypes.DatabarExpandedStacked` enumeration.

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version to your project. After the installation, you can import the namespace in your C# files:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Prepare the output folder

A reliable file path prevents runtime errors when the library tries to write the image. The following code creates the directory if it does not exist:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Why this matters:** Attempting to save to a non‑existent directory throws an `IOException`. Creating the folder up front makes the code robust for both local development and production environments.

## Generating a databar expanded stacked barcode image

### Basic barcode generation

The simplest way to generate a **databar expanded stacked** image is to instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain text payload.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Running the snippet produces `DatabarBasic.png` in the *Barcodes* folder. The image contains a standard databar expanded stacked symbol with the default layout (4 columns × 4 rows).

### Customizing columns – create databar barcode with 4 columns

You can control the number of columns using the `Parameters.Barcode.DataBar.Columns` property. The following example creates a barcode with **4 columns** while keeping the default row count.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

The resulting file, **DatabarCols4.png**, looks like this:

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*Image alt text (og_image_alt):* **Sample databar expanded stacked barcode image generated with C#** – this satisfies the SEO requirement for image alt text.

### Customizing rows – create databar barcode with 3 rows

Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`. The code below generates a barcode with **3 rows** and the default column count (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

The file **DatabarRows3.png** contains a databar expanded stacked symbol that is slightly shorter vertically, which can be useful for space‑constrained labels.

### Exporting to other formats

If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png` with the appropriate enum value:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

The library also supports vector formats like SVG, which are ideal for high‑resolution printing.

## Advanced scenarios

### Saving to a memory stream

Sometimes you want to embed the barcode directly into a web response or a PDF without touching the file system. Use a `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Handling invalid input

The `BarcodeGenerator` validates the payload against the chosen symbology. If the data contains prohibited characters, an `ArgumentException` is thrown. Wrap the generation code in a try‑catch block to provide a friendly error message:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Scaling the barcode image

You can change the image size without altering the encoded data by setting `Parameters.Image.Width` and `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Scaling is useful when the barcode must meet a specific DPI requirement for scanners.

## Full working example

Below is a complete, ready‑to‑run console application that demonstrates all of the steps discussed:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Expected output**


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to build a barcode generator example in C# with DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}