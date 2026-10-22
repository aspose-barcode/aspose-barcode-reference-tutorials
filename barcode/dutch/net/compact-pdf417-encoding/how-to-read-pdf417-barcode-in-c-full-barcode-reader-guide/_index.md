---
category: general
date: 2026-10-21
description: Hoe PDF417‑barcode te lezen in C# met een barcodelezer vanuit een afbeelding.
  Volg dit stapsgewijze C#‑barcodelezer‑voorbeeld voor betrouwbare decodering.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: nl
lastmod: 2026-10-21
og_description: Hoe PDF417-barcode te lezen in C# met een compleet barcodelezer‑voorbeeld.
  Leer Macro PDF417‑afbeeldingen te decoderen en toegang te krijgen tot alle uitgebreide
  velden.
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: Hoe PDF417-barcode lezen in C# – gedetailleerde gids
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hoe PDF417-barcode lezen in C# – volledige gids voor barcodelezers
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode lezen in C# – volledige barcode lezer gids

Als je **hoe PDF417-barcode te lezen** in een .NET‑applicatie nodig hebt, laat deze gids je een kant‑klaar werkende oplossing zien. Je ziet hoe je **barcode van afbeelding C#** kunt lezen met een populaire barcode‑bibliotheek en elk Macro PDF417‑attribuut krijgt zonder extra gereedschap.

De tutorial behandelt alles wat nodig is voor een **C# barcode reader example**: projectconfiguratie, code‑uitleg en tips voor het omgaan met randgevallen. Aan het einde kun je de code in een console‑project plakken en direct PDF417‑afbeeldingen decoderen.

## Wat je nodig hebt

Controleer vóór je begint de volgende vereisten:

