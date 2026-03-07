---
title: Create EAN-13 Barcode with Supplemental Data – Aspose.BarCode
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
description: Learn how to create EAN-13 barcode with supplemental data in C# using Aspose.BarCode for .NET – generate barcode PNG quickly.
weight: 10
url: /net/supplemental-barcode-data/supplemental-barcode-data-configuration/
date: 2026-03-07
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create EAN-13 Barcode with Supplemental Data – Aspose.BarCode for .NET

In this hands‑on tutorial you’ll **create EAN-13 barcode** that includes supplemental EAN‑2 or EAN‑5 data, and you’ll see how to **generate barcode PNG** files with just a few lines of C#. Whether you’re building a retail checkout system, a logistics application, or a simple inventory tool, the ability to add supplemental information makes your barcodes far more useful.

## Quick Answers
- **What does “supplemental data” mean?** Extra digits (EAN‑2/EAN‑5) printed beside the main barcode, often used for price or issue numbers.  
- **Which barcode type is used?** EAN‑13 as the primary symbol, with optional EAN‑2 or EAN‑5 supplements.  
- **Can I output PNG images?** Yes – the `Save` method lets you export directly to PNG.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Is this compatible with .NET Core / .NET 6?** Absolutely – Aspose.BarCode supports all modern .NET runtimes.

## Prerequisites

Before we dive into the code, make sure you have:

- Visual Studio (or any .NET‑compatible IDE).  
- A copy of Aspose.BarCode for .NET – download it **[here](https://releases.aspose.com/barcode/net/)**.  
- Basic C# knowledge.  
- A writable folder where the generated PNG files will be saved.

## Importing Namespaces

First, add the Aspose.BarCode namespace so you can access the generator classes:

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** If you’re using .NET Core, add the NuGet package `Aspose.BarCode` to your project instead of referencing the DLL manually.

## What is a Supplemental Barcode?

A supplemental barcode is an auxiliary numeric string printed next to the main barcode.  
- **EAN‑2** – two‑digit supplement, often used for issue numbers on magazines.  
- **EAN‑5** – five‑digit supplement, commonly used for price extensions on retail items.

Adding these supplements does not change the primary EAN‑13 data; it simply provides extra context that scanners can read.

## Why Use Aspose.BarCode for Supplemental Data?

- **One‑line API** – configure both the main barcode and its supplement in a single object.  
- **Full control over dimensions** – adjust X‑dimension, supplement spacing, and image format.  
- **Cross‑platform** – works on .NET Framework, .NET Core, and .NET 5/6+.  

## Step‑by‑Step Guide

### Step 1: Set Up the Output Directory

Define where the PNG files will be stored. Replace the placeholder with a real path on your machine.

```csharp
string path = "Your Directory Path";
```

### Step 2: Initialise the Barcode Generator (Barcode Generator C#)

Create a `BarcodeGenerator` instance, specifying **EAN‑13** as the main type and providing the 13‑digit payload.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### Step 3: Adjust Barcode Dimensions

Fine‑tune the visual size of the barcode and the space reserved for the supplement.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### Step 4: Add an EAN‑2 Supplement

Set the supplemental data to a two‑digit value (e.g., “12”). This will appear to the right of the main barcode.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### Step 5: Save the EAN‑2 Barcode as PNG

Export the image. The `BarCodeImageFormat.Png` argument ensures a high‑quality PNG file.

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### Step 6: Switch to an EAN‑5 Supplement

Change the `SupplementData` to a five‑digit string for price extensions.

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### Step 7: Save the EAN‑5 Barcode as PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **Why this works:** The same `BarcodeGenerator` instance is reused, so you only need to modify the `SupplementData` property before each `Save` call. This keeps the code concise and avoids unnecessary object creation.

## Common Issues & Tips

- **Invalid directory path** – ensure the folder exists and the application has write permissions.  
- **Incorrect supplement length** – EAN‑2 expects exactly 2 digits, EAN‑5 expects 5; otherwise an exception is thrown.  
- **Image not visible** – verify that `BarCodeImageFormat.Png` is used; other formats (e.g., JPEG) may introduce compression artifacts that affect scanner readability.  

## Frequently Asked Questions

### Can I use Aspose.BarCode for .NET in my .NET Core project?
Yes, Aspose.BarCode for .NET is fully compatible with .NET Core, .NET 5, and .NET 6.

### Is there a free trial available for Aspose.BarCode for .NET?
Yes, you can try it for free by visiting **[this link](https://releases.aspose.com/)**.

### Where can I get a temporary license for Aspose.BarCode for .NET?
You can obtain a temporary license from **[this link](https://purchase.aspose.com/temporary-license/)**.

### Does Aspose.BarCode support a wide range of barcode types?
Absolutely – it supports EAN‑13, QR Code, Code 128, DataMatrix, PDF‑417, and many more.

### Can I customize the appearance of the generated barcodes?
Yes, you can modify colors, fonts, margins, and even add background images using the extensive `Parameters` API.

## Conclusion

You now know how to **create EAN-13 barcode** with supplemental EAN‑2 or EAN‑5 data and **generate barcode PNG** files using Aspose.BarCode for .NET. This approach gives you full control over barcode dimensions, supplement spacing, and output format, making it ideal for retail, logistics, and any scenario where extra numeric information is required.

For deeper exploration, check out the full reference guide: **[Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)**.

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}