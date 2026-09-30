---
category: general
date: 2026-07-27
description: Crea rapidamente un'immagine di codice a barre planetario. Scopri come
  generare il codice a barre planetario con C# e personalizzare le barre piene o vuote.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: it
lastmod: 2026-07-27
og_description: Crea un'immagine di codice a barre planetario in pochi secondi. Segui
  questa guida per imparare a generare il codice a barre planetario, regolare la dimensione
  X e passare da barre piene a barre vuote.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Crea immagine del codice a barre del pianeta – Tutorial completo C#
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Crea immagine del codice a barre del pianeta – Guida passo passo
url: /it/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# create planet barcode image – Tutorial completo C#

Ti sei mai chiesto **come generare planet barcode** per un sistema di mailing o un'app di logistica? Non sei il primo a grattarsi la testa su questo argomento. In questo tutorial vedremo passo passo tutto ciò che serve per **creare planet barcode image**, dalle basi della classe `BarcodeGenerator` alla regolazione della X‑dimension e alla sostituzione delle barre piene con quelle vuote.

Daremo anche un’occhiata a una simbologia correlata—RM4SCC—così potrai vedere come lo stesso schema funziona per altri codici a barre postali. Alla fine avrai tre snippet pronti all’uso che generano file PNG da inserire direttamente nel tuo progetto.

## What You’ll Need

- .NET 6.0 o versioni successive (il codice funziona anche su .NET Framework 4.7+)  
- Un riferimento a **Aspose.BarCode** (o a qualsiasi libreria che esponga `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)  
- Un IDE con cui ti trovi a tuo agio—Visual Studio, Rider o VS Code vanno benissimo  
- Una cartella in cui poter scrivere le immagini (sostituisci `YOUR_DIRECTORY` nei campioni)

Questo è tutto. Nessun pacchetto NuGet aggiuntivo oltre alla libreria di barcode stessa.

---

## Step 1: Set Up the Project and Imports

First things first, let’s create a tiny console app so we can run the code instantly.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Pro tip:** Keep your `Main` method tidy; delegate each scenario to its own method. It makes the code easier to read and mirrors the three examples in the original snippet.

---

## Step 2: **create planet barcode image** with Default Filled Bars

The Planet symbology is used by many postal services for tracking numbers. To **create planet barcode image** with the usual solid bars, follow these three lines:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Why the X‑dimension matters
The X‑dimension controls how wide each tiny bar (or “module”) is. A value of **4 pixels** yields a barcode that’s clear on screen and prints nicely on standard label printers. If you need a denser image for a high‑resolution print, bump the value up to 6 or 8.

### Expected output
Open the resulting `PostalPlanetFilledBars.png` and you should see a classic Planet barcode—solid vertical bars with a quiet zone on each side. It looks just like the example you’d find on a postal envelope.

---

## Step 3: **create planet barcode image** with Empty Bars

Sometimes the postal specification calls for an *empty‑bar* style, where the bars are outlines rather than solid fills. Switching to that mode is a single property change.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### What “FilledBars = false” does
Setting `FilledBars` to `false` tells the rendering engine to draw only the bar outlines. This is useful when you need a lighter‑weight image for on‑screen display or when a printing guideline explicitly requires the empty style.

### Expected output
The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but each bar is a thin line instead of a solid block. It’s perfect for low‑contrast printing on colored paper.

---

## Step 4: Generate an RM4SCC Barcode (Bonus)

Even though our primary focus is the Planet symbology, the same API lets you **create planet barcode image**‑like results for other postal codes. Here’s how to **how to generate planet barcode**‑style output for RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### When to use RM4SCC
RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country logistics platform, having both Planet and RM4SCC generators at hand saves you a lot of boilerplate code.

---

## Common Questions & Edge Cases

### What if I need a different image format?
Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library handles the conversion automatically.

### How do I change the barcode height?
Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points` (or pixels, depending on the library version). Higher values give you a taller barcode, which can improve scan reliability on low‑resolution scanners.

### Can I embed the barcode directly into a PDF?
Absolutely. The `Save` method returns a `byte[]` if you call the overload that writes to a stream. Feed that stream into a PDF generation library (e.g., iTextSharp) and you’ve got a fully‑automated mailing label.

### What if the data string contains non‑numeric characters?
Planet and RM4SCC expect **numeric only** payloads. Passing letters will throw an `ArgumentException`. Validate your input first:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### Does the X‑dimension affect scanning speed?
A larger X‑dimension creates a more robust barcode, which generally improves scanning speed, especially on low‑quality scanners. However, it also increases the physical size of the label, so balance readability with space constraints.

---

## Full Working Example (All Three Methods)

Below is the complete program you can copy‑paste into a new console project. Replace `YOUR_DIRECTORY` with an absolute or relative path that your app can write to.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Run the program, open the three PNG files, and you’ll see the exact images described earlier. No additional configuration is required.

---

## Recap & Next Steps

We’ve covered **how to generate planet barcode** images from scratch, toggling between solid and outline styles, and extending the same approach to RM4SCC. The key takeaways:

1. Instantiate `BarcodeGenerator` with the correct `EncodeTypes` and data.  
2. Adjust `XDimension.Pixels` to control bar width.  
3. Use `FilledBars = false` for the empty‑bar variant.  
4. Save the result in your preferred image format.

Now that you can **create planet barcode image** files, consider these follow‑up ideas:

- **Batch generation**: Loop over a CSV of tracking numbers and dump a PNG for each.  
- **Dynamic sizing**: Expose X‑dimension and bar height as configuration parameters in a web API.  
- **Integration with label printers**: Send the PNG bytes directly to a ZPL‑compatible printer for on‑the‑fly label creation.

Feel free to experiment—swap the data string, try different dimensions, or combine the barcode with a QR code on the same label. The barcode library is flexible enough to handle all of that.

Got a tricky scenario you’re not sure about? Drop a comment below, and we’ll troubleshoot together. Happy coding!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create barcode image c# – Configure Codablock F Rows & Columns](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}