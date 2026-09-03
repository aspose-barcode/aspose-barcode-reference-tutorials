---
category: general
date: 2026-07-15
description: Tutorial sul codice a barre databar stacked omnidirezionale in C#. Scopri
  come generare databar, impostare il rapporto d'aspetto e utilizzare un generatore
  di codici a barre C# per risultati perfetti.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar stacked omnidirectional
- barcode generator c#
- how to set aspect ratio
- how to generate databar
- create databar barcode
language: it
lastmod: 2026-07-15
og_description: Barcode Databar stacked omnidirezionale in C# spiegato. Segui questo
  tutorial passo‑passo per generare il Databar, regolare il rapporto d'aspetto e padroneggiare
  il generatore di barcode in C#.
og_image_alt: Two PNG images showing a databar stacked omnidirectional barcode with
  aspect ratios 15 and 30
og_title: DataBar impilato omnidirezionale – Guida C#
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  headline: databar stacked omnidirectional barcode in C# – Complete Guide
  type: TechArticle
- description: databar stacked omnidirectional barcode in C# tutorial. Learn how to
    generate databar, set aspect ratio, and use a barcode generator c# for perfect
    results.
  name: databar stacked omnidirectional barcode in C# – Complete Guide
  steps:
  - name: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
    text: The **X‑Dimension** isn’t too low (below 1 pixel is impossible).
  - name: The **AspectRatio** matches what your scanning hardware expects.
    text: The **AspectRatio** matches what your scanning hardware expects.
  - name: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
    text: The **output path** is writable—sometimes `UnauthorizedAccessException`
      hides behind a silent failure.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Codice a barre databar impilato omnidirezionale in C# – Guida completa
url: /it/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# databar stacked omnidirectional barcode in C# – Guida completa

Ti sei mai chiesto come impostare il rapporto d'aspetto quando **databar stacked omnidirectional barcode** in C#? Non sei l'unico. Molti sviluppatori si trovano in difficoltà nel perfezionare questi codici a barre per etichette retail o logistiche, e la documentazione può risultare un po' scarsa.  

In questo tutorial vedremo **come generare databar**, configurare la X‑Dimension e—soprattutto—**come impostare il rapporto d'aspetto** affinché lo scanner lo legga perfettamente. Alla fine avrai un esempio di codice pronto all'uso che crea due immagini di codice a barre affiancate, una con un rapporto d'aspetto di 15 e l'altra di 30. Nessun mistero, solo passaggi chiari.

## What This Guide Covers

- Configurare un **barcode generator c#** usando la popolare libreria Aspose.BarCode.  
- Comprendere l'anatomia di un simbolo **databar stacked omnidirectional**.  
- Regolare il **rapporto d'aspetto** per rispettare le specifiche GS1.  
- Salvare il risultato come file PNG da inserire in qualsiasi progetto .NET.  

Prerequisiti? Solo un SDK .NET recente (4.6+ o .NET Core 3.1+) e un riferimento NuGet a `Aspose.BarCode`. Se li hai, sei pronto a partire.

---

## Understanding the databar stacked omnidirectional barcode

Il formato **databar stacked omnidirectional** comprime un GTIN a 14 cifre e qualche cifra supplementare in un simbolo compatto a due righe. È la scelta ideale per piccoli articoli dove lo spazio è limitato—pensa a cosmetici, prodotti farmaceutici o confezioni di snack minuscole.

Perché il rapporto d'aspetto è importante? La specifica del codice a barre definisce una relazione larghezza‑altezza che influisce sull'affidabilità della scansione. Troppo schiacciato, lo scanner potrebbe perdere una barra; troppo allungato, il codice potrebbe superare le dimensioni dell'etichetta. La proprietà `AspectRatio` sull'oggetto `DataBar` ti permette di regolare finemente questo equilibrio.

---

## Step 1: Create a **databar stacked omnidirectional** barcode generator

First, spin up the generator with the right encode type and the data you want to embed. Here we use a sample GTIN‑14 value wrapped in parentheses, as the spec expects.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Initialize the generator for a DataBar Stacked Omnidirectional barcode
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

> **Pro tip:** The string must start with “(01)” to tell the library that the following 14 digits are a GTIN. Forgetting the parentheses throws a `ArgumentException`.

---

## Step 2: Define the basic size of the bars (X‑Dimension)

The X‑Dimension controls how many pixels each module (the smallest bar) occupies. A common starting point is 2 pixels per module, which offers a good trade‑off between readability and file size.

