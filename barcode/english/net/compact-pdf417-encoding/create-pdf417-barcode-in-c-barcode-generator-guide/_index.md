---
category: general
date: 2026-07-18
description: Create PDF417 barcode in C# using the C# PDF417 barcode generator. Follow
  a step‑by‑step tutorial to build extended codetext, set appearance, and save the
  image.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- c# pdf417 barcode generator
language: en
lastmod: 2026-07-18
og_description: Create PDF417 barcode in C# instantly. This guide shows how to use
  the C# PDF417 barcode generator, configure extended mode, and export a PNG.
og_image_alt: Generated PDF417 barcode image created with C# PDF417 barcode generator
og_title: Create PDF417 Barcode in C# – Complete Generator Walkthrough
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  headline: Create PDF417 Barcode in C# – Barcode Generator Guide
  type: TechArticle
- description: Create PDF417 barcode in C# using the C# PDF417 barcode generator.
    Follow a step‑by‑step tutorial to build extended codetext, set appearance, and
    save the image.
  name: Create PDF417 Barcode in C# – Barcode Generator Guide
  steps:
  - name: 1. Install the barcode library
    text: 'Open your terminal in the project folder and run:'
  - name: 2. Build the extended codetext
    text: 'PDF417 supports **extended encoding**, allowing you to mix different character
      sets in a single barcode. Below we create three segments:'
  - name: 3. Initialise the **C# PDF417 barcode generator**
    text: Now that we have a valid codetext string, we hand it to the generator. The
      `using` statement ensures the underlying resources are released automatically.
  - name: 4. Configure appearance and encoding mode
    text: 'The default settings give you a tiny barcode that might be hard to read.
      Let’s tweak a few parameters:'
  - name: 5. Save the barcode image
    text: Finally, write the image to disk. The library supports PNG, JPEG, BMP, and
      several vector formats—PNG is a safe default because it preserves crisp edges.
  - name: Handling Unicode and special characters
    text: When you feed Unicode symbols directly into a plain‑text barcode, the generator
      may fall back to a fallback encoding, resulting in garbled output. By using
      `AddECICodetext` you explicitly tell the encoder which character set to apply,
      eliminating guesswork. If you ever need to support **Arabic**, **
  - name: Adjusting error correction level
    text: 'PDF417 offers four error‑correction levels (0‑8). Higher levels increase
      resilience but also enlarge the barcode. Adjust it via:'
  - name: Scaling for print vs. screen
    text: 'For on‑screen display you might keep the default 96 dpi. For high‑resolution
      printing (300 dpi or more), set:'
  - name: Common pitfalls
    text: '- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;`
      will cause `ECIEncodings` to be undefined. - **Directory not found** – The `Save`
      method won’t create intermediate folders; create them beforehand or use `Path.Combine`
      with `Environment.CurrentDirectory`. - **Wrong encode'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Create PDF417 Barcode in C# – Barcode Generator Guide
url: /net/compact-pdf417-encoding/create-pdf417-barcode-in-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PDF417 Barcode in C# – Barcode Generator Guide

Ever needed to **create PDF417 barcode** in a C# application but weren’t sure where to start? You’re not alone—many developers hit the same wall when they first tackle two‑dimensional barcodes. The good news? With the built‑in **C# PDF417 barcode generator** you can spin up a fully‑featured barcode in just a handful of lines.

In this tutorial we’ll walk through the entire process: building an extended codetext that mixes different character sets, configuring the generator for the right visual style, and finally saving the barcode as a PNG file. By the end you’ll have a ready‑to‑use snippet you can drop into any .NET project, plus tips for handling edge cases like Unicode characters or custom module widths.

---

## What You’ll Need

Before we dive in, make sure you have the following on your machine:

- **.NET 6.0** or later (the example works with .NET Framework 4.6+ as well)
- **Aspose.BarCode for .NET** (or any compatible library that exposes `BarcodeGenerator`, `EncodeTypes.Pdf417`, etc.)
- A code editor—Visual Studio, Rider, or even VS Code will do
- A folder you can write to, because the generator will save the PNG there

That’s it—no extra NuGet packages beyond the barcode library itself.

---

## Step‑by‑Step Guide to **create PDF417 barcode**

### 1. Install the barcode library

Open your terminal in the project folder and run:

```bash
dotnet add package Aspose.BarCode
```

The package adds the `Aspose.BarCode` namespace, which contains the `BarcodeGenerator` class we’ll use throughout.

### 2. Build the extended codetext

PDF417 supports **extended encoding**, allowing you to mix different character sets in a single barcode. Below we create three segments:

- A Windows‑1251 (Cyrillic) segment
- A UTF‑8 segment containing Unicode characters (the Japanese kanji for “dog” and “right”)
- A plain‑text segment

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