| Voorwaarde | Reden |
|------------|-------|
| .NET 6.0 SDK or later | Levert de runtime voor de C# console‑app |
| Visual Studio 2022 (or any C# IDE) | Maakt eenvoudige projectcreatie en debugging mogelijk |
| Aspose.BarCode for .NET (NuGet package) | Levert de `BarCodeReader`‑ en `DecodeType`‑klassen |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | Dient als invoer voor decodering |

You can install the library with the dotnet CLI:

```bash
dotnet add package Aspose.BarCode
```

## Hoe PDF417-barcode lezen van een afbeelding in C#

De kern van de **read barcode from image C#** workflow bestaat uit drie acties:

1. Initialiseer de `BarCodeReader` voor het specifieke `DecodeType`.
2. Itereer door de geretourneerde `BarCodeResult`‑collectie.
3. Toegang tot zowel basis‑ als uitgebreide PDF417‑velden.

Hieronder staat de volledige, uitvoerbare code. Sla deze op als `Program.cs` in een console‑project.

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Uitleg van elke stap

* **Step 1 – Initialise the reader**  
  De `BarCodeReader`‑constructor ontvangt het pad naar het afbeeldingsbestand en een `DecodeType`. `DecodeType.MacroPdf417` vertelt de bibliotheek om te zoeken naar Macro PDF417‑symbolen, die extra metadata bevatten boven gewone PDF417‑barcodes.

* **Step 2 – ReadBarCodes()**  
  Deze methode retourneert een `IEnumerable<BarCodeResult>` die meerdere barcodes kan bevatten als de afbeelding er meer dan één bevat. De `foreach`‑lus garandeert dat elk gedetecteerd symbool wordt verwerkt.

* **Step 3 – Basic information**  
  `CodeTypeName` identificeert het barcode‑formaat (bijv. “MacroPDF417”). `CodeText` bevat de ruwe gegevensreeks die in het symbool is gecodeerd.

* **Step 4 – Extended fields**  
  Macro PDF417 voegt een reeks uitgebreide eigenschappen toe onder `barcodeResult.Extended.Pdf417`. Deze velden tonen bestands‑niveau gegevens zoals `FileID`, `SegmentID` en `FileName`. Directe toegang maakt het mogelijk om multi‑segment documenten opnieuw op te bouwen of de integriteit te verifiëren.

#### Verwachte console‑output

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

De exacte waarden weerspiegelen de inhoud die is gecodeerd in je `MacroPdf417.png`. Als de afbeelding één segment bevat, zal `SegmentsCount` 1 zijn en `SegmentID` 0.

## Stel de C# barcode lezer omgeving in

Een betrouwbare **C# barcode reader example** hangt af van een schone projectconfiguratie:

1. **Maak een nieuw console‑project**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **Voeg het Aspose.BarCode‑pakket toe** (zoals eerder getoond).
3. **Kopieer het afbeeldingsbestand** naar de projectmap of verwijs ernaar met een absoluut pad.
4. **Bouw en voer uit**  
   ```bash
   dotnet run
   ```

Als de build faalt met een ontbrekende referentiefout, controleer dan of de `using Aspose.BarCode;`‑verklaringen overeenkomen met de geïnstalleerde pakketversie. De API van de bibliotheek is stabiel over .NET 6 en .NET 8, zodat je de runtime kunt upgraden zonder code‑wijzigingen.

## Decodeer de Macro PDF417‑barcode

Wanneer je `ReadBarCodes()` aanroept, voert de bibliotheek intern het volgende uit:

* **Image preprocessing** – converteert de bitmap naar een binaire matrix, corrigeert rotatie en ruis.
* **Pattern detection** – scant naar PDF417 start/stop‑patronen en extraheert de module‑breedte.
* **Error correction** – past Reed‑Solomon‑codes toe om beschadigde codewoorden te herstellen.
* **Macro extraction** – parseert de uitgebreide PDF417‑segmentheader en vult het `Extended.Pdf417`‑object.

Het begrijpen van deze pijplijn helpt je te bepalen wanneer je decoder‑opties moet aanpassen. Bijvoorbeeld, als je afbeeldingen weinig contrast hebben, kun je de `BarCodeReader`‑eigenschap `ReadQuality` (beschikbaar in latere versies) inschakelen om de detectiegraad te verbeteren.

## Interpreteer de uitgebreide PDF417‑velden

De uitgebreide velden corresponderen direct met de Macro PDF417‑specificatie:

| Veld | Betekenis |
|------|-----------|
| `MacroPdf417FileID` | Unieke identifier voor het volledige bestand over alle segmenten heen |
| `MacroPdf417SegmentID` | Nul‑gebaseerde index van het huidige segment |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten waaruit het bestand bestaat |
| `MacroPdf417FileName` | Originele bestandsnaam opgeslagen tijdens codering |
| `MacroPdf417Checksum` | 16‑bit checksum voor integriteitsverificatie |
| `MacroPdf417FileSize` | Grootte van het originele bestand in bytes |
| `MacroPdf417TimeStamp` | UTC‑tijdstempel toen de barcode werd gegenereerd |
| `MacroPdf417Addressee` | Beoogde ontvanger van het document |
| `MacroPdf417Sender` | Afzender van het document |
| `MacroPdf417Terminator` | Letterlijke string “END” die het laatste segment markeert |

Je kunt deze waarden gebruiken om een multi‑segment PDF te reconstrueren, te verifiëren dat er geen segment ontbreekt, of audit‑informatie te loggen voor nalevingsdoeleinden.

## Veelvoorkomende valkuilen en probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Geen output verschijnt | Afbeeldingspad onjuist of niet‑ondersteund formaat | Gebruik een absoluut pad en zorg dat het bestand een PNG/JPEG is die door Aspose.BarCode wordt ondersteund |
| `CodeType` shows “PDF417” instead of “MacroPDF417” | Afbeelding bevat een regulier PDF417‑symbool, geen macro‑variant | Controleer of de bron‑barcode is gecodeerd met Macro PDF417‑extensies |
| Some fields are empty | De barcode is gegenereerd zonder die macro‑velden | Codeer de barcode met een volledige macro‑payload, of behandel null‑waarden in de code |
| Decoder throws `ArgumentException` | Verkeerde `DecodeType` opgegeven | Verander `DecodeType.MacroPdf417` naar `DecodeType.Pdf417` als je alleen standaard PDF417‑gegevens nodig hebt |

**Pro tip:** Wikkel de veldtoegang in null‑controles als je niet‑macro barcodes verwacht. Het `Extended.Pdf417`‑object retourneert standaardwaarden (bijv. `0` voor numerieke velden) wanneer de gegevens ontbreken.

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## Volledige werkende voorbeeld samenvatting

Door alles samen te voegen bestaat het uiteindelijke programma uit de using‑directives, de `Main`‑methode en de vier‑stappen‑lus die eerder werd getoond. Er zijn geen extra configuratiebestanden nodig. Compileer en voer het project uit om de console‑output met alle Macro PDF417‑eigenschappen te zien.

## Conclusie

Je weet nu **hoe PDF417-barcode te lezen** in C# met een beknopt **C# barcode reader example**. De gids heeft je door de omgeving‑setup, code‑implementatie en interpretatie van elk uitgebreid Macro PDF417‑veld geleid. Met deze basis kun je barcode‑scannen integreren in voorraadsystemen, document‑beheerprocessen of mobiele back‑ends.

### Volgende

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 lezen in C# – volledige barcode lezer gids](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Hoe PDF417 decoderen in C# met een barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [Hoe PDF417-barcode afbeelding maken in C# met Macro PDF417‑opties](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}