---
category: general
date: 2026-09-29
description: Learn how to create a Databar Expanded Stacked barcode and generate barcode
  image in C#. This step‑by‑step guide shows how to set rows and columns using BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: en
lastmod: 2026-09-29
og_description: Databar Expanded Stacked barcode generation in C# explained. Follow
  the tutorial to create barcode images, set rows, and save PNG files with BarcodeGenerator.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: Databar Expanded Stacked barcode generation in C# – complete guide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Databar Expanded Stacked barcode generation in C#
url: /python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar Expanded Stacked barcode generation in C#

If you need to generate a **Databar Expanded Stacked** barcode in C#, this guide shows you exactly **how to create barcode** images with custom rows and columns. You’ll see **how to set rows**, how to set columns, and how to **generate barcode image** files using the Aspose.BarCode `BarcodeGenerator` class.

In this tutorial you will:

* Install the required NuGet package.
* Initialize a `BarcodeGenerator` for the Databar Expanded Stacked symbology.
* Configure the number of columns and rows.
* Save the resulting PNG files.
* Understand common pitfalls such as missing licenses or incorrect image paths.

The only prerequisites are a recent .NET SDK (≥ .NET 6) and an IDE such as Visual Studio 2022. No external services are required.

## Install and configure BarcodeGenerator C# library

Before writing any code, add the Aspose.BarCode package to your project:

```bash
dotnet add package Aspose.BarCode
```

If you are using Visual Studio, you can also install it via the **NuGet Package Manager** (search for *Aspose.BarCode*). After the package restores, you can start coding.

> **Pro tip:** The free evaluation version adds a small watermark to generated barcodes. For production use, obtain a license file and call `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` before creating any barcode objects.

## Generate a Databar Expanded Stacked barcode image

Create a new console application (or integrate the code into any C# project) and add the following `using` statements:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Now write the full program. The code follows the exact steps from the original example and adds explanatory comments.

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Why each step matters

* **Step 1** creates a `BarcodeGenerator` bound to the *Databar Expanded Stacked* symbology, which is required for GS1‑compatible retail scanning.
* **Step 2** demonstrates **how to set rows** indirectly by first adjusting columns—this shows that column and row settings are independent.
* **Step 3** persists the image, allowing you to verify the visual impact of the column count.
* **Step 4** re‑initializes the generator so that row configuration does not inherit the previously set column value, a common source of confusion.
* **Step 5** explicitly shows **how to set rows**, which is the main focus of the secondary keyword.
* **Step 6** saves the second image, giving you a side‑by‑side comparison of column‑ vs. row‑based density.

Running the program produces two PNG files in the output directory:

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

Open either file with an image viewer to confirm that the barcode renders correctly.

## Common variations and edge cases

| Scenario | What to change | Reason |
|----------|----------------|--------|
| **Different data payload** | Replace the second argument of `BarcodeGenerator` with your own string (e.g., `"123456789012"`). | The barcode encodes the supplied text; make sure it complies with GS1 rules for Databar. |
| **Other image formats** | Use `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp`. | Choose a format that matches your downstream processing pipeline. |
| **Higher resolution** | Call `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);` where the last argument is DPI. | Improves readability when printing large labels. |
| **License handling** | Add the `License` code snippet before any generator creation. | Removes the evaluation watermark and unlocks full functionality. |

## Tips for reliable barcode generation

* **Validate the input string** – Databar Expanded Stacked expects numeric data up to 70 characters. Supplying non‑numeric characters may cause an exception.
* **Check file paths** – Use `Path.Combine(Environment.CurrentDirectory, "output.png")` to avoid hard‑coded directories that may not exist on the target machine.
* **Dispose objects** – `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block if you generate many barcodes in a loop to free native resources promptly.

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## Conclusion

You now know **how to create a Databar Expanded Stacked barcode** and **how to set rows** (and columns) using the **barcode generator C#** API, and you can **generate barcode image** files in PNG format. By following the complete example above you can integrate Databar barcodes into inventory systems, point‑of‑sale applications, or any .NET solution that needs high‑density GS1 barcodes.

**Next steps**

* Experiment with other symbologies such as `EncodeTypes.DatabarExpanded` or `EncodeTypes.QR`.  
* Explore the `BarcodeReader` class to verify that your generated images are scannable.  
* Combine barcode generation with PDF creation (e.g., using `Aspose.PDF`) to produce printable labels.

Happy coding!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to set columns for a Databar Expanded Stacked barcode – complete C# guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [How to change barcode size in C# with DataBar Stacked](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked: generate barcode image in C#](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}