// Step 1: Build the extended codetext for the PDF417 barcode
Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();

// Add a Win1251‑encoded segment
builder.AddECICodetext(ECIEncodings.Win1251, "Will");

// Add a UTF‑8 segment with Unicode characters
builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");

// Add a plain‑text segment
builder.AddPlainCodetext("Plain text");

// Retrieve the combined codetext string
string extendedCodetext = builder.GetExtendedCodetext();
```

**Why this matters:**  
If you only use plain text, you’re limited to the default ASCII subset. By explicitly declaring ECI (Extended Channel Interpretation) segments you guarantee that scanners interpret each part correctly, regardless of the language or symbols involved.

### 3. Initialise the **C# PDF417 barcode generator**

Now that we have a valid codetext string, we hand it to the generator. The `using` statement ensures the underlying resources are released automatically.

```csharp
// Step 2: Create a PDF417 barcode generator using the extended codetext
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
{
    // Configuration goes here (see next step)
}
```

### 4. Configure appearance and encoding mode

The default settings give you a tiny barcode that might be hard to read. Let’s tweak a few parameters:

- **X‑Dimension** – controls the width of each module (pixel size)
- **EncodeMode** – tells the engine to treat the input as extended mode
- **TwoDDisplayText** – optional human‑readable text shown beneath the barcode

```csharp
    // Step 3: Configure barcode appearance and encoding mode
    generator.Parameters.Barcode.XDimension.Pixels = 15; // Wider modules for better scannability
    generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended; // Activate extended encoding
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode"; // Display text under the symbol
```

**Pro tip:** If you’re printing the barcode on a label printer, bump the `XDimension` up to 20 px or more; most scanners love a little extra space.

### 5. Save the barcode image

Finally, write the image to disk. The library supports PNG, JPEG, BMP, and several vector formats—PNG is a safe default because it preserves crisp edges.

```csharp
    // Step 4: Save the generated barcode image
    generator.Save("YOUR_DIRECTORY/Pdf417Extended.png", BarCodeImageFormat.Png);
}
```

Make sure `YOUR_DIRECTORY` exists and is writable. After running the program you should see a file similar to the screenshot below.

![Generated PDF417 barcode created with C# PDF417 barcode generator](https://example.com/images/pdf417-extended.png "Generated PDF417 barcode created with C# PDF417 barcode generator")

---

## Using the **C# PDF417 barcode generator** – deeper dive

### Handling Unicode and special characters

When you feed Unicode symbols directly into a plain‑text barcode, the generator may fall back to a fallback encoding, resulting in garbled output. By using `AddECICodetext` you explicitly tell the encoder which character set to apply, eliminating guesswork. If you ever need to support **Arabic**, **Hebrew**, or **emoji**, just pick the appropriate `ECIEncodings` value.

### Adjusting error correction level

PDF417 offers four error‑correction levels (0‑8). Higher levels increase resilience but also enlarge the barcode. Adjust it via:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // Balanced level
```

### Scaling for print vs. screen

For on‑screen display you might keep the default 96 dpi. For high‑resolution printing (300 dpi or more), set:

```csharp
generator.Parameters.ImageResolution = 300;
```

That ensures the saved PNG retains enough detail for laser printers.

### Common pitfalls

- **Missing `using` directive** – Forgetting `using Aspose.BarCode.Encoding;` will cause `ECIEncodings` to be undefined.
- **Directory not found** – The `Save` method won’t create intermediate folders; create them beforehand or use `Path.Combine` with `Environment.CurrentDirectory`.
- **Wrong encode mode** – If you leave `EncodeMode` at `Pdf417EncodeMode.Auto`, the library may treat your extended codetext as plain text, stripping out the ECI markers.

---

## Full, Ready‑to‑Run Example

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;

class Program
{
    static void Main()
    {
        // 1️⃣ Build extended codetext
        Pdf417ExtCodetextBuilder builder = new Pdf417ExtCodetextBuilder();
        builder.AddECICodetext(ECIEncodings.Win1251, "Will");
        builder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
        builder.AddPlainCodetext("Plain text");
        string extendedCodetext = builder.GetExtendedCodetext();

        // 2️⃣ Initialise generator with the extended codetext
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, extendedCodetext))
        {
            // 3️⃣ Configure appearance
            generator.Parameters.Barcode.XDimension.Pixels = 15;
            generator.Parameters.Barcode.Pdf417.EncodeMode = Pdf417EncodeMode.Extended;
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
            generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended mode";

            // 4️⃣ Save to PNG (ensure the folder exists)
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "Pdf417Extended.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine("PDF417 barcode generated successfully!");
    }
}
```


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}