---
category: general
date: 2026-10-12
description: How to generate barcode in C# quickly. Learn to create empty barcode
  and customize bar width for clear postal barcodes.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: en
lastmod: 2026-10-12
og_description: How to generate barcode in C# using Aspose.BarCode. This guide shows
  you how to create empty barcode and adjust bar dimensions for postal standards.
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: How to generate barcode images in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: How to generate barcode images in C# with Aspose.BarCode
url: /python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to generate barcode images in C# with Aspose.BarCode

If you need to **how to generate barcode** images from a string in a .NET application, this guide provides a complete, ready‑to‑run solution. You’ll see how to generate standard Planet and RM4SCC barcodes, adjust bar width for readability, and **create empty barcode** variants where the bars are unfilled. The code works with the latest Aspose.BarCode for .NET (v.24.10) and runs on .NET 6 or later.

Generating barcodes is a common requirement for shipping labels, inventory systems, and ticketing platforms. By the end of this tutorial you will be able to produce both filled and empty barcodes programmatically, without needing external tools.

## Prerequisites

Before you start, make sure you have:

* .NET 6 SDK (or any newer .NET version)
* Visual Studio 2022 or VS Code
* A valid Aspose.BarCode for .NET license (the free evaluation works for testing)
* Basic familiarity with C# console applications

You can install the Aspose.BarCode NuGet package with:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Set up a minimal console project

Create a new console project and add the required `using` directives. The following code is a self‑contained example; copy it into `Program.cs` and run it.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### Why this step matters

* **Project scaffolding** ensures the tutorial is runnable without extra configuration.
* The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;` namespaces expose the `BarcodeGenerator` class and image formats.
* Creating the output folder programmatically avoids “directory not found” errors on first run.

## Step 2: Generate a filled Planet barcode

The first call to `GeneratePlanetBarcode` passes `filled: true`. This produces a standard Planet barcode where each bar is rendered as a solid, black rectangle.

* **Resulting file:** `PostalPlanetFilledBars.png`
* **Visual cue:** Bars appear black, matching postal specifications for printed mail.

### Expected output

Running the program will create an image similar to the one below (the actual image is not displayed here, but you’ll see a clear, 6‑digit barcode when you open the file).

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## Step 3: Create empty barcode (Planet with unfilled bars)

To **create empty barcode**, the same method is called with `filled: false`. The `FilledBars` property tells Aspose.BarCode to draw only the outlines of the bars, leaving the interior transparent.

* **Resulting file:** `PostalPlanetEmptyBars.png`
* **Use case:** Empty barcodes are useful when you want the background to show a logo or color while still maintaining barcode readability.

### Expected output

The generated PNG contains only the bar outlines:

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## Step 4: Generate a filled RM4SCC barcode

RM4SCC is the Dutch postal barcode standard. The example uses the same X‑dimension (4 pixels) to keep visual consistency with the Planet barcodes.

* **Resulting file:** `PostalRM4SCCFilledBars.png`
* **Why RM4SCC?** It encodes numeric data in a compact format that many European postal services accept.

### Expected output

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## Practical tips and common pitfalls

| Tip | Explanation |
|-----|-------------|
| **Consistent X‑dimension** | Using the same `XDimension.Pixels` value across different symbologies ensures a uniform appearance on printed labels. |
| **Do not reuse the same generator instance** | Changing `FilledBars` on an existing generator can produce unexpected results; instantiate a new `BarcodeGenerator` for each distinct barcode. |
| **Verify image format** | PNG is lossless and ideal for barcodes; JPEG compression may blur thin bars, causing scan failures. |
| **License handling** | If you run the code without a license, the generated images will contain a watermark. Apply your license early in `Main` with `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`. |
| **Thread safety** | `BarcodeGenerator` is **not** thread‑safe. Create separate instances per thread if you generate barcodes in parallel. |

## Edge cases you might encounter

* **Data length limits** – Planet barcodes accept up to 6 numeric characters. Supplying more characters throws an `ArgumentException`. Validate input length before calling the generator.
* **Non‑numeric data** – RM4SCC also expects numeric input. For alphanumeric data you need a different symbology (e.g., Code128). The same pattern of setting `FilledBars` works for any barcode type that supports it.
* **High‑resolution printing** – If you need barcodes larger than on‑screen size, increase `XDimension.Pixels` (e.g., 8 or 10) and optionally set `Resolution` in `generator.Parameters.Image`. This keeps the bars crisp at 300 dpi printing.

## Full source file recap

Below is the entire source file again for quick copy‑paste. It includes all steps, comments, and the optional license snippet (commented out).

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## Conclusion

You now know **how to generate barcode** images in C# using Aspose.BarCode, and you can **create empty barcode** variants by toggling the `FilledBars` property. The tutorial covered:

* Setting up a console project and installing the Aspose.BarCode package
* Generating filled Planet and RM4SCC barcodes
* Producing an empty (outline‑only) Planet barcode
* Adjusting bar width for readability and handling common pitfalls

Next, explore other symbologies (Code128, QR, DataMatrix) and experiment with color, size, and image formats. Integrating barcode generation into a web API or a Windows service follows the same pattern—just replace the console `Main` method with your application’s entry point.

Happy coding, and let your applications start scanning!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}