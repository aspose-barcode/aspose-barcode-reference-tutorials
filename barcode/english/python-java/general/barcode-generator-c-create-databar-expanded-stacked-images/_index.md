---
category: general
date: 2026-07-24
description: Barcode Generator C# tutorial that shows how to generate barcode image,
  set columns, set rows, and create Databar barcode in just a few lines of code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
- how to set columns
- how to set rows
- create databar barcode
language: en
lastmod: 2026-07-24
og_description: Barcode Generator C# tutorial walks you through generating barcode
  image, configuring columns and rows, and creating a Databar barcode with clear code
  examples.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Barcode Generator C# – Build DataBar Stacked Barcodes Fast
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Barcode Generator C# tutorial that shows how to generate barcode image,
    set columns, set rows, and create Databar barcode in just a few lines of code.
  headline: Barcode Generator C# – Create DataBar Expanded Stacked Images
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcode Generator C# – Create DataBar Expanded Stacked Images
url: /python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator C# – Complete Guide to DataBar Expanded Stacked

Ever wondered how to use **barcode generator c#** to spit out crisp, scannable images in seconds? Maybe you’ve stared at a blank project, unsure where the columns or rows belong, or how to actually *generate barcode image* files without a headache. Well, you’re in the right spot. In this tutorial we’ll set up a tiny console app, spin up a DataBar Expanded Stacked barcode, tweak its layout, and save the result as PNGs—all with the **barcode generator c#** library.

We’ll cover everything you need to know: installing the package, configuring columns and rows (yes, we’ll answer *how to set columns* and *how to set rows*), and finally how to **create databar barcode** objects that you can drop into invoices, tickets, or anything that needs a machine‑readable label. No external docs required; just copy‑paste, run, and you’ll see two PNG files appear in your folder.

## What You’ll Need

- .NET 6.0 SDK or later (the code works on .NET Core, .NET Framework, and .NET 5+)
- A fresh console project (`dotnet new console`) – you can also use Visual Studio if you prefer a UI.
- The Aspose.BarCode for .NET NuGet package (the library that powers **barcode generator c#**). Install it with:

```bash
dotnet add package Aspose.BarCode
```

That’s it. Once the package is restored you’re ready to roll.

## Barcode Generator C# – Setting Up the Project

First, let’s bring the necessary namespaces into scope and create a helper method that will keep our main routine tidy.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        string outputFolder = Environment.CurrentDirectory;

        // Build the first barcode with custom columns
        GenerateDatabarWithColumns(outputFolder, columns: 4);

        // Build the second barcode with custom rows
        GenerateDatabarWithRows(outputFolder, rows: 3);
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets columns
    // -----------------------------------------------------------------
    static void GenerateDatabarWithColumns(string folder, int columns)
    {
        // Step 1: Create a DataBar Expanded Stacked barcode generator with the desired text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 2: Configure the barcode to use the supplied number of columns
        // This answers the “how to set columns” question.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = columns;

        // Step 3: Save the barcode image as PNG – this is the “generate barcode image” part.
        string filePath = System.IO.Path.Combine(folder, $"DatabarCols{columns}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {columns} columns: {filePath}");
    }

    // -----------------------------------------------------------------
    // Helper: creates a DataBar Expanded Stacked barcode and sets rows
    // -----------------------------------------------------------------
    static void GenerateDatabarWithRows(string folder, int rows)
    {
        // Step 4: Create another generator for the same barcode type and text
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // Step 5: Configure the barcode to use the supplied number of rows
        // This answers the “how to set rows” query.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = rows;

        // Step 6: Save the second barcode image as PNG
        string filePath = System.IO.Path.Combine(folder, $"DatabarRows{rows}.png");
        barcodeGenerator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Created barcode with {rows} rows: {filePath}");
    }
}
```

### Why This Structure Works

- **Separation of concerns** – each helper focuses on a single configuration (columns vs. rows). That makes the code easier to read and reuse.
- **Explicit parameters** – we pass `columns` or `rows` as arguments, so you can call the same method with any value without editing the body.
- **Immediate feedback** – `Console.WriteLine` tells you exactly where the file landed, which is handy when you run the program from a terminal.

## How to Set Columns for DataBar Expanded Stacked

The `DataBar.Columns` property is the knob that determines how many vertical slices the barcode will contain. The default is `4`, but you might need `2` or `6` depending on the amount of data you encode or the scanner’s requirements. Here’s a quick snippet that isolates the column‑setting logic:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Columns = 5;   // ← change this number as needed
generator.Save("databar_columns5.png", BarCodeImageFormat.Png);
```

