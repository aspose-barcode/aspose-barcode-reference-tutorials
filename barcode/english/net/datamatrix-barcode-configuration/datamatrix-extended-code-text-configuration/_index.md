---
title: Create barcode aspose .net: Configuring DataMatrix Code Text
linktitle: DataMatrix Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
description: Learn how to create barcode aspose .net and configure DataMatrix extended code text using Aspose.BarCode for .NET.
weight: 17
url: /net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
date: 2026-01-17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create barcode aspose .net: Configuring DataMatrix Code Text

Integrating barcodes into modern .NET applications is no longer a niche task—it’s a core requirement for inventory, logistics, and mobile scanning solutions. In this guide you’ll **create barcode aspose .net** by configuring a DataMatrix barcode with extended code text using the Aspose.BarCode library. We’ll walk through every step, from setting up the environment to generating and validating the barcode, so you can drop this functionality straight into your projects.

## Quick Answers
- **What library is needed?** Aspose.BarCode for .NET  
- **Which barcode type?** DataMatrix with extended code text  
- **Can I use .NET Core / .NET 6?** Yes, the API is cross‑platform  
- **Do I need a license for testing?** A free trial works for development; a license is required for production  
- **How long does implementation take?** About 10‑15 minutes for a basic example  

## Prerequisites

Before you start, verify that you have the following:

1. **Aspose.BarCode for .NET** – download it from the official site [here](https://releases.aspose.com/barcode/net/).  
2. **A .NET development environment** – Visual Studio, Rider, or VS Code with the .NET SDK.  
3. **Basic C# knowledge** – you should be comfortable with classes, namespaces, and the `using` directive.

## Import Namespaces

Add the required namespaces at the top of your C# file so the compiler knows where to find the barcode classes.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

These namespaces give you access to both barcode generation and recognition features.

## Why use DataMatrix extended code text?

DataMatrix supports **extended code text**, allowing you to embed multiple encodings (UTF‑8, C40, Text, etc.) in a single symbol. This is especially useful when you need to store multilingual data or combine alphanumeric and binary information—perfect for product labeling, medical devices, and smart packaging.

## Step‑by‑step guide

### Step 1: Define the output folder

Specify where the generated barcode image will be saved. Replace the placeholder with a valid path on your machine.

```csharp
string path = "Your Directory Path";
```

### Step 2: Build the extended code text

Create a `DataMatrixExtCodetextBuilder` instance and add different segments. The builder handles the necessary ECI (Extended Channel Interpretation) markers automatically.

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

Instantiate `BarcodeGenerator` with the `EncodeTypes.DataMatrix` enum and the extended codetext. Adjust visual parameters such as X‑dimension and the human‑readable text that appears below the symbol.

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

Use `BarCodeReader` to make sure the generated symbol can be decoded correctly. This step is crucial for automated test pipelines.

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

## Frequently Asked Questions

### Q1: What is Aspose.BarCode for .NET?
A1: Aspose.BarCode for .NET is a powerful library that enables developers to generate and recognize a wide variety of barcode symbologies, including DataMatrix, QR, Code128, and more.

### Q2: Where can I find the documentation for Aspose.BarCode for .NET?
A2: You can access the full API reference [here](https://reference.aspose.com/barcode/net/).

### Q3: Is there a free trial available for Aspose.BarCode for .NET?
A3: Yes, a free trial version can be downloaded from [here](https://releases.aspose.com/).

### Q4: How do I obtain a temporary license for testing?
A4: Temporary licenses are provided for evaluation purposes and can be requested [here](https://purchase.aspose.com/temporary-license/).

### Q5: Where can I get support or ask questions about Aspose.BarCode for .NET?
A5: The official Aspose.BarCode forum is the best place to seek help: [here](https://forum.aspose.com/c/barcode/13).

---

**Last Updated:** 2026-01-17  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}