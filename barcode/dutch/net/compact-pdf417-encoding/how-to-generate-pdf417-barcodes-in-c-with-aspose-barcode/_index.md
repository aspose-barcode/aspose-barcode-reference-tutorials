---
category: general
date: 2026-09-10
description: Hoe PDF417-barcodes te genereren in C# met Aspose.BarCode. Volg een stapsgewijze
  handleiding om Macro PDF417 te maken, parameters aan te passen en te exporteren
  als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: nl
lastmod: 2026-09-10
og_description: Hoe PDF417-barcodes te genereren in C# met Aspose.BarCode. Leer de
  volledige workflow van installatie tot het opslaan van een Macro PDF417 PNG-afbeelding.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Hoe PDF417-barcodes te genereren in C# – volledige Aspose.BarCode-gids
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Hoe PDF417-barcodes te genereren in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodes te genereren in C# met Aspose.BarCode

Als je **hoe PDF417 te genereren** in een .NET‑project nodig hebt, laat deze tutorial de volledige workflow zien. Je ziet hoe je een Macro PDF417‑barcode maakt, de instellingen fijnstemt en het resultaat exporteert als een PNG‑afbeelding — alles met Aspose.BarCode voor .NET.

Het genereren van PDF417‑barcodes is gebruikelijk in logistiek, ticketing en beveiligde documentprocessen. Aan het einde van deze gids heb je een kant‑en‑klaar C#‑barcode‑generator die je in elke applicatie kunt gebruiken.

## Wat je nodig hebt