**Pro tip:** When you increase columns, the overall width of the barcode grows proportionally. If you plan to embed the image in a PDF or a web page, make sure the container can accommodate the extra width, otherwise the scanner may misread it.

## How to Set Rows for DataBar Expanded Stacked

Rows work the same way, but they affect the barcode’s height. The default row count is `3`. If your label has limited vertical space, you might drop it to `2`. Conversely, more rows can improve readability on low‑resolution printers.

```csharp
var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Sample Text");
generator.Parameters.Barcode.DataBar.Rows = 2;   // ← adjust rows here
generator.Save("databar_rows2.png", BarCodeImageFormat.Png);
```

**Watch out:** Setting rows to a value lower than the minimum required for the encoded data will cause an exception at runtime. The library throws `ArgumentException` with a clear message, so you’ll know instantly if the configuration is invalid.

## Generate Barcode Image – Saving as PNG

Both helpers above end with a call to `Save`. The `BarCodeImageFormat.Png` enum tells Aspose.BarCode to output a loss‑less PNG file, which is ideal for most scanning scenarios because it preserves sharp edges. If you prefer a different format (JPEG for web, BMP for legacy systems), just swap the enum value—no other code changes needed.

```csharp
generator.Save("mybarcode.jpeg", BarCodeImageFormat.Jpeg);
```

The generated PNGs look like this (imagine the image; alt text below describes it):

> **Alt text for the generated images:** *DataBar Expanded Stacked barcode with 4 columns (left) and 3 rows (right), rendered in high‑contrast black on a transparent background.*

## Create DataBar Barcode – Full Working Example

Putting everything together, here’s a compact version you can drop straight into `Program.cs`. It demonstrates both column and row configuration, plus a quick sanity check that the files exist after saving.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Demo
{
    static void Main()
    {
        string outDir = Directory.GetCurrentDirectory();

        // ---------- Create barcode with custom columns ----------
        var colGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        colGen.Parameters.Barcode.DataBar.Columns = 4;   // how to set columns
        string colPath = Path.Combine(outDir, "DatabarCols4.png");
        colGen.Save(colPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved column barcode → {colPath}");

        // ---------- Create barcode with custom rows ----------
        var rowGen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked,
                                          "Databar Expanded Stacked long");
        rowGen.Parameters.Barcode.DataBar.Rows = 3;      // how to set rows
        string rowPath = Path.Combine(outDir, "DatabarRows3.png");
        rowGen.Save(rowPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved row barcode → {rowPath}");

        // ---------- Verify files exist ----------
        Console.WriteLine(File.Exists(colPath)
            ? "✅ Column image generated successfully."
            : "❌ Column image missing.");
        Console.WriteLine(File.Exists(rowPath)
            ? "✅ Row image generated successfully."
            : "❌ Row image missing.");
    }
}
```

### Expected Output

When you run the program (`dotnet run`), you should see console lines similar to:

```
Saved column barcode → C:\MyProject\DatabarCols4.png
Saved row barcode → C:\MyProject\DatabarRows3.png
✅ Column image generated successfully.
✅ Row image generated successfully.
```

Open the two PNG files in any image viewer; you’ll notice the left file has four vertical modules (columns) while the right file is three modules tall (rows). Both are perfectly scannable with any standard DataBar reader.

## Common Pitfalls & How to Avoid Them

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `ArgumentException: Columns value is out of range` | Columns set to 0 or > 8 (the library caps at 8). | Stick to values between **1** and **8**. |
| Barcode appears blurry in PDF | PNG saved at default DPI (96) and then scaled. | Use `generator.Parameters.ImageResolution = 300;` before saving. |
| Scanner fails on rows‑only configuration | Rows changed but columns left at default that don’t match data length. | Adjust both rows **and** columns together, or let the library auto‑size by omitting manual settings. |

## Next Steps

Now that you know how to **generate barcode image**, **set columns**, **set rows**, and **create databar barcode** with **barcode generator c#**, you can:

- Embed the PNGs into PDFs using `Aspose.PDF` or `iTextSharp`.
- Switch to `EncodeTypes.DatabarLimited` if you need a smaller footprint.
- Experiment with colors (`generator.Parameters.Barcode.ForeColor = Color.Blue`).
- Add QR codes or other symbologies in the same project—Aspose.BarCode supports over 150 types.

If you hit any snags, drop a comment below or check the official Aspose.BarCode documentation (the API reference is exhaustive and includes dozens of live code samples). Happy coding, and may your scanners never miss a mark!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}