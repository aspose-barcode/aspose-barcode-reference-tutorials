---
category: general
date: 2026-09-29
description: How to set width of a GS1 DataBar Omni‑Directional barcode and how to
  change height using C#. Follow a step‑by‑step guide with full code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: en
lastmod: 2026-09-29
og_description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
  to change height in C#. Learn the exact API calls and see a complete runnable example.
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: How to set width of a GS1 DataBar barcode – C# guide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
  in C#
url: /python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode in C#

How to set width of a GS1 DataBar Omni‑Directional barcode is a frequent task when you need exact sizing for scanning equipment. In this tutorial you’ll also learn **how to change height** so the barcode fits your layout perfectly. The guide walks you through the complete process, from project setup to a fully runnable code sample.

We’ll cover:

* The required NuGet package and .NET version.
* Why X‑dimension (module width) matters for barcode readability.
* The exact API calls to **how to set width** and **how to change height**.
* Edge‑case handling such as minimum module width and high‑resolution rendering.
* A complete, copy‑and‑paste example that produces two PNG files with different bar heights.

## Prerequisites

Before you start, make sure you have:

| Requirement | Reason |
|------------|--------|
| .NET 6.0 SDK or later | The example uses modern C# features and runs on Windows, Linux, or macOS. |
| Visual Studio 2022 (or any C# IDE) | Provides IntelliSense for the Aspose.Barcode API. |
| **Aspose.Barcode for .NET** NuGet package | Contains `BarcodeGenerator`, `EncodeTypes`, and image format support. Install with `dotnet add package Aspose.Barcode`. |
| Write permission to a folder where PNG files will be saved | The generator writes the output images to disk. |

## How to set width of the barcode

The **how to set width** step is performed by configuring the `XDimension` property of the barcode parameters. `XDimension` represents the module width (the smallest bar or space) in pixels, points, or millimetres. Setting it correctly ensures the barcode meets scanner specifications.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### Why the X‑dimension matters

* **Scanner tolerance** – Most scanners expect a minimum module width; too small a value can cause read errors.
* **Print resolution** – When printing at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended range for GS1 DataBar.
* **Image size** – Larger X‑dimension values increase the overall barcode width, which may affect layout constraints.

### Tips for reliable width settings

* **Never set XDimension below 1 px** – the library will clamp the value, but the resulting barcode may be unreadable.
* **Match the target DPI** – if you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension proportionally.
* **Test with a real scanner** – after changing the width, validate the barcode on the device that will read it.

## How to change height of the barcode

Once the width is defined, you can control the vertical size with the `BarHeight` property. The following code demonstrates **how to change height** from 30 px to 60 px and save two separate images.

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### Understanding bar height

* **Visual balance** – Taller bars improve readability on low‑contrast backgrounds but increase the image’s vertical footprint.
* **Regulatory limits** – Some standards (e.g., retail labeling) specify a maximum bar height; adjust accordingly.
* **Aspect ratio** – Changing height does not affect the module width; you can fine‑tune both independently.

### Edge‑case handling for height adjustments

| Situation | Recommended approach |
|-----------|----------------------|
| Height < 10 px | Increase to at least 10 px; very short bars may be ignored by scanners. |
| Very tall bars (≥ 100 px) | Verify that the output medium (paper, label) can accommodate the extra space. |
| Need proportional scaling | Compute `BarHeight = XDimension * desiredRatio` to keep visual consistency. |

## Full, runnable example

Below is the complete program that combines the **how to set width** and **how to change height** steps. Copy the code into a new console project, restore the Aspose.Barcode NuGet package, and run it. Two PNG files will appear in the `bin/Debug/net6.0` folder.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**Expected output**

Running the program produces two PNG files:

* `DatabarBarHeight30Pixels.png` – a barcode 30 px tall, 2 px wide modules.
* `DatabarBarHeight60Pixels.png` – the same barcode with double the vertical size.

Open either image in any viewer; you’ll see a clean GS1 DataBar Omni‑Directional symbol ready for scanning.

## Common questions answered

| Question | Answer |
|----------|--------|
| *Can I use millimetres instead of pixels?* | Yes. Set `generator.Parameters.Barcode.XDimension.Millimeters` and `BarHeight.Millimeters`. The library converts to device pixels based on the image’s DPI. |
| *What if I need a different barcode type?* | Replace `EncodeTypes.DatabarOmniDirectional` with any other `EncodeTypes` value (e.g., `EncodeTypes.QR`). Width and height properties work the same way. |
| *Is there a way to generate SVG instead of PNG?* | Use `BarCodeImageFormat.Svg` in the `Save` call. The width/height settings remain applicable. |
| *Do I need to call `generator.Dispose()`?* | The `BarcodeGenerator` implements `IDisposable`. In a console app you can wrap it in a `using` block, but for short‑lived examples it’s optional. |

## Conclusion

You now know **how to set width** of a GS1 DataBar Omni‑Directional barcode and **how to change height** using the Aspose.Barcode API in C#. The full example demonstrates creating a generator, configuring `XDimension` and `BarHeight`, and saving PNG files with different vertical sizes.  

From here you can:

* Experiment with other `EncodeTypes` (e.g., QR, Code128).
* Render to high‑resolution formats like TIFF for printing.
* Integrate the generator into a web API that returns barcodes on‑the‑fly.

Happy coding, and may your barcodes always scan cleanly!


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}