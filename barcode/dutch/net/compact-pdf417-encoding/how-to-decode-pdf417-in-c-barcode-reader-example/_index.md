---
category: general
date: 2026-09-26
description: Leer hoe je PDF417 decodeert in C# met een stap‑voor‑stap barcodelezer‑voorbeeld.
  Deze gids laat zien hoe je een barcode‑afbeelding leest in C# met behulp van Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: nl
lastmod: 2026-09-26
og_description: Hoe PDF417 snel te decoderen in C#. Volg dit barcodelezer‑voorbeeld
  om een barcode‑afbeelding te lezen met C# en Aspose.BarCode en macro‑details te
  extraheren.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Hoe PDF417 te decoderen in C# – volledige gids voor barcodelezers
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Hoe PDF417 te decoderen in C# – barcodelezer voorbeeld
url: /nl/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 decoderen in C# – barcode‑lezer voorbeeld

Als je **hoe PDF417 te decoderen** in een .NET‑applicatie nodig hebt, biedt deze tutorial een complete, kant‑klaar werkende oplossing. Je ziet hoe je een barcode‑afbeelding in C# leest met de Aspose.BarCode‑bibliotheek, de uitgebreide PDF417‑macro‑informatie ophaalt en elk relevant veld weergeeft.

PDF417 decoderen is niet beperkt tot platte tekst; het formaat kan bestandssegmentatie‑data, tijdstempels en controlesommen bevatten. Deze gids leidt je stap voor stap door het proces, legt uit waarom de code op deze manier is opgebouwd en belicht veelvoorkomende valkuilen die je kunt tegenkomen bij het implementeren van een C# barcode‑lezer voorbeeld.

## Vereisten

Zorg er voordat je begint voor dat je het volgende hebt:

* .NET 6.0 (of later) SDK geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑compatibele IDE)  
* **Aspose.BarCode for .NET** NuGet‑pakket (`Aspose.BarCode`)  
* Een voorbeeld Macro PDF417‑afbeelding (bijv. `ExtPDF417Meta.png`)

Deze vereisten zorgen ervoor dat de code compileert en draait zonder extra configuratie.

## Stap 1: Installeer het Aspose.BarCode NuGet‑pakket

De eerste stap in elk **read barcode image C#**‑project is het toevoegen van de barcode‑bibliotheek. Open de terminal in je solution‑map en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket levert `BarCodeReader`, `DecodeType` en de `Extended`‑eigenschap die wordt gebruikt om macro‑data te benaderen. Eenmalig installeren maakt de klassen beschikbaar in je hele project.

## Stap 2: Maak een barcode‑lezer voor een Macro PDF417‑afbeelding

Nu kun je `BarCodeReader` instantieren met het pad naar de afbeelding en `DecodeType.MacroPdf417` opgeven. Dit vertelt de bibliotheek om te zoeken naar het uitgebreide PDF417‑formaat dat macro‑informatie bevat.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Waarom dit belangrijk is:**  
`DecodeType.MacroPdf417` activeert de macro‑specifieke parser. Als je dit weglaat, geeft de lezer alleen de platte tekstpayload terug en negeert de macro‑velden die je waarschijnlijk nodig hebt voor bestandsreconstructie.

## Stap 3: Lees alle barcodes in de afbeelding

Een enkele afbeelding kan meerdere PDF417‑symbolen bevatten, vooral wanneer de data over segmenten is verdeeld. Door te itereren over `ReadBarCodes()` zorg je dat je elk segment vastlegt.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Waarom lus:**  
PDF417‑macro‑data verschijnt vaak in meerdere segmenten. Het verwerken van elk `BarCodeResult` zorgt ervoor dat je de volledige set macro‑velden verzamelt, zoals `MacroPdf417FileID` en `MacroPdf417SegmentsCount`.

## Stap 4: Haal de basis‑barcode‑gegevens op en toon ze

Het `BarCodeResult`‑object bevat het type en de gedecodeerde tekst. Het weergeven van deze waarden helpt te verifiëren dat de lezer het symbool correct heeft geïdentificeerd voordat je de macro‑details onderzoekt.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Tip:** Als `CodeText` leeg is, kan de afbeelding beschadigd zijn of is de decodeermodus onjuist. Controleer de gebruikte `DecodeType` tijdens de initialisatie.

