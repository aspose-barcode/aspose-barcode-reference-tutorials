---
category: general
date: 2026-08-15
description: Barcode image PNG in C# – learn how to generate postal barcodes, create
  a Planet barcode, and change barcode height with a simple generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: en
lastmod: 2026-08-15
og_description: Barcode image PNG in C# tutorial shows how to generate postal barcodes,
  create a Planet barcode, and change barcode height using the BarcodeGenerator API.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Barcode image PNG in C# – generate and adjust barcodes
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Barcode image PNG in C# generate barcodes, change height
url: /python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode image PNG in C# – generate barcodes, change height

If you need a **barcode image PNG** in C#, this guide walks you through the complete process. You’ll learn how to generate postal barcodes, create a Planet barcode, and change the barcode height without leaving your IDE.

Generating reliable PNG barcodes is a common requirement for shipping labels, inventory systems, and automated mailing solutions. By the end of this tutorial you’ll have a reusable code snippet that produces high‑quality PNG files for both Planet and RM4SCC formats, and you’ll understand how to adjust the bar height to meet postal specifications.

## What you’ll need

- .NET 6+ or .NET Framework 4.7.2 (the BarcodeGenerator API works with any recent .NET runtime)  
- A reference to the **Aspose.BarCode for .NET** NuGet package (or any compatible library that provides `BarcodeGenerator`, `EncodeTypes`, and `BarCodeImageFormat`)  
- Basic familiarity with C# syntax and file I/O  

No additional tools are required; the code runs in Visual Studio, Rider, or the `dotnet` CLI.

## Barcode image PNG – basic generation

The first step is to create a **barcode image PNG** with default dimensions. This establishes the baseline file that you can later customize.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Why this works:**  
- `EncodeTypes.Planet` tells the generator to use the Planet symbology, which is required for many postal services.  
- `XDimension.Pixels` controls the width of the smallest bar; a value of 4 px yields a readable barcode at typical label sizes.  
- The `Save` method writes a **barcode image PNG** file to disk, preserving all vector information as raster pixels.

## Change barcode height – customizing the visual weight

Postal guidelines often require a specific bar height. The following snippet demonstrates how to set a custom 100‑pixel height for the same Planet barcode.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Why you change the height:**  
A taller bar improves scan reliability on low‑resolution printers, while a shorter bar reduces label space. The `BarHeight.Pixels` property lets you fine‑tune this attribute without affecting the X‑dimension.

## Generate postal barcode – creating an RM4SCC example

The RM4SCC format is another common postal barcode used in the United Kingdom. The generation steps mirror the Planet example, reinforcing the **barcode generator c#** pattern.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Change barcode height – RM4SCC variation

Just like the Planet barcode, you can adjust the RM4SCC bar height. The code below sets the height to 100 px, producing a second **barcode image PNG** for the same data string.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Full, runnable example

Putting all steps together yields a single, self‑contained program that creates four PNG files:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}