---
category: general
date: 2026-10-24
description: Leer hoe je PDF417‑barcode kunt lezen in C# met Aspose.BarCode. Deze
  tutorial behandelt het lezen van een barcode‑afbeelding, het extraheren van Macro
  PDF417‑velden en het afhandelen van veelvoorkomende scenario’s.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: nl
lastmod: 2026-10-24
og_description: Hoe PDF417-barcode te lezen in C# met Aspose.BarCode. Volg deze volledige
  tutorial om afbeeldingen te decoderen, Macro PDF417-metadata op te halen en veelvoorkomende
  valkuilen te vermijden.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Hoe PDF417-barcode te lezen in C# met Aspose – volledige gids
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Hoe PDF417-barcode lezen in C# met Aspose – stapsgewijze gids
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcode lezen in C# met Aspose – stapsgewijze handleiding

Als je **PDF417 barcode wilt lezen** in een .NET‑applicatie, laat deze handleiding je precies zien hoe je PDF417 barcode kunt lezen in C# met behulp van de Aspose.BarCode‑bibliotheek. Of je nu gescande documenten, mobiele opnames of batch‑geïmporteerde afbeeldingen verwerkt, de onderstaande code decodeert de barcode en haalt elke Macro PDF417‑eigenschap op die je nodig zou kunnen hebben.

Het lezen van een barcode‑afbeelding in C# kan ontmoedigend aanvoelen, vooral wanneer de barcode uitgebreide metadata bevat. Deze tutorial verwijdert het giswerk door een volledig, uitvoerbaar voorbeeld te bieden, elke regel uit te leggen en randgevallen te behandelen, zoals ontbrekende macro‑segmenten of beschadigde afbeeldingen. Aan het einde kun je PDF417‑decodering met vertrouwen integreren in elk C#‑project.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een IDE die .NET ondersteunt)  
* Een licentie of gratis evaluatie van **Aspose.BarCode for .NET** – je kunt een tijdelijke sleutel verkrijgen via de Aspose‑website  
* Een afbeeldingsbestand dat een Macro PDF417 barcode bevat (bijv. `ExtPDF417Meta.png`)

> **Pro tip:** Als je alleen wilt experimenteren, biedt Aspose een proefperiode van 30 dagen die volledige functionaliteit voor barcode‑lezen bevat.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

Open je projectmap in een terminal en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `Aspose.BarCode.ReadRecognition`‑namespace toe, die de `BarCodeReader`‑klasse bevat die wordt gebruikt om afbeeldingen te decoderen.

## Stap 2: Maak een BarCodeReader voor een PDF417‑afbeelding

De `BarCodeReader`‑constructor neemt twee argumenten: het pad naar het afbeeldingsbestand en de `DecodeType` die je wilt targeten. Het specificeren van `DecodeType.MacroPdf417` vertelt Aspose om naar Macro PDF417‑symbolen te zoeken en de uitgebreide eigenschappen automatisch in te vullen.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Waarom `DecodeType.MacroPdf417` gebruiken?

* **Macro PDF417** slaat extra velden op (bestand‑ID, segment‑aantal, tijdstempels, enz.) die niet aanwezig zijn in standaard PDF417.  
* De `Extended`‑eigenschap van `BarCodeResult` wordt alleen gevuld wanneer je het macro‑type aanvraagt, waardoor je een aparte parse‑stap bespaart.

## Stap 3: Doorloop alle gedetecteerde barcodes

