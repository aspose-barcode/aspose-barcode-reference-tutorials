---
category: general
date: 2026-10-24
description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
  guide to generate barcode from string and render PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: en
lastmod: 2026-10-24
og_description: How to create GS1 barcode in ASP.NET using Aspose.BarCode. Follow
  this tutorial to generate barcode from string, configure visual settings, and save
  PNG files.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: How to create GS1 barcode in ASP.NET – complete Aspose guide
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: How to create GS1 barcode in ASP.NET with Aspose.BarCode
url: /net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to create GS1 barcode in ASP.NET with Aspose.BarCode

If you need to **how to create GS1 barcode** in an ASP.NET application, this guide shows you the exact steps. You will see how to generate a barcode from a string, configure the visual appearance, and save the result as a PNG image.

Creating GS1 barcodes does not require custom encoding logic. By using Aspose.BarCode you get a reliable, standards‑compliant solution that works on .NET 6+ and earlier frameworks. This tutorial covers everything from project setup to verifying the output, so you can copy the code directly into your own web project.

## Prerequisites

Before you start, make sure you have:

* Visual Studio 2022 (or any IDE that supports .NET)
* .NET 6 SDK (or .NET Framework 4.7.2 and higher)
* Basic knowledge of ASP.NET Core or ASP.NET Framework
* An Aspose.BarCode license (the free evaluation works for testing)

No additional third‑party libraries are required because Aspose.BarCode handles all encoding and rendering internally.

## Step 1: Create a new ASP.NET project

Open Visual Studio and create a **ASP.NET Core Web App** (choose *Empty* template). For a classic Web Forms project, the same code works inside a code‑behind file.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Running the project should display *GS1 barcode generator is ready.* in the browser. This confirms that the web host is operational.

## Step 2: Install Aspose.BarCode via NuGet

Open the **Package Manager Console** and run:

```powershell
Install-Package Aspose.BarCode
```

The package adds the `Aspose.BarCode.Generation` namespace, which contains the `BarcodeGenerator` class you will use to **generate barcode from string**. The NuGet command also updates the project file with the required reference.

## Step 3: Generate a simple barcode from a string

To illustrate the basic usage, create a helper method that returns a PNG byte array. This method can be called from a controller, a Razor page, or any endpoint.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

You can now call `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` from any endpoint and write the resulting bytes to the HTTP response. This demonstrates the **barcode generator asp.net** pattern for arbitrary strings.

## Step 4: How to create GS1 barcode – Micro PDF417 example

GS1 barcodes embed application‑identifiers (AIs) that convey product information. Aspose.BarCode supports the GS1‑compatible variant of Micro PDF417, which is ideal for compact data representation.

### 4.1 Prepare the GS1 data string

GS1 data must be wrapped in parentheses with the AI code. For a product identifier (01) and a batch number (10) the string looks like:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

The parentheses are part of the standard; Aspose.BarCode parses them automatically.

### 4.2 Build the GS1 Micro PDF417 generator

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Expose the generator through an ASP.NET endpoint

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Visiting `https://localhost:5001/gs1barcode` now streams the generated PNG. The image matches the GS1 specification, and the file is also stored on disk for later use.

## Step 5: Rendering additional barcode types

The same **create barcode with aspose** approach works for other symbologies. Below is a quick example that creates a QR code from a URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

You can swap `EncodeTypes.QR` with `EncodeTypes.Code128`, `EncodeTypes.DataMatrix`, or any other supported type. The visual parameters (`XDimension`, `Resolution`, `Color`) are configurable through the `Parameters` object.

## Step 6: Common pitfalls and best‑practice tips

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Incorrect AI formatting** | Missing parentheses or wrong AI length causes encoding errors. | Always build the GS1 string exactly as the standard specifies. Use a helper method to concatenate AIs. |
| **Too many columns** | Micro PDF417 supports only 1‑4 columns; setting 5 throws an exception. | Validate the column value before assigning: `if (columns < 1 || columns > 4) throw …` |
| **Low image resolution** | Small `XDimension` values can make the barcode unreadable on printers. | For print‑ready barcodes, increase `Resolution` (e.g., `generator.Parameters.Image.Resolution = 300`). |
| **File path issues on Linux** | Hard‑coded backslashes break on non‑Windows hosts. | Use `Path.Combine` to build file paths; it handles OS‑specific separators. |
| **License not applied** | The free evaluation adds a watermark after 30 days. | Apply your license early: `new License().SetLicense("Aspose.BarCode.lic");` |

## Step 7: Verify the generated barcode

After you run the endpoint, open the PNG in any image viewer. To confirm that the GS1 data is encoded correctly, you can use a free mobile scanner that supports GS1 Micro PDF417 (many barcode scanner apps list this symbology). Scan the image; the app should return:

```
(01)12345678901234
(10)ABCD
```

If the scanner reports an error, double‑check the AI formatting and column count.

## Conclusion

You now know **how to create GS1 barcode** in an ASP.NET environment using Aspose.BarCode. The tutorial covered:

* Setting up an ASP.NET project and installing the Aspose.BarCode NuGet package.  
* Using **generate barcode from string** for generic barcodes.  
* Implementing **create barcode with aspose** to produce a GS1‑compatible Micro PDF417 image.  
* Saving the image to disk and streaming it via an HTTP endpoint.  

From here you can explore other GS1 symbologies (e.g., GS1 DataMatrix) or integrate the generator into a larger order‑processing workflow. Experiment with different `XDimension` values, colors, and error‑correction levels to match your branding and scanning environment.

Happy coding, and let your applications speak the universal language of barcodes!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create code 128 barcode with GS1 using Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to Create ITF-14 Barcode .NET – Comprehensive Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}