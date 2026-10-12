---
category: general
date: 2026-10-02
description: Leer hoe je een barcode uit een afbeelding kunt lezen in C# met een compleet
  voorbeeld dat laat zien hoe je een PDF417‑barcode decodeert met Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: nl
lastmod: 2026-10-02
og_description: Lees barcode van afbeelding c# met Aspose.BarCode. Deze tutorial legt
  uit hoe je een PDF417-barcode decodeert en uitgebreide metadata extraheert.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Barcode lezen uit afbeelding c# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcode uit een afbeelding lezen in C# met Aspose.BarCode
url: /nl/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode uit een afbeelding lezen in C# met Aspose.BarCode

Als je een **barcode uit een afbeelding c#** moet lezen, leidt deze gids je door een complete, uitvoerbare oplossing. Je leert hoe je een PDF417‑barcode decodeert, toegang krijgt tot de uitgebreide macro‑gegevens en de resultaten naar de console print.

Barcodes uit afbeeldingen lezen is een veelvoorkomende eis voor voorraad‑systemen, ticketvalidatie en documentverwerking. Deze tutorial behandelt alles wat je nodig hebt: vereiste pakketten, code‑uitleg, afhandeling van randgevallen en verwachte output. Geen externe documentatie is nodig; het voorbeeld werkt direct met Aspose.BarCode .NET.

## Vereisten

Zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE)  
* Een NuGet‑referentie naar **Aspose.BarCode** (versie 23.10 of nieuwer)  
* Een afbeeldingsbestand dat een PDF417‑barcode bevat – bijvoorbeeld `ExtPDF417Meta.png`

Als een van deze items ontbreekt, installeer dan de .NET SDK, voeg het NuGet‑pakket toe met `dotnet add package Aspose.BarCode` en plaats de afbeelding in een map die je vanuit je project kunt refereren.

## Hoe een barcode uit een afbeelding lezen in C# – stap‑voor‑stap

De volgende secties splitsen de implementatie op in logische stappen. Elke stap bevat een code‑fragment, een uitleg **waarom** de stap belangrijk is, en een tip die je kunt toepassen in real‑world projecten.

### Stap 1: Maak een `BarCodeReader` voor een PDF417‑afbeelding

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Waarom dit belangrijk is** – De constructor van `BarCodeReader` accepteert het pad naar de afbeelding en het verwachte barcode‑type. Het specificeren van `MacroPdf417` beperkt de zoekopdracht, wat de prestaties verbetert en valse positieven vermindert wanneer de afbeelding meerdere symbologieën bevat.

**Pro tip:** Als je niet zeker bent van het barcode‑type, gebruik dan `DecodeType.AllSupportedTypes` en filter de resultaten later.

### Stap 2: Itereer over alle gedetecteerde barcodes

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Waarom dit belangrijk is** – Een PDF417‑macro‑afbeelding kan verschillende segmenten bevatten. De methode `ReadBarCodes()` retourneert een collectie, zodat je elk segment afzonderlijk kunt verwerken.

**Randgeval:** Als de afbeelding geen PDF417‑symbolen bevat, is de collectie leeg en wordt de lus‑inhoud nooit uitgevoerd. Overweeg om na de lus een controle toe te voegen om de gebruiker te informeren.

### Stap 3: Toegang tot de uitgebreide PDF417‑macro‑metadata

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Waarom dit belangrijk is** – De eigenschap `Extended.Pdf417` geeft velden weer die gedefinieerd zijn in de PDF417‑specificatie, zoals bestands‑ID, segment‑ID en bestandsnaam. Deze gegevens zijn essentieel wanneer je een meer‑pagina‑document moet reconstrueren uit afzonderlijke barcode‑scans.

**Pro tip:** Controleer altijd of `barcodeResult.Extended` niet null is voordat je `Pdf417` benadert. De bibliotheek retourneert `null` voor symbologieën die geen uitgebreide gegevens ondersteunen.

### Stap 4: Print de barcode‑tekst en macro‑details

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Waarom dit belangrijk is** – De console‑output geeft je direct inzicht in zowel de gedecodeerde tekst als de macro‑metadata. Dit is nuttig voor debugging en voor verdere verwerking, zoals het opslaan van de informatie in een database.

**Verwachte output** (ervan uitgaande dat de voorbeeldafbeelding één macro‑segment bevat):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Bevat de afbeelding drie segmenten, dan print de lus drie blokken, elk met een andere `Segment ID`.

### Stap 5: Fouten afhandelen en resources opruimen

De `using`‑statement zorgt er automatisch voor dat de `BarCodeReader` wordt vrijgegeven. Je moet echter nog steeds uitzonderingen opvangen die kunnen ontstaan door ontbrekende bestanden of niet‑ondersteunde formaten:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Waarom dit belangrijk is** – Robuuste applicaties crashen niet omdat een bestand ontbreekt of de afbeelding corrupt is. Het geven van een duidelijke foutmelding helpt jou of je supportteam het probleem snel te diagnosticeren.

## Hoe een PDF417‑barcode decoderen met Aspose.BarCode

Het secundaire trefwoord **how to decode pdf417 barcode** komt hier natuurlijk voor. Het decoderen van een PDF417‑barcode volgt hetzelfde patroon als hierboven, maar je kunt de `MacroPdf417`‑vlag weglaten als je alleen de platte tekst nodig hebt:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Waarom je voor deze variant zou kiezen** – Wanneer de barcode geen macro‑informatie bevat, vermindert het gebruik van `DecodeType.Pdf417` de verwerkingsbelasting en vereenvoudigt het de resultaatsafhandeling.

**Veelgestelde vraag:** *Wat als de barcode gedraaid is?*  
Aspose.BarCode detecteert automatisch rotatie en corrigeert deze, zodat je geen extra beeld‑preprocessing code nodig hebt.

## Volledig, uitvoerbaar voorbeeld

Kopieer het volledige programma hieronder naar een nieuw console‑project (`dotnet new console`) en vervang `YOUR_DIRECTORY/ExtPDF417Meta.png` door het daadwerkelijke pad naar jouw afbeelding.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Het uitvoeren van het programma print het barcode‑type, de gedecodeerde tekst en eventuele macro‑metadata. Bevat de afbeelding geen PDF417‑macro, dan informeert het programma je op een nette manier.

## Conclusie

Je weet nu hoe je een **barcode uit een afbeelding c#** kunt lezen met Aspose.BarCode, hoe je een **PDF417‑barcode** decodeert, en hoe je de uitgebreide macro‑PDF417‑velden kunt extraheren. De oplossing omvat initialisatie, iteratie, metadata‑toegang, foutafhandeling en een variant voor gewone PDF417‑decodering.

Vanaf hier kun je:

* De geëxtraheerde gegevens opslaan in een SQL‑database voor later gebruik.  
* Meerdere segmenten combineren om het originele document te reconstrueren.  
* Andere symbologieën verkennen die door Aspose.BarCode worden ondersteund, zoals

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids zijn getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 lezen in C# – Compleet Barcode‑voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Hoe PDF417 lezen in C# – Compleet Barcode‑Reader‑voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hoe PDF417‑barcode‑afbeelding genereren in C# met Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}