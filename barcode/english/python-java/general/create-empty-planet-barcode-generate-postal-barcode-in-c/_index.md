---
category: general
date: 2026-10-08
description: Create empty planet barcode with C# and learn how to generate postal
  barcode using Aspose.BarCode. Step‑by‑step code and tips included.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create empty planet barcode
- how to generate postal barcode
- Aspose.BarCode C#
- postal barcode example
- barcode XDimension setting
language: en
lastmod: 2026-10-08
og_description: Create empty planet barcode with Aspose.BarCode in C# and see how
  to generate postal barcode images for mailing applications.
og_image_alt: Screenshot of generated empty Planet barcode and filled RM4SCC barcode
og_title: Create empty planet barcode – C# postal barcode guide
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Create empty planet barcode with C# and learn how to generate postal
    barcode using Aspose.BarCode. Step‑by‑step code and tips included.
  headline: Create empty planet barcode, generate postal barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- postal
title: Create empty planet barcode, generate postal barcode in C#
url: /python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create empty planet barcode, generate postal barcode in C#

If you need to **create empty planet barcode** for a mailing system, this guide shows you exactly how to do it with Aspose.BarCode for .NET. You will also learn **how to generate postal barcode** images such as Planet and RM4SCC, customize bar width, and control the filled‑bars option.

Generating postal barcodes does not require a separate graphics library. The Aspose.BarCode SDK provides a single API that handles encoding, image rendering, and image format selection. By the end of this tutorial you will have three ready‑to‑use PNG files:

* `PostalPlanetEmptyBars.png` – an empty‑bars Planet barcode  
* `PostalPlanetFilledBars.png` – the default filled‑bars Planet barcode  
* `PostalRM4SCCFilledBars.png` – a filled‑bars RM4SCC barcode  

You can drop these files into any mailing label template, print them on envelopes, or pass them to a third‑party service.

## Prerequisites

* .NET 6.0 or later (the code also works with .NET Framework 4.7+).  
* Visual Studio 2022 or any C# IDE.  
* Aspose.BarCode for .NET – install via NuGet:

```bash
dotnet add package Aspose.BarCode
```

No additional dependencies are required.

## Create empty planet barcode with Aspose.BarCode

The Planet symbology is part of the United States Postal Service (USPS) barcode family. By default the SDK draws **filled** bars. To **create empty planet barcode**, you disable the `FilledBars` flag.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1 – instantiate a Planet barcode generator with the data to encode.
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Step 2 – set the width of a single bar. XDimension defines the pixel size of one bar.
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Step 3 – disable the FilledBars option to get empty (hollow) bars.
planetEmpty.Parameters.Barcode.FilledBars = false;

// Step 4 – save the image. The PNG format is widely supported by printers and browsers.
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Why this works:**  
`EncodeTypes.Planet` tells the generator to use the Planet symbology. `XDimension.Pixels` controls the physical width of each bar, which is crucial for postal scanners that expect a specific module size. Setting `FilledBars` to `false` tells the renderer to draw only the outline of each bar, producing the *empty* appearance required by some mailing standards.

### Expected output

You will find `PostalPlanetEmptyBars.png` in the target folder. The image shows a Planet barcode where each bar is an outline rather than a solid rectangle.

![Empty Planet barcode example](empty-planet.png){: .align-center alt="Create empty planet barcode – example of an empty‑bars Planet barcode"}

## How to generate postal barcode images (filled version)

Most postal workflows use the default filled‑bars version. The same API can generate a filled Planet barcode and an RM4SCC barcode with just a few lines of code.

```csharp
// Filled Planet barcode (default behavior)
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// RM4SCC barcode – another USPS format that always uses filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
```

**Why you might need RM4SCC:**  
RM4SCC is the newer USPS barcode that encodes the same data as Planet but with higher density. Some carriers require RM4SCC for bulk mailing discounts. The code above demonstrates how to **how to generate postal barcode** for both standards without changing the overall workflow.

### Expected output

* `PostalPlanetFilledBars.png` – a classic filled‑bars Planet barcode.  
* `PostalRM4SCCFilledBars.png` – a filled‑bars RM4SCC barcode, visually similar but with tighter spacing.

Both files can be opened in any image viewer to verify the bar patterns.

## Adjusting bar width for different printing resolutions

Postal scanners often specify a minimum module width (e.g., 0.013 inches). If your printer works at 300 dpi, a 4‑pixel module corresponds to 0.013 inches. Adjust the `XDimension.Pixels` value to match your hardware:

| Desired module (inches) | DPI | Pixels needed (`XDimension`) |
|--------------------------|-----|------------------------------|
| 0.013                    | 300 | 4                            |
| 0.013                    | 600 | 8                            |
| 0.015                    | 300 | 5                            |

**Pro tip:** Always test a


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [How to generate postal barcode in C# with Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}