- **Visual Studio 2022** (of een andere C#‑IDE)  
- **.NET 6.0** of hoger  
- **Aspose.BarCode for .NET** NuGet‑pakket (`Install-Package Aspose.BarCode`)  
- Basiskennis van C#‑syntaxis  

> **Pro tip:** Gebruik de nieuwste versie van Aspose.BarCode om de nieuwste Macro PDF417‑functies en bug‑fixes te krijgen.

---

## Hoe PDF417-barcodes te genereren in C#  

Hieronder vind je een volledig uitvoerbaar voorbeeld dat een **Macro PDF417**‑barcode maakt, de macro‑specifieke velden configureert en de afbeelding opslaat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Waarom elke stap belangrijk is

1. **Maak een Macro PDF417‑generator** – `EncodeTypes.MacroPdf417` vertelt Aspose.BarCode om de macro‑versie van PDF417 te gebruiken, die het splitsen van een grote payload over meerdere symbolen ondersteunt.  
2. **Pas de basisuiterlijk aan** – `XDimension` bepaalt de breedte van de module (dot); `Columns` geeft aan hoeveel kolommen elk symbool bevat, wat zowel de grootte als de leesbaarheid beïnvloedt.  
3. **Stel macro‑specifieke velden in** – Deze eigenschappen (`MacroPdf417FileID`, `MacroPdf417SegmentID`, enz.) zijn vereist volgens de PDF417‑macro‑specificatie om de oorspronkelijke data aan de scanner‑kant weer samen te stellen.  
4. **Exporteer de afbeelding** – `BarCodeImageFormat.Png` levert een verliesvrije afbeelding die goed werkt voor web, print en mobiele scenario's.

---

## Aspose.BarCode voor .NET instellen (C# barcode‑generator)

Voordat je de bovenstaande code kunt uitvoeren, moet je de Aspose.BarCode‑bibliotheek aan je project toevoegen:

```bash
dotnet add package Aspose.BarCode
```

*Het NuGet‑pakket bevat alle afhankelijkheden, dus er zijn geen extra DLL‑s nodig.*  
Als je .NET Framework target, werkt dezelfde `Install-Package Aspose.BarCode`‑opdracht vanuit de Package Manager Console.

### Veelvoorkomende valkuilen

- **Ontbrekende licentie** – Standaard draait Aspose in evaluatiemodus, waardoor een watermerk aan de barcode wordt toegevoegd. Registreer een licentiebestand (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) om dit te verwijderen.  
- **Onjuiste `EncodeTypes`** – Het gebruik van `EncodeTypes.Pdf417` in plaats van `EncodeTypes.MacroPdf417` negeert alle macro‑velden, waardoor reconstructie van meerdere segmenten mislukt.

---

## Macro PDF417‑barcodeparameters configureren

De macro‑velden laten je een groot document over meerdere PDF417‑symbolen verdelen. Hieronder een snelle referentie:

| Eigenschap | Doel | Typisch bereik |
|------------|------|----------------|
| `MacroPdf417FileID` | Unieke identifier voor het volledige bestand | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Index van het huidige segment (start bij 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten in het bestand | 1‑255 |
| `MacroPdf417FileName` | Optionele mens‑leesbare naam | 0‑255 tekens |
| `MacroPdf417Checksum` | CCITT‑16 checksum voor foutdetectie | 0‑65535 |
| `MacroPdf417FileSize` | Originele bestandsgrootte in bytes | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Aanmaak‑timestamp (optioneel) | `DateTime`‑waarde |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Optionele metadata voor routing | Elke string |
| `MacroPdf417Terminator` | Geeft het laatste segment aan (`Set` of `Unset`) | `Pdf417MacroTerminator`‑enum |

Pas deze waarden aan op basis van de data die je codeert. Bijvoorbeeld, als je een bestand van 2 MB in 20 segmenten splitst, stel je `MacroPdf417FileSize` in op `2_000_000` en `MacroPdf417SegmentsCount` op `20`.

---

## De barcode exporteren als PNG‑afbeelding (barcode afbeelding export)

Het opslaan van de barcode als PNG is het meest gangbare exportformaat omdat het scherpe randen behoudt en transparantie ondersteunt. Aspose.BarCode ondersteunt ook JPEG, BMP, GIF en TIFF — kies wat het beste past bij je downstream‑proces.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Tips voor output van hoge kwaliteit**

- Verhoog `XDimension.Pixels` voor grotere modules bij afdrukken op hoog‑resolutie media.  
- Gebruik `BarCodeImageFormat.Tiff` met CCITT Group 4‑compressie voor fax‑compatibele PDF‑s.  
- Stel `generator.Parameters.ImageOptions.Resolution` in als je een specifieke DPI nodig hebt (bijv. 300 dpi voor print).

---

## Testen en oplossen van problemen met je PDF417‑barcode

1. **Visuele verificatie** – Open `MacroPdf417.png` in een willekeurige afbeeldingsviewer. Je zou een stapel verticale strepen moeten zien met een kleine tekstbijschrift (de gecodeerde data).  
2. **Scanner‑test** – Gebruik een mobiele barcode‑scanner‑app die PDF417 ondersteunt. Scan de afbeelding; de app moet de oorspronkelijke “Sample text” plus macro‑metadata (file ID, segment ID, enz.) teruggeven.  
3. **Foutafhandeling** – Als de scanner “checksum error” meldt, controleer dan `MacroPdf417Checksum` en zorg dat `MacroPdf417Terminator` correct is ingesteld op het laatste segment.  
4. **Prestaties** – Het genereren van veel segmenten in een lus kan CPU‑intensief zijn. Hergebruik één `BarcodeGenerator`‑instantie en werk alleen de macro‑velden bij tussen opslagen om de doorvoersnelheid te verbeteren.

---

## Conclusie

Je weet nu **hoe PDF417‑barcodes te genereren** in C# met Aspose.BarCode, van het installeren van de bibliotheek tot het configureren van Macro PDF417‑velden en het exporteren van een nette PNG‑afbeelding. De volledige oplossing toont:

- Het opzetten van een **C#‑barcode‑generator** met het Macro PDF417‑type  
- Het aanpassen van **PDF417‑barcode‑parameters** voor multi‑segment data  
- Het uitvoeren van **barcode‑afbeeldingsexport** voor downstream‑gebruik  

Vanaf hier kun je geavanceerde onderwerpen verkennen, zoals het embedden van de barcode in PDF‑documenten, het genereren van QR‑code‑companions, of het automatiseren van batch‑verwerking van grote bestanden.

**Volgende stappen**

- Probeer verschillende `BarCodeImageFormat`‑waarden (bijv. `Tiff` voor hoge‑resolutie prints).  
- Combineer Macro PDF417 met andere symbologieën in hetzelfde document via `generator.Parameters.Barcode.Symbology`.  
- Bekijk de [Aspose.BarCode‑documentatie](https://docs.aspose.com/barcode/net/) voor diepere aanpassingsopties zoals fout‑correctieniveau en coderingsmodi.

Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}