---
date: 2026-09-08
description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
  with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free customization.
images:
- /net/gs1-barcode-encoding/gs1-code-128-example/og-image.png
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: GS1 Code 128 Example
og_description: Learn how to create code 128 barcode and generate GS1 barcodes in
  C# with Aspose.BarCode for .NET. Follow a step‑by‑step guide to generate and save
  barcode images quickly.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: How to create code 128 barcode with GS1 using Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: How to create code 128 barcode with GS1 using Aspose.BarCode
url: /net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create code 128 barcode with GS1 using Aspose.BarCode

In this tutorial you’ll learn how to **create code 128 barcode** that complies with the GS1 standard using the Aspose.BarCode library for .NET. Whether you need a barcode for inventory, shipping, or point‑of‑sale, this guide walks you through every step—from setting up the development environment to saving the final image—so you can start generating reliable barcodes in minutes.

## Quick answers
- **What is the primary class to generate a barcode?** `BarcodeGenerator` creates and configures the barcode image.  
- **Which symbology does GS1 Code 128 use?** It uses the `EncodeTypes.Code128` type with GS1‑specific data formatting.  
- **Do I need a license for development?** A free trial works for evaluation; a commercial license is required for production.  
- **Can I change the image format?** Yes—save as PNG, JPEG, BMP, or TIFF by changing the file extension.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, and .NET 6+.

## What is create code 128 barcode?
`create code 128 barcode` refers to generating a linear barcode that encodes alphanumeric data using the Code 128 symbology, which is widely adopted for logistics because it supports the full ASCII set and can embed GS1 Application Identifiers. The barcode can store product identifiers, serial numbers, and other custom data, making it suitable for a broad range of business scenarios.

## Why use Aspose.BarCode for GS1 Code 128?
Aspose.BarCode supports **30+ barcode symbologies** and can render images up to **10,000 × 10,000 px** without loss of quality, making it suitable for high‑resolution label printing. The library also validates GS1 data structures automatically, reducing the risk of malformed barcodes in production lines. Additionally, it offers extensive customization options for size, color, and layout, which helps meet strict industry standards.

## Prerequisites
Before you start, make sure you have the following:

1. **.NET development environment** – Visual Studio 2022, Rider, or any IDE that supports .NET 6+.  
2. **Aspose.BarCode for .NET** – download it from the **Aspose.BarCode for .NET download page** at [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) and add the NuGet package `Aspose.BarCode` to your project.  
3. **Basic C# knowledge** – you should be comfortable with creating console or Windows applications.  
4. **Understanding of GS1 Code 128** – optional but helpful; GS1 uses Application Identifiers (AIs) like `(01)` for GTIN and `(21)` for serial numbers.

## How to create code 128 barcode step by step

Load the library, configure the barcode type, set GS1 data, customize dimensions, and finally save the image. The direct answer to the question “how to create code 128 barcode?” is: **instantiate `BarcodeGenerator` with `EncodeTypes.Code128` and GS1‑formatted data, adjust `XDimension` if needed, then call `Save` with the desired file name and format**. The following sections break down each step.

### Step 1: set your directory path
Define the folder where the generated image will be stored. Keeping the path configurable makes the code reusable across environments.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Replace `"Your Directory Path"` with an absolute or relative path that your application can write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Step 2: create a GS1 Code 128 barcode
Create the barcode generator, specify the symbology, and provide GS1‑formatted data. The data string must include Application Identifiers wrapped in parentheses.

```csharp
string path = "Your Directory Path";
```

The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`, and an additional custom AI `(30)9876`. Aspose.BarCode automatically inserts the required FNC1 character for GS1 compliance.

### Step 3: customize barcode parameters
Adjust visual parameters such as `XDimension` (the width of the narrow bar) to control the barcode’s density. You can also modify height, colors, and margins.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld readers while keeping the image size modest.

### Step 4: save the barcode image
Persist the generated barcode to disk. You may choose PNG for lossless quality, JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes the image file in the format indicated by the file extension.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Replace `GS1Code128Example.png` with any valid filename and extension that matches your desired output format.

### Step 5: verify the barcode (optional)
After saving, you can load the image back into your application or use a barcode scanner to confirm that the encoded data matches the original string. This step is useful during development and automated testing.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Common issues and troubleshooting tips
- **FNC1 not detected** – Ensure the data string starts with an opening parenthesis and includes valid GS1 AIs; the library inserts FNC1 automatically only for recognized patterns.  
- **Image not saved** – Verify that the target directory exists and the application has write permissions. Use `Directory.CreateDirectory(path)` to create it on the fly.  
- **Barcode too dense** – Decrease `XDimension` or increase the image height to give scanners more room to read narrow bars.  
- **Unsupported characters** – Code 128 can only encode the full ASCII set; avoid Unicode characters outside this range.

## Frequently asked questions

**Q: Can I generate barcodes in a web API without installing the full .NET Framework?**  
A: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose a lightweight REST endpoint that returns barcode images on demand.

**Q: Does the library support batch generation of multiple barcodes?**  
A: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator` for each, and call `Save` inside the loop. The library is thread‑safe for parallel processing.

**Q: Is there a way to embed the barcode directly into a PDF?**  
A: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage` with the barcode image stream. This avoids writing intermediate files to disk.

**Q: How can I ensure the barcode meets ISO/GS1 quality standards?**  
A: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm and enable `BarHeight` according to the label size. Aspose.BarCode validates the AI format and throws an exception for invalid data.

**Q: What licensing options are available for production use?**  
A: Aspose offers perpetual, subscription, and cloud‑based licensing models. A trial license works for evaluation, but a paid license removes the evaluation watermark and unlocks all features.

## Additional resources

- **Documentation** – Access the full API reference at [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Download** – Get the latest library release from [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Free trial** – Start a 30‑day trial at [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Purchase** – Buy a commercial license at [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Support** – Join the community forum at [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) for troubleshooting help.

---

**Last Updated:** 2026-09-08  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/net/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}