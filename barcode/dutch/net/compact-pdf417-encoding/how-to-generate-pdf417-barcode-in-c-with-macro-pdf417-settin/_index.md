---
category: general
date: 2026-10-15
description: Leer hoe je een PDF417‑barcode genereert in C# met Macro‑PDF417‑parameters,
  de afmetingen van de barcode instelt en opslaat als PNG. Volledig codevoorbeeld
  inbegrepen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: nl
lastmod: 2026-10-15
og_description: Hoe PDF417‑barcode te genereren in C# met volledige Macro‑PDF417‑configuratie,
  dimensie‑controle en PNG‑output. Volg het volledige voorbeeld.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Hoe PDF417‑barcode te genereren in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Hoe PDF417‑barcode te genereren in C# met Macro‑PDF417‑instellingen
url: /nl/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode te genereren in C# met Macro‑PDF417‑instellingen

Als je **hoe PDF417-barcode te genereren** voor een document‑workflow nodig hebt, laat deze gids je de exacte stappen zien. Je ziet hoe je Macro‑PDF417‑parameters configureert, de afmetingen van de barcode instelt en het resultaat exporteert als een PNG‑afbeelding — allemaal in één uitvoerbaar C#‑programma.

Het genereren van een PDF417-barcode vereist geen meerdere bibliotheken of complexe post‑processing. Door Aspose.Barcode for .NET te gebruiken kun je elk aspect van de barcode beheersen, van module‑breedte tot checksum, en een afbeelding van hoge kwaliteit produceren die klaar is voor afdrukken of scannen.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 (of later) SDK geïnstalleerd  
* Visual Studio 2022 of een andere C#‑IDE naar keuze  
* Aspose.Barcode for .NET NuGet‑pakket (`Install-Package Aspose.Barcode`)  

Deze vereisten zorgen ervoor dat de code compileert zonder extra configuratie.

## Stap 1: Maak een barcode‑generator voor een Macro‑PDF417‑barcode

De eerste bewerking maakt een `BarcodeGenerator`‑instantie die het `EncodeTypes.MacroPdf417`‑formaat target. De constructor ontvangt de gegevens die je wilt coderen — in dit geval de string `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Het aanmaken van de generator zet het interne `Parameters`‑object op, dat je later gebruikt om **C# PDF417 barcode**‑eigenschappen aan te passen.

## Stap 2: Stel basis‑uiterlijk van de barcode in – stel barcode‑afmetingen in

Het visueel bepalen van de grootte van een barcode verbetert de scanbetrouwbaarheid. De eigenschap `XDimension.Pixels` definieert de breedte van de module (dot), terwijl `Pdf417.Columns` bepaalt hoeveel kolommen de barcode bevat.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Het instellen van deze afmetingen zorgt ervoor dat de barcode past binnen typische labelgroottes en voldoet aan de specificaties van scanners.

## Stap 3: Geef Macro‑PDF417‑bestandidentificatie op

Macro‑PDF417 breidt de standaard PDF417‑barcode uit met metadata op bestandsniveau. Je moet een unieke bestand‑ID, segment‑ID, totaal aantal segmenten en een mens‑leesbare bestandsnaam toewijzen.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Deze **Macro PDF417‑parameters** stellen downstream‑systemen in staat om het oorspronkelijke bestand uit meerdere barcode‑segmenten te reconstrueren.

## Stap 4: Voeg extra macro‑metadata toe – inclusief barcode‑checksum

Naast identificatie kan Macro‑PDF417 checksum, bestandsgrootte, tijdstempel, geadresseerde, afzender en een terminator‑vlag opslaan. Het leveren van een checksum verbetert de integriteitscontroles tijdens het decoderen.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Het opnemen van een **barcode‑checksum** en andere metadata maakt de barcode zelf‑beschrijvend, wat waardevol is voor geautomatiseerde documentverwerkings‑pijplijnen.

## Stap 5: Sla de gegenereerde barcode op als PNG‑afbeelding – kies barcode‑afbeeldingsformaat

De laatste stap schrijft de barcode naar een bestand. De `Save`‑methode accepteert een bestands‑pad en een `BarCodeImageFormat`‑enum. PNG biedt verliesloze compressie, waardoor scherpe randen behouden blijven voor betrouwbare scanning.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Na uitvoering bevat het bestand `MacroPdf417.png` een scherpe PDF417‑barcode die klaar is om in PDF‑bestanden te embedden, op labels te printen of op schermen te tonen.

## Verwachte uitvoer

Het openen van `C:/Barcodes/MacroPdf417.png` toont een rechthoekige barcode met de gecodeerde tekst “Sample text”. De barcode bevat de macro‑metadata die je hebt ingesteld, die je kunt verifiëren met elke PDF417‑scanner die Macro‑PDF417 ondersteunt. De afbeeldingsafmetingen weerspiegelen de module‑breedte (2 px) en het aantal kolommen (5), wat resulteert in een compacte maar goed leesbare barcode.

## Veelvoorkomende variaties en randgevallen

| Situatie | Aanpassing |
|-----------|------------|
| **Andere gegevenslengte** | Vervang `"Sample text"` door een willekeurige UTF‑8‑string; de generator past automatisch de barcode‑grootte aan. |
| **Hogere resolutie** | Verhoog `XDimension.Pixels` naar 3 of 4 voor grotere modules, handig voor printers met lage resolutie. |
| **Meer segmenten** | Wijzig `MacroPdf417SegmentsCount` zodat het overeenkomt met het totale aantal barcode‑delen dat je wilt genereren. |
| **Alternatief afbeeldingsformaat** | Gebruik `BarCodeImageFormat.Jpeg` of `BarCodeImageFormat.Bmp` als je downstream‑systeem die formaten prefereert. |
| **Aangepaste foutcorrectie** | Pas `generator.Parameters.Barcode.Pdf417.ErrorLevel` (bereik 0‑8) aan om de dichtheid van gegevens af te wegen tegen fouttolerantie. |

**Pro tip:** Valideer de gegenereerde barcode altijd met een fysieke scanner voordat je deze in productie neemt. Scanners kunnen firmware‑specifieke limieten hebben voor module‑breedte of kolomaantal.

## Volledige broncode

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Het uitvoeren van dit programma maakt `MacroPdf417.png` aan in de map `C:/Barcodes`. De console bevestigt een succesvolle generatie.

## Conclusie

Je weet nu **hoe PDF417-barcode te genereren** in C# met volledige Macro‑PDF417‑controle, hoe je **barcode‑afmetingen** instelt, hoe je **barcode‑checksum** en andere macro‑metadata embedt, en hoe je het resultaat exporteert met een gekozen **barcode‑afbeeldingsformaat**. Het volledige voorbeeld kan in elk .NET‑project worden gekopieerd, aangepast voor verschillende gegevenspayloads, en geïntegreerd in grotere document‑automatiserings‑pijplijnen.

### Volgende stappen

* Verken **C# PDF417 barcode**‑foutcorrectieniveaus om de scanbetrouwbaarheid te verbeteren.  
* Combineer meerdere Macro‑PDF417‑segmenten om grote bestanden zoals PDF’s of afbeeldingen te coderen.  
* Schakel het **barcode‑afbeeldingsformaat** over naar SVG voor schaalbare vectorafbeeldingen in webapplicaties.  

Voel je vrij om met de parameters te experimenteren, en deel je resultaten in de reacties of op community‑forums. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Generate barcode C# with Macro PDF417 – full example](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}