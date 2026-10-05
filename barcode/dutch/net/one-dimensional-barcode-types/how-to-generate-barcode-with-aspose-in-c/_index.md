---
category: general
date: 2026-09-19
description: Hoe barcode te genereren met Aspose in C# – een stapsgewijze handleiding
  om snel en betrouwbaar een barcode te maken met Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: nl
lastmod: 2026-09-19
og_description: Hoe barcode te genereren met Aspose in C#. Volg deze gids om een barcode
  te maken met Aspose, MacroPdf417 te configureren en op te slaan als PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Hoe een barcode te genereren met Aspose – complete C#‑gids
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Hoe een barcode te genereren met Aspose in C#
url: /nl/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode te genereren met Aspose in C#

Het genereren van een barcode in C# is eenvoudig wanneer je de Aspose.BarCode bibliotheek gebruikt. Deze tutorial laat je stap voor stap zien hoe je **een barcode met Aspose** maakt, met aandacht voor het MacroPdf417-formaat, algemene weergave‑instellingen en hoe je het resultaat opslaat als een PNG‑afbeelding.

Je leert hoe je:

* Aspose.BarCode voor .NET installeert en referentieert  
* MacroPdf417‑specifieke eigenschappen configureert, zoals bestand‑ID, segment‑ID en checksum  
* Visuele opties aanpast, zoals X‑dimension en kolomaantal  
* De barcode exporteert naar een afbeeldingsbestand  

Ervaring met Aspose is niet vereist—alleen een basisbegrip van C# en Visual Studio.

## Vereisten

| Vereiste | Detail |
|----------|--------|
| .NET runtime | .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider, of elke editor die C# ondersteunt |
| Aspose.BarCode | NuGet‑pakket `Aspose.BarCode` (gratis proefversie of gelicentieerde versie) |
| Basiskennis van C# | Bekendheid met `using`‑statements en objectinitialisatie |

Je kunt Aspose.BarCode aan je project toevoegen via de NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Hoe een barcode te genereren in C# – algemeen werkproces

Het proces bestaat uit vier logische stappen:

1. **Maak een `BarcodeGenerator`‑instantie** met het gewenste coderings‑type (MacroPdf417) en de tekst die je wilt coderen.  
2. **Stel algemene weergave‑opties in** zoals X‑dimension en kolomaantal.  
3. **Configureer MacroPdf417‑specifieke eigenschappen** zoals bestand‑ID, segment‑ID en tijdstempel.  
4. **Sla de barcode op** in een bestandsformaat naar keuze (PNG in dit voorbeeld).

Elke stap wordt hieronder in detail uitgelegd.

## Stap 1: Maak een barcode‑generator voor MacroPdf417

De `BarcodeGenerator`‑klasse is het toegangspunt voor alle barcode‑creatietaken. Wanneer je een instantie maakt, geef je twee argumenten door:

* `EncodeTypes.MacroPdf417` – geeft Aspose aan de MacroPdf417‑symbologie te gebruiken.  
* De gegevensreeks – de tekst die in de barcode wordt gecodeerd.  

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Waarom dit belangrijk is:** MacroPdf417 is een tweedimensionale barcode die grote hoeveelheden data kan dragen en macro‑functies ondersteunt zoals bestandssegmentatie, wat nuttig is voor het verzenden van grote bestanden in delen.

## Stap 2: Stel algemene barcode‑weergave‑opties in

Hoewel MacroPdf417 veel gespecialiseerde instellingen heeft, wil je nog steeds de visuele dichtheid en lay‑out beheersen. De meest voorkomende parameters zijn:

* **X‑dimension** – de breedte van de kleinste module (pixel). Kleinere waarden geven een dichtere afbeelding.  
* **Columns** – het aantal datakolommen per rij; hogere aantallen verkleinen de hoogte van de barcode.  

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Tip:** Houd `XDimension` tussen 2 en 4 pixels voor de meeste scherm‑weergave‑scenario's. Grotere waarden verbeteren de leesbaarheid op laag‑resolutieprinters maar vergroten de totale afbeeldingsgrootte.

## Stap 3: Configureer MacroPdf417‑specifieke eigenschappen

MacroPdf417 voegt een reeks metadata‑velden toe waarmee je een groot bestand kunt opsplitsen in meerdere barcode‑segmenten. De volgende eigenschappen worden vaak vereist:

| Eigenschap | Doel |
|------------|------|
| `MacroPdf417FileID` | Unieke identifier voor het volledige bestand (max 8 cijfers). |
| `MacroPdf417SegmentID` | De index van het huidige segment (begint bij 0). |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten in het bestand. |
| `MacroPdf417FileName` | Menselijk leesbare naam van het originele bestand. |
| `MacroPdf417Checksum` | Optionele CCITT‑16 checksum voor foutdetectie. |
| `MacroPdf417FileSize` | Grootte van het originele bestand in bytes. |
| `MacroPdf417TimeStamp` | Tijdstempel wanneer het bestand werd gegenereerd. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Optionele strings om afzender/ontvanger te identificeren. |
| `MacroPdf417Terminator` | Bepaalt of de barcode het laatste segment is (`Set`) of een tussenliggend segment (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Waarom deze velden nuttig zijn:**  
> *Wanneer je een groot document via een kanaal met lage bandbreedte moet verzenden, kun je het document opsplitsen in meerdere MacroPdf417‑barcodes. De ontvanger reconstrueert het originele bestand door de metadata van elk segment te lezen.*

## Stap 4: Sla de gegenereerde barcode op als afbeelding

Aspose ondersteunt vele uitvoerformaten: PNG, JPEG, BMP, TIFF, SVG en PDF. PNG is een verliesvrij formaat, ideaal voor weergave op het web of in een UI.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Wanneer je het programma uitvoert, vind je een PNG‑bestand dat lijkt op de onderstaande illustratie.

![MacroPdf417 barcode gegenereerd met Aspose in C#](placeholder-image.png){.img-fluid alt="hoe een barcode te genereren met Aspose in C#"}

> **Verwachte output:** Een PNG van 300 × 150 pixel die een MacroPdf417‑barcode toont die de tekst “Sample” codeert, samen met de macro‑metadata die je hebt opgegeven.

## Volledig, uitvoerbaar voorbeeld

Alles samengevoegd, hier is het volledige programma dat je kunt kopiëren, plakken en uitvoeren:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Voer het programma uit met `dotnet run` (of druk op **F5** in Visual Studio). Controleer na uitvoering of het PNG‑bestand bestaat en zonder fouten opent.

## Veelgestelde vragen en afhandeling van randgevallen

### Wat als ik een ander afbeeldingsformaat nodig heb?

Aspose ondersteunt `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` en `Pdf`. Vervang simpelweg `BarCodeImageFormat.Png` door de gewenste enum‑waarde.

### Hoe genereer ik automatisch meerdere segmenten?

Je kunt de bovenstaande code in een lus plaatsen, waarbij je `MacroPdf417SegmentID` bij elke iteratie verhoogt en de gegevensreeks bijwerkt. Zorg ervoor dat `MacroPdf417SegmentsCount` constant blijft voor alle segmenten.

### Wat als de data de capaciteit van één MacroPdf417‑symbool overschrijdt?

MacroPdf417 is ontworpen voor grote payloads, maar elke barcode heeft een theoretisch maximum (≈ 1,1 KB per segment). Splits het bronbestand in stukken die binnen deze limiet passen en codeer elk stuk als een afzonderlijk segment.

### Moet de checksum handmatig worden berekend?

Aspose kan de CCITT‑16‑checksum automatisch genereren als je `MacroPdf417Checksum` op `0` zet. In het voorbeeld hebben we een vaste waarde opgegeven ter illustratie; in productiecodel zou je de bibliotheek normaal gesproken de checksum laten berekenen.

### Hoe kan ik de voor‑ en achtergrondkleuren van de barcode wijzigen?

Use the `BarColor` and `BackColor` properties:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Conclusie

Je weet nu **hoe je een barcode kunt genereren** in C# met Aspose.BarCode en, specifiek, hoe je **een barcode met Aspose** maakt voor de MacroPdf417‑symbologie. De tutorial behandelde installatie, configuratie van weergave‑ en macro‑specifieke velden


## Wat kun je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes te genereren met Aspose.BarCode voor .NET – Stapsgewijze gids](/barcode/english/net/datamatrix-barcode-configuration/)
- [Hoe een PDF417‑barcode‑afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hoe een Aztec‑barcode met aangepaste beeldverhouding te genereren met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}