Een enkele afbeelding kan meerdere PDF417‑symbolen bevatten (bijvoorbeeld wanneer een document over meerdere pagina's is verdeeld). De `ReadBarCodes()`‑methode retourneert een `IEnumerable<BarCodeResult>` waar je over kunt itereren.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Als de afbeelding geen barcode bevat, wordt de lus simpelweg nooit uitgevoerd en sluit het programma zich netjes af. Dit gedrag maakt de code veilig voor batchverwerking waarbij sommige bestanden mogelijk barcode‑vrij zijn.

## Stap 4: Geef Macro PDF417 uitgebreide eigenschappen weer

De `Extended.Pdf417`‑eigenschap groepeert alle macro‑specifieke velden. Elk veld komt direct overeen met de PDF417‑specificatie, zodat je ze kunt opslaan in een database, loggen of gebruiken voor verdere validatie.

```csharp
        // Macro PDF417 extended properties
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

### Wat elke eigenschap betekent

| Eigenschap | Beschrijving |
|------------|--------------|
| **MacroPdf417FileID** | Unieke identifier voor het volledige multi‑segment document. |
| **MacroPdf417SegmentID** | Index van het huidige segment (beginnend bij 0). |
| **MacroPdf417SegmentsCount** | Totaal aantal segmenten dat tot het bestand behoort. |
| **MacroPdf417FileName** | Optionele bestandsnaam ingebed in de barcode. |
| **MacroPdf417Checksum** | CRC‑16 checksum voor het macro‑datablok. |
| **MacroPdf417FileSize** | Originele bestandsgrootte in bytes. |
| **MacroPdf417TimeStamp** | Tijdstempel wanneer de macro‑barcode werd gegenereerd. |
| **MacroPdf417Addressee** | Beoogde ontvanger van het document. |
| **MacroPdf417Sender** | Afzender van het document. |
| **MacroPdf417Terminator** | Terminator‑vlag die het einde van de macro‑reeks aangeeft. |

Deze velden zijn vooral nuttig wanneer je een grote PDF of afbeelding reconstrueert die in meerdere PDF417‑symbolen is opgesplitst voor afdrukken op media met lage resolutie.

## Stap 5: Afhandelen van veelvoorkomende randgevallen

### Ontbrekende macro‑velden

Soms wordt een PDF417‑barcode gegenereerd zonder de optionele macro‑velden. Toegang tot een ontbrekende eigenschap retourneert `null` of `0`. Bescherm hiertegen als je de waarden wilt opslaan:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Beschadigde of lage‑kwaliteit afbeeldingen

Als de afbeelding onscherp is, kun je de detectie verbeteren door de kwaliteitsopties van `BarCodeReader` in te schakelen:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Deze instellingen zijn optioneel, maar kunnen de succesratio voor gescande documenten aanzienlijk verhogen.

### Meerdere barcode‑formaten in één afbeelding

Als je vermoedt dat er andere barcode‑typen aanwezig kunnen zijn, gebruik dan `DecodeType.AllSupported` en filter de resultaten:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Volledig uitvoerbaar voorbeeld

Kopieer het volgende programma naar een nieuw console‑project (`dotnet new console`) en voer het uit. Vervang de `imagePath`‑variabele door de locatie van je eigen Macro PDF417‑afbeelding.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Verwachte output** (waarden zullen verschillen afhankelijk van je afbeelding):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Als de afbeelding geen Macro PDF417‑symbolen bevat, schrijft het programma niets en sluit stilletjes af — perfect voor batch‑taken die veel bestanden verwerken.

## Veelgestelde vragen

**V: Kan ik een standaard PDF417 (niet‑macro) lezen met dezelfde code?**  
A: Ja. Verander `DecodeType.MacroPdf417` in `DecodeType.Pdf417`. De `Extended`‑eigenschap zal leeg zijn, maar `CodeText` en `CodeTypeName` blijven beschikbaar.

**V: Ondersteunt Aspose.BarCode het lezen vanuit een stream in plaats van een bestandspad?**  
A: Absoluut. Gebruik de overload `new BarCodeReader(Stream, DecodeType)` en geef een `FileStream` of `MemoryStream` door. Dit is handig wanneer de afbeelding afkomstig is van een web‑API.

**V: Hoe valideer ik de checksum?**  
A: Het veld `MacroPdf417Checksum` bevat de ruwe CRC‑16‑waarde. Je kunt de checksum opnieuw berekenen op het gereconstrueerde bestand en vergelijken om de gegevensintegriteit te waarborgen.

## Volgende stappen en gerelateerde onderwerpen

* **PDF417 barcodes schrijven** – verken `BarCodeGenerator` om macro‑barcodes te maken voor testdoeleinden.  
* **Meerdere segmenten combineren** – na het lezen van alle segmenten, sorteer ze op `MacroPdf417SegmentID` en concateneer `CodeText` om de oorspronkelijke payload te reconstrueren.  
* **Prestatie‑afstemming** – voor scenario's met hoge doorvoer, hergebruik een enkele `BarCodeReader`‑instantie over vele afbeeldingen en

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze handleiding worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 lezen in C# – Volledig barcode‑voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Hoe macro PDF417 barcode maken in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Barcode lezen van afbeelding C# – volledige gids met Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}