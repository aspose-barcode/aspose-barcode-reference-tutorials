---
title: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding with Aspose.BarCode – full guide for .NET Core barcode generation.
weight: 16
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
date: 2026-06-09
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
schemas:
- type: TechArticle
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  dateModified: '2026-06-09'
  author: Aspose
- type: HowTo
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
- type: FAQPage
  questions:
  - question: What is DataMatrix Encoding Mode (C40)?
    answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
  - question: Where can I find the Aspose.BarCode for .NET documentation?
    answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
  - question: Is Aspose.BarCode for .NET compatible with all .NET versions?
    answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
  - question: Can I try Aspose.BarCode for .NET before purchasing?
    answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
  - question: Where can I get support for Aspose.BarCode for .NET?
    answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Master DataMatrix Encoding Mode (C40) with Aspose.BarCode for .NET

## Introduction

In this tutorial you’ll learn **how to generate datamatrix** barcodes and save them as PNG files using the C40 encoding mode with Aspose.BarCode for .NET. Whether you’re building an inventory system, a shipping‑label generator, or any solution that demands compact, high‑density symbols, mastering C40 gives you smaller symbols without sacrificing readability. We’ll walk through every step—from setting up the environment to producing the final PNG—so you can integrate the code instantly into your project.

## Quick Answers
- **What does “how to generate datamatrix” refer to?** Creating a DataMatrix barcode image programmatically.  
- **Which encoding mode is covered?** DataMatrix C40, an efficient alphanumeric scheme.  
- **Do I need a license?** A free trial works for testing; a commercial license is required for production.  
- **Can I run this on .NET Core?** Yes, Aspose.BarCode fully supports .NET Core, .NET 5, .NET 6 and later.  
- **What file format is produced?** PNG – a loss‑less, web‑friendly image format.

## How to Generate DataMatrix with C40 Encoding

Load your data, configure the generator, and call `Save` – that’s the complete workflow in three concise steps. The `BarcodeGenerator` class handles symbol creation, while the `BarCodeImageFormat.Png` enum tells Aspose.BarCode to write the result as a PNG file. `Save` writes the generated barcode image to the specified file path in the chosen format. This direct‑answer paragraph gives you the end‑to‑end solution before we dive into each line of code.

## What is DataMatrix Encoding Mode (C40)?

`DataMatrixEncodeMode` is an enumeration that specifies which encoding scheme Aspose.BarCode should use for DataMatrix symbols. The `DataMatrixEncodeMode.C40` option selects the C40 alphanumeric encoding, which packs letters, digits, and a limited set of punctuation into fewer modules, reducing the overall symbol size while maintaining readability for typical inventory text. This efficient scheme is ideal when you need to encode alphanumeric data in a compact form.

## Why Use Aspose.BarCode for .NET?

Aspose.BarCode provides **30+ configurable parameters** for dimensions, error‑correction levels, and encoding modes, and it supports **50+ image and barcode formats**. The library runs on **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, delivering zero‑dependency generation that works on servers, desktops, and mobile devices alike.

## Prerequisites

Before we dive into the code, make sure you have the following:

1. **.NET Development Environment** – Visual Studio, Rider, or any IDE that supports C#.  
2. **Aspose.BarCode for .NET** – installed via NuGet or the official installer. See the [documentation](https://reference.aspose.com/barcode/net/) for details.  
3. **Basic C# knowledge** – you should be comfortable with namespaces, classes, and using statements.  
4. **Write‑access folder** – a directory on your machine where the PNG will be saved.

## Importing Necessary Namespaces

The `BarcodeGenerator` class is the entry point for creating any barcode. Add the required namespace at the top of your C# source file so you can access the generation API:

```csharp
using Aspose.BarCode.Generation;
```

## Step‑by‑Step Barcode Generation

Below is a **step‑by‑step barcode** walkthrough. Each step is explained in plain language, and the original placeholders are kept unchanged for copy‑paste convenience.

### Step 1: Define the Directory Path
Set the folder where the PNG image will be stored. Replace the placeholder with an actual path on your machine.

```csharp
string path = "Your Directory Path";
```

### Step 2: Set Up Barcode Generation
Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`, and provide the data you want to encode.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Step 3: Customize Barcode
Configure the X‑dimension (pixel width of the modules) and switch the encoding mode to C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Step 4: Save the Barcode Image
Finally, save the generated barcode as a PNG file. This is the concrete answer to **how to save png** with Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

When you run the program, you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready to be used in reports, labels, or web pages.

## Common Issues & Tips

- **Invalid Path** – Ensure the directory exists and you have write permissions; otherwise `gen.Save` will throw an exception.  
- **Incorrect Encoding Mode** – If you need to encode characters outside the C40 set, switch to `DataMatrixEncodeMode.Auto` or another appropriate mode.  
- **Image Size** – Adjust `XDimension.Pixels` to increase or decrease the overall barcode size without affecting readability.

## Frequently Asked Questions

**Q: What is DataMatrix Encoding Mode (C40)?**  
A: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols, ideal for text that includes letters, numbers, and a limited set of special characters.

**Q: Where can I find the Aspose.BarCode for .NET documentation?**  
A: You can find the documentation [here](https://reference.aspose.com/barcode/net/). It provides detailed guidance on all barcode types and encoding options.

**Q: Is Aspose.BarCode for .NET compatible with all .NET versions?**  
A: Yes, the library supports a wide range of .NET versions, from .NET Framework 4.5+ to .NET 6 and later.

**Q: Can I try Aspose.BarCode for .NET before purchasing?**  
A: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting [this link](https://releases.aspose.com/). It allows you to test the library’s features and capabilities.

**Q: Where can I get support for Aspose.BarCode for .NET?**  
A: You can find a supportive community and access support for Aspose.BarCode for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).

## Conclusion

By following this **step‑by‑step barcode** guide, you now know exactly **how to generate datamatrix** barcodes and save them as PNG files using the C40 encoding mode with Aspose.BarCode for .NET. This approach gives you full control over the barcode’s appearance, size, and data representation, making it easy to embed high‑quality barcodes into any .NET application.

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [DataMatrix Encoding in Bytes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Master DataMatrix Encoding in ASCII with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}