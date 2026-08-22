---
category: general
date: 2026-08-22
description: De barcodegenerator C#‑tutorial laat zien hoe je een Macro PDF417‑barcode
  met metadata maakt en opslaat als PNG met behulp van Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: nl
lastmod: 2026-08-22
og_description: barcode generator C# laat je een Macro PDF417‑barcode maken met volledige
  metadata op bestandsniveau en exporteer deze als PNG. Volg deze gids om de oplossing
  te implementeren.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: barcode generator C# – maak Macro PDF417‑barcodes stap voor stap
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Hoe een barcodegenerator in C# te gebruiken voor Macro PDF417
url: /nl/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode generator C# te gebruiken voor Macro PDF417

Als je een **barcode generator C#** nodig hebt die een Macro PDF417‑symbool kan genereren met metadata op bestandsniveau, biedt deze gids een complete, kant‑klaar oplossing. Je ziet hoe je het uiterlijk van de barcode configureert, macro‑informatie zoals bestand‑ID en segment‑aantal toevoegt, en uiteindelijk het resultaat opslaat als een PNG‑afbeelding.

Het voorbeeld maakt gebruik van de Aspose.BarCode‑bibliotheek, een breed geaccepteerde **C# barcode library** die de volledige PDF417‑functionaliteit ondersteunt. Er zijn geen externe services nodig en de code werkt met .NET 6 of hoger.

## Voorwaarden

Zorg ervoor dat je het volgende hebt voordat je begint:

* .NET 6 SDK (of een latere versie) geïnstalleerd.
* Visual Studio 2022, VS Code, of een andere C#‑IDE.
* Een NuGet‑referentie naar **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Basiskennis van C#‑syntaxis en het concept van PDF417‑barcodes helpt je de stappen te volgen, maar de tutorial legt elke configuratie‑optie in detail uit.

## Waar de tutorial over gaat

* Een **barcode generator C#**‑instantie initialiseren voor het Macro PDF417‑formaat.  
* Visuele parameters aanpassen zoals X‑dimensie en kolomaantal.  
* Macro PDF417‑velden op bestandsniveau leveren: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender en terminator.  
* Het gegenereerde symbool opslaan als PNG‑bestand.  
* Tips voor het omgaan met randgevallen zoals grote bestandsgroottes of aangepaste timestamps.

Aan het einde van dit artikel heb je een zelfstandige applicatie die een volledig conforme Macro PDF417‑barcode produceert.

## Stap 1: Maak de barcode generator C#‑instantie

De eerste handeling is het aanmaken van `BarcodeGenerator` met de enum‑waarde `EncodeTypes.MacroPdf417` en de tekst die je wilt coderen. De constructor accepteert ook de payload‑string, die het gegevensgedeelte van de macro‑barcode wordt.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Waarom dit belangrijk is** – De `EncodeTypes.MacroPdf417`‑vlag vertelt Aspose.BarCode het symbool als een macro‑barcode te behandelen, waardoor de extra velden die volgen worden ingeschakeld. Zonder deze vlag zou de bibliotheek een gewone PDF417‑barcode genereren zonder metadata op bestandsniveau.

## Stap 2: Basis‑uiterlijk van de barcode aanpassen (PDF417‑visuele instellingen)

Visuele duidelijkheid is cruciaal voor betrouwbare scanning. Twee veelvoorkomende parameters zijn de module‑breedte (`XDimension`) en het aantal kolommen. Het instellen van deze waarden balanceert grootte en leesbaarheid.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` bepaalt de breedte van elke zwarte/witte balk. Een waarde van **2** werkt goed voor de meeste labelprinters.
* `Pdf417.Columns` geeft aan hoeveel kolommen de barcode zal gebruiken. Vijf kolommen leveren een compact symbool zonder verlies van datacapaciteit.

## Stap 3: Definieer Macro PDF417‑informatie op bestandsniveau

Macro PDF417 breidt het standaard PDF417‑formaat uit met velden die beschrijven hoe een groot bestand over meerdere barcode‑segmenten wordt verdeeld. Het leveren van deze velden zorgt ervoor dat downstream‑scanners het oorspronkelijke bestand kunnen reconstrueren.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` moet voor elk segment dat tot hetzelfde logische bestand behoort gelijk zijn.
* `MacroPdf417SegmentID` loopt van **0** tot `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` geeft de decoder aan hoeveel stukken er verwacht worden.
* `MacroPdf417FileName` is optioneel maar handig voor menselijk leesbare identificatie.

