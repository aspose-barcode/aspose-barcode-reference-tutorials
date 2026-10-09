---
category: general
date: 2026-09-26
description: barcode generator C# guide shows how to set rows and how to set columns
  when creating Databar Expanded Stacked barcodes in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: en
lastmod: 2026-09-26
og_description: barcode generator C# tutorial explains how to set rows and how to
  set columns for Databar Expanded Stacked barcodes, with full code and tips.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Barcode generator C# – set rows and columns step by step
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: How to use barcode generator C# for rows and columns
url: /python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use barcode generator C# for rows and columns

If you need a **barcode generator C#** that lets you control the visual layout of a Databar Expanded Stacked barcode, this tutorial gives you a complete, runnable solution. You’ll learn **how to set rows** and **how to set columns** so the generated image matches the exact design you require.

Generating barcodes programmatically often feels like guessing which property does what. By the end of this guide you’ll understand the API surface, avoid common pitfalls, and have a ready‑to‑run code sample that you can copy into your own project.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed (the code works with .NET Core and .NET Framework as well)
* A reference to the barcode‑generation library that provides `BarcodeGenerator` and `EncodeTypes` (for example, Aspose.BarCode, Dynamsoft, or any compatible SDK)
* An IDE such as Visual Studio or VS Code
* Write permission to a folder where the PNG files will be saved

No additional NuGet packages are required beyond the barcode SDK itself.

## Barcode generator C# – setting rows and columns

The following sections walk through each configuration step. The code snippets are complete and can be pasted directly into a console application’s `Main` method.

### Step 1: Create a generator for a Databar Expanded Stacked barcode

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Why this matters:* Instantiating `BarcodeGenerator` is the first action you take with any **barcode generator C#** workflow. The constructor receives the encoding type and the data string that will be encoded.

### Step 2: How to set columns – configure the barcode to use 4 columns

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Setting the `Columns` property changes the number of vertical modules that the DataBar uses. A value of `4` creates a denser, more compact barcode, which is useful when you have limited horizontal space.

### Step 3: Save the barcode image with the column setting

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

The `Save` method writes the generated image to disk. Verify the output file to confirm that the four‑column layout appears as expected.

![Barcode generator C# example showing rows and columns settings](./images/barcode-rows-columns.png)

*The image above illustrates the result of the column configuration.*

### Step 4: Re‑initialize the generator for a different layout

When you need a separate barcode with a different visual arrangement, create a new instance rather than re‑using the previous one. This guarantees that previous settings (like columns) do not bleed into the new configuration.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Step 5: How to set rows – configure the barcode to use 3 rows

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

The `Rows` property controls the vertical stacking of the DataBar modules. A three‑row layout is the default for many scanning devices, but you can increase it for higher data density.

### Step 6: Save the barcode image that includes the row setting

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Open `DatabarRows3.png` to see the three‑row arrangement. If the barcode does not scan, double‑check the rows/columns values against your scanner’s specifications.

## Full source code – ready to copy

Below is the complete program that combines all the steps above. Replace `YOUR_DIRECTORY` with an absolute or relative path that exists on your machine.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Expected output

Running the program produces two PNG files:

| File name            | Layout description                         |
|----------------------|--------------------------------------------|
| `DatabarCols4.png`   | Databar Expanded Stacked with **4 columns** |
| `DatabarRows3.png`   | Databar Expanded Stacked with **3 rows**    |

Both images should be scannable by standard barcode readers that support the Databar Expanded Stacked symbology.

## Common pitfalls and pro tips

| Pitfall                              | Why it happens                               | Fix / Tip |
|--------------------------------------|----------------------------------------------|-----------|
| Using the same `BarcodeGenerator` instance for both rows and columns | The SDK keeps the previous configuration, so setting rows after columns may produce an unexpected mix | Re‑initialize the generator (as shown in Step 4) before changing the other dimension |
| Forgetting to set `EncodeTypes` correctly | The SDK defaults to a different symbology, leading to an invalid barcode | Always pass `EncodeTypes.DatabarExpandedStacked` when you need this specific format |
| Saving to a non‑existent folder      | `Save` throws an exception if the path is invalid | Ensure `YOUR_DIRECTORY` exists or use `Directory.CreateDirectory` before calling `Save` |
| Using values outside the allowed range (e.g., 0 columns) | The SDK validates the range and throws `ArgumentOutOfRangeException` | Valid column values are 1‑4; valid row values are 1‑3 for this symbology |

### Pro tip

If you need to generate many barcodes with varying rows and columns, wrap the configuration logic in a helper method:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

This approach reduces duplication and makes the code easier to maintain.

## Conclusion

You now have a clear, end‑to‑end example of using a **barcode generator C#** to control both the number of rows and the number of columns in a Databar Expanded Stacked barcode. By following the steps above, you can generate precise barcode images that meet the exact layout requirements of your scanning hardware.

From here you might explore:

* Adjusting other `DataBar` properties such as **AspectRatio** or **BarHeight**
* Generating other symbologies (e.g., QR, Code128) with the same `BarcodeGenerator` class
* Embedding the generated PNG into PDFs or printing directly from C#

Feel free to experiment with different row/column combinations, and share your results in the comments. Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode guide – how to generate and size it in C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}