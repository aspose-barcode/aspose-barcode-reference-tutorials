---
date: 2026-09-28
description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET –
  a step‑by‑step guide for generating DotCode barcodes with extended code text.
images:
- /net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/og-image.png
keywords:
- create 2d matrix barcode
- how to generate dotcode
- dotcode extended codetext
lastmod: 2026-09-28
linktitle: DotCode Extended Code Text Configuration
og_description: Learn to create 2d matrix barcode using Aspose.BarCode for .NET. This
  guide shows step‑by‑step how to generate DotCode barcodes with extended code text.
og_image_alt: Guide showing how to create a 2d matrix DotCode barcode with extended
  codetext in .NET
og_title: Create 2d matrix barcode with Aspose.BarCode for .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create 2d matrix barcode with Aspose.BarCode for .NET
    – a step‑by‑step guide for generating DotCode barcodes with extended code text.
  headline: How to create 2d matrix barcode via Aspose.BarCode for .NET
  type: TechArticle
- questions:
  - answer: Yes. The PNG image produced by the generator can be embedded in iOS, Android,
      or any cross‑platform mobile application.
    question: Can I use the generated barcode in a mobile app?
  - answer: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g.,
      `ECIEncodings.Base64`) to embed binary payloads.
    question: What if I need to encode binary data instead of text?
  - answer: Adjust the `XDimension.Pixels` property; higher values increase module
      size, while lower values make the barcode more compact.
    question: How do I change the barcode size without affecting readability?
  - answer: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone
      in pixels.
    question: Is there a way to add a quiet zone around the barcode?
  - answer: The latest Aspose.BarCode releases are compatible with .NET 8; just reference
      the appropriate NuGet package version.
    question: Does the library support .NET 8?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- dotcode
- Aspose.BarCode
- .NET barcode generation
- 2d matrix barcode
title: How to create 2d matrix barcode via Aspose.BarCode for .NET
url: /net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create 2d matrix barcode via Aspose.BarCode for .NET

## Introduction

In the realm of barcode generation and management, Aspose.BarCode for .NET stands out as a versatile solution that supports **50+ input and output formats** and can process multi‑hundred‑page documents without loading the entire file into memory. Whether you need barcodes for product tracking, inventory control, or data‑rich applications, creating a **2d matrix barcode** such as DotCode with extended codetext lets you embed both textual and binary payloads in a compact square symbol. This tutorial walks you through building that extended codetext step‑by‑step and rendering the final image.

## Quick answers
- **What does “create dotcode extended codetext” mean?** It means building a DotCode barcode that includes FNC1, ECICodetext, plain text, and symbol separators in a single extended payload.  
- **Which library is required?** Aspose.BarCode for .NET.  
- **Do I need a license?** A temporary license works for evaluation; a full license is required for production.  
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **How long does implementation take?** About 10‑15 minutes for a basic example.

## How to create dotcode extended codetext

Load your project, set the directory, build the extended codetext, and generate the image – all in under a dozen lines of code. The following direct answer summarizes the whole process:

Load the `BarcodeGenerator` with `EncodeTypes.DotCode`, build the extended codetext using `DotCodeExtendedCodetextBuilder` (adding FNC1, ECICodetext, plain text, and FNC3 separators), then call `Save` to write a PNG file. This sequence creates a fully compliant 2d matrix barcode in a single call.

## What is dotcode extended codetext?

The **dotcode extended codetext** is a composite string that combines multiple data segments—such as FNC1 identifiers, ECICodetext, plain text, and FNC3 separators—into one payload that DotCode can decode. It enables encoding of multilingual text, binary blobs, and structured data within a single 2d matrix barcode, making it ideal for supply‑chain, healthcare, and IoT scenarios.

## Why use Aspose.BarCode for this task?