## Stap 4: Extra macro‑metadata instellen

Naast de kern‑bestand‑informatie staat de specificatie extra velden toe, zoals checksum, bestandsgrootte, timestamp, addressee, sender en een terminator‑vlag. Het invullen van deze velden verbetert de gegevensintegriteit en traceerbaarheid.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` levert een 16‑bit CCITT‑checksum voor het volledige bestand; de decoder kan de integriteit na reconstructie verifiëren.
* `MacroPdf417FileSize` moet de exacte byte‑telling van het oorspronkelijke bestand weerspiegelen; waarden groter dan `2^31‑1` vereisen een 64‑bit‑veld, wat Aspose automatisch afhandelt.
* `MacroPdf417TimeStamp` registreert wanneer de barcode is gegenereerd. Gebruik UTC om tijdzone‑ambiguïteit te vermijden.
* `MacroPdf417Addressee` en `MacroPdf417Sender` zijn vrije tekstvelden die routing‑informatie kunnen bevatten.
* `MacroPdf417Terminator` geeft aan dat dit het laatste segment is; zet het op `Set` voor het laatste stuk, anders laat je de standaard (`NotSet`) staan.

**Tip voor randgevallen** – Als je bestandsgrootte groter is dan 4 GB, splits dan de inhoud over meerdere macro‑segmenten en pas `SegmentsCount` dienovereenkomstig aan. De bibliotheek beheert het groot‑formaat‑veld zonder overflow.

## Stap 5: Sla de barcode op als PNG‑afbeelding

De laatste stap schrijft het gegenereerde symbool naar schijf. PNG behoudt de exacte pixelafmetingen en wordt breed ondersteund door scanning‑hardware.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Vervang `YOUR_DIRECTORY` door een absoluut of relatief pad waar het uitvoerende proces naar kan schrijven. De `BarCodeImageFormat.Png`‑enum zorgt voor verliesvrije output.

**Waarom PNG?** – Rasterformaten zoals PNG houden de module‑randen scherp, wat essentieel is voor scanners die vertrouwen op hoog‑contrast randen. Als je een vectorformaat nodig hebt, ondersteunt Aspose ook `Pdf` en `Svg`.

## Volledig uitvoerbaar voorbeeld

Hieronder vind je het complete programma dat je kunt kopiëren naar een console‑applicatie. Het bevat de benodigde `using`‑directives en een `Main`‑methode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma maakt een bestand genaamd **MacroPdf417.png** aan in de werkmap van het project. Het openen van de afbeelding toont een compact PDF417‑symbool met de ingebedde macro‑velden. Het scannen van de afbeelding met een PDF417‑compatibele lezer (bijv. ZXing, Aspose.BarCode‑decoder) levert de oorspronkelijke `"Sample text"`‑payload terug, samen met de macro‑metadata.

## Veelgestelde vragen en probleemoplossing

| Vraag | Antwoord |
|----------|--------|
| *Wat als de barcode te groot is voor het doel‑label?* | Verlaag `XDimension.Pixels` of vergroot `Pdf417.Columns`. Beide parameters beïnvloeden de totale grootte. |
| *Kan ik een vectorafbeelding genereren in plaats van PNG?* | Ja. Roep `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` aan voor schaalbare output. |
| *Hoe verifieer ik de checksum na het scannen?* | De Aspose.BarCode‑decoder valideert automatisch `MacroPdf417Checksum` en meldt afwijkingen in het `MacroPdf417Result`‑object. |
| *Is de bibliotheek compatibel met .NET Core?* | Het NuGet‑pakket ondersteunt .NET Standard 2.0+, wat .NET Core, .NET 5, .NET 6 en later dekt. |
| *Wat als ik binaire data wil embedden in plaats van tekst?* | Converteer de binaire payload naar Base64 of gebruik de `EncodeTypes.MacroPdf417`‑overload die een byte‑array accepteert. |

## Pro‑tips voor productiegebruik

* **Cache de generator** –


## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}