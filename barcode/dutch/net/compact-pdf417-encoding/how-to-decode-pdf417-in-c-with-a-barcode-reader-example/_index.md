---
category: general
date: 2026-09-19
description: Hoe PDF417 te decoderen in C# – leer barcodes uit een afbeelding te lezen
  met een beknopt barcode‑lezer‑voorbeeld dat volledige Macro PDF417‑gegevens extraheert.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: nl
lastmod: 2026-09-19
og_description: Hoe PDF417 te decoderen in C# met een stap‑voor‑stap barcodelezer‑voorbeeld.
  Extraheer elk Macro PDF417‑veld uit een afbeelding in enkele seconden.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Hoe PDF417 te decoderen in C# – volledige gids voor barcodelezers
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Hoe PDF417 te decoderen in C# met een barcodelezer voorbeeld
url: /nl/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 te decoderen in C# met een barcodelezer‑voorbeeld

Als je PDF417 in C# moet decoderen, laat deze gids je precies zien hoe je PDF417 uit een afbeeldingsbestand decodeert. Je leert barcodes uit een afbeelding te lezen, toegang te krijgen tot de uitgebreide Macro PDF417‑velden, en de oplossing te integreren in elk .NET‑project.

Het decoderen van PDF417‑barcodes is gebruikelijk in logistiek, ticketing en identiteitsverificatie. Deze tutorial behandelt alles wat nodig is voor een productie‑klare implementatie, inclusief vereiste bibliotheken, volledige broncode en tips voor het omgaan met randgevallen.

## Vereisten