```csharp
// Set 2 pixels per module – a safe default for most printers
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

If you’re printing on a high‑resolution laser printer, you might bump this up to 3 or 4 pixels. Just remember: larger X‑Dimension means larger overall barcode dimensions.

---

## Step 3: **How to set aspect ratio** – first version (15)

Now comes the part that trips many people up: the `AspectRatio`. It’s a simple integer, but it directly influences the height of the stacked rows relative to the width.

```csharp
// Aspect ratio of 15 – the default for many retail scenarios
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

// Save the first image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

The resulting PNG will look something like this (placeholder image):

![databar stacked omnidirectional barcode with aspect ratio 15](databar_aspect_ratio_15.png)

*Testo alternativo immagine (per SEO):* **databar stacked omnidirectional barcode with aspect ratio 15**.

---

## Step 4: **How to set aspect ratio** – second version (30)

Sometimes a higher ratio is required, especially when the label height is generous or the scanner expects a taller symbol. Let’s switch to 30 and save a second file.

```csharp
// Change the aspect ratio to 30 for a taller barcode
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;

// Save the second image
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

And the output:

![databar stacked omnidirectional barcode with aspect ratio 30](databar_aspect_ratio_30.png)

*Testo alternativo immagine:* **databar stacked omnidirectional barcode with aspect ratio 30**.

You’ll notice the bars are taller, but the width stays the same because we kept the X‑Dimension constant.

---

## Step 5: Verify the output – quick sanity check

Open the due PNG files in any image viewer. Both should display a clean, two‑row barcode with the same numeric data. If you have a handheld scanner handy, try scanning each file. The scanner should return the raw GTIN string `(01)12345678901231`.  

If a scan fails, double‑check:

1. The **X‑Dimension** isn’t too low (below 1 pixel is impossible).  
2. The **AspectRatio** matches what your scanning hardware expects.  
3. The **output path** is writable—sometimes `UnauthorizedAccessException` hides behind a silent failure.

---

## Common pitfalls when you **create databar barcode**

| Sintomo | Probabile causa | Correzione |
|---------|-----------------|------------|
| Blank image saved | `EncodeTypes` mismatch (e.g., using `DatabarExpanded` instead of `DatabarStackedOmniDirectional`) | Verify `EncodeTypes.DatabarStackedOmniDirectional` |
| Barcode too wide | X‑Dimension set too high | Reduce `XDimension.Pixels` |
| Scanner reports “invalid format” | Aspect ratio not supported by the scanner model | Adjust `AspectRatio` to 15 or 30 as per device specs |
| Exception on `Save` | Output folder missing or no write permission | Create folder or run with elevated rights |

---

## Advanced: Dynamically choosing the aspect ratio

In real‑world apps you might need to pick an aspect ratio based on label size. Here’s a tiny helper method that picks 15 for narrow labels and 30 for tall ones.

```csharp
private static int ChooseAspectRatio(int labelWidthPx, int labelHeightPx)
{
    // Simple heuristic: if height > 2× width, use a taller ratio
    return (labelHeightPx > 2 * labelWidthPx) ? 30 : 15;
}

// Usage
int chosenRatio = ChooseAspectRatio(200, 500);
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = chosenRatio;
barcodeGenerator.Save(@"YOUR_DIRECTORY\DatabarDynamic.png", BarCodeImageFormat.Png);
```

Now your **barcode generator c#** code adapts on the fly—no need to hard‑code two separate saves.

---

## Recap – what we achieved

- **Created** a **databar stacked omnidirectional** barcode generator in C#.  
- **Set** the X‑Dimension to 2 pixels per module for crisp rendering.  
- **Demonstrated** **how to set aspect ratio** both to 15 and 30, saving each as PNG.  
- **Explored** common errors and offered a tiny dynamic‑ratio helper.

All of this fits inside a single, self‑contained file that you can drop into any .NET project. No external scripts, no mysterious configuration files.

---

## What’s next? Expand your barcode toolbox

Now that you’ve mastered the **create databar barcode** basics, consider exploring:

- **Adding human‑readable text** below the symbol (`barcodeGenerator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true`).  
- **Embedding the barcode** directly into a PDF using `Aspose.Pdf` for invoice generation.  
- **Batch processing** a list of GTINs with a `foreach` loop and naming each file after its product code.  

Each of these topics builds on the same core concepts you just learned, and they’ll make your **barcode generator c#** projects even more powerful.

---

### Final Thoughts

Generating a **databar stacked omnidirectional** barcode in C# isn’t magic; it’s just a handful of property tweaks on a solid library. By controlling the X‑Dimension and la **aspect ratio**, you get full command over the barcode’s shape and scan reliability.  

Give the code a spin, tweak the numbers, and watch the scanner dance. If you hit a snag, revisit the “Common pitfalls” table—most issues are resolved with a quick property adjustment.  

Happy coding, and may your labels always scan on the first try!

## What Should You Learn Next?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)
- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}