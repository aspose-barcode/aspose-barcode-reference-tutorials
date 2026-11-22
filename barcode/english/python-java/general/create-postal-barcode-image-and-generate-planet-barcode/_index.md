---
category: general
date: 2026-11-20
description: Create postal barcode image in C# quickly. Learn how to generate planet
  barcode and RM4SCC barcodes with customizable bar styles.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: en
lastmod: 2026-11-20
og_description: Create postal barcode image in C# with Aspose.BarCode. This tutorial
  shows how to generate planet barcode, customize bar styles, and produce RM4SCC images.
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: Create postal barcode image in C# – step‑by‑step guide
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Create postal barcode image and generate planet barcode
url: /python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create postal barcode image and generate planet barcode

Create postal barcode image in C# using the Aspose.BarCode library. If you need to generate planet barcode or RM4SCC barcodes for mailing applications, this tutorial provides a complete, ready‑to‑run solution.

Generating barcodes for postal services often requires precise dimensions and the option to switch between filled and empty bar styles. This guide walks you through setting up the output folder, creating both filled and empty Planet barcodes, and producing an RM4SCC barcode with the same visual settings. By the end you will have four PNG files you can use directly in your mailing workflow.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed  
* Visual Studio 2022 (or any C# IDE you prefer)  
* The **Aspose.BarCode** NuGet package (`Install-Package Aspose.BarCode`)  

No additional configuration is required; the code uses only the default font and PNG encoder.

## Create postal barcode image – overview

The core of the process is the `BarcodeGenerator` class. It accepts an `EncodeTypes` value that determines the barcode symbology (for example, `EncodeTypes.Planet` for a Planet barcode). After configuring the generator, you call `Save` to write the image file.

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: Create postal barcode image example showing filled and empty bars.*

## Step 1: Set up the output folder

First define a folder where the PNG files will be saved. Using an absolute or relative path works the same; just ensure the folder exists or let the code create it.

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

Creating the folder programmatically prevents `DirectoryNotFoundException` when the tutorial runs on a fresh machine.

## Step 2: Generate planet barcode with filled bars

A filled‑bar Planet barcode is the default visual style. The following code creates the barcode, sets the X‑dimension to 4 pixels (a common size for postal applications), and saves the image.

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**Why this works:**  
* `EncodeTypes.Planet` tells the generator to use the Planet symbology, which is required for many postal services.  
* `XDimension.Pixels` controls the width of each bar; 4 px yields a clear, scannable image without excessive file size.  
* The `Save` method automatically selects the PNG encoder based on the `BarCodeImageFormat` enum.

## Step 3: Generate planet barcode with empty bars

Some postal specifications prefer empty (white) bars on a dark background. You can achieve this by setting `FilledBars` to `false`.

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**Tip:** When `FilledBars` is `false`, the generator paints the bars in the background color (white by default) and the spaces in the foreground color (black). If you need a different color scheme, adjust `Parameters.Barcode.ForeColor` and `BackColor`.

## Step 4: Generate RM4SCC barcode with filled bars

RM4SCC is another postal symbology used in the United Kingdom. The creation steps mirror the Planet example; only the `EncodeTypes` value changes.

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**What to expect:** The resulting PNG displays a compact RM4SCC barcode that complies with UK postal guidelines. The image size will be similar to the Planet barcodes because the X‑dimension is identical.

## Step 5: Verify the generated images

After running the program, open the four files in the `Barcodes` folder. You should see:

* `PostalPlanetFilledBars.png` – dark bars on a light background  
* `PostalPlanetEmptyBars.png` – light bars on a dark background (inverse)  
* `PostalRM4SCCFilledBars.png` – standard RM4SCC pattern  

If any image looks distorted, check the following:

* **X‑dimension** – too small (< 2 px) can cause blurring; too large (> 10 px) may exceed label size limits.  
* **Data string** – the value `"123456"` must meet the length requirements of the chosen symbology (Planet expects 6 digits, RM4SCC expects 6 digits as well).  
* **Folder permissions** – ensure the application has write access to the output directory.

## Common variations and edge cases

| Scenario | Adjustment |
|----------|------------|
| **Different barcode data** | Replace `"123456"` with any valid numeric string. For Planet, the length must be exactly 6 digits; RM4SCC also requires 6 digits. |
| **Custom colors** | Set `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` and `BackColor = System.Drawing.Color.LightYellow;`. |
| **Higher resolution** | Increase `XDimension.Pixels` to 6 or 8 for larger prints. |
| **Other image formats** | Use `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Bmp` in the `Save` call. |
| **Batch generation** | Loop over a collection of strings and call the same generator logic inside the loop, reusing the `outputFolder` path. |

## Full, runnable example

Copy the code below into a new C# console project. It compiles with .NET 6.0 and produces all four barcode images automatically.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the output folder
            string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate a Planet barcode with filled bars
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters =
                {
                    Barcode = { XDimension = { Pixels = 4 } }
                }
            };
            planetFilled.Save(Path.Combine(outputFolder, "PostalPlanetFilledBars.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate a Planet barcode with empty bars
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters =
                {
                    Barcode =
                    {
                        XDimension = { Pixels = 4 },
                        FilledBars = false
                    }
                }
            };
            planetEmpty.Save(Path.Combine(outputFolder, "PostalPlanetEmptyBars.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate an RM4SCC barcode with filled bars
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters =
                {
                    Barcode = { XDimension = { Pixels = 4 } }
                }
            };
            rm4sccFilled


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create postal barcode image with custom heights in C#](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [How to create RM4SCC barcode and generate planet barcode in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}