Aspose.BarCode processes **up to 500 pages per second** on typical server hardware and supports **over 30 barcode symbologies**, including DotCode. Its `GetExtendedCodetext` API guarantees correct placement of control characters, eliminating manual string concatenation errors and ensuring compliance with ISO/IEC 24724. Additionally, it offers built‑in error correction and automatic quiet‑zone handling, reducing the need for manual tuning.

## Prerequisites

- **Aspose.BarCode for .NET** – download from the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).  
- A .NET development environment (Visual Studio 2022 or later recommended).  
- Optional: a temporary license file for evaluation.

## Import namespaces

`using Aspose.BarCode.Generation;`  
`using Aspose.BarCode.ComplexBarcodes;`  

These namespaces expose the `BarcodeGenerator` class and the `DotCodeExtendedCodetextBuilder` helper needed for the example.

```csharp
using Aspose.BarCode.Generation;
```

Now that we have the prerequisites covered, let's break down the process of generating DotCode Extended Code Text into a step‑by‑step guide.

## Step 1: define the directory path

Specify where the generated PNG will be saved. Use an absolute or relative path that your application can write to.

```csharp
string path = "Your Directory Path";
```

Replace `"Your Directory Path"` with the actual path on your system.

## Step 2: create dotcode extended codetext

The `DotCodeExtendedCodetextBuilder` class assembles the various segments into a single extended codetext string.

To create the DotCode Extended Code Text, follow these sub‑steps:

### 2.1 add fnc1 format identifier

The FNC1 format identifier marks the start of a new data field. It is required for GS1‑compliant DotCode symbols.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 add ecicodetext

The ECICodetext encodes special characters and international text. In this example we encode `"犬Right狗"` using UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 add plain codetext

You can also add plain text to the DotCode Extended Code Text. Here, we add `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 add fnc3 symbol separator

The FNC3 symbol separator separates different sections of the code, improving readability for scanners.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 add fnc3 reader initialization

This step adds the FNC3 Reader Initialization information, which tells the scanner how to interpret the following data.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 generate codetext

Now generate the DotCode Extended Codetext by calling the `GetExtendedCodetext` method on the `textBuilder` object.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Step 3: generate dotcode image

Render the barcode image from the extended codetext.

#### 3.1 initialize barcode generator

The `BarcodeGenerator` class is Aspose.BarCode's core object for creating any barcode. You instantiate it with the desired symbology (`EncodeTypes.DotCode`) and the extended codetext you just built.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Finally, call `Save` to write the PNG file to disk. The image is ready for embedding in reports, mobile apps, or printed labels.

## Common issues and solutions

- **Incorrect encoding** – Ensure you use `ECIEncodings.UTF8` when adding multilingual text; otherwise characters may appear garbled.  
- **File‑access errors** – Verify the application has write permissions to the target directory.  
- **Quiet zone missing** – Set `gen.Parameters.Barcode.Margin` if scanners require extra white space around the symbol.

## Frequently asked questions

**Q: Can I use the generated barcode in a mobile app?**  
A: Yes. The PNG image produced by the generator can be embedded in iOS, Android, or any cross‑platform mobile application.

**Q: What if I need to encode binary data instead of text?**  
A: Use the `AddECICodetext` method with the appropriate `ECIEncodings` (e.g., `ECIEncodings.Base64`) to embed binary payloads.

**Q: How do I change the barcode size without affecting readability?**  
A: Adjust the `XDimension.Pixels` property; higher values increase module size, while lower values make the barcode more compact.

**Q: Is there a way to add a quiet zone around the barcode?**  
A: Yes. Set `gen.Parameters.Barcode.Margin` to define the desired quiet zone in pixels.

**Q: Does the library support .NET 8?**  
A: The latest Aspose.BarCode releases are compatible with .NET 8; just reference the appropriate NuGet package version.

If you need further guidance or have questions, don't hesitate to visit the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) or engage with the community on the [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-09-28  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Related Tutorials

- [Create DotCode Barcode .NET (Auto Mode) with Aspose.BarCode](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/net/datamatrix-barcode-configuration/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}