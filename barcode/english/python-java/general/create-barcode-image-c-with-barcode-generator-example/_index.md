---
category: general
date: 2026-09-10
description: Create barcode image C# quickly using a barcode generator example C#
  that shows how to set dimensions and save PNG files.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image c#
- barcode generator example c#
language: en
lastmod: 2026-09-10
og_description: Create barcode image C# with a concise barcode generator example C#.
  Learn to configure size, height, and export PNG files in minutes.
og_image_alt: Screenshot of a barcode image created with C# code
og_title: Create barcode image C# – step‑by‑step generator example
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Create barcode image C# quickly using a barcode generator example C#
    that shows how to set dimensions and save PNG files.
  headline: Create barcode image C# with barcode generator example
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Create barcode image C# with barcode generator example
url: /python-java/general/create-barcode-image-c-with-barcode-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode image C# with barcode generator example

If you need to **create barcode image C#** for product labeling, inventory tracking, or mobile scanning, this guide shows a complete solution. You’ll see a **barcode generator example C#** that configures module width, bar height, and saves PNG files in just a few lines of code.

The tutorial covers everything from installing the required library to running a ready‑to‑compile console program. By the end, you will have two barcode PNG files—one with a 30‑pixel bar height and another with a 60‑pixel bar height—ready for use in any .NET application.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* A development environment such as Visual Studio 2022 or VS Code  
* The **Aspose.BarCode** NuGet package (the code uses `BarcodeGenerator` from this library)  

You can add the package with the following CLI command:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up the console project

Create a new console project and reference the barcode library.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

The command creates a `Program.cs` file where you will place the **barcode generator example C#** code.

## Step 2: Write the full barcode generation program

Replace the contents of `Program.cs` with the complete, runnable example below. The program demonstrates how to **create barcode image C#** with custom dimensions and how to save the result as PNG files.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a DataBar Omnidirectional barcode generator with the desired data.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set the X‑dimension (module width) to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Configure a 30‑pixel bar height and save the first image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            SaveBarcode(generator, "DatabarBarHeight30Pixels.png");

            // 4️⃣ Change the bar height to 60 pixels and save the second image.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            SaveBarcode(generator, "DatabarBarHeight60Pixels.png");

            Console.WriteLine("Barcode images have been saved to the output folder.");
        }

        /// <summary>
        /// Saves the current barcode image as a PNG file.
        /// </summary>
        /// <param name="generator">The configured BarcodeGenerator instance.</param>
        /// <param name="fileName">The file name for the PNG image.</param>
        private static void SaveBarcode(BarcodeGenerator generator, string fileName)
        {
            // Ensure the output directory exists.
            string outputPath = System.IO.Path.Combine(
                AppDomain.CurrentDomain.BaseDirectory, "output");
            System.IO.Directory.CreateDirectory(outputPath);

            // Combine the directory and file name.
            string fullPath = System.IO.Path.Combine(outputPath, fileName);

            // Save the barcode as a PNG image.
            generator.Save(fullPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Why each line matters

* **EncodeTypes.DatabarOmniDirectional** – selects the DataBar Omnidirectional symbology, which encodes numeric data and is widely used in retail.  
* **XDimension.Pixels = 2** – sets the module width; a smaller value yields a more compact barcode.  
* **BarHeight.Pixels** – controls the visual height of the bars. Adjusting this value lets you create barcodes that fit different label sizes.  
* **Save method** – writes the barcode to a PNG file, a format that preserves sharp edges and works with most imaging libraries.

## Step 3: Build and run the program

Execute the following command from the project folder:

```bash
dotnet run
```

When the program finishes, you will see two PNG files in the `output` subfolder:

* `DatabarBarHeight30Pixels.png` – 30‑pixel bar height  
* `DatabarBarHeight60Pixels.png` – 60‑pixel bar height  

Both images contain the same encoded data but differ in visual height, illustrating how the **barcode generator example C#** can be adapted for various label requirements.

## Step 4: Verify the generated barcodes

Open the PNG files with any image viewer. You should see a clear, high‑contrast DataBar barcode. To confirm that the barcodes are readable, you can use a mobile scanner app (e.g., ZXing‑based apps) or a desktop library such as **Aspose.BarCode** in decode mode:

```csharp
var reader = new BarCodeReader(fullPath, DecodeType.DatabarOmniDirectional);
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"Decoded value: {result.CodeText}");
}
```

If the output matches `(01)12345678901231`, the generation succeeded.

## Common variations and edge cases

| Situation | Adjustment | Code snippet |
|-----------|------------|--------------|
| **Different symbology** (e.g., QR, Code128) | Change `EncodeTypes` value | `new BarcodeGenerator(EncodeTypes.QR, "Hello World")` |
| **Custom image format** (JPEG, BMP) | Use a different `BarCodeImageFormat` enum | `generator.Save(path, BarCodeImageFormat.Jpeg)` |
| **Dynamic data** (user input) | Replace the hard‑coded string with a variable | `string data = Console.ReadLine(); var generator = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data);` |
| **Invalid data length** | Catch `ArgumentException` thrown by the generator | ```csharp try { ... } catch (ArgumentException ex) { Console.WriteLine(ex.Message); }``` |

Pro tip: always validate the input length for the selected symbology; Aspose.BarCode throws an exception if the data does not meet the specification.

## Troubleshooting checklist

* **Directory not found** – The `SaveBarcode` helper creates the `output` folder automatically, but ensure the application has write permissions.  
* **Unexpected image size** – Verify that `XDimension.Pixels` and `BarHeight.Pixels` are set before calling `Save`. Changing these values after saving does not affect already written files.  
* **Unreadable barcode** – Make sure the encoded string follows the GS1 format when using DataBar symbologies. Missing parentheses or incorrect Application Identifiers cause decoding failures.

## Conclusion

You now know how to **create barcode image C#** using a practical **barcode generator example C#**. The complete program sets module width, adjusts bar height, and saves PNG files with minimal code. From here you can explore additional features such as color customization, multi‑page PDF export, or real‑time generation in ASP.NET Core web APIs.

**Next steps**

* Experiment with other symbologies (`EncodeTypes.Code128`, `EncodeTypes.QR`) to broaden your scanning options.  
* Integrate the generator into a web service that returns barcode images on demand.  
* Combine the barcode with product metadata in a PDF invoice using Aspose.PDF.

Happy coding, and enjoy the flexibility that C# provides for barcode image creation!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}