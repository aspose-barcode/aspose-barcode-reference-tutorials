---
category: general
date: 2026-09-19
description: barcode generator example showing how to change height, create DataBar
  Omni‑Directional, and adjust barcode dimensions for C# image output
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: en
lastmod: 2026-09-19
og_description: barcode generator example that teaches how to change height, create
  DataBar Omni‑Directional, and adjust barcode dimensions for a C# PNG image
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Barcode generator example in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: How to build a barcode generator example in C#
url: /python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator example in C# – complete programming guide

If you need a **barcode generator example** for a .NET project, this guide shows you exactly how to create, configure, and save a DataBar Omni‑Directional barcode using C#. You’ll learn how to change height, adjust barcode dimensions, and output a high‑quality PNG image—all in a single, runnable console application.

The steps below cover everything from installing the required SDK to tweaking the X‑dimension and bar height. By the end of the tutorial you’ll have a ready‑to‑use barcode generator that you can integrate into invoicing, inventory, or any scanning workflow.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any IDE that supports .NET)  
* An active license for **Aspose.BarCode for .NET** (the free trial works for testing)  

If you prefer a different library, the concepts of adjusting dimensions and saving the image remain the same; just replace the API calls accordingly.

## Step 1: Set up the project and add the Aspose.BarCode package

Create a new console project and reference the barcode library.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

The `dotnet add package` command pulls the latest stable version of Aspose.BarCode, which includes full support for DataBar Omni‑Directional symbols.

## Step 2: Write the complete barcode generator example

Open **Program.cs** and replace its content with the following code. This block contains the full **barcode generator example**—no missing pieces.

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Why each line matters

* **Create a barcode generator** – The `BarcodeGenerator` constructor ties the encoding type (`EncodeTypes.DatabarOmniDirectional`) to the data you want to embed. This is the core of the **how to create databar** step.
* **Adjust barcode dimensions** – The `XDimension.Pixels` property defines the width of the narrowest bar. Changing this value influences the overall size and scan reliability.
* **How to change height** – The `BarHeight.Pixels` property controls vertical size. Increasing height improves readability for handheld scanners, while decreasing it saves space on small labels.
* **Optional tweaks** – Setting foreground/background colors or error‑correction levels is optional but demonstrates how to extend the **adjust barcode dimensions** concept.
* **Create barcode image C#** – The `Save` method writes the barcode to disk. Using `BarCodeImageFormat.Png` ensures lossless compression, which is ideal for most applications.

## Step 3: Build and run the example

Compile and execute the program:

```bash
dotnet run
```

You should see the console output:

```
Barcode saved to DatabarOmniDirectional.png
```

A file named **DatabarOmniDirectional.png** appears in the project folder. Opening the image reveals a crisp DataBar Omni‑Directional barcode ready for scanning.

## How to change height after the fact

If you need to generate barcodes with varying heights, wrap the height assignment in a method:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Call `SetBarHeight(generator, 45);` before `Save`. This approach lets you **how to change height** dynamically based on user input or configuration files.

## How to create DataBar Omni‑Directional barcodes with different data

The DataBar Omni‑Directional symbology supports GTIN‑14, GTIN‑13, and other numeric identifiers. To encode a different value, simply replace the string in the constructor:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Remember to keep the data numeric and properly formatted; otherwise the generator throws a `BarcodeException`.

## Adjust barcode dimensions for different printing scenarios

Different printers and label sizes demand different X‑dimensions and heights. Use the following table as a quick reference:

| Scenario                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| Small label (25 mm × 15 mm)  | 1                    | 20                  |
| Medium label (50 mm × 30 mm) | 2                    | 30                  |
| Large label (100 mm × 50 mm) | 3                    | 45                  |

Apply these values by setting `generator.Parameters.Barcode.XDimension.Pixels` and `BarHeight.Pixels` accordingly.

## Pro tip: validate the generated barcode

Before shipping a label, you can verify its readability programmatically:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

This snippet demonstrates a quick **adjust barcode dimensions** sanity check, ensuring the barcode meets scanning requirements.

## Common pitfalls and how to avoid them

| Pitfall                              | Why it happens                              | Fix                                                                 |
|--------------------------------------|---------------------------------------------|---------------------------------------------------------------------|
| Using non‑numeric data for DataBar    | DataBar expects numeric GTIN formats        | Ensure the string matches the `(01)XXXXXXXXXXXXX` pattern.         |
| Setting X‑dimension to 0 or negative  | Library throws `ArgumentOutOfRangeException`| Use a minimum of 1 pixel; test on target printer first.            |
| Saving to a read‑only folder          | `UnauthorizedAccessException` on `Save`     | Choose a writable directory or run the app with appropriate rights.|
| Forgetting to dispose `BarCodeReader` | Memory leak in long‑running services        | Wrap the reader in a `using` block or call `Dispose()` manually.   |

Addressing these issues early saves debugging time and improves production stability.

## Full source code recap

Below is the complete, ready‑to‑copy program that implements the **barcode generator example** from start to finish.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Running this program produces a PNG file that looks like this (illustrative):

![DataBar Omni‑Directional barcode generated in C#](https://example.com/og-image.png "DataBar Omni‑Directional barcode generated in C#")

*Image alt text*: **DataBar Omni‑Directional barcode generated in C#** (matches `og_image_alt`).

## Conclusion

You now have a **barcode generator example** that demonstrates how to change height, how to create DataBar Omni‑Directional symbols, and how to **adjust barcode dimensions** for optimal scanning. The complete C# code saves a PNG image, validates it, and can be extended for bulk generation or integration into web services.

Next, explore related topics such as **creating QR codes with Aspose.BarCode**, **batch processing multiple barcode values**, or **embedding barcodes into PDF documents**. Each of these builds on the same fundamentals covered in this guide.

Happy coding, and may your barcodes always be scannable!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}