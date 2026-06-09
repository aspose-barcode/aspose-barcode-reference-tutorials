---
title: "Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode"
linktitle: DataMatrix Barcode Configuration
second_title: Aspose.BarCode .NET API
description: "Learn how to generate datamatrix barcode with Aspose.BarCode for .NET, customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient barcode creation."
weight: 30
url: /net/datamatrix-barcode-configuration/
date: 2026-06-09
keywords:
  - generate datamatrix barcode
  - datamatrix c40 encoding
  - aspose barcode .net
  - datamatrix ecc modes
  - barcode aspect ratio
schemas:
- type: TechArticle
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  dateModified: '2026-06-09'
  author: Aspose
- type: HowTo
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
- type: FAQPage
  questions:
  - question: How do I decide which ECC mode to use?
    answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
  - question: Can I embed custom text in a DataMatrix barcode?
    answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
  - question: Is there a way to automatically select the best encoding mode?
    answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
  - question: What are the performance considerations for large barcode batches?
    answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
  - question: Does Aspose.BarCode support .NET Core and .NET 5/6?
    answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode

Welcome to our comprehensive tutorial series on **generate datamatrix barcode** using Aspose.BarCode for .NET. Whether you're a seasoned developer fine‑tuning barcode output or a newcomer eager to understand the fundamentals, this guide walks you through every step—from basic configuration to advanced encoding techniques—so you can deliver reliable, scan‑ready barcodes in any .NET application.

## Quick Answers
- **What is the primary purpose?** To create and customize DataMatrix barcodes programmatically.  
- **Which library is used?** Aspose.BarCode for .NET.  
- **Do I need a license?** A free trial is available; a commercial license is required for production.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Can I customize aspect ratio?** Yes – see the “How to customize DataMatrix aspect ratio” section.

## What is generate datamatrix barcode?
A DataMatrix barcode is a two‑dimensional matrix of black and white cells that can store up to 2 300 alphanumeric characters. Using Aspose.BarCode, you can **generate datamatrix barcode** images, PDFs, or SVGs directly from your .NET code, controlling size, error‑correction level, and encoding mode to meet any industry standard.

## Why use Aspose.BarCode for DataMatrix?
Aspose.BarCode renders DataMatrix symbols at up to **600 dpi** without pixelation, guaranteeing crisp scans on high‑resolution printers. It supports **all 50+ ECC and macro modes**—including ECC 000‑140, ECC 200, and Macro 05/06—so you can choose the optimal error‑correction level for your data size. The API offers **ASCII, C40, Text, X12, and Bytes** encoding options, letting you pack data efficiently. Integration requires only a single NuGet package and no external native libraries.

## How to customize DataMatrix aspect ratio
The `AspectRatio` property of `BarCodeGenerator` controls the width‑to‑height proportion of the generated DataMatrix symbol. `BarCodeGenerator` is the main class in Aspose.BarCode used to create barcode images.  

**Direct answer:** Set `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2` (or any value between 0.5 and 2.0) before calling `GenerateBarCodeImage()`. The library automatically recalculates module size to preserve scan reliability while respecting the requested ratio.

### Step‑by‑step
1. **Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.  
2. **Adjust** `AspectRatio` to your desired value.  
3. **Generate** the image and verify with a scanner or Aspose’s built‑in reader.

## How to generate DataMatrix ECC 000‑140 barcodes
ECC 000‑140 is ideal for short data strings where a compact symbol is required, offering up to 140 error‑correction codewords. `DataMatrixEccMode.Ecc000140` selects the ECC 000‑140 error‑correction scheme for DataMatrix.  

**Direct answer:** Use `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` before rendering. This switches the encoder to the ECC 000‑140 algorithm, producing the smallest possible matrix for the given data while still providing robust error correction.

### Practical tip
When encoding numeric data under 20 characters, ECC 000‑140 often yields a 10 × 10 matrix, which saves valuable label space.

## How to generate DataMatrix ECC 200 barcodes
ECC 200 is the most widely adopted DataMatrix mode, supporting up to 2 335 alphanumeric characters and offering superior error correction. `DataMatrixEccMode.Ecc200` selects the ECC 200 error‑correction scheme for DataMatrix.  

**Direct answer:** Set `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` and provide your payload via `CodeText`. The library then selects the optimal matrix size automatically.

### When to prefer ECC 200
Use ECC 200 for longer strings, mixed‑type data, or when you need the highest resilience against damage—up to **30 %** of the symbol can be restored.

## How to master DataMatrix encoding in ASCII
ASCII mode encodes characters using a single byte per character, making it the most space‑efficient for plain text. `DataMatrixEncodeMode.Ascii` tells the generator to use ASCII encoding for the DataMatrix symbol.  

**Direct answer:** Assign `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` and set `CodeText` to your ASCII string. The engine packs the data without extra overhead, producing the smallest possible matrix for pure ASCII content.

### Example scenario
A warehouse SKU consisting of uppercase letters and digits (e.g., “AB1234”) fits perfectly in ASCII mode, often resulting in a 12 × 12 matrix.

## How to generate DataMatrix Mode (Auto)
Auto mode lets Aspose.BarCode analyze the input and automatically pick the most efficient encoding (ASCII, C40, Text, X12, or Bytes). `DataMatrixEncodeMode.Auto` enables this automatic selection feature.  

**Direct answer:** Set `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto`. The library evaluates the payload, selects the optimal mode, and renders the barcode in a single step.

### Benefits
Auto mode reduces development effort and guarantees the smallest possible symbol for mixed‑type data, improving scan speed.

