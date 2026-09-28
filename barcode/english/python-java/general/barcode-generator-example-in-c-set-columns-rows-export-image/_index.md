---
category: general
date: 2026-07-15
description: Barcode generator example in C# showing how to set columns, how to set
  rows, and export barcode image quickly. Follow this step‑by‑step guide.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: en
lastmod: 2026-07-15
og_description: Barcode generator example in C# demonstrates how to set columns, how
  to set rows, and export barcode image. Learn the full workflow in minutes.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Barcode Generator Example in C# – Columns, Rows & Image Export
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Barcode Generator Example in C# – Set Columns, Rows & Export Image
url: /python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator Example in C# – Full Walkthrough

Ever wondered how to create a **barcode generator example** in C# that lets you tweak columns, rows, and then export the result as an image? You're not alone. Many developers hit a wall when they need a quick way to generate DataBar Expanded Stacked barcodes with custom layout options. In this tutorial we’ll solve that problem step‑by‑step, showing you **how to set columns**, **how to set rows**, and finally **export barcode image** files—all with clean, production‑ready code.

By the end of this guide you’ll have a complete, runnable program that creates a barcode image, adjusts its layout, and saves two PNG files to disk. No mystery libraries, no hidden configuration—just plain C# and a reliable barcode SDK.

---

## Prerequisites

Before we dive in, make sure you have the following:

- **.NET 6.0** (or any later .NET version). The code compiles with .NET Framework as well, but .NET 6+ gives you the latest runtime improvements.
- A **barcode generation library** that supports DataBar Expanded Stacked. In the examples we’ll use **Aspose.BarCode for .NET**, which is free for trial and offers a straightforward API.
- A development environment—Visual Studio 2022, Rider, or VS Code will all do.
- Write permission to a folder where the PNG files will be saved.

If you don’t already have the library, grab it from NuGet:

```bash
dotnet add package Aspose.BarCode
```

That single line pulls in everything you need, including the `BarcodeGenerator` class and the `BarCodeImageFormat` enum used later.

---

## Step 1: Set Up the Project Skeleton

Create a new console application and add the necessary `using` directives:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Here’s the **complete** `Program.cs` file skeleton:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Pro tip:** Keep the `Main` method tidy; we’ll delegate the heavy lifting to helper methods later. This makes the code easier to test and reuse.

---

## Step 2: Create the Barcode Generator Example

Now we’ll build the core **barcode generator example** that creates a DataBar Expanded Stacked barcode. This is the heart of the tutorial.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Why do we separate this into its own method? It isolates the **barcode generator example** logic, making it reusable if you later need to generate multiple barcodes with different data.

---

## Step 3: How to Set Columns

The DataBar Expanded Stacked format can be rendered in a column‑oriented layout. By default the SDK picks a sensible value, but you often need to match a specific label size. Here’s **how to set columns** to four:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Why columns matter:** Each column adds vertical space, which can be crucial when printing on narrow labels. Setting it to `4` gives you a balanced, readable barcode without sacrificing scan reliability.

In the main flow we’ll call this method:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Step 4: How to Set Rows

Sometimes you need a more compact layout, especially if you’re printing on a short, wide label. That’s where **how to set rows** comes in. Switching from a column‑centric to a row‑centric arrangement can shrink the barcode’s footprint.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Calling it looks like this:

```csharp
SetRows(generator, 3);
```

> **Edge case note:** You can’t set both columns *and* rows simultaneously—the SDK will prioritize rows if you assign a non‑zero value to `Rows`. So make sure to clear the other property if you switch layouts:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Step 5: Export Barcode Image

With the layout configured, the final piece is to **export barcode image** files. The SDK supports PNG, JPEG, BMP, and more. PNG is lossless and works well for most label printers.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Putting everything together in `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Expected Output

When you run the program, you should see two PNG files in `YOUR_DIRECTORY`:

- **DatabarCols4.png** – a barcode rendered with four vertical columns.
- **DatabarRows3.png** – the same data, but laid out in three horizontal rows.

Both images will be 300 × 150 px (as set in `CreateGenerator`) and ready for printing or embedding in a PDF.

---

## Common Pitfalls & Tips

| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **File path errors** | Using a relative path without the proper directory can throw `DirectoryNotFoundException`. | Use `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` or ensure the folder exists with `Directory.CreateDirectory`. |
| **Rows vs. Columns conflict** | Setting both properties leads the SDK to ignore columns. | Explicitly set the opposite property to `0` when you switch layouts. |
| **Unsupported barcode type** | Not all barcode libraries support DataBar Expanded Stacked. | Verify that your library version includes `EncodeTypes.DatabarExpandedStacked`. |
| **Image quality too low** | Default DPI may be insufficient for high‑resolution printers. | Adjust `generator.Parameters.Image.ResolutionX/Y` to `300` or higher. |

---

## Extending the Barcode Generator Example

Now that you have a solid **barcode generator example**, you might wonder what else you can do.

1. **Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to `Color.Blue`.
2. **Encode different data** – Pass a variable string instead of the hard‑coded `"Databar Expanded Stacked long"`.
3. **Batch processing** – Loop over a CSV file of product codes, generating a PNG for each.
4. **Integrate with a web API** – Expose an endpoint that returns the barcode as a base64‑encoded string.

Each of these extensions follows the same pattern: configure the `BarcodeGenerator` instance, then call `Save` or `Export` as needed.

---

## Conclusion

We’ve walked through a complete **barcode generator example** in C# that shows **how to set columns**, **how to set rows**, and how to **export barcode image** files. The code is self‑contained, runs out‑of‑the‑box with Aspose.BarCode, and demonstrates best practices for readability and maintainability.

Feel free to experiment—swap the data string, tweak the image dimensions, or switch to a different barcode symbology. The concepts you’ve learned here—initializing the generator, configuring layout parameters, and exporting—apply to virtually any barcode type supported by the SDK.

Got questions about creating barcode image c# programs, or need help with a specific label printer? Drop a comment below, and happy coding!

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}