---
title: Create barcode image C# – GS1 DataMatrix Example
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
description: Learn how to create barcode image C# using Aspose.BarCode for .NET and generate GS1 DataMatrix barcodes quickly and efficiently.
weight: 14
url: /net/gs1-barcode-encoding/gs1-datamatrix-example/
date: 2026-02-22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix Example

If you are looking for a reliable way to **create barcode image C#** in your .NET applications, Aspose.BarCode for .NET makes the process straightforward. This powerful library supports a wide range of symbologies, including GS1 DataMatrix, and provides a clean API that lets you focus on your business logic instead of low‑level barcode details. In the next few minutes, we’ll walk through a complete, hands‑on example that shows you how to generate a GS1 DataMatrix barcode, customize its appearance, and save it as an image file.

## Quick Answers
- **What does the example generate?** A GS1 DataMatrix barcode containing sample product data.  
- **Which library is used?** Aspose.BarCode for .NET.  
- **Can I change the output format?** Yes, you can save as PNG, JPEG, BMP, etc.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Is the code compatible with .NET Core?** Absolutely – the same API works on .NET Framework and .NET Core/5/6.

## What is a GS1 DataMatrix barcode?
A GS1 DataMatrix is a two‑dimensional barcode that encodes product‑level information (such as GTIN, serial number, and additional application identifiers). It’s widely used in retail, healthcare, and logistics for compact, high‑density data storage.

## Why use Aspose.BarCode to create barcode image C#?
- **Full‑featured API** – supports GS1 standards, error correction, and size control.  
- **No external dependencies** – pure .NET library, easy to integrate.  
- **Cross‑platform** – works on Windows, Linux, and macOS.  
- **Extensive documentation** – includes examples like this one to get you started quickly.

## Prerequisites

Before we dive into the tutorial, make sure you have the following prerequisites in place:

1. **Aspose.BarCode for .NET** – You need to have Aspose.BarCode for .NET installed. If you haven't already, you can [download it here](https://releases.aspose.com/barcode/net/).  
2. **Development Environment** – You should have a .NET development environment set up on your system (Visual Studio, VS Code, or any IDE you prefer).

Now that you have the prerequisites ready, let's start generating GS1 DataMatrix barcodes.

## Import Namespaces

First, import the necessary namespaces to work with Aspose.BarCode for .NET. These namespaces give you access to the barcode generation capabilities.

```csharp
using Aspose.BarCode;
using System;
```

## How to create barcode image C# – Step‑by‑Step Guide

### Step 1: Set Up the Barcode Generator

To begin, create a `BarcodeGenerator` instance and specify the **GS1 DataMatrix** symbology along with the data you want to encode. In this example we encode the string **"(01)12345678901231(21)ASPOSE(30)9876"**, which follows the GS1 Application Identifier format.

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*Pro tip:* Replace the sample data with your own GS1 identifiers to suit your product catalog.

### Step 2: Customize Barcode Properties

You can tailor the barcode’s appearance using the `Parameters` object. Here we set the X‑dimension (the size of the smallest module) to 8 pixels, and define a matrix size of 36 columns by 12 rows. Adjust these values to meet your scanning requirements.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*Why adjust X‑dimension?* A larger X‑dimension makes the barcode easier to scan on low‑resolution devices, while a smaller value reduces image size.

### Step 3: Save the Barcode Image

Finally, save the generated barcode to disk. The example uses PNG, but you can choose from JPEG, GIF, BMP, and other formats supported by Aspose.BarCode.

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

When you run the code, you’ll find **Gs1DataMatrixExample.png** in the specified folder, ready to be used in labels, packaging, or digital applications.

## Common Use Cases

- **Retail product labeling** – Encode GTIN, batch numbers, and expiration dates.  
- **Pharmaceutical tracking** – Meet regulatory requirements with GS1‑compliant data.  
- **Warehouse logistics** – Compactly store location and inventory information.  

## Troubleshooting & Tips

- **Incorrect data format** – Ensure your string follows the GS1 Application Identifier syntax; otherwise the barcode may not be scannable.  
- **Image size issues** – If the generated image appears blurry, increase the `XDimension.Pixels` value.  
- **License errors** – A trial license works for evaluation, but a full license is required for production deployments.

## Frequently Asked Questions

### What is GS1 DataMatrix?
GS1 DataMatrix is a two-dimensional barcode symbology used for encoding data related to products and their identification, particularly in the retail and healthcare industries.

### Is Aspose.BarCode for .NET suitable for other barcode types?
Yes, Aspose.BarCode for .NET supports a wide range of barcode types, making it versatile for different applications.

### Can I generate barcodes in other image formats besides PNG?
Yes, Aspose.BarCode for .NET allows you to save generated barcodes in various image formats, such as JPEG, GIF, and BMP, in addition to PNG.

### Do I need a license to use Aspose.BarCode for .NET?
Yes, a valid license is required for commercial use of Aspose.BarCode for .NET. You can obtain a license from the [Aspose website](https://purchase.aspose.com/buy).

### Where can I get support for Aspose.BarCode for .NET?
You can find answers to your questions and seek support in the [Aspose.BarCode for .NET forum](https://forum.aspose.com/c/barcode/13).

## Additional FAQ (AI‑Optimized)

**Q: How do I generate a DataMatrix barcode in C# without GS1 formatting?**  
A: Use `EncodeTypes.DataMatrix` instead of `EncodeTypes.GS1DataMatrix` and provide the plain data string to the `BarcodeGenerator`.

**Q: Can I change the barcode colors programmatically?**  
A: Yes, set `gen.Parameters.Barcode.ForeColor` and `gen.Parameters.Barcode.BackColor` to customize foreground and background colors.

**Q: Is it possible to embed the generated barcode directly into a PDF?**  
A: Absolutely – retrieve the barcode as a `System.Drawing.Image` and add it to a PDF using Aspose.PDF or any other PDF library.

**Q: What .NET versions are supported?**  
A: Aspose.BarCode for .NET supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET 6, and later.

**Q: How can I improve scanning reliability for small labels?**  
A: Increase the X‑dimension, add quiet zones (`gen.Parameters.Barcode.Margin`), and ensure sufficient contrast between the barcode and background.

## Conclusion

In this tutorial, we explored how to **create barcode image C#** using Aspose.BarCode for .NET to generate a GS1 DataMatrix barcode. With just a few lines of code you can embed high‑quality barcodes into your applications, whether you’re building retail solutions, healthcare systems, or logistics platforms. Explore the library further to discover additional symbologies, advanced rendering options, and integration scenarios.

For more information and detailed documentation, please refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.BarCode for .NET (latest version)  
**Author:** Aspose  

---