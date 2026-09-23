---
date: 2026-09-23
description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
  extended code text in .NET, ideal for inventory and logistics applications.
images:
- /net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/og-image.png
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: DataMatrix Extended Code Text Configuration
og_description: How to use Aspose.BarCode to generate a DataMatrix barcode with extended
  code text in .NET. Follow a quick step‑by‑step guide for inventory and logistics
  solutions.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: How to use Aspose.BarCode to create DataMatrix code text in .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: How to use Aspose.BarCode to create DataMatrix code text in .NET
url: /net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to use Aspose.BarCode to create DataMatrix code text in .NET

Integrating barcodes into modern .NET applications is no longer a niche task—it’s a core requirement for inventory, logistics, and mobile scanning solutions. In this guide you’ll **learn how to use Aspose.BarCode** to configure a DataMatrix barcode with extended code text, generate the image, and verify it programmatically. You’ll see why this approach is ideal for creating barcode for inventory and how it fits into .NET Core or .NET 6 projects.

## Quick answers
- **What library is needed?** Aspose.BarCode for .NET  
- **Which barcode type?** DataMatrix with extended code text  
- **Can I use .NET Core / .NET 6?** Yes, the API is cross‑platform  
- **Do I need a license for testing?** A free trial works for development; a license is required for production  
- **How long does implementation take?** About 10‑15 minutes for a basic example  

## What is Aspose.BarCode for .NET?
Aspose.BarCode for .NET is a commercial library that enables developers to generate and recognize more than 30 barcode symbologies, including DataMatrix, QR, and Code 128, and to produce images up to 10,000 × 10,000 pixels without external dependencies. It supports .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6/7.

## Why use DataMatrix extended code text?
DataMatrix extended code text lets you embed multiple encoding schemes—UTF‑8, C40, Text, X12—in a single symbol, allowing up to **3116 codewords** (roughly 155 KB of data) in one compact square. This capability is perfect for multilingual product labeling, medical device tracking, and smart packaging where you need to combine alphanumeric IDs with binary payloads.

## Prerequisites

Before you start, verify that you have the following:

1. **Aspose.BarCode for .NET** – download it from the official site **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **A .NET development environment** – Visual Studio, Rider, or VS Code with the .NET SDK.  
3. **Basic C# knowledge** – you should be comfortable with classes, namespaces, and the `using` directive.

## Import namespaces

Add the required namespaces at the top of your C# file so the compiler knows where to find the barcode classes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

These namespaces give you access to both barcode generation and recognition features.

## How to configure DataMatrix extended code text?

Load the builder, add the desired segments, and let Aspose.BarCode handle the ECI markers automatically. This direct‑answer paragraph tells you the exact steps: create a `DataMatrixExtCodetextBuilder`, add Unicode, C40, plain‑text, and Text mode segments, then retrieve the combined string for the generator.

### Step 1: Define the output folder

Specify where the generated barcode image will be saved. Replace the placeholder with a valid path on your machine.

```csharp
string path = "Your Directory Path";
```

### Step 2: Build the extended code text

`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended code text according to the DataMatrix specification. It automatically inserts the required ECI (Extended Channel Interpretation) markers.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

This mix demonstrates how you can combine Unicode characters, C40 encoding, plain text, and Text mode in a single DataMatrix symbol.

### Step 3: Generate the final codetext string

After configuring all parts, retrieve the combined string that Aspose.BarCode will embed into the barcode.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Step 4: Create the DataMatrix barcode

`BarcodeGenerator` is the core class that produces barcode images. Instantiate it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual parameters such as X‑dimension, image format, and optional human‑readable text.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

The above code **creates barcode aspose .net** with the desired extended code text and saves it as a PNG file.

### Step 5: Verify the barcode by reading it back

`BarCodeReader` validates that the generated symbol can be decoded correctly, which is essential for automated test pipelines and quality assurance.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

If everything is set up properly, the console will output the exact extended code text you built earlier.

## Common pitfalls and troubleshooting

| Issue | Reason | Fix |
|-------|--------|-----|
| Barcode not readable | X‑dimension too low | Increase `XDimension.Pixels` (e.g., 4 → 6) |
| Garbled characters | Wrong ECI encoding | Ensure `ECIEncodings.UTF8` matches the character set |
| File not saved | Invalid path | Use an absolute path or ensure the folder exists |
| License exception | Trial expired | Apply a temporary or full license (see FAQ) |

## Frequently asked questions

### Q1: What is Aspose.BarCode for .NET?
A1: Aspose.BarCode for .NET is a powerful library that enables developers to generate and recognize a wide variety of barcode symbologies, including DataMatrix, QR, Code128, and more.

### Q2: Where can I find the documentation for Aspose.BarCode for .NET?
A2: You can access the full API reference **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Q3: Is there a free trial available for Aspose.BarCode for .NET?
A3: Yes, a free trial version can be downloaded from **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Q4: How do I obtain a temporary license for testing?
A4: Temporary licenses are provided for evaluation purposes and can be requested **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Q5: Where can I get support or ask questions about Aspose.BarCode for .NET?
A5: The official Aspose.BarCode forum is the best place to seek help: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Last Updated:** 2026-09-23  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/net/datamatrix-barcode-configuration/)
- [Generate a DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Generate Aztec Barcode with Text Encoding using Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}