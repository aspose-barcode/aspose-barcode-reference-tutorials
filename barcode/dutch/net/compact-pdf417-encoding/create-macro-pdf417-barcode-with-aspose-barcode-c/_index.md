---
category: general
date: 2026-09-22
description: Maak een macro‑PDF417‑barcode met Aspose.BarCode in C#. Leer stap‑voor‑stap
  hoe je een barcode genereert met Aspose, metadata configureert en opslaat als PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: nl
lastmod: 2026-09-22
og_description: Maak een macro PDF417‑barcode met Aspose.BarCode in C#. Deze gids
  laat zien hoe je een barcode genereert met Aspose, macro‑metadata instelt en de
  afbeelding exporteert.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Macro PDF417‑barcode maken met Aspose.BarCode (C#) – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Maak macro-PDF417-barcode met Aspose.BarCode (C#)
url: /nl/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak macro PDF417 barcode met Aspose.BarCode (C#)

Als je een **macro PDF417 barcode** moet **maken** in een .NET‑applicatie, laat deze tutorial je precies zien hoe je dat doet met Aspose.BarCode. Je ziet een volledig, uitvoerbaar voorbeeld dat **barcode genereert met Aspose**, alle macro‑specifieke velden configureert en het resultaat opslaat als een PNG‑afbeelding.

Barcodes worden vaak gebruikt voor voorraad, verzending of documenttracking, en de Macro PDF417‑variant laat je extra bestands‑metadata in de barcode zelf opnemen. Aan het einde van deze gids kun je een volledig uitgeruste macro PDF417 barcode genereren die voldoet aan de ISO/IEC 15438‑standaard.

## Wat je nodig hebt

* .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
* Visual Studio 2022 (of een andere C#‑IDE)
* Een NuGet‑compatibele internetverbinding om het Aspose.BarCode‑pakket op te halen
* Basiskennis van C#‑syntaxis

Deze vereisten zorgen ervoor dat de code compileert zonder extra configuratie.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

De Aspose.BarCode‑bibliotheek levert de `BarcodeGenerator`‑klasse die door de hele tutorial wordt gebruikt.

```bash
dotnet add package Aspose.BarCode
```

Het uitvoeren van het commando voegt de nieuwste stabiele versie toe aan je projectbestand (`*.csproj`). Het pakket bevat ondersteuning voor PDF417, Macro PDF417 en vele andere symbologieën.

## Stap 2: Maak een nieuw console‑project (optioneel)

Als je een schone start wilt, genereer dan een console‑applicatie:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Het gegenereerde `Program.cs` zal de barcode‑generatiecode bevatten.

## Stap 3: Initialiseert de barcode‑generator

De generator wordt aangemaakt met de `EncodeTypes.MacroPdf417`‑enumwaarde en de tekst die je wilt coderen. Aspose.BarCode verwerkt automatisch Unicode‑tekens, zodat je accenten of symbolen direct kunt opnemen.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Waarom dit belangrijk is
`EncodeTypes.MacroPdf417` vertelt de bibliotheek om de macro‑versie van PDF417 te gebruiken, die de mogelijkheid toevoegt om bestands‑metadata (bestand‑ID, segment‑aantal, etc.) in te sluiten. De tekst `"Åspóse.Barcóde©"` toont aan dat de generator UTF‑8‑tekens correct codeert.

## Stap 4: Stel basisbarcode‑afmetingen in

PDF417 stelt je in staat het aantal kolommen en de X‑dimensie (de breedte van een enkele module) te regelen. Het aanpassen van deze waarden beïnvloedt de fysieke grootte van de barcode en de scanbetrouwbaarheid.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Kleinere waarden produceren een dichtere barcode; grotere waarden maken het makkelijker voor scanners met lage resolutie.
* **Columns** – Regelt het aantal datakolommen; typische waarden liggen tussen 1 en 30.

## Stap 5: Configureer Macro PDF417‑metadata

Macro PDF417 bevat extra velden die het bestand beschrijven dat de barcode vertegenwoordigt. Elk veld is optioneel, maar het instellen ervan verbetert de interoperabiliteit met scanners die het macro‑formaat begrijpen.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Uitleg van elk veld

| Eigenschap | Doel | Typisch bereik |
|------------|------|----------------|
| **MacroPdf417FileID** | Unieke identifier voor het logische bestand dat over meerdere barcodes kan worden verdeeld. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Index van het huidige segment (begint bij 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Totaal aantal segmenten waaruit het volledige bestand bestaat. | 1‑99 |
| **MacroPdf417FileName** | Menselijk leesbare naam van het bestand. | Up to 255 characters |
| **MacroPdf417Checksum** | Optionele checksum voor foutdetectie. | 0‑65535 |
| **MacroPdf417FileSize** | Grootte van het originele bestand in bytes. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Tijdstempel van aanmaak of wijziging van het bestand. | Any `DateTime` |
| **MacroPdf417Addressee** | Bestemmingsidentifier (bijv. afdeling of machine). | Free‑form string |
| **MacroPdf417Sender** | Herkomstidentifier (bijv. bedrijfsnaam). | Free‑form string |
| **MacroPdf417Terminator** | Geeft aan of dit segment het laatste is. | `Set` or `Unset` |

**Pro tip:** Als je een groot bestand over meerdere barcodes verdeelt, zorg er dan voor dat elke segment‑`SegmentID` opeenvolgend is en dat `SegmentsCount` constant blijft over alle segmenten. Scanners vertrouwen op deze waarden om het originele bestand te reconstrueren.

## Stap 6: Sla de barcode‑afbeelding op

Aspose.BarCode ondersteunt vele uitvoerformaten (PNG, JPEG, BMP, SVG, enz.). PNG biedt verliesvrije kwaliteit, wat ideaal is voor testen en documentatie.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Het uitvoeren van het programma maakt een bestand genaamd `ExtPDF417Meta.png` aan in de output‑map van het project (`bin/Debug/net6.0/`). Open de afbeelding met een willekeurige viewer om te controleren of de barcode correct wordt weergegeven.

## Stap 7: Verifieer de gegenereerde barcode (optioneel)

Als je een PDF417‑scannerapp (mobiel of desktop) hebt, scan dan de opgeslagen PNG. De scanner zou moeten teruggeven:

* De gecodeerde tekst `"Åspóse.Barcóde©"`
* Alle macro‑velden die je hebt geconfigureerd (bestand‑ID, segment‑ID, enz.)

Voor geautomatiseerde verificatie biedt Aspose.BarCode ook een `BarCodeReader`‑klasse:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Dit fragment toont hoe je de macro‑metadata programmatisch kunt uitlezen, waarmee wordt bevestigd dat **barcode genereren met Aspose** end‑to‑end werkt.

## Randgevallen en best practices

| Situatie | Aanbevolen aanpak |
|----------|-------------------|
| **Unicode‑tekens** | Zorg ervoor dat de bronstring UTF‑8 is (standaard in .NET). Aspose.BarCode codeert Unicode automatisch, maar controleer de tekenset van de scanner. |
| **Groot bestand** | Macro PDF417 splitst bestanden in maximaal 99 segmenten. Als het bestand groter is dan 400 KB, verhoog dan `SegmentsCount` en genereer meerdere barcodes, elk met een opeenvolgende `SegmentID`. |
| **Tijdstempelprecisie** | Gebruik `DateTime.UtcNow` voor universele tijd; sommige scanners verwachten UTC. |
| **Checksum‑validatie** | Geef een correcte checksum op als je de integriteit aan de ontvangende kant wilt valideren. |
| **Verschillende afbeeldingsformaten** | Gebruik `BarCodeImageFormat.Svg` voor vectorafbeeldingen wanneer je oneindig schaalbare barcodes nodig hebt. |
| **Prestaties** | Herbruik een enkele `BarcodeGenerator`‑instantie bij het genereren van veel barcodes; wijzig alleen de `Parameters` tussen iteraties. |

## Volledig, uitvoerbaar voorbeeld

Hieronder staat het volledige programma dat je kunt kopiëren, plakken en uitvoeren zonder aanpassingen (ervan uitgaande dat het NuGet‑pakket is geïnstalleerd).



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Aspose barcode voorbeeld: macro PDF417 genereren in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [PDF417 barcode‑metadata maken in C# – Complete stap‑voor‑stap‑gids](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Hoe PDF417 barcode‑afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}