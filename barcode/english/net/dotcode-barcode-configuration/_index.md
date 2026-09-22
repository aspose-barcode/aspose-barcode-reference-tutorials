---
title: How to Generate DotCode Barcodes – Configuration Guide
linktitle: How to Generate DotCode Barcodes – Configuration Guide
second_title: Aspose.BarCode .NET API
description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET, covering aspect ratio, encoding modes, extended text, and reader initialization.
weight: 32
url: /net/dotcode-barcode-configuration/
date: 2026-06-14
keywords:
  - how to generate dotcode
  - dotcode barcode configuration
  - aspose barcode .net
schemas:
- type: TechArticle
  headline: How to Generate DotCode Barcodes – Configuration Guide
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  dateModified: '2026-06-14'
  author: Aspose
- type: FAQPage
  questions:
  - question: Can I generate DotCode barcodes in SVG format?
    answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
  - question: Is it possible to embed a logo inside a DotCode symbol?
    answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
  - question: How does error correction work for DotCode?
    answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
  - question: Do I need a separate library to read DotCode from a PDF?
    answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
  - question: What is the maximum data size for a single DotCode symbol?
    answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Generate DotCode Barcodes – Configuration Guide

## Introduction
**How to generate DotCode** barcodes quickly and reliably is a common requirement for developers building inventory, tracking, or mobile‑scan solutions. In this tutorial we’ll walk you through every configuration option that Aspose.BarCode for .NET offers for DotCode symbols—aspect‑ratio tweaks, Auto and Bytes encoding modes, extended code‑text handling, reader initialization, rows/columns layout, and structured‑append mode. By the end you’ll be able to produce perfectly sized, high‑density DotCode images that meet industry standards and integrate seamlessly into any .NET application.

## Quick Answers
- **What is the primary class to create a DotCode barcode?** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **Which property controls the aspect ratio?** `BarCodeImageAspectRatio`.
- **Can I switch between Auto and Bytes encoding?** Yes, via `EncodeMode` property.
- **Is a separate reader required for DotCode?** No, the same `BarcodeGenerator` can decode when `ReadBarcode` is called.
- **What .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## How to generate DotCode barcodes using Aspose.BarCode for .NET?
`BarcodeGenerator` is the primary class in Aspose.BarCode for creating barcode images. Load the `BarcodeGenerator` with `EncodeTypes.DotCode`, set the desired properties (aspect ratio, encoding mode, rows/columns, etc.), and call `GenerateBarCodeImage()`—the library returns a ready‑to‑use `System.Drawing.Image` or a byte array. This single‑step workflow handles all low‑level encoding details, supports output formats such as PNG, JPEG, and SVG, and can render images up to 10 000 × 10 000 px without consuming excessive memory.

## What is a DotCode barcode?
A DotCode barcode is a high‑density, square‑shaped 2D symbology that stores up to 1 200 numeric or 800 alphanumeric characters in a compact matrix of dots. It is optimized for small package labeling and mobile scanning, offering fast read rates even on low‑resolution cameras.

## Why use DotCode with Aspose.BarCode?
Aspose.BarCode supports **20+** 2D barcode types, including DotCode, and can process files larger than **200 MB** without loading the entire image into memory. The library guarantees **99.9 %** scan accuracy on standard smartphone cameras and provides built‑in error‑correction levels to minimise read failures.

## Prerequisites
- .NET Framework 4.5 or higher, or .NET Core 3.1 / .NET 5+.
- Aspose.BarCode for .NET (latest version recommended).
- A temporary or full license key (trial works for development).

## DotCode Aspect Ratio Customization
The **aspect‑ratio** determines how stretched or squashed the DotCode matrix appears. Use the `BarCodeImageAspectRatio` property to set a value between **0.5** (taller) and **2.0** (wider). A ratio of **1.0** yields a perfectly square symbol, which is the default and works best for most scanners.

> **Tip:** When printing on narrow labels, a ratio of **0.75** often improves readability without sacrificing data capacity.

## DotCode Encoding Mode (Auto)
In **Auto** mode the library analyses the input string and automatically selects the most efficient encoding (numeric, alphanumeric, or byte). This maximizes data density and reduces the overall symbol size.

> **Direct answer:** Set `EncodeMode = EncodeModes.Auto` on the `BarcodeGenerator` to let Aspose.BarCode decide the optimal encoding for your data, ensuring the smallest possible DotCode while preserving all characters.

## DotCode Encoding Mode (Bytes)
When you need to store binary data or pre‑encoded byte arrays, choose **Bytes** mode. This forces the generator to treat the input as raw bytes, bypassing automatic character set detection.

> **Direct answer:** Use `EncodeMode = EncodeModes.Bytes` and provide a `byte[]` payload to embed binary information such as encrypted identifiers or compressed files directly into the DotCode symbol.

