---
category: general
date: 2026-09-07
description: Leer hoe je PDF417‑barcodes decodeert in C# met BarCodeReader. Deze stapsgewijze
  gids legt ook uit hoe je PDF417‑gegevens efficiënt kunt lezen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: nl
lastmod: 2026-09-07
og_description: Hoe PDF417-barcodes te decoderen in C# met BarCodeReader. Volg deze
  tutorial om te leren hoe je PDF417-gegevens leest en MacroPdf417-velden extraheert.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Hoe PDF417-barcodes te decoderen in C# – volledige gids
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Hoe PDF417-barcodes te decoderen in C# met BarCodeReader
url: /nl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodes te decoderen in C# met BarCodeReader

Als je **PDF417 wilt decoderen** in een .NET‑applicatie, leidt deze gids je door het volledige proces. Je ontdekt ook **hoe je PDF417**‑gegevens kunt lezen, zoals MacroPdf417‑bestand‑ en segment‑identifiers, allemaal met een paar regels C#.

Decoderen van PDF417 is gebruikelijk bij het werken met vervoersbewijzen, rijbewijzen of verzendlabels. Aan het einde van deze tutorial heb je een uitvoerbaar console‑programma dat elk MacroPdf417‑veld weergeeft dat door de GroupDocs.Barcode SDK wordt blootgesteld.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later (de code compileert met .NET Core en .NET Framework)
* Visual Studio 2022 of een IDE die C# ondersteunt
* Het **GroupDocs.Barcode** NuGet‑pakket (`GroupDocs.Barcode` ≥ 23.3)
* Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (bijv. `ExtPDF417Meta.png`)

> **Pro tip:** Installeer het pakket via de CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Hoe PDF417-barcodes te decoderen in C#

De volgende secties splitsen de oplossing op in logische stappen. Elke stap bevat de exacte code die je nodig hebt en een korte uitleg waarom deze belangrijk is.

### Stap 1: Bereid het project voor en importeer namespaces

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Waarom?*  
`GroupDocs.Barcode` levert de `BarCodeReader`‑klasse, terwijl `GroupDocs.Barcode.Common` de `DecodeType`‑enumeratie bevat die nodig is voor PDF417‑decodering.

### Stap 2: Definieer het afbeeldingspad

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Waarom?*  
De lezer werkt met elk door .NET ondersteund afbeeldingsformaat (`.png`, `.jpg`, `.bmp`). Het juiste pad opgeven zorgt ervoor dat de SDK het bestand kan vinden.

### Stap 3: Initialiseert de barcode‑lezer voor MacroPdf417‑decodering

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Waarom?*  
`DecodeType.MacroPdf417` vertelt de SDK om te zoeken naar het uitgebreide Macro PDF417‑formaat, dat extra metadata bevat zoals bestand‑ en segment‑IDs. Het gebruik van de `using`‑statement zorgt ervoor dat onbeheerste resources tijdig worden vrijgegeven.

### Stap 4: Lees elke barcode die in de afbeelding wordt gevonden

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Waarom?*  
Een afbeelding kan meerdere barcodes bevatten. De `ReadBarCodes()`‑methode retourneert een collectie, zodat je elke barcode afzonderlijk kunt verwerken.

### Stap 5: Haal Macro PDF417‑specifieke gegevens op en toon ze

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Waarom?*  
Het `Extended.Pdf417`‑object exposeert alle Macro PDF417‑velden die in de specificatie zijn gedefinieerd. Ze afdrukken laat je verifiëren dat de decode‑operatie geslaagd is en geeft je de gegevens die je nodig hebt voor verdere verwerking.

### Volledig uitvoerbaar voorbeeld

Combineer de bovenstaande fragmenten in één `Program.cs`‑bestand:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Verwachte console‑output** (waarden zullen verschillen afhankelijk van de barcode‑inhoud):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Als de afbeelding geen Macro PDF417‑barcode bevat, zal de `ReadBarCodes()`‑collectie leeg zijn en wordt er niets afgedrukt.

## Veelvoorkomende variaties en randgevallen

| Situatie | Hoe de code aan te passen |
|-----------|---------------------------|
| **Standaard (niet‑macro) PDF417** | Verander `DecodeType.MacroPdf417` naar `DecodeType.Pdf417`. Het `Extended.Pdf417`‑object zal `null` zijn, dus bescherm tegen null‑referenties. |
| **Meerdere afbeeldingen** | Plaats de lezerinitialisatie in een `foreach (var path in imagePaths)`‑lus. |
| **Grote afbeeldingen** | Stel `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` in om het geheugenverbruik te beperken. |
| **Prestaties‑kritieke batch** | Hergebruik één `BarCodeReader`‑instantie met `reader.SetImage(path)` in plaats van voor elk bestand een nieuw object te maken. |

## Checklist voor probleemoplossing

* **Geen output:** Controleer of `imagePath` naar een geldig bestand wijst en of de afbeelding daadwerkelijk een PDF417‑barcode bevat. |
* **Null `Extended.Pdf417`:** Je hebt waarschijnlijk `DecodeType.Pdf417` gebruikt in plaats van `MacroPdf417`. |
* **Uitzondering `FileNotFoundException`:** Zorg ervoor dat de werkmap overeenkomt met het pad of gebruik een absoluut pad. |
* **Lage confidence‑score:** Verhoog de beeldkwaliteit of pas de `reader.Options.Quality`‑instellingen aan.

## Conclusie

Je weet nu **hoe je PDF417**‑barcodes kunt decoderen in C# en **hoe je PDF417**‑metadata kunt lezen, zoals Macro‑bestand‑IDs, segment‑IDs en tijdstempels. Het volledige voorbeeld toont hoe je `BarCodeReader` initialiseert, het juiste decode‑type selecteert, over de resultaten iterereert en elk beschikbaar MacroPdf417‑veld extraheert.

Vanaf hier kun je:

* Integreer de geëxtraheerde gegevens in een logistiek‑ of ticket‑validatiesysteem.
* Breid de console‑app uit om resultaten naar een database of JSON‑bestand te schrijven.
* Verken andere barcode‑formaten die door GroupDocs.Barcode worden ondersteund (QR, DataMatrix, Code128, enz.) door de `DecodeType`‑enumeratie te wijzigen.

Veel programmeerplezier, en voel je vrij om te experimenteren met verschillende afbeeldingen en barcode‑instellingen om PDF417‑decodering onder de knie te krijgen in je .NET‑projecten!

## Wat je hierna moet leren

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 te lezen in C# – Complete stap‑voor‑stap‑gids](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Hoe PDF417 te lezen in C# – Volledig Barcode Reader‑voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hoe PDF417 Barcode te genereren – Complete programmeergids](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}