---
title: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
linktitle: DataMatrix Encoding Mode (ASCII)
second_title: Aspose.BarCode .NET API
description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode for .NET. This guide shows how to generate barcode C# quickly.
weight: 13
url: /net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
date: 2026-06-09
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
schemas:
- type: TechArticle
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  dateModified: '2026-06-09'
  author: Aspose
- type: HowTo
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
- type: FAQPage
  questions:
  - question: Can I use this in a commercial application?
    answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
  - question: Does the library work with .NET Core?
    answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
  - question: How many characters can I encode in ASCII mode?
    answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
  - question: Can I change the barcode’s foreground or background color?
    answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
  - question: Where can I find more advanced examples?
    answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET

## Introduction

Ready to **create DataMatrix barcode** images that use the efficient ASCII encoding? In this tutorial you’ll learn how to generate a DataMatrix barcode in ASCII mode using Aspose.BarCode for .NET. We’ll walk through every step—from setting up the project to saving the final image—so you can add barcode generation to your C# applications in minutes.

## Quick Answers
- **What library is best for DataMatrix in .NET?** Aspose.BarCode for .NET  
- **How many lines of code are needed?** About 5‑7 lines for a basic ASCII barcode  
- **Do I need a license?** A free trial works for development; a license is required for production  
- **Supported platforms?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Can I change size or colors?** Yes, Aspose.BarCode exposes properties for dimensions and foreground/background colors  

## What is DataMatrix barcode?
DataMatrix is a two‑dimensional barcode that stores text and binary data in a compact square pattern.  
A DataMatrix barcode encodes information in a grid of black and white modules, allowing up to 2,335 alphanumeric characters in a single symbol. It is widely used in manufacturing, logistics, and healthcare because it can be printed at very small sizes while remaining highly scannable.

## How to create DataMatrix barcode in ASCII mode?
Load the Aspose.BarCode namespace, instantiate a `BarcodeGenerator`, set the `EncodeMode` to **EncodeMode.ASCII**, assign your data string, and call `Save` to write the image file. This approach produces a perfectly compliant DataMatrix barcode with ASCII‑only encoding in just a few lines of C# code.

## Why use ASCII encoding for DataMatrix?
ASCII mode is the default and most efficient encoding for plain‑text data, delivering the smallest possible symbol size for alphanumeric strings. It supports all 128 ASCII characters, processes data faster than extended modes, and guarantees maximum compatibility with legacy scanners that expect standard ASCII symbols.

## Prerequisites

1. **Development Environment** – Visual Studio, Rider, or any C#‑compatible IDE.  
2. **Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).  
   - Documentation: [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
   - Community help: [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  
3. **Basic C# knowledge** – Familiarity with .NET project structure will help you follow the steps quickly.  
4. **Other Aspose products** can be found [here](https://releases.aspose.com/).

## Import Namespaces

To start, add the required `using` directives at the top of your C# file:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

These namespaces give you access to the `BarcodeGenerator` class and the image‑related types needed for saving the output.

## Step 1: Create a Directory

Choose a folder where the generated barcode images will be stored. Replace `"Your Directory Path"` with an absolute or relative path that exists on your machine.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

The code ensures the directory exists before attempting to write any files, preventing runtime errors.

## Step 2: Encoding Data in ASCII Mode

The `BarcodeGenerator` class creates and configures barcode images. The `DataMatrixEncodeMode` enumeration selects the encoding algorithm for DataMatrix symbols.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

After running the code, you’ll find `datamatrix_ascii.png` in the folder you specified. The image contains a DataMatrix barcode that encodes the string `"1234567890"` using the compact ASCII mode.

## Common issues and solutions

- **File‑access errors** – Ensure the application has write permissions to the target folder. Running Visual Studio as Administrator can resolve permission issues on Windows.  
- **Incorrect symbol size** – If the barcode appears too large or too small, tweak `generator.Parameters.Image.Width` and `Height` or let Aspose automatically calculate the optimal size by omitting those properties.  
- **Unsupported characters** – ASCII mode only accepts characters in the 0‑127 range. For Unicode data, switch to `DataMatrixEncodeMode.Base256` or another suitable mode.

## Frequently Asked Questions

**Q: Can I use this in a commercial application?**  
A: Yes, a valid Aspose license is required for production use; a free trial is available for evaluation.

**Q: Does the library work with .NET Core?**  
A: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET 6, and later versions.

**Q: How many characters can I encode in ASCII mode?**  
A: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol when using ASCII encoding.

**Q: Can I change the barcode’s foreground or background color?**  
A: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to any `System.Drawing.Color` value.

**Q: Where can I find more advanced examples?**  
A: The official documentation contains dozens of samples covering custom sizes, colors, and error‑correction levels.

## FAQ's

### Q1: Can I use Aspose.BarCode for .NET with other programming languages besides C#?

A1: Aspose.BarCode supports multiple programming languages, but this tutorial focuses on C#.

### Q2: What are the different encoding modes available in DataMatrix barcodes?

A2: DataMatrix barcodes support various encoding modes, including ASCII, C40, Text, and Base256. Each mode is suited for different types of data.

### Q3: Can I customize the appearance of the generated barcode, such as its size and color?

A3: Yes, Aspose.BarCode provides a wide range of parameters for customizing barcode appearance, including size, color, and more.

### Q4: Is there a free trial version of Aspose.BarCode for .NET available?

A4: Yes, you can explore Aspose.BarCode for .NET with a free trial from [here](https://releases.aspose.com/).

### Q5: Where can I purchase a license for Aspose.BarCode for .NET?

A5: You can purchase a license from the Aspose website [here](https://purchase.aspose.com/buy).

---

**Last Updated:** 2026-06-09  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [DataMatrix Encoding in Bytes with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}