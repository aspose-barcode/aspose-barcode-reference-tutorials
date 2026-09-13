---
category: general
date: 2026-09-13
description: Leer hoe je een barcode genereert in C#, de barcodegrootte aanpast en
  de barcode‑afbeelding opslaat als PNG met Aspose.BarCode. Volledige stap‑voor‑stap
  handleiding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: nl
lastmod: 2026-09-13
og_description: Hoe een barcode te genereren in C# met aangepaste barcodegrootte en
  de barcode‑afbeelding op te slaan als PNG. Volg deze volledige gids voor Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Hoe een barcode te genereren, een aangepaste grootte in te stellen en een
  afbeelding op te slaan in C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Hoe een barcode met aangepaste grootte te genereren en de afbeelding op te
  slaan in C#
url: /nl/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode met aangepaste grootte te genereren en afbeelding op te slaan in C#

Als je **hoe je een barcode moet genereren** in een .NET‑applicatie, laat deze tutorial je een volledige oplossing zien. Je zult zien hoe je de **aangepaste barcode‑grootte** kunt aanpassen en **barcode‑afbeeldingen** kunt opslaan met slechts een paar regels C#‑code.

Barcodes genereren is een veelvoorkomende eis voor voorraadbeheersystemen, verzendlabels en point‑of‑sale‑toepassingen. Aan het einde van deze gids heb je een uitvoerbaar programma dat twee DataBar‑Stacked‑Omnidirectional‑barcodes maakt, elk met een andere beeldverhouding, en deze naar PNG‑bestanden op schijf schrijft.

**Prerequisites**

- .NET 6.0 of hoger (de code werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 of een andere C#‑IDE
- Aspose.BarCode for .NET (gratis proefversie of gelicentieerd NuGet‑pakket)

---

## Hoe een barcode te genereren met Aspose.BarCode

De Aspose.BarCode‑bibliotheek abstraheert de low‑level details van barcode‑standaarden, zodat je je kunt concentreren op de data die je wilt coderen en het visuele uiterlijk dat je nodig hebt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Waarom elke regel belangrijk is

| Stap | Uitleg |
|------|--------|
| **1️⃣ Maak een generator** | De `EncodeTypes.DatabarStackedOmniDirectional`‑enum vertelt Aspose welke barcode‑symbologie gebruikt moet worden. De string `"(01)12345678901231"` volgt het GS1‑128‑dataformaat, waarbij `(01)` de Application Identifier voor een GTIN is. |
| **2️⃣ Stel X‑dimension in** | `XDimension.Pixels` definieert de breedte van één barcode‑module (de kleinste balk). Het wijzigen van deze waarde is de primaire manier om een **aangepaste barcode‑grootte** te bereiken zonder de gecodeerde data te veranderen. |
| **3️⃣ Stel beeldverhouding in & sla op** | `DataBar.AspectRatio` bepaalt de hoogte‑tot‑breedte‑verhouding van DataBar‑symbolen. Een beeldverhouding van 15 levert een relatief korte, brede barcode op, terwijl 30 deze hoger maakt. `Save` schrijft de visuele weergave naar een PNG‑bestand, waarmee aan de **save barcode image**‑vereiste wordt voldaan. |
| **4️⃣ Verander beeldverhouding & sla opnieuw op** | Het hergebruiken van dezelfde generator‑instantie stelt je in staat meerdere afbeeldingen met verschillende visuele kenmerken te produceren terwijl de data constant blijft. |

---

## Aangepaste barcode‑grootte aanpassen buiten X‑dimension

Hoewel `XDimension.Pixels` de module‑breedte instelt, kun je de algehele afmetingen van de barcode ook fijn afstemmen door twee eigenschappen te combineren:

1. **`BarHeight`** – expliciete hoogte in pixels.  
2. **`BarWidth`** – expliciete breedte in pixels (overschrijft X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** Bij het afdrukken van barcodes test je altijd de gegenereerde afbeelding op de uiteindelijke afdrukgrootte. Een module‑breedte van 2 px werkt voor weergave op scherm, maar afgedrukte labels hebben vaak minstens 4 px nodig om scanbaar te blijven.

---

## Het juiste afbeeldingsformaat kiezen voor het opslaan van een barcode‑afbeelding

Aspose.BarCode ondersteunt PNG, JPEG, BMP, GIF en TIFF. PNG is lossless en behoudt scherpe randen, waardoor het de veiligste keuze is voor de meeste toepassingen. Als je een kleiner bestand voor webgebruik nodig hebt, werkt JPEG met een kwaliteitsinstelling van 90 goed, maar wees je ervan bewust dat compressie‑artefacten de scanbetrouwbaarheid kunnen beïnvloeden.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Volledig, uitvoerbaar voorbeeld

Hieronder vind je een zelfstandige console‑applicatie die je kunt kopiëren, plakken en uitvoeren. Het demonstreert **hoe je een barcode moet genereren**, **aangepaste barcode‑grootte** aanpast, en **barcode‑afbeeldingen** opslaat in twee verschillende formaten.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Verwachte uitvoer op de console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

De vier afbeeldingsbestanden verschijnen in het programma

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode for .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hoe PDF417‑barcode te genereren met Aspose – Complete gids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}