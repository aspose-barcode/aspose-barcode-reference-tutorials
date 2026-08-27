---
title: How to Read DataMatrix Append with Aspose.BarCode for .NET
linktitle: DataMatrix Structured Append Configuration
second_title: Aspose.BarCode .NET API
description: Learn how to read datamatrix and generate structured append barcodes in .NET using Aspose.BarCode, the fast and reliable barcode library.
weight: 11
url: /net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/
date: 2026-06-14
keywords:
  - how to read datamatrix
  - DataMatrix structured append
  - Aspose.BarCode .NET
schemas:
- type: TechArticle
  headline: How to Read DataMatrix Append with Aspose.BarCode for .NET
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  dateModified: '2026-06-14'
  author: Aspose
- type: HowTo
  name: How to Read DataMatrix Append with Aspose.BarCode for .NET
  description: Learn how to read datamatrix and generate structured append barcodes
    in .NET using Aspose.BarCode, the fast and reliable barcode library.
  steps:
  - name: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
    text: Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
  - name: You can also browse other Aspose products [here](https://releases.aspose.com/).
    text: You can also browse other Aspose products [here](https://releases.aspose.com/).
  - name: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
    text: A .NET development environment such as Visual Studio 2022 or Visual Studio
      Code with the C# extension.
- type: FAQPage
  questions:
  - question: What library handles DataMatrix structured append?
    answer: Aspose.BarCode for .NET.
  - question: How many symbols can a single structured append sequence contain?
    answer: Up to 16 DataMatrix symbols.
  - question: Do I need a license for development?
    answer: A free trial works for development and testing.
  - question: Which .NET versions are supported?
    answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
  - question: Can I read the barcode without an image file?
    answer: Yes, you can decode from a byte array or stream.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrix Structured Append Configuration with Aspose.BarCode for .NET

If you're a developer looking for **how to read datamatrix** using structured append in your .NET applications, Aspose.BarCode for .NET is your go‑to solution. In this step‑by‑step guide, we’ll walk through generating and decoding DataMatrix barcodes that are split across multiple symbols. By the end of this tutorial you’ll be comfortable creating, configuring, and reading DataMatrix structured append barcodes with Aspose.BarCode for .NET.

## Quick Answers
- **What library handles DataMatrix structured append?** Aspose.BarCode for .NET.
- **How many symbols can a single structured append sequence contain?** Up to 16 DataMatrix symbols.
- **Do I need a license for development?** A free trial works for development and testing.
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Can I read the barcode without an image file?** Yes, you can decode from a byte array or stream.

## What is how to read datamatrix?
**how to read datamatrix** refers to the process of decoding DataMatrix symbols and, when applicable, stitching together the pieces of a structured‑append sequence to retrieve the original data payload. Aspose.BarCode provides built‑in support for this workflow, handling symbol ordering and data concatenation automatically.

## Why use Aspose.BarCode for DataMatrix structured append?
Aspose.BarCode supports **30+ barcode symbologies** and can decode images up to **10,000 × 10,000 px** in under **200 ms** on typical server hardware. The library also offers **zero‑dependency deployment**, meaning you don’t need additional native DLLs, and it works across Windows, Linux, and macOS .NET runtimes.

## Prerequisites

Before diving into the tutorial, you'll need:

1. Aspose.BarCode for .NET Library – download it from [here](https://releases.aspose.com/barcode/net/).
2. You can also browse other Aspose products [here](https://releases.aspose.com/).
3. A .NET development environment such as Visual Studio 2022 or Visual Studio Code with the C# extension.

Now, let’s start building and reading DataMatrix structured append barcodes.

## Import Namespaces

The first step is to import the namespaces that expose the barcode API.

The `BarCodeWriter` class is Aspose.BarCode's entry point for creating barcodes, while `BarCodeReader` handles decoding.

```csharp
using Aspose.BarCode.BarCodeRecognition;
using Aspose.BarCode.Generation;
using System;
using System.Drawing;
```

Now that you've imported the required namespaces, let’s generate a structured‑append barcode.

## How to read DataMatrix structured append barcodes?

Load the generated image (or stream) into a `BarCodeReader`, enable the `ReadStructuredAppend` option, and call `ReadBarcode`. The reader will automatically return the combined data and expose sequence details such as `StructuredAppendFileId`, `StructuredAppendTotalCount`, and `StructuredAppendSegmentId`. The combined result is returned as a single string, and you can also retrieve the individual segment identifiers via the reader's `StructuredAppendSegmentId` property for custom processing.

```csharp
    using (BarCodeReader reader = new BarCodeReader(bitmap, DecodeType.DataMatrix))
    {
        reader.ReadBarCodes();

        Console.WriteLine("Barcode ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodeId);
        Console.WriteLine("Barcodes count: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendBarcodesCount);
        Console.WriteLine("File ID: {0}", reader.FoundBarCodes[0].Extended.DataMatrix.StructuredAppendFileId);
    }
}
```

In this step, we use the reader to extract the barcode ID, total count, and file ID, confirming that the structured‑append configuration was correctly interpreted.

## Step 1: Set Up DataMatrix Structured Append Configuration

To create a DataMatrix structured append barcode, you need to set up its configuration. This includes defining the directory path, the barcode ID, the number of barcodes, and the file ID.

```csharp
string path = "Your Directory Path";

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;

    // Set DataMatrix structured append mode
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodeId = 3;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendBarcodesCount = 5;
    generator.Parameters.Barcode.DataMatrix.StructuredAppendFileId = 150;

    // Generate the barcode image
    Bitmap bitmap = generator.GenerateBarCodeImage();
```

In this step, we've configured the DataMatrix barcode with the desired parameters.

## Common Issues and Solutions

- **Incorrect segment ordering:** Ensure `StructuredAppendSegmentId` values are sequential starting at 0; otherwise the reader cannot re‑assemble the data correctly.
- **Mismatched total count:** The `StructuredAppendTotalCount` must be the same across all symbols; a mismatch will cause the reader to treat the sequence as incomplete.
- **Image quality:** Low‑resolution images can cause decoding failures. Aim for at least **300 dpi** when rendering the barcode to a bitmap.

## Frequently Asked Questions

### Q1: What is DataMatrix structured append, and why is it used?

A1: DataMatrix structured append is a feature that allows you to split a large amount of data into multiple smaller barcodes. This is particularly useful when you have limited space for a single barcode or need to organize data efficiently. It's commonly used in logistics, healthcare, and manufacturing.

### Q2: Can I use Aspose.BarCode for .NET in my open‑source project?

A2: Yes, Aspose.BarCode for .NET offers a free trial version that you can use in open‑source projects. You can find the trial version [here](https://releases.aspose.com/).

### Q3: Is there any community support available for Aspose.BarCode for .NET?

A3: Yes, you can seek community support and interact with other users on the Aspose.BarCode forum [here](https://forum.aspose.com/c/barcode/13).

### Q4: How can I obtain a temporary license for Aspose.BarCode for .NET?

A4: If you need a temporary license for evaluation or testing purposes, you can obtain one from [here](https://purchase.aspose.com/temporary-license/).

### Q5: Does Aspose.BarCode for .NET support other barcode types?

A5: Yes, Aspose.BarCode for .NET supports a wide range of barcode types, including QR codes, Code 128, EAN‑13, and many more. You can explore the full documentation [here](https://reference.aspose.com/barcode/net/) to see the complete list of supported barcode types.

---

**Last Updated:** 2026-06-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [DataMatrix Reader Programming with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-reader-programming/)
- [Generate DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-versions/)
- [Master DataMatrix Macro Configuration with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}