## DotCode Extended Code Text Configuration
Extended code text lets you attach supplemental information that isn’t part of the main data payload but can be displayed alongside the barcode in reports or GUIs. Set the `ExtendedCodeText` property to any string (up to **256** characters) and choose a font via `ExtendedCodeTextFont`.

> **Pro tip:** Pair extended text with a smaller font size (e.g., 8 pt) to keep the visual footprint low while still providing human‑readable context.

## DotCode Reader Initialization
`BarCodeReader` is the class used to decode barcodes from images or streams. Reading a DotCode image is as straightforward as generation. Instantiate a `BarCodeReader` with the image stream and specify `EncodeTypes.DotCode`. Call `ReadBarCode()` to retrieve the decoded string.

> **Direct answer:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – this single block decodes the symbol without external dependencies.

## DotCode Rows and Columns Configuration
DotCode allows explicit control over the number of rows and columns, which influences symbol size and error‑correction capacity. Use `Rows` and `Columns` properties to set values between **10** and **144**. Larger matrices increase data capacity and robustness.

> **Best practice:** For inventory tags that must survive rough handling, configure **Rows = 64** and **Columns = 64** to add extra redundancy.

## DotCode Structured Append Mode Configuration
Structured Append enables splitting a large payload across multiple DotCode symbols that can be read sequentially. Set `StructuredAppend = true` and define `StructuredAppendCount` and `StructuredAppendIndex` for each part.

> **Direct answer:** Enable `StructuredAppend` on each `BarcodeGenerator`, assign a unique index (starting at 1), and set the total count; the library will embed the necessary linking information automatically.

## Common Issues and Solutions
- **Unreadable barcode on low‑resolution screens:** Increase the `Resolution` property to at least **300 dpi** before generation.
- **Data truncation warnings:** Verify that the input length does not exceed the maximum for the selected rows/columns; adjust size or switch to Bytes mode if needed.
- **License expiration during development:** Use a temporary license obtained from the Aspose portal; replace it with a permanent key before production deployment.

## Frequently Asked Questions

**Q: Can I generate DotCode barcodes in SVG format?**  
A: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator to receive a scalable vector output.

**Q: Is it possible to embed a logo inside a DotCode symbol?**  
A: Aspose.BarCode does not support direct logo embedding for DotCode, but you can overlay an image after generation using standard graphics libraries.

**Q: How does error correction work for DotCode?**  
A: The symbology includes built‑in Reed‑Solomon error correction; increasing rows/columns automatically raises the correction level.

**Q: Do I need a separate library to read DotCode from a PDF?**  
A: No, the same `BarCodeReader` can extract DotCode from PDF pages, images, or streams without additional tools.

**Q: What is the maximum data size for a single DotCode symbol?**  
A: Up to **1 200** numeric or **800** alphanumeric characters, depending on the chosen rows/columns configuration.

---

**Last Updated:** 2026-06-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

## DotCode Barcode Configuration Tutorials
### [Customize DotCode Aspect Ratio](./dotcode-aspect-ratio-customization/)
Learn to customize DotCode barcode aspect ratio using Aspose.BarCode for .NET. Create tailored barcodes for your applications effortlessly.
### [DotCode Encoding Mode (Auto)](./dotcode-encoding-mode-auto/)
Explore DotCode Encoding Mode (Auto) in Aspose.BarCode for .NET, a powerful tool for barcode generation. Learn how to generate DotCode barcodes step by step. Check out the documentation, download the library, and get temporary licenses.
### [DotCode Encoding Mode (Bytes)](./dotcode-encoding-mode-bytes/)
Learn DotCode Encoding with Aspose.BarCode for .NET: Step-by-step guide to generate barcodes.
### [DotCode Extended Code Text Configuration](./dotcode-extended-code-text-configuration/)
Generate DotCode Extended Code Text Configuration with ease using Aspose.BarCode for .NET. Follow our step-by-step guide for efficient barcode creation.
### [DotCode Reader Initialization](./dotcode-reader-initialization/)
Learn how to initialize DotCode Reader using Aspose.BarCode for .NET. Create DotCode barcodes with ease for various applications.
### [DotCode Rows and Columns Configuration](./dotcode-rows-columns-configuration/)
Learn to configure DotCode Rows and Columns with Aspose.BarCode for .NET. Generate precise and customizable 2D barcodes effortlessly.
### [DotCode Structured Append Mode Configuration](./dotcode-structured-append-mode-configuration/)
Learn to configure DotCode Structured Append Mode with Aspose.BarCode for .NET and create efficient barcodes.

## Related Tutorials

- [Customize DotCode Aspect Ratio with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [DotCode Extended Code Text Configuration with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [DotCode Encoding Mode (Auto) in Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}