---
category: general
date: 2026-08-03
description: Barcode generator C# tutorial shows how to generate barcode image with
  Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: en
lastmod: 2026-08-03
og_description: Barcode generator C# tutorial explains how to generate barcode image
  using Aspose.BarCode, configure DataBar Expanded Stacked columns and rows, and save
  PNG files.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: Barcode generator C# – step-by-step guide to generate barcode image
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Barcode generator C# – generate barcode image
url: /python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – generate barcode image

If you need a barcode generator C# that can generate barcode image for DataBar Expanded Stacked, this guide walks you through the complete process. You will learn how to configure column and row settings, save the result as PNG, and adapt the code for other symbologies.

Generating barcode images programmatically removes manual steps and ensures consistency across invoices, shipping labels, and inventory systems. This tutorial covers everything you need, from project setup to full source code, so you can run the example immediately.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 or later installed  
* An IDE such as Visual Studio 2022 (any editor that supports C# works)  
* A license for **Aspose.BarCode for .NET** – the free evaluation works for testing  
* Basic familiarity with C# syntax  

If any of these items are missing, install the .NET SDK from dotnet.microsoft.com and obtain the Aspose.BarCode NuGet package with:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Create a barcode generator C# project

Create a new console application and add the required `using` directives:

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
            // The implementation starts in the next sections
        }
    }
}
```

The `BarcodeGenerator` class is the core of the barcode generator C# API. It receives the symbology type and the text to encode.

## Step 2: Generate a DataBar Expanded Stacked barcode and set columns

The first example creates a barcode with four columns. Adjusting the `Columns` property changes the visual density of the DataBar Expanded Stacked symbology.

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**Why this matters:** The column count influences the amount of data that can be stored in a compact space. Setting it to 4 produces a wider barcode that remains readable by most scanners.

## Step 3: Generate a barcode with custom row count

The second example shows how to control the vertical layout by setting the `Rows` property. A three‑row configuration is useful when you need a taller barcode for limited horizontal space.

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**Why this matters:** Adjusting rows lets you fit the barcode into a narrow column while preserving readability. The barcode generator C# automatically recalculates the module size to meet the specification.

## Step 4: Full, runnable example

Below is a self‑contained program that combines the previous steps. Copy the code into `Program.cs`, replace `YOUR_DIRECTORY` with an existing folder path, and run the application.

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
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### Expected output

When you run the program, two PNG files appear in the target directory:

* **DatabarCols4.png** – a DataBar Expanded Stacked barcode with four columns  
* **DatabarRows3.png** – the same data encoded in three rows  

Open the images with any image viewer; they display sharp, scannable barcodes ready for printing or embedding in PDFs.

## How to generate barcode image with custom dimensions

If you need a specific image size, adjust the `ImageHeight` and `ImageWidth` properties before calling `Save`:

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

Changing dimensions does not affect the encoded data; it only scales the visual representation. This technique is useful when integrating barcodes into UI components with fixed layout constraints.

## Common pitfalls and pro tips

* **Path separators:** Use verbatim strings (`@"C:\Path\file.png"`) or `Path.Combine` to avoid escape‑character issues on Windows.  
* **License enforcement:** Without a valid license, the generated images contain a watermark. Apply your license early in the application:

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **Encoding limits:** DataBar Expanded Stacked supports up to 74 numeric characters. Exceeding this limit throws an exception. Validate input length before creating the generator.  
* **Performance:** Reusing a single `BarcodeGenerator` instance for multiple saves reduces memory allocation. Only change the `Rows` or `Columns` properties between saves if the encoded text stays the same.

## Next steps

Now that you can generate barcode images with the barcode generator C#, consider exploring:

* **Different symbologies** – try `EncodeTypes.QR`, `EncodeTypes.Code128`, or `EncodeTypes.Pdf417`.  
* **Color customization** – set `Parameters.Barcode.ForeColor` and `BackColor` to match branding.  
* **Embedding in PDFs** – combine the generated PNG with Aspose.PDF to create printable documents.  

These extensions let you build a full‑featured barcode solution for inventory, logistics, or retail applications.

---


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}