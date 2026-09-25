---
category: general
date: 2026-08-22
description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
  code, configure dimensions, and generate PNG images for Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: en
lastmod: 2026-08-22
og_description: Create FCC 11 barcode in C# with Aspose.BarCode. Follow this concise
  tutorial to generate PNG barcodes for Australia Post, including FCC 59 and FCC 62
  variants.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Create FCC 11 barcode in C# – complete Aspose.BarCode guide
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: How to create FCC 11 barcode in C# with Aspose.BarCode
url: /python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create FCC 11 barcode in C# with Aspose.BarCode

If you need to **create FCC 11 barcode** in a .NET application, this guide shows you the exact code required. You will see how to configure the barcode dimensions, choose the proper encoding table, and save the result as a PNG file.

Generating Australia Post barcodes is a common requirement for logistics, mailing systems, and inventory tracking. This tutorial covers the FCC 11 format and also demonstrates how to produce FCC 59 and FCC 62 barcodes with different encoding tables, so you can reuse the same pattern for other postal services.

## What you’ll need

Before you start, make sure you have:

* .NET 6.0 SDK or later installed  
* Visual Studio 2022 (or any C#‑compatible IDE)  
* A valid license for **Aspose.BarCode for .NET** – the community edition works for evaluation  
* Write permission to a folder where the PNG files will be saved  

These prerequisites guarantee that the code compiles and runs without additional configuration.

## Step 1: Install the Aspose.BarCode NuGet package

Open a terminal in the project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The command adds the latest stable version of the library to your project file. The package contains the `BarcodeGenerator` class used throughout this tutorial.

## Step 2: Define the output folder

Create a folder where the generated images will be stored. The path can be absolute or relative to the executable.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` ensures the folder exists, preventing runtime errors when the `Save` method writes the file.

## Step 3: Generate the FCC 11 barcode

The FCC 11 format is the default encoding for Australia Post’s postal barcodes. The following code creates a barcode that encodes the numeric string `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Why this works:**  
* `EncodeTypes.AustraliaPost` tells the library to apply the Australia Post encoding rules.  
* The data string `1101234567` follows the FCC 11 specification: the first two digits (`11`) identify the format, followed by a 7‑digit customer reference.  
* `XDimension` and `BarHeight` control the size of the printed barcode, which is important for scanner readability.  

After running the program, you will find `PostalAustraliaPostFCC11.png` in the `Barcodes` folder. The image looks like this:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Step 4: Create additional Australia Post barcodes (optional)

While the primary goal is to **create FCC 11 barcode**, you often need FCC 59 or FCC 62 barcodes for different mail classes. The code below reuses the same `BarcodeGenerator` instance, only changing the data string and the optional encoding table.

### 4.1 FCC 59 with N‑Table encoding

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 with N‑Table encoding

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 with C‑Table encoding

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 with Other encoding

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

All four images are saved side‑by‑side in the same folder, making it easy to compare visual differences.

## Step 5: Understand the encoding tables

Australia Post defines three encoding tables:

* **N‑Table** – interprets numeric customer information. Use it when the payload contains only digits.  
* **C‑Table** – supports alphanumeric characters, useful for reference numbers that include letters.  
* **Other** – a fallback for custom or extended data formats.

Choosing the correct table ensures that the barcode scanner decodes the information exactly as intended. If you omit the `AustralianPostEncodingTable` property, the library defaults to the N‑Table, which may truncate non‑numeric characters.

## Tips, edge cases, and common pitfalls

| Situation | Recommended approach |
|-----------|----------------------|
| Data string length is shorter than required | Pad the numeric portion with leading zeros to meet the FCC specification. |
| Barcode appears blurry when printed | Increase `XDimension` to 5 or 6 pixels and verify the printer’s DPI settings. |
| Scanner returns “invalid format” | Verify that the correct encoding table (N‑Table, C‑Table, Other) matches the data payload. |
| Running on Linux without a GUI | Ensure the `System.Drawing.Common` package is referenced, or use the `Save` method with `BarCodeImageFormat.Png` which does not require a display context. |
| Need a different image format | Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg` or `BarCodeImageFormat.Tiff` as required. |

These practical tips stem from real‑world deployments of postal barcode solutions.

## Complete runnable example

Below is a self‑contained program that you can copy into a new console project (`dotnet new console`) and execute without modification.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputPath);

        // -------------------------------------------------
        // Create FCC 11 barcode – primary goal
        // -------------------------------------------------
        var fcc11 = new BarcodeGenerator(EncodeTypes.AustraliaPost, "1101234567");
        fcc11.Parameters.Barcode.XDimension.Pixels = 4;
        fcc11.Parameters.Barcode.BarHeight.Pixels = 50;
        fcc11


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Create One-Dimensional Databar GS1 Encoding with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [How to create barcode quiet zone .NET for Code 16K using Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}