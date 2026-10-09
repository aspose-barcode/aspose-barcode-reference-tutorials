---
category: general
date: 2026-10-09
description: Leer hoe u een PDF417-barcode kunt maken in C# met Aspose.BarCode – genereer
  een Macro PDF417 met volledige metadata-ondersteuning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Leer hoe u een PDF417-barcode kunt maken in C# met Aspose.BarCode
  – genereer een Macro PDF417 met volledige metadata-ondersteuning, inclusief bestands-ID,
  segmentgegevens, tijdstempel en meer.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Hoe PDF417-barcode te maken in C# met Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Hoe PDF417-barcode te maken in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te maken in C# met Aspose.BarCode

Als je snel en betrouwbaar **PDF417 barcode C#** wilt maken, leidt deze tutorial je door het volledige proces met behulp van Aspose.BarCode. Je ziet elke vereiste instelling, van basisafmetingen tot de volledige set Macro PDF417‑metadatavelden, en je eindigt met een PNG‑afbeelding klaar voor downstream verwerking.

## Snelle antwoorden
- **Welke bibliotheek genereert PDF417-barcodes?** Aspose.BarCode for .NET.
- **Welk formaat geeft het voorbeeld terug?** Een verliesvrije PNG-afbeelding.
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor het voorbeeld; een commerciële licentie is vereist voor productie.
- **Welke .NET‑versie wordt ondersteund?** .NET 6.0 of later.
- **Kan ik metadata aan de barcode toevoegen?** Ja – Macro PDF417 ondersteunt bestand‑ID, segmenttelling, tijdstempels en meer.

## Wat is een PDF417-barcode?
Een PDF417‑barcode is een gestapelde lineaire symbologie die tot ongeveer 1 KB aan gegevens per symbool kan coderen en optionele macro‑metadata ondersteunt voor multi‑segmentbestanden. Het bestaat uit meerdere rijen gestapelde lineaire patronen, waardoor een hoge gegevenscapaciteit mogelijk is terwijl het leesbaar blijft voor standaard 2‑D‑scanners. Het formaat bevat ook foutcorrigatieniveaus om de betrouwbaarheid te verbeteren, en de optionele macro‑functie maakt het splitsen van grote bestanden over meerdere barcodes mogelijk met metadata die helpt bij het weer samenvoegen.

## Waarom Aspose.BarCode gebruiken voor PDF417?
Aspose.BarCode ondersteunt **meer dan 50 barcode‑symbologieën** en kan Macro PDF417‑barcodes genereren met tot **2 000 kolommen**, waardoor bestanden groter dan **10 MB** verwerkt kunnen worden zonder de volledige payload in het geheugen te laden. Deze gekwantificeerde mogelijkheid zorgt ervoor dat high‑throughput‑enterprise‑scenario's soepel verlopen, en biedt uitgebreide aanpassingsopties.

## Vereisten

- .NET 6.0 (of later) geïnstalleerd  
- Visual Studio 2022 of een andere C#‑compatibele IDE  
- Een geldige licentie voor **Aspose.BarCode for .NET** (de gratis proefversie werkt voor dit voorbeeld)  

Voeg het Aspose.BarCode NuGet‑pakket toe aan je project:

```bash
dotnet add package Aspose.BarCode
```

## Hoe een PDF417-barcode te maken in C#?

`BarcodeGenerator` is de hoofdklasse voor het maken van barcode‑afbeeldingen.  
`EncodeTypes.MacroPdf417` selecteert de Macro PDF417‑symbologie voor barcode‑generatie.  
`Save` schrijft de gegenereerde barcode naar een afbeeldingsbestand.

Laad de `BarcodeGenerator` met de `EncodeTypes.MacroPdf417`‑enum en je doeltekst, roep vervolgens `Save` aan – dat is de volledige creatiestroom in drie regels. De generator verwerkt Unicode automatisch, en de `using`‑statement zorgt ervoor dat onbeheerde bronnen worden vrijgegeven nadat de afbeelding is opgeslagen.

### Stap 1: maak de barcode‑generator C#‑instantie

De `BarcodeGenerator`‑klasse maakt en configureert barcode‑afbeeldingen.  

Instantieer `BarcodeGenerator` met de `EncodeTypes.MacroPdf417`‑enumwaarde en de tekst die je wilt coderen. De tekst kan Unicode‑tekens bevatten, die de bibliotheek automatisch verwerkt.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Why this matters*: `EncodeTypes.MacroPdf417` vertelt de engine een Macro PDF417‑symbool te produceren, wat gesegmenteerde data en extra bestands‑level metadata ondersteunt. De `using`‑statement garandeert dat onbeheerde bronnen worden vrijgegeven nadat de afbeelding is opgeslagen.

### Stap 2: basisuiterlijk van de barcode definiëren

`XDimension.Pixels` stelt de grootte van elke barcode‑module in pixels in.

Een Macro PDF417‑barcode bestaat uit vierkante modules. Het regelen van de module‑grootte en het aantal kolommen beïnvloedt zowel de leesbaarheid als de bestandsgrootte.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Why this matters*: `XDimension.Pixels` bepaalt de visuele dichtheid; een waarde van 2 pixels werkt goed voor schermweergave terwijl de afbeelding klein blijft. Pas het aantal kolommen aan om aan je lay‑outbeperkingen te voldoen — meer kolommen maken een bredere, kortere barcode.

