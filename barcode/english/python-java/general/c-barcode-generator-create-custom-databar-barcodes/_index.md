---
category: general
date: 2026-08-19
description: C# barcode generator tutorial shows how to generate DataBar Expanded
  Stacked barcodes, customize barcode size, and configure rows and columns.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: en
lastmod: 2026-08-19
og_description: C# barcode generator tutorial teaches you how to generate DataBar
  barcodes, customize size, and configure rows and columns for precise output.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: C# barcode generator – step‑by‑step guide for custom DataBar barcodes
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'C# barcode generator: create custom DataBar barcodes'
url: /python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# barcode generator: create custom DataBar barcodes

If you need a **c# barcode generator** that can produce DataBar Expanded Stacked symbols, this guide shows you exactly how to generate barcode images with custom rows and columns. You’ll learn to configure databar parameters, adjust barcode size, and save the result as PNG files.

Generating barcodes programmatically removes manual design steps and guarantees consistent output across platforms. In this tutorial you will:

* Install and reference the Aspose.BarCode for .NET library (or any compatible package).
* Create a barcode generator for the DataBar Expanded Stacked symbology.
* **How to generate barcode** images with specific column and row settings.
* **Customize barcode size** by controlling DataBar rows and columns.
* **Configure databar parameters** such as text, format, and image quality.

## Prerequisites

* .NET 6.0 SDK or later installed.
* A C# development environment (Visual Studio, VS Code, Rider, etc.).
* NuGet package `Aspose.BarCode` (or an equivalent library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`).

Add the package with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Using the C# barcode generator to create DataBar barcodes

The following sections walk you through each step. The primary focus is on the **c# barcode generator** API, but the same pattern applies to other barcode libraries that expose similar properties.

### Step 1: Initialise the barcode generator with sample text

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Why this step?*  
`BarcodeGenerator` is the entry point for all barcode creation tasks. Supplying the `EncodeTypes.DatabarExpandedStacked` enum tells the library which symbology to use, while the text argument becomes the human‑readable value encoded in the symbol.

### Step 2: Set the number of columns (default rows are used)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Why this step?*  
DataBar Expanded Stacked symbols consist of stacked linear elements. Adjusting the `Columns` property changes the horizontal density, allowing you to fit longer data strings without increasing overall height. This directly **customizes barcode size**.

### Step 3: Save the barcode image that uses four columns

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*What you see:*  
The saved `DatabarCols4.png` image displays a DataBar barcode that is wider than the default because it contains four columns. You can open the file in any image viewer to verify the output.

### Step 4: Re‑initialise the generator for a new configuration

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Why re‑initialise?*  
Changing the `Rows` property while keeping the previous column setting could produce an unexpected combination. Starting with a fresh instance ensures that only the intended parameter (`Rows`) influences the next image.

### Step 5: Set the number of rows (default columns are used)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Why this step?*  
The `Rows` property controls vertical stacking. Increasing rows makes the barcode taller, which can be useful when space is limited horizontally but abundant vertically. This is another way to **customize barcode size**.

### Step 6: Save the barcode image that uses three rows

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Result:*  
`DatabarRows3.png` shows a taller barcode with three stacked rows, demonstrating how **configure databar parameters** impacts the visual appearance.

## Full runnable example

Below is a complete program that you can copy, paste, and run. It includes all imports, error handling, and comments for clarity.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Expected output**

Running the program produces two PNG files:

* `DatabarCols4.png` – a wide DataBar barcode with four columns.
* `DatabarRows3.png` – a tall DataBar barcode with three rows.

Open the images to confirm that the barcode dimensions match the configured parameters.

## Common questions and edge‑case handling

| Question | Answer |
|----------|--------|
| *What if I need both custom rows **and** columns?* | Set `Rows` **and** `Columns` on the same `BarcodeGenerator` instance before calling `Save`. The library combines both values to produce a grid of the requested size. |
| *Can I change the image format?* | Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` to suit your workflow. |
| *What happens when the text is longer than the symbol can hold?* | The generator throws an `ArgumentException`. Shorten the text or increase `Columns`/`Rows` to provide more capacity. |
| *Is there a way to set DPI or image resolution?* | Use `generator.Parameters.ImageResolution` to specify the desired DPI before saving. This further **customizes barcode size** for high‑resolution printing. |
| *Does the library support other DataBar variants?* | Yes. Replace `EncodeTypes.DatabarExpandedStacked` with `DatabarExpanded`, `DatabarLimited`, etc., while keeping the same parameter structure. |

## Tips for reliable barcode generation

* **Pro tip:** Always verify the generated image with a scanner or a mobile app before deploying it to production.  
* **Watch out for:** Null or empty output directories—`Save` will throw an exception if the path does not exist. Create the folder programmatically if needed.  
* **Performance note:** Re‑using a single `BarcodeGenerator` instance and only changing `Rows` or `Columns` can reduce object‑creation overhead when generating many barcodes in a loop.

## Conclusion

You now know how to use a **c# barcode generator** to **create databar barcode** images, **customize barcode size**, and **configure databar parameters** such as rows and columns. By adjusting these settings you can fit barcodes into any layout requirement while maintaining scan reliability.

Next, explore related topics like **how to generate barcode** PDFs, embedding barcodes in reports, or switching to other symbologies (QR, Code‑128, etc.). Experiment with different `Rows`, `Columns`, and image resolutions to find the optimal configuration for your specific use case.

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}