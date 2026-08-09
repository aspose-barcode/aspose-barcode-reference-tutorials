---
category: general
date: 2026-08-09
description: Aspose barcode-voorbeeld dat laat zien hoe je een barcodegenerator in
  C# gebruikt om een Macro PDF417 met volledige metadata-ondersteuning te maken.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: nl
lastmod: 2026-08-09
og_description: Het Aspose barcode-voorbeeld toont het gebruik van een barcodegenerator
  in C# om een Macro PDF417-barcode te maken die bestand‑ID, segmentgegevens, tijdstempel
  en andere metadata bevat.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose barcode voorbeeld – maak Macro PDF417 met C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Aspose barcode-voorbeeld: genereer Macro PDF417 in C#'
url: /nl/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose barcode voorbeeld: genereer Macro PDF417 in C#

Als je een **aspose barcode voorbeeld** nodig hebt dat een Macro PDF417 barcode maakt, laat deze gids je zien hoe je dit doet met een **barcode generator C#**. Je ziet elke vereiste instelling, van basisafmetingen tot de volledige set van Macro PDF417 metadata‑velden, en je eindigt met een PNG‑afbeelding die klaar is voor downstream verwerking.

De tutorial behandelt de volledige workflow, legt uit waarom elke parameter belangrijk is, en biedt een kant‑klaar code‑voorbeeld. Er zijn geen externe referenties nodig; je kunt de code kopiëren, de waarden aanpassen en direct uitvoeren.

## Vereisten

- .NET 6.0 (of later) geïnstalleerd  
- Visual Studio 2022 of een C#‑compatibele IDE  
- Een geldige licentie voor **Aspose.BarCode for .NET** (de gratis proefversie werkt voor dit voorbeeld)  

Voeg het Aspose.BarCode NuGet‑pakket toe aan je project:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Maak de barcode generator C#‑instantie

De eerste stap is om `BarcodeGenerator` te instantieren met de `EncodeTypes.MacroPdf417` enum‑waarde en de tekst die je wilt coderen. De tekst kan Unicode‑tekens bevatten, die de bibliotheek automatisch verwerkt.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Waarom dit belangrijk is*: `EncodeTypes.MacroPdf417` vertelt de engine om een Macro PDF417‑symbool te produceren, dat gesegmenteerde data en extra bestands‑niveau metadata ondersteunt. De `using`‑statement garandeert dat niet‑beheerde resources worden vrijgegeven nadat de afbeelding is opgeslagen.

## Stap 2: Definieer basis barcode‑uiterlijk

Een Macro PDF417‑barcode bestaat uit vierkante modules. Het regelen van de module‑grootte en het aantal kolommen beïnvloedt zowel de leesbaarheid als de bestandsgrootte.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Waarom dit belangrijk is*: `XDimension.Pixels` bepaalt de visuele dichtheid; een waarde van 2 pixels werkt goed voor weergave op schermen terwijl de afbeelding klein blijft. Pas het aantal kolommen aan om aan je lay‑outbeperkingen te voldoen — meer kolommen creëren een bredere, kortere barcode.

## Stap 3: Stel Macro PDF417‑specifieke metadata in

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

*Waarom dit belangrijk is*:  
- `MacroPdf417FileID` koppelt alle segmenten die tot hetzelfde logische bestand behoren.  
- `MacroPdf417SegmentID` en `MacroPdf417SegmentsCount` stellen de decoder in staat fragmenten correct te herschikken.  
- `MacroPdf417Checksum` biedt een snelle integriteitscontrole zonder de volledige payload te decoderen.  
- `MacroPdf417FileSize` en `MacroPdf417TimeStamp` stellen downstream‑systemen in staat te verifiëren dat het gereconstrueerde bestand overeenkomt met het origineel.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` zijn nuttig in logistieke of document‑uitwisselingsscenario's.  
- Het instellen van `MacroPdf417Terminator` op `Set` markeert deze barcode als het laatste segment, wat het reconstructie‑algoritme vereenvoudigt.

## Stap 4: Sla de gegenereerde barcode‑afbeelding op

Tot slot schrijf je de barcode naar een PNG‑bestand. Je kunt elk ondersteund formaat kiezen (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Waarom dit belangrijk is*: PNG behoudt verliesvrije pixeldata, waardoor scanners het exacte module‑patroon dat je hebt geconfigureerd kunnen lezen. Het wijzigen van het formaat kan de visuele kwaliteit en bestandsgrootte beïnvloeden.

### Verwachte output

Het uitvoeren van het volledige programma maakt een bestand genaamd **ExtPDF417Meta.png** aan. Het openen van de afbeelding toont een rechthoekige Macro PDF417‑barcode met de tekst “Åspóse.Barcóde©” gecodeerd, en de visuele dichtheid komt overeen met de 2‑pixel X‑dimensie die je hebt ingesteld. Het scannen van de afbeelding met een PDF417‑compatibele lezer retourneert alle metadata‑velden die in Stap 3 zijn gedefinieerd.

## Volledig werkend voorbeeld

Kopieer de onderstaande code in een nieuw console‑project (`dotnet new console`) en vervang `YOUR_DIRECTORY` door een absoluut of relatief pad dat bestaat op jouw machine.

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

Voer het programma uit (`dotnet run`). Na uitvoering, controleer of het PNG‑bestand verschijnt op de opgegeven locatie. Gebruik een barcode‑lezer‑app die Macro PDF417 ondersteunt om te bevestigen dat de metadata correct is ingebed.

## Veelvoorkomende variaties en randgevallen

- **Verschillende afbeeldingsformaten**: Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Tiff` als je downstream‑systeem een ander formaat prefereert.  
- **Aanpassen module‑grootte**: Grotere `XDimension.Pixels`‑waarden verbeteren de scan‑betrouwbaarheid op low‑resolution scanners maar vergroten de afbeelding.  
- **Meerdere segmenten**: Om een multi‑segment bestand te produceren, genereer een reeks barcodes, verhoog `MacroPdf417SegmentID` voor elk, en houd `MacroPdf417FileID` constant. Alleen het laatste segment moet `MacroPdf417Terminator` ingesteld hebben.  
- **Unicode‑ondersteuning**: De generator codeert Unicode‑tekens automatisch; zorg ervoor dat je bron‑string UTF‑8‑codering gebruikt als je deze uit een extern bestand leest.  
- **Foutafhandeling**: Plaats de `using`‑block in een try‑catch om `BarCodeException` te vangen voor ongeldige parameters (bijv. kolom‑aantal buiten bereik).

## Pro‑tips

- **Prestaties**: Hergebruik een enkele `BarcodeGenerator`‑instantie bij het maken van veel barcodes met dezelfde instellingen; wijzig alleen de `CodeText`‑eigenschap tussen opslagen.  
- **Bestandsgrootte‑schatting**: Het `MacroPdf417FileSize`‑veld moet overeenkomen met het byte‑aantal van de originele payload; mismatches kunnen downstream‑validatiefouten veroorzaken.  
- **Testen**: Valideer gegenereerde barcodes met zowel Aspose’s ingebouwde decoder (`BarCodeReader`) als een scanner van derden om interoperabiliteit te waarborgen.

## Conclusie

Dit **aspose barcode voorbeeld

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een barcode‑rustzone te maken voor Code 16K met Aspose.BarCode voor .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Hoe een barcode‑rustzone te maken voor ITF-14 met Aspose.BarCode voor .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}