---
category: general
date: 2026-10-12
description: Leer hoe je een Aspose‑barcode‑voorbeeld in C# maakt dat een MacroPdf417‑barcode
  genereert met volledige metadata en deze terugleest met BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: nl
lastmod: 2026-10-12
og_description: Aspose barcode-voorbeeld in C# dat laat zien hoe je een MacroPdf417-barcode
  met ingebedde metadata genereert en deze terugleest met BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Maak een Aspose‑barcodevoorbeeld met MacroPdf417 in C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Hoe een Aspose barcode‑voorbeeld met MacroPdf417 in C# te bouwen
url: /nl/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een Aspose barcode voorbeeld te bouwen met MacroPdf417 in C#

Als je een **aspose barcode example** nodig hebt die een MacroPdf417‑barcode maakt en de ingebedde metadata uitleest, laat deze gids je de volledige workflow zien. Je ziet hoe je de generator configureert, bestands‑niveau informatie embedt, de afbeelding opslaat en vervolgens dezelfde gegevens decodeert met `BarCodeReader`.

De tutorial behandelt alles wat je moet weten voor **C# barcode generation** met Aspose.BarCode, inclusief veelvoorkomende valkuilen en tips voor het omgaan met grote bestands‑ID's of aangepaste tijdstempels.

## Wat je nodig hebt

* .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
* Visual Studio 2022 of een IDE die C# ondersteunt
* Een actieve Aspose.BarCode-licentie (de gratis proefversie werkt voor ontwikkeling)
* Het NuGet‑pakket `Aspose.BarCode` geïnstalleerd in je project

Deze vereisten garanderen dat het voorbeeld zonder extra configuratie draait.

## Stap 1: Het Aspose barcode voorbeeldproject opzetten

Maak een nieuwe console‑applicatie aan en voeg de Aspose.BarCode‑bibliotheek toe:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Het `Aspose.BarCode`‑pakket levert `BarcodeGenerator`, `BarCodeReader` en alle typen die nodig zijn voor MacroPdf417‑verwerking.

### Waarom deze stap belangrijk is
Het toevoegen van het NuGet‑pakket lost de `EncodeTypes`, `DecodeType` en `BarCodeImageFormat`‑enumeraties op die later worden gebruikt. Zonder het pakket zou de compiler deze symbolen niet herkennen en zou het voorbeeld falen tijdens het bouwen.

## Stap 2: De MacroPdf417‑barcodegenerator maken

Open **Program.cs** en vervang de sjablooncode door het volgende blok. Dit blok maakt een `BarcodeGenerator` geconfigureerd voor de MacroPdf417‑symbologie en stelt basis‑weergave‑parameters in.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Uitleg van belangrijke eigenschappen

| Eigenschap | Doel | Typisch bereik / opmerkingen |
|------------|------|------------------------------|
| `MacroPdf417FileID` | Unieke identifier voor het gehele bestand | Moet ≤ 2³¹‑1 zijn |
| `MacroPdf417SegmentID` | Index van het huidige segment | Begint bij 0 |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten in het bestand | Moet ≥ SegmentID zijn |
| `MacroPdf417FileName` | Menselijk leesbare naam voor het bestand | Tot 255 tekens |
| `MacroPdf417Checksum` | CCITT‑16 checksum van het originele bestand | Bereken door extern hulpmiddel indien nodig |
| `MacroPdf417FileSize` | Grootte van het originele bestand in bytes | Handig voor validatie |
| `MacroPdf417TimeStamp` | Datum/tijd waarop het bestand is aangemaakt | Gebruik UTC voor consistentie |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Optionele routeringsinformatie | Elke string tot 255 tekens |
| `MacroPdf417Terminator` | Markeert het laatste segment | Gebruik `Set` voor het laatste segment |

Deze velden vormen de **barcode metadata** die de lezer later kan extraheren.

## Stap 3: Decodeer de barcode en toon de metadata

Na het opslaan van de afbeelding gaat hetzelfde programma verder door het bestand te openen met `BarCodeReader`. Voeg de volgende code toe binnen de `Main`‑methode, na het vorige `using`‑blok:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Waarom teruglezen belangrijk is
De `BarCodeReader` controleert of de metadata die je hebt ingebed correct is gecodeerd. Als een eigenschap ontbreekt of buiten het bereik valt, retourneert de lezer `null` voor dat veld, zodat je fouten netjes kunt afhandelen.

## Stap 4: Voer uit en controleer de output

Voer het programma uit:

```bash
dotnet run
```

Je zou console‑output moeten zien die lijkt op:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Als de waarden overeenkomen met die je in Stap 2 hebt ingesteld, werkt het **aspose barcode example** zoals verwacht.

## Randgevallen en best‑practice tips

| Situatie | Waar op te letten | Aanbevolen aanpak |
|----------|-------------------|-------------------|
| **FileID overschrijdt 32‑bit bereik** | Aspose geeft een `ArgumentOutOfRangeException`. | Houd de ID ≤ 2 147 483 647 of splits het bestand in meerdere MacroPdf417‑blokken. |
| **Tijdstempel in lokale tijd** | Lezers in een andere tijdzone kunnen de waarde verkeerd interpreteren. | Sla tijdstempels op in UTC (`DateTime.UtcNow`) en converteer bij weergave indien nodig. |
| **Grote bestandsgrootte** | `MacroPdf417FileSize` is een `int`; waarden > 2 GB overlopen. | Gebruik een aangepast veld of splits het bestand in kleinere segmenten. |
| **Ontbrekend segment** | Als `SegmentID` niet opeenvolgend is, mislukt de reconstructie. | Valideer de segmentvolgorde vóór het coderen of gebruik foutcorrectie‑instellingen. |
| **Niet‑ondersteund afbeeldingsformaat** | Opslaan als BMP kan de grootte sterk verhogen. | PNG is een goede standaard; JPEG kan worden gebruikt als je verliesgevende compressie accepteert. |

**Pro tip:** Wanneer je veel barcodes in één batch genereert, hergebruik dan één `BarcodeGenerator`‑instantie en wijzig alleen de `EncodeTypes` en de brontekst. Dit vermindert geheugenallocaties en versnelt de verwerking.

## Gerelateerde onderwerpen die je hierna kunt verkennen

* **Andere macro-symbologieën** – Aspose ondersteunt ook MacroPdf417 met foutcorrectieniveaus.
* **Barcodes in PDF's embedden** – Combineer `Aspose.PDF` met de barcodegenerator om afdrukbare documenten te maken.
* **ASP.NET Core integratie** – Serveer gegenereerde barcodes direct vanuit een web‑API.
* **Scannen via mobiele apparaten** – Gebruik de `Aspose.BarCode.Cloud` SDK voor cross‑platform decodering.

Deze vervolgonderwerpen breiden het **aspose barcode example** natuurlijk uit en verdiepen je expertise in **C# barcode generation**.

## Conclusie

Je hebt nu een volledig functioneel **aspose barcode example** dat een MacroPdf417‑barcode maakt, rijke **barcode metadata** embedt, de afbeelding opslaat en de gegevens terugleest met `BarCodeReader`. Door de bovenstaande stappen te volgen, kun je de code aanpassen aan verschillende bestands‑ID's, tijdstempels of zelfs andere barcode‑typen die door Aspose worden ondersteund.

Voel je vrij om te experimenteren met extra metadata‑velden, het afbeeldingsformaat te wijzigen, of de generator in een grotere applicatie te integreren. Veel programmeerplezier!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}