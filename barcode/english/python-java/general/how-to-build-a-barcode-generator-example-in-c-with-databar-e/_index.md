---
category: general
date: 2026-09-19
description: barcode generator example in C# showing how to generate barcode C# using
  Aspose.BarCode for column and row layouts
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: en
lastmod: 2026-09-19
og_description: barcode generator example demonstrates how to generate barcode C#
  with column and row layouts using Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: barcode generator example – create DataBar Expanded Stacked barcodes in
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to build a barcode generator example in C# with DataBar Expanded Stacked
url: /python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator example – create DataBar Expanded Stacked barcodes in C#

If you need a **barcode generator example** that works in a .NET project, this guide shows you exactly how to generate barcode C# using the Aspose.BarCode library. You’ll see how to configure a DataBar Expanded Stacked barcode for both a column‑based layout and a row‑based layout, and you’ll get ready‑to‑run code that produces PNG images.

The tutorial covers everything from installing the NuGet package to saving the final images, so you can copy the code into your own solution without additional research.

## What you’ll learn

* How to install and reference Aspose.BarCode in a C# project.  
* How to create a **barcode generator example** that encodes a long data string.  
* How to set a 4‑column layout and a 3‑row layout on the same barcode type.  
* How to save the generated images as PNG files.  

By the end of this article you will have two ready‑to‑use PNG files: `ExpandedStackedCols4.png` (four columns) and `ExpandedStackedRows3.png` (three rows).

## Prerequisites

* .NET 6.0 SDK or later (the code also works with .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code, or any C# IDE you prefer.  
* Internet access to download the **Aspose.BarCode** NuGet package.  

No additional external services are required.

## Step 1: Install the Aspose.BarCode NuGet package

Open a terminal in your project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version of Aspose.BarCode to your project file. After the package is restored, you can reference its namespaces in your C# source files.

## Step 2: Add the required using directives

Create a new C# console application (or add the code to an existing project) and include the following `using` statements at the top of the file:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

These directives give you access to the `BarcodeGenerator` class and the `EncodeTypes` enumeration used in the **barcode generator example**.

## Step 3: Create a barcode generator example with a 4‑column layout

The first part of the example builds a DataBar Expanded Stacked barcode that uses a four‑column arrangement. The code below follows the exact steps shown in the original snippet, but adds comments that explain why each line is necessary.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Why this works**

* `EncodeTypes.DatabarExpandedStacked` tells Aspose.BarCode to generate a DataBar Expanded Stacked symbol, which is suited for retail applications.  
* Setting `DataBar.Columns` to `4` forces the generator to split the symbol into four vertical sections, improving readability on narrow labels.  
* `Save` writes the barcode to disk; the `BarCodeImageFormat.Png` argument ensures lossless image quality.

Running this block creates `ExpandedStackedCols4.png` in the application’s working directory. The file contains a high‑resolution barcode that can be scanned by any standard DataBar reader.

## Step 4: Re‑initialize the generator for a different layout

To demonstrate a row‑based layout, you need a fresh `BarcodeGenerator` instance. Re‑initialising guarantees that the previous column setting does not affect the new configuration.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Step 5: Configure the barcode to use a 3‑row layout

The DataBar API also supports a row arrangement. Setting the `Rows` property defines how many horizontal slices the symbol will contain.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Why you might choose rows over columns**

Rows are useful when the label height is limited but width is ample. A three‑row layout compresses the barcode vertically while preserving the required amount of data.

## Complete source file

Below is a full, self‑contained `Program.cs` that you can compile and run directly. It includes both the column and row examples, so you get two PNG files with a single execution.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Expected output

After running the program you will see two console messages confirming the file creation:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Both PNG files will display a DataBar Expanded Stacked barcode that encodes the string `"Long data string"`. Scanning either image with a standard barcode scanner returns the original data.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| **Can I change the image format?** | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Tiff` depending on your requirements. |
| **What if the data string is shorter?** | The DataBar format automatically adjusts the symbol size; you do not need to modify the layout settings. |
| **How do I set the barcode size (width/height)?** | Use `generator.Parameters.Image.Width` and `generator.Parameters.Image.Height` before calling `Save`. |
| **Is it possible to add a human‑readable caption?** | Set `generator.Parameters.Barcode.CodeText` and enable `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **What .NET versions are supported?** | Aspose.BarCode supports .NET Standard 2.0, .NET 5/6, and .NET Framework 4.6.1+. |

Addressing these variations makes the **barcode generator example** robust enough for production use.

## Pro tips

* **Reuse the generator object only when the layout stays the same.** Creating a new instance for each layout, as shown in Steps 4‑5, prevents accidental property carry‑over.  
* **Validate the generated barcode** with `generator.Validate()` if you need to ensure compliance with ISO/GS1 standards.  
* **Batch processing:** Wrap the column and row logic inside a loop that iterates over a list of layout configurations. This reduces code duplication when you need many variations.

## Conclusion

This **barcode generator example** demonstrates how to **generate barcode C#** code that produces both a 4‑column and a 3‑row DataBar Expanded Stacked barcode. You now have a complete, runnable program, an understanding of the key properties (`Columns`, `Rows`), and practical tips for extending the solution.

Next, explore related topics such as **customizing barcode colors**, **embedding barcodes in PDF documents**, or **generating QR codes with Aspose.BarCode**. Each of those subjects builds on the same API principles covered here.

Feel free to experiment with different data strings, image formats, and layout combinations. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}