---
category: general
date: 2026-08-25
description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
  barcode height for precise sizing.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: en
lastmod: 2026-08-25
og_description: Create RM4SCC barcode C# with Aspose.BarCode and learn how to set
  barcode height for precise control in your .NET applications.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Create RM4SCC barcode C# – guide to setting barcode height
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Create RM4SCC barcode C# and set barcode height
url: /python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create RM4SCC barcode C# and set barcode height

Create RM4SCC barcode C# quickly using the Aspose.BarCode library. This tutorial shows **how to set barcode height** and customize other visual properties so the barcode fits your layout exactly.

You’ll see a complete, ready‑to‑run console program that generates three PNG files:

* a default‑height Planet barcode (for comparison)  
* an RM4SCC barcode with a manual height of 100 px  
* a Planet barcode with empty (unfilled) bars  

The example assumes you have Visual Studio 2022 (or any .NET 6+ IDE) and a valid Aspose.BarCode for .NET license or evaluation copy.

## Prerequisites

| Requirement | Reason |
|-------------|--------|
| .NET 6 SDK (or later) | Provides the runtime for the console app |
| Aspose.BarCode for .NET NuGet package | Supplies `BarcodeGenerator`, `EncodeTypes`, and image export APIs |
| Basic C# knowledge | Needed to understand the code flow |

Install the NuGet package with:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** If you run the code without a license, the generated images will contain a small Aspose watermark.

## Step 1: Set up the project structure

Create a new console project and add the necessary `using` directives:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

The `using` statements give you access to the barcode generator classes and the PNG format enum.

## Step 2: Define the output folder

Choose a folder where the PNG files will be saved. The folder must exist before you call `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Creating the directory programmatically avoids a *FileNotFoundException* when the code runs on a fresh machine.

## Step 3: Generate a Planet barcode with the default height (baseline)

The Planet barcode is not the focus of this guide, but it provides a visual baseline to compare against the manually sized RM4SCC barcode.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Why this matters:*  
`XDimension` determines the width of a single bar. Keeping it constant while changing `BarHeight` isolates the height effect.

## Step 4: **Create RM4SCC barcode C#** – set a manual height

Now we address the primary task: **create RM4SCC barcode C#** and explicitly control its height.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### How to set barcode height

The `BarHeight` property lives under `Parameters.Barcode`. It accepts a `float` value expressed in **pixels**, **points**, or **millimeters** depending on the `Unit` you choose (`Pixels`, `Points`, `Millimeters`). In the example we use `Pixels` because the output format is PNG.

If you need a height in millimeters, switch the unit first:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Step 5: Generate a Planet barcode with empty (unfilled) bars

This step demonstrates another useful property—`FilledBars`. Setting it to `false` creates a “hollow” barcode, which can be handy for design purposes.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Full, runnable program

Copy the following code into `Program.cs`. Build and run the project; three PNG files will appear in the `GeneratedBarcodes` folder.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // 1️⃣ Planet barcode – default height (baseline)
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // 2️⃣ RM4SCC barcode – manual height of 100 px
        var rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100; // how to set barcode height
        rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // 3️⃣ Planet barcode – empty (unfilled) bars
        var planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmptyBars.Parameters.Barcode.FilledBars = false;
        planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", Bar


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}