---
category: general
date: 2026-10-28
description: Create barcode image in C# and learn how to adjust height using the BarcodeGenerator
  API. Step‑by‑step guide for custom barcode height and changing bar height.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: en
lastmod: 2026-10-28
og_description: Create barcode image in C# and instantly see how to adjust height.
  Follow this complete example to set custom barcode height with the BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Create barcode image with custom height in C# – full guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Create barcode image with custom height in C#
url: /python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode image with custom height in C#

If you need to **create barcode image** and control its dimensions, this guide shows you exactly how. Using the Aspose.BarCode .NET library you can generate a GS1‑Databar Omni‑Directional barcode, then **how to adjust height** to meet any layout requirement.

You’ll walk through a complete, runnable program that demonstrates a **c# barcode generator**, explains each property you set, and shows two different outputs—one with a 30‑pixel bar height and another with a 60‑pixel bar height. By the end you’ll be able to **change barcode height** programmatically for any barcode type supported by the library.

## Prerequisites

- .NET 6.0 SDK or later (the code also works with .NET Framework 4.6+)
- Visual Studio 2022 or any editor that can build C# projects
- Aspose.BarCode for .NET NuGet package (`Install-Package Aspose.BarCode`)
- Basic familiarity with C# syntax

> **Pro tip:** If you are using a CI pipeline, add the NuGet package to your `csproj` file so the build restores it automatically.

## Step 1: Set up the project and import namespaces

Create a new console project and add the required `using` statements. The namespaces give you access to `BarcodeGenerator`, `EncodeTypes`, and image‑format helpers.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Why this matters:** Importing the correct namespaces prevents compile‑time errors and makes the API discoverable in IntelliSense.

## Step 2: Initialize the **c# barcode generator** for a GS1‑Databar Omni‑Directional code

The constructor takes two arguments: the barcode type (`EncodeTypes.DatabarOmniDirectional`) and the data string. The data string must follow the GS1 Application Identifier format, e.g., `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Explanation:** The `BarcodeGenerator` object is the entry point for all barcode‑related settings. Once you have this instance you can tweak dimensions, colors, and output format.

## Step 3: Define a common X‑dimension (pixel width of the narrowest bar)

A 2‑pixel X‑dimension is a good starting point for most screen‑display scenarios.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Why set X‑dimension?** It controls the overall width of the barcode. Keeping it consistent ensures that changing the bar height does not distort the visual balance.

## Step 4: **Create barcode image** with a 30‑pixel bar height

Now we configure the bar height, save the first image, then change the height for the second one.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Result:** You get a PNG file where each vertical bar is 30 pixels tall. The X‑dimension remains 2 pixels, so the overall width is unchanged.

## Step 5: **How to adjust height** – change the bar height to 60 pixels

To demonstrate **custom barcode height**, simply assign a new value to the same property and save again.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Key insight:** The `BarHeight` property is mutable; you do not need to recreate the `BarcodeGenerator` instance. This makes it cheap to generate multiple sizes in a loop or batch process.

## Step 6: Verify the output

Run the console program (`dotnet run`). After execution you should see two PNG files in the project’s output folder:

- `DatabarBarHeight30Pixels.png` – short bars (30 px)
- `DatabarBarHeight60Pixels.png` – tall bars (60 px)

Both images contain the same encoded data, but the visual height differs, which is useful when integrating barcodes into forms, product labels, or UI components with varying space constraints.

![Create barcode image with custom height](barcode-example.png){.align-center width="600" alt="Create barcode image with custom height"}

> **Tip:** Open the PNG files in any image viewer. The taller barcode should be exactly double the vertical size of the shorter one, while the horizontal spacing stays identical.

## Step 7: Common variations and edge cases

| Situation | Recommended setting |
|-----------|---------------------|
| **Printing on a high‑resolution label printer** | Use a larger X‑dimension (e.g., 4 px) and increase `BarHeight` proportionally. |
| **Displaying on a low‑dpi screen** | Keep `XDimension` at 1 px and `BarHeight` between 20‑40 px for readability. |
| **Generating QR codes or 2‑D barcodes** | The `BarHeight` property is ignored; use `EncodeTypes.QR` and adjust `ImageHeight` instead. |
| **Batch generating many heights** | Loop over an array of heights and call `Save` inside the loop; no need to recreate the generator each iteration. |

### Handling invalid heights

The library throws an `ArgumentOutOfRangeException` if you set `BarHeight` to a non‑positive value. Guard against this with a simple check:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Full source code (ready to copy)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Why this works:** All required settings (`EncodeTypes`, `XDimension`, `BarHeight`) are applied before each `Save` call. The same `BarcodeGenerator` instance is reused, which is both memory‑efficient and easy to read.

## Conclusion

You now know how to **create barcode image** files in C# and precisely **change barcode height** using the `BarcodeGenerator` API. By adjusting `BarHeight.Pixels` you achieve a **custom barcode height** without rebuilding the generator, making the solution ideal for dynamic label creation, UI rendering, or batch processing pipelines.

Next, explore related topics such as **how to adjust width**, **adding human‑readable text**, or **exporting to SVG for scalable web use**. The same pattern—set a property, call `Save`—applies across those scenarios, letting you extend this example with confidence.


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example – create Planet and RM4SCC barcodes with custom height](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [How to create rm4scc barcode and control its height in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}