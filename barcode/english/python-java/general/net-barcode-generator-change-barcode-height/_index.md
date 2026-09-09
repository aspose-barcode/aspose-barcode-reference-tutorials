---
category: general
date: 2026-07-18
description: Learn how to generate barcode images with a .net barcode generator and
  easily change barcode height for GS1‑Databar Omni‑Directional symbols.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: en
lastmod: 2026-07-18
og_description: .net barcode generator lets you quickly create barcode images. This
  guide shows how to generate barcode, adjust bar height, and save PNG files.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Change barcode height with .net barcode generator
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .net barcode generator – change barcode height
url: /python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – change barcode height

Ever wondered **how to generate barcode** images without juggling a dozen third‑party tools? In the .NET world there’s a surprisingly clean way to do it, and the key piece is the **.net barcode generator**. With just a few lines of C# you can spin up a GS1‑Databar Omni‑Directional symbol, tweak the bar height, and dump the result to a PNG file.

If you’re building an inventory system, a shipping label printer, or any app that needs a scannable code, this tutorial will get you from zero to a working barcode in minutes. We’ll walk through the complete code, explain why each setting matters, and show you how to **change barcode height** without breaking the spec.

## What you’ll need

- .NET 6.0 or later (the API works the same on .NET Framework 4.7+)
- A reference to the barcode library (for example, Aspose.BarCode for .NET – the same classes are used by many commercial kits)
- A development environment (Visual Studio, Rider, or VS Code with the C# extension)
- A folder where you have write permission – the tutorial will save PNG files there

That’s it. No extra NuGet packages beyond the barcode library itself.

## Using the .net barcode generator to change barcode height

Below is a **complete, runnable console program**. Paste it into a new C# project, adjust the output folder, and hit F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Why each line matters

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional` enum tells the library to use the GS1‑Databar Omni‑Directional format. |
| `XDimension.Pixels = 2;` | The X‑dimension is the width of the thinnest bar. Setting it to *2 pixels* gives a crisp image on most monitors while keeping file size low. |
| `BarHeight.Pixels = 30;` | This is the **change barcode height** step that determines how tall each bar will be. A 30‑pixel height is a good default for small labels. |
| `generator.Save(...);` | Persists the barcode to a PNG file. PNG is loss‑less, which means scanners see the exact pattern you generated. |
| `BarHeight.Pixels = 60;` | Here we **change barcode height** again—this time to 60 pixels. The library automatically re‑renders the symbol with the new dimension when you call `Save` a second time. |
| `Console.WriteLine(...);` | Gives you quick feedback that the process finished without throwing an exception. |

> **Pro tip:** If you need higher‑resolution output for printing, switch `BarCodeImageFormat.Png` to `BarCodeImageFormat.Tiff` and bump the `Resolution` property (e.g., `generator.Parameters.ImageResolution = 300;`). The bar height will still be respected, just rendered at a finer DPI.

## How to generate barcode images with different settings

The snippet above covers the basics, but real‑world scenarios often demand extra tweaks:

### Adjusting the X‑dimension for larger prints
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Increasing the X‑dimension makes the whole barcode larger without altering the encoded data. This is handy when you print on large labels.

### Switching output formats
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG scales infinitely, which is perfect for web‑based scanners that need crisp vectors.

### Adding human‑readable text
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Enabling `CodeTextVisible` appends the raw data under the barcode, useful for verification during testing.

## Common pitfalls when you **change barcode height**

1. **Height too small** – Some scanners require a minimum bar height (often 10 mm in physical units). If you set `BarHeight.Pixels` too low, the generated image might be unreadable on a real scanner. Always test with your target hardware.
2. **Mismatched X‑dimension and height** – A huge bar height paired with a tiny X‑dimension can look stretched and may cause decoding errors. Aim for a balanced ratio (roughly 3:1 to 5:1) unless the spec says otherwise.
3. **Forgetting to reset parameters** – The generator keeps state between saves. If you change `BarHeight` for one image and then reuse the same instance for another barcode, the previous height will stick around. Either reset the property or instantiate a new `BarcodeGenerator` for each distinct barcode.

## Full end‑to‑end example (including NuGet install)

If you’re starting from scratch, follow these steps to get the project running:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Replace the autogenerated `Program.cs` with the code block shown earlier, **remember to replace `YOUR_DIRECTORY`** with something like `Path.Combine(Environment.CurrentDirectory, "output")`. Then:

```bash
dotnet run
```

You should see two PNG files in the `output` folder:

- `DatabarBarHeight30Pixels.png` – a compact 30‑pixel tall barcode.
- `DatabarBarHeight60Pixels.png` – a taller 60‑pixel version.

Both images will look similar, but the second one will have noticeably longer bars, making it easier for low‑resolution scanners to read.

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output showing different bar heights"}

## Recap & next steps

We’ve covered how to **generate barcode** images using a **.net barcode generator**, fine‑tuned the **change barcode height** property, and saved the results in PNG format. The key takeaways are:

- Instantiate the generator with the correct `EncodeTypes`.
- Control visual size via `XDimension` and `BarHeight`.
- Call `Save` after each change to persist a new image.
- Adjust resolution, format,


## What Should You Learn Next?


The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}