## How to use DataMatrix encoding mode (Bytes)
Bytes mode is designed for binary data, such as encrypted payloads or compressed files. `DataMatrixEncodeMode.Bytes` instructs the generator to treat each byte as raw data.  

**Direct answer:** Use `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` and provide a Base64‑encoded string as `CodeText`. The encoder treats each byte as raw data, preserving the exact binary representation.

### Use case
Embedding a 128‑bit GUID or a small encrypted token directly into a DataMatrix symbol.

## How to master DataMatrix encoding mode (C40)
C40 mode compresses upper‑case alphanumeric data, achieving up to **40 %** size reduction compared with ASCII. `DataMatrixEncodeMode.C40` activates this compression algorithm.  

**Direct answer:** Set `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` and supply an upper‑case string (e.g., “HELLO WORLD”). The engine packs three characters into two codewords, shrinking the final matrix.

### Pro tip
C40 works best when the payload consists mainly of upper‑case letters, numbers, and spaces. For mixed case, consider Auto mode.

## How to configure DataMatrix code text
The `CodeText` property defines the exact data stored in the barcode. It can include plain text, numeric strings, or even XML payloads. `CodeText` is the primary string property of `BarCodeGenerator` that holds the barcode payload.  

**Direct answer:** Assign `generator.Parameters.Barcode.CodeText = "YourDataHere"` before rendering. The property accepts any UTF‑8 string up to the maximum length supported by the chosen ECC mode.

### Advanced tip
Combine `CodeText` with `ExtendedDataMatrix` to embed additional metadata without increasing the visible matrix size.

## How to master DataMatrix macro configuration
Macro modes (Macro 05 and Macro 06) allow you to embed a secondary DataMatrix symbol inside the primary one, useful for linking to external data sources. `DataMatrixMacroMode.Macro05` and `DataMatrixMacroMode.Macro06` enable these macro features.  

**Direct answer:** Enable macro mode with `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05` (or `Macro06`) and set `MacroPdf417` properties for the secondary payload. The generator creates a composite symbol that scanners can interpret as two linked codes.

### Real‑world example
Embedding a URL in the macro portion while keeping product identifiers in the primary matrix, enabling seamless web‑to‑barcode integration.

---

*Using Aspose.BarCode For .NET Tutorials Listing*

## DataMatrix Barcode Configuration Tutorials
### [Customizing DataMatrix Aspect Ratio](./datamatrix-aspect-ratio-customization/)
Learn how to customize DataMatrix barcode aspect ratios using Aspose.BarCode for .NET. Step-by-step guide for barcode generation.
### [Generate DataMatrix ECC 000-140 Barcodes](./datamatrix-ecc-000-140-configuration/)
Create DataMatrix ECC 000-140 barcodes with ease using Aspose.BarCode for .NET. Boost efficiency in inventory management and more.
### [Generate DataMatrix ECC 200 Barcodes](./datamatrix-ecc-200-configuration/)
Learn how to generate DataMatrix ECC 200 barcodes in .NET using Aspose.BarCode. Streamline operations with efficient barcode creation.
### [Master DataMatrix Encoding in ASCII](./datamatrix-encoding-mode-ascii/)
Learn to create DataMatrix barcodes in ASCII mode using Aspose.BarCode for .NET. Step-by-step guide for developers.
### [Generate DataMatrix Mode (Auto)](./datamatrix-encoding-mode-auto/)
Learn how to generate DataMatrix Mode (Auto) with Aspose.BarCode for .NET. This step-by-step guide covers everything from prerequisites to reading barcodes.
### [DataMatrix Encoding Mode (Bytes)](./datamatrix-encoding-mode-bytes/)
Learn how to encode data in DataMatrix format using Bytes mode with Aspose.BarCode for .NET. Follow our step-by-step guide for barcode generation and recognition.
### [Master DataMatrix Encoding Mode (C40)](./datamatrix-encoding-mode-c40/)
Learn DataMatrix Encoding Mode (C40) with Aspose.BarCode for .NET. Create custom barcodes efficiently. Explore step-by-step guide.
### [Configuring DataMatrix Code Text](./datamatrix-extended-code-text-configuration/)
Learn to configure DataMatrix extended code text using Aspose.BarCode for .NET. Generate, recognize, and integrate barcodes in your .NET applications.
### [Master DataMatrix Macro Configuration](./datamatrix-macro-configuration/)
Learn how to configure DataMatrix Macro barcodes with Aspose.BarCode for .NET. Generate, customize, and recognize DataMatrix barcodes in your .NET applications.

## Frequently Asked Questions

**Q: How do I decide which ECC mode to use?**  
A: Choose ECC 000‑140 for small data sets with limited error correction, or ECC 200 for larger data and higher reliability. Macro mode adds an extra data layer for linking.

**Q: Can I embed custom text in a DataMatrix barcode?**  
A: Yes, set the `CodeText` property to your custom string, then select the appropriate encoding mode (ASCII, C40, etc.) to control size.

**Q: Is there a way to automatically select the best encoding mode?**  
A: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks the most space‑efficient mode automatically.

**Q: What are the performance considerations for large barcode batches?**  
A: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and generate PNG images for lossless quality or JPEG for smaller file size. Processing 10 000 symbols typically completes in under 30 seconds on a standard 8‑core server.

**Q: Does Aspose.BarCode support .NET Core and .NET 5/6?**  
A: Absolutely – the library is fully compatible with .NET Framework, .NET Core, and the latest .NET releases, offering the same feature set across all platforms.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}