- .NET 6.0 of later geïnstalleerd  
- Visual Studio 2022 (of een IDE die C# ondersteunt)  
- Het **Aspose.BarCode for .NET** NuGet‑pakket (versie 23.11 of nieuwer)  

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

De `BarCodeReader`‑klasse uit deze bibliotheek ondersteunt het `MacroPdf417`‑decodeertype dat nodig is voor volledige PDF417‑extractie.

## Stap 1: Hoe PDF417 te decoderen in C# – initialiseer de lezer

De eerste stap maakt een `BarCodeReader`‑instantie aan die zich richt op een Macro PDF417‑afbeelding. De `DecodeType.MacroPdf417`‑vlag vertelt de bibliotheek om de uitgebreide Macro‑velden te parseren.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Waarom dit belangrijk is:** Initialiseren met `MacroPdf417` maakt de `Extended.Pdf417`‑eigenschap beschikbaar op elk `BarCodeResult`, waardoor je toegang krijgt tot bestands‑niveau metadata zoals segment‑ID's en tijdstempels.

## Stap 2: Barcodes lezen uit afbeelding

Een PDF417‑afbeelding kan meerdere macro‑segmenten bevatten. De `ReadBarCodes()`‑methode retourneert een enumerable van alle gedetecteerde barcodes, zodat je er veilig doorheen kunt itereren.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Tip:** Als je slechts één barcode verwacht, kun je na de eerste iteratie stoppen, maar door over alle resultaten te itereren garandeer je dat je elk segment in meer‑pagina documenten vastlegt.

## Stap 3: PDF417‑barcode decoderen – basis‑ en uitgebreide gegevens extraheren

Binnen de lus, geef zowel de generieke barcode‑informatie als de macro‑specifieke velden weer. Het `Extended.Pdf417`‑object bevat elk stuk metadata dat door de PDF417‑standaard is gedefinieerd.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**Uitleg van belangrijke velden**

| Veld | Betekenis |
|-------|-----------|
| `MacroPdf417FileID` | Identifier die alle segmenten groepeert die tot hetzelfde logische bestand behoren |
| `MacroPdf417SegmentID` | Index van het huidige segment (begint bij 0) |
| `MacroPdf417SegmentsCount` | Totaal aantal verwachte segmenten voor het bestand |
| `MacroPdf417FileName` | Optionele bestandsnaam ingebed in de macro |
| `MacroPdf417Checksum` | CRC‑16‑controlesom voor gegevensintegriteit |
| `MacroPdf417FileSize` | Originele bestandsgrootte in bytes |
| `MacroPdf417TimeStamp` | Tijdstempel wanneer de macro is gegenereerd |
| `MacroPdf417Addressee` | Beoogde ontvanger van de macro‑gegevens |
| `MacroPdf417Sender` | Afzender van de macro‑gegevens |
| `MacroPdf417Terminator` | Boolean‑vlag die het laatste segment aangeeft |

Toegang tot deze velden stelt je in staat het originele document te reconstrueren, integriteit te verifiëren, of de gegevens te routeren op basis van afzender/ontvanger‑informatie.

## Stap 4: Volledig C# barcode‑lezer voorbeeld – alles samenvoegen

Hieronder staat het volledige, uitvoerbare programma. Vervang `YOUR_DIRECTORY` door de map die je `MacroPdf417.png`‑bestand bevat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Verwachte console‑output (voorbeeld)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

De exacte waarden zullen verschillen op basis van de inhoud van je Macro PDF417‑barcode.

## Veelvoorkomende randgevallen afhandelen

| Situatie | Aanbevolen aanpak |
|-----------|-------------------|
| **Geen barcode gedetecteerd** | Controleer het afbeeldingspad, zorg dat het bestand niet corrupt is, en bevestig dat de barcode zichtbaar is (voldoende contrast). |
| **Gedeeltelijke macro‑segmenten** | Gebruik `MacroPdf417SegmentsCount` om ontbrekende delen te detecteren. Je kunt de resterende segmenten opvragen bij het bronsysteem en de decoder opnieuw uitvoeren. |
| **Grote afbeeldingen die geheugenbelasting veroorzaken** | Laad de afbeelding in een `System.Drawing.Bitmap` met een verlaagde resolutie voordat je deze aan `BarCodeReader` doorgeeft. |
| **Niet‑Macro PDF417** | Verander `DecodeType.MacroPdf417` naar `DecodeType.Pdf417` als je alleen de platte barcode‑tekst nodig hebt. |

## Pro‑tips

- **Batchverwerking:** Plaats de lezerlogica in een methode die een lijst met bestandspaden accepteert. Hergebruik een enkele `BarCodeReader`‑instantie per thread om toewijzings‑overhead te verminderen.  
- **Prestaties:** Voor scenario's met hoge doorvoer, schakel de `ReaderOptions`‑eigenschap `ReadQuality` in om snelheid en nauwkeurigheid in balans te brengen.  
- **Beveiliging:** Valideer `CodeText` voordat je het gebruikt in bestandssysteem‑operaties om pad‑traversal‑aanvallen te voorkomen.

## Conclusie

In deze tutorial heb je geleerd hoe je PDF417 in C# decodeert door barcodes uit een afbeelding te lezen, elk Macro PDF417‑veld te extraheren, en een compleet C# barcode‑lezer voorbeeld te bouwen. De oplossing werkt met de nieuwste Aspose.BarCode‑bibliotheek, verwerkt macro‑segmenten met meerdere delen, en biedt praktische richtlijnen voor real‑world projecten.

Vervolgens kun je gerelateerde onderwerpen verkennen, zoals **QR‑codes lezen**, **batch‑barcodeverwerking**, en **PDF417‑barcodes genereren**, om je document‑automatiseringstoolkit uit te breiden. Voel je vrij om te experimenteren met verschillende afbeeldingsbronnen, de code te integreren in ASP.NET‑services, of deze uit te breiden om de geëxtraheerde metadata op te slaan in een database. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 te lezen in C# – Volledig barcode‑lezer voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hoe PDF417‑barcode‑afbeelding te genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Barcode lezen uit afbeelding – C# barcode‑lezer voorbeeld](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}