### Stap 3: Macro PDF417‑specifieke metadata instellen

`MacroPdf417FileID` identificeert het bestand waartoe alle barcode‑segmenten behoren.

Macro PDF417 breidt het standaard PDF417‑formaat uit met velden die reconstructie van grote bestanden uit meerdere barcode‑segmenten mogelijk maken. Elk veld is optioneel, maar het instellen ervan toont de volledige mogelijkheden van de API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Why this matters*:  
- `MacroPdf417FileID` koppelt alle segmenten die tot hetzelfde logische bestand behoren.  
- `MacroPdf417SegmentID` en `MacroPdf417SegmentsCount` stellen de decoder in staat fragmenten correct te herschikken.  
- `MacroPdf417Checksum` biedt een snelle integriteitscontrole zonder de volledige payload te decoderen.  
- `MacroPdf417FileSize` en `MacroPdf417TimeStamp` laten downstream‑systemen verifiëren dat het gereconstrueerde bestand overeenkomt met het origineel.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` zijn nuttig in logistieke of document‑uitwisselingsscenario's.  
- Het instellen van `MacroPdf417Terminator` op `Set` markeert deze barcode als het laatste segment, wat het reconstructie‑algoritme vereenvoudigt.

### Stap 4: sla de gegenereerde barcode‑afbeelding op

`Save` schrijft de barcode‑afbeelding naar het opgegeven bestandspad.

Schrijf tenslotte de barcode naar een PNG‑bestand. Je kunt elk ondersteund formaat kiezen (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Why this matters*: PNG behoudt verliesvrije pixeldata, waardoor scanners het exacte modulepatroon lezen dat je hebt geconfigureerd. Het wijzigen van het formaat kan de visuele kwaliteit en bestandsgrootte beïnvloeden.

#### Verwachte output

Het uitvoeren van het volledige programma maakt een bestand genaamd **ExtPDF417Meta.png** aan. Het openen van de afbeelding toont een rechthoekige Macro PDF417‑barcode met de tekst “Åspóse.Barcóde©” gecodeerd, en de visuele dichtheid komt overeen met de 2‑pixel X‑dimensie die je hebt ingesteld. Het scannen van de afbeelding met een PDF417‑compatibele lezer retourneert alle metadata‑velden die in Stap 3 zijn gedefinieerd.

## Volledig werkend voorbeeld

Kopieer de onderstaande code naar een nieuw console‑project (`dotnet new console`) en vervang `YOUR_DIRECTORY` door een absoluut of relatief pad dat op je machine bestaat.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Voer het programma uit (`dotnet run`). Na uitvoering controleer je of het PNG‑bestand op de opgegeven locatie verschijnt. Gebruik een barcode‑leestoepassing die Macro PDF417 ondersteunt om te bevestigen dat de metadata correct is ingebed.

## Veelvoorkomende variaties en randgevallen

- **Verschillende afbeeldingsformaten**: Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Tiff` als je downstream‑systeem een ander formaat prefereert.  
- **Wijzigen van module‑grootte**: Grotere `XDimension.Pixels`‑waarden verbeteren de scan‑betrouwbaarheid op laag‑resolutie‑scanners maar vergroten de bestandsgrootte.  
- **Meerdere segmenten**: Om een multi‑segmentbestand te produceren, genereer je een reeks barcodes, verhoog je `MacroPdf417SegmentID` voor elke, en houd je `MacroPdf417FileID` constant. Alleen het laatste segment moet `MacroPdf417Terminator` ingesteld hebben.  
- **Unicode‑ondersteuning**: De generator codeert Unicode‑tekens automatisch; zorg ervoor dat je bronstring UTF‑8‑codering gebruikt als je deze uit een extern bestand leest.  
- **Foutafhandeling**: Plaats de `using`‑block in een try‑catch om `BarCodeException` af te vangen bij ongeldige parameters (bijv. kolomaantal buiten bereik).

## Pro‑tips

- **Performance**: Hergebruik één enkele `BarcodeGenerator`‑instantie bij het maken van veel barcodes met dezelfde instellingen; wijzig alleen de `CodeText`‑eigenschap tussen opslagen.  
- **Bestandsgrootte‑schatting**: Het `MacroPdf417FileSize`‑veld moet overeenkomen met het byte‑aantal van de originele payload; mismatches kunnen downstream‑validatiefouten veroorzaken.  
- **Testing**: Valideer gegenereerde barcodes zowel met Aspose’s ingebouwde decoder (`BarCodeReader`) als met een scanner van een derde partij om interoperabiliteit te waarborgen.

## Conclusie

Dit **Aspose.BarCode**‑voorbeeld laat zien hoe je **PDF417 barcode C#** kunt **maken** met volledige Macro‑metadata‑ondersteuning, waardoor je een solide basis krijgt voor het bouwen van robuuste barcode‑gebaseerde gegevensuitwisselings‑pijplijnen.

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een barcode‑rustzone te maken voor Code 16K met Aspose.BarCode voor .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hoe een barcode‑rustzone te maken voor ITF-14 met Aspose.BarCode voor .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Laatst bijgewerkt:** 2026-10-09  
**Getest met:** Aspose.BarCode 24.11 for .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe PDF417-barcode-afbeelding te genereren in C met Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Barcode‑generator‑tutorial Hoe PDF417-barcode te genereren in](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}