## Stap 5: Extraheer de uitgebreide PDF417‑macro‑informatie

De macro‑data bevindt zich onder `barcodeResult.Extended.Pdf417`. Elke eigenschap correspondeert met een veld dat is gedefinieerd in de PDF417‑specificatie.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Wat elk veld betekent**

| Eigenschap | Beschrijving |
|------------|--------------|
| `MacroPdf417FileID` | Identifier die alle segmenten groepeert die tot hetzelfde logische bestand behoren. |
| `MacroPdf417SegmentID` | Index van het huidige segment (beginnend bij 1). |
| `MacroPdf417SegmentsCount` | Totaal aantal segmenten dat nodig is om het originele bestand te reconstrueren. |
| `MacroPdf417FileName` | Optionele bestandsnaam ingebed in de macro. |
| `MacroPdf417Checksum` | CRC‑16‑controlesom voor integriteitsverificatie. |
| `MacroPdf417FileSize` | Verwachte grootte van het gereconstrueerde bestand (in bytes). |
| `MacroPdf417TimeStamp` | Datum‑tijd waarop de macro is gegenereerd. |
| `MacroPdf417Addressee` | Optionele ontvanger‑identifier. |
| `MacroPdf417Sender` | Optionele afzender‑identifier. |
| `MacroPdf417Terminator` | Terminator‑vlag; moet `true` zijn bij het laatste segment. |

Het begrijpen van deze velden stelt je in staat het originele bestand te herbouwen, de dataintegriteit te valideren en aangepaste bedrijfslogica te implementeren (bijv. verouderde documenten afwijzen).

## Stap 6: Verwerk meerdere segmenten en herstel het originele bestand (geavanceerd)

Wanneer `MacroPdf417SegmentsCount` groter is dan 1, moet je elk segment verzamelen, sorteren op `MacroPdf417SegmentID` en de `CodeText`‑waarden samenvoegen. Hieronder vind je een beknopte implementatie:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Waarom dit belangrijk is:**  
Zonder sortering en concatenatie zou de gedecodeerde data onvolledig of vervormd zijn. De snippet toont ook defensief programmeren door het segment‑aantal te controleren.

## Stap 7: Rond af met foutafhandeling en best practices

Een productie‑klare **c# barcode reader example** moet rekening houden met IO‑fouten, niet‑ondersteunde formaten en beschadigde afbeeldingen.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Checklist best practices**

* Valideer het afbeeldingspad voordat je `BarCodeReader` maakt.  
* Gebruik `using`‑statements om de vrijgave van unmanaged resources te garanderen.  
* Log macro‑velden voor audit‑trails — vooral `MacroPdf417Checksum` en `MacroPdf417TimeStamp`.  
* Bij het verwerken van grote bestanden, overweeg om de samengevoegde payload te streamen naar schijf in plaats van volledig in het geheugen te houden.

## Verwachte output

Het uitvoeren van het volledige programma tegen een geldige `ExtPDF417Meta.png` levert output vergelijkbaar met:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Als alle drie de segmenten aanwezig zijn, print het reconstructie‑blok de volledige payload na het verificatie‑bericht.

## Conclusie

Je weet nu **hoe PDF417 te decoderen** in C# met een robuust barcode‑lezer voorbeeld. De tutorial besprak het installeren van Aspose.BarCode, het initialiseren van een `BarCodeReader` voor Macro PDF417, het itereren over meerdere barcodes, het extraheren van macro‑velden, het herbouwen van gesegmenteerde data en het implementeren van foutafhandeling.  

Vanaf hier kun je:

* De lezer integreren in een web‑API die geüploade afbeeldingen accepteert.  
* Macro‑metadata opslaan in een database voor auditdoeleinden.  
* De oplossing uitbreiden naar andere 2‑D‑symbologieën door `DecodeType` te wijzigen (e

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 lezen in C# – Volledig barcode‑lezer voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hoe PDF417‑barcode maken met Aspose – Complete stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [PDF417‑barcode lezen in C# – barcode‑lezer voorbeeld](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}