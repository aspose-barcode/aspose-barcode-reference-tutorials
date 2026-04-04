---
title: "Generate barcode image – Code 93 with Aspose.BarCode"
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
description: "Learn how to generate barcode image and save barcode PNG using Aspose.BarCode for .NET – a complete aspose barcode example."
weight: 12
url: /net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
date: 2026-02-25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate barcode image – One-Dimensional Code 93 with Aspose.BarCode

## Introduction

In today's digital age, barcodes have become an integral part of our lives, simplifying processes such as inventory management, product labeling, and point‑of‑sale tracking. **Generating a barcode image** is often the first step in integrating these identifiers into your applications. Aspose.BarCode for .NET provides a robust, easy‑to‑use API that lets you create high‑quality Code 93 barcodes in just a few lines of C# code. Whether you’re building a warehouse system, a retail app, or a custom reporting tool, this tutorial walks you through a complete **aspose barcode example** that shows how to generate, customize, and **save barcode PNG** files.

## Quick Answers
- **What does the tutorial cover?** Creating and saving a Code 93 barcode image with checksum handling.  
- **Which library is used?** Aspose.BarCode for .NET (latest stable release).  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I change the output format?** Yes – you can save as PNG, JPEG, BMP, etc., by changing the `BarCodeImageFormat`.  
- **What are the minimum requirements?** .NET Framework 4.6+ or .NET Core 3.1+ and Visual Studio.

## What is a Code 93 barcode?
Code 93 is a high‑density, alphanumeric symbology that supports the full ASCII character set. It is often chosen for its compact size and built‑in checksum, which helps ensure data integrity during scanning.

## Why generate barcode images with Aspose.BarCode?
- **Full control** over encoding type, checksum, size, and image format.  
- **No external dependencies** – the library runs on any .NET platform.  
- **Excellent rendering quality**, suitable for both on‑screen display and high‑resolution printing.  
- **Comprehensive documentation** and a large set of examples that speed up development.

## Prerequisites

Before we dive into the code, make sure you have the following:

1. **Visual Studio** (any recent edition).  
2. **Aspose.BarCode for .NET** installed – you can get it from the official download page.  
3. Basic familiarity with **C#** and .NET project structure.

Now that you’re set, let’s move on to the step‑by‑step guide.

## Import Namespaces

First, import the required namespaces so you can access the barcode generation classes.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## Step 1: Set the Directory Path

Define where the generated barcode image will be saved. Replace the placeholder with a valid folder on your machine.

```csharp
string path = "Your Directory Path";
```

## Step 2: Create a One‑Dimensional Code 93 Barcode

Instantiate a `BarcodeGenerator` with the `Code93Extended` type and the data you want to encode.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## Step 3: Enable Checksum (Optional)

Code 93 includes a checksum by default. You can toggle it using the `IsChecksumEnabled` property.

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## Step 4: Save the Barcode Image (Save Barcode PNG)

Generate the image and save it as a PNG file in the folder you specified earlier.

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## Step 5: Handling Exceptions – Generating Without a Checksum

If you need to create a barcode **without** a checksum, you must handle potential exceptions that may arise.

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### Common Issues and Solutions
- **Invalid path** – ensure the directory exists and the application has write permissions.  
- **Unsupported characters** – Code 93 supports the full ASCII set, but control characters may cause errors.  
- **License not set** – without a valid license, the library runs in evaluation mode and may add a watermark.

## Frequently Asked Questions (FAQs)

### Q: Where can I find the documentation for Aspose.BarCode for .NET?
A: You can find the documentation at [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/).

### Q: How do I download Aspose.BarCode for .NET?
A: You can download Aspose.BarCode for .NET from the website at [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/).

### Q: Is there a free trial available for Aspose.BarCode for .NET?
A: Yes, you can get a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).

### Q: How can I purchase a license for Aspose.BarCode for .NET?
A: You can purchase a license from the purchase page at [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy).

### Q: Where can I get support or ask questions about Aspose.BarCode for .NET?
A: You can find a community forum for support and discussions at [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}