---
category: general
date: 2026-10-28
description: Hoe PDF417-barcodes snel te decoderen in C#. Leer hoe je een barcode-afbeelding
  in C# kunt lezen met Aspose.BarCode, met een compleet, uitvoerbaar voorbeeld.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- PDF417 decoding C#
- barcode reader C#
- Aspose.BarCode example
language: nl
lastmod: 2026-10-28
og_description: Hoe PDF417-barcodes te decoderen in C# met Aspose.BarCode. Deze gids
  laat je stap voor stap zien hoe je een barcode‑afbeelding in C# leest, inclusief
  code.
og_image_alt: Screenshot of C# code that decodes a PDF417 barcode from an image
og_title: Hoe PDF417-barcodes te decoderen in C# – barcode‑afbeelding lezen C#‑tutorial
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  headline: How to decode PDF417 barcodes in C# and read barcode image C#
  type: TechArticle
- description: How to decode PDF417 barcodes in C# quickly. Learn to read barcode
    image C# using Aspose.BarCode with a complete, runnable example.
  name: How to decode PDF417 barcodes in C# and read barcode image C#
  steps:
  - name: What each line does
    text: '| Line | Explanation | |------|-------------| | `result.CodeTypeName` |
      Human‑readable name of the detected barcode type (e.g., “MacroPdf417”). | |
      `result.CodeText` | The raw data encoded in the barcode. | | `result.Extended.Pdf417.MacroPdf417FileID`
      | Identifier that ties all segments of a macro P'
  - name: Handling common edge cases
    text: '| Situation | Recommended handling | |-----------|----------------------|
      | **No barcode found** | Check `reader.ReadBarCodes().Any()` before the loop
      and display a friendly message. | | **Corrupted image** | Wrap the `BarCodeReader`
      creation in a `try/catch` block for `BarCodeException`. | | **Mult'
  - name: Next steps
    text: '* Explore other barcode formats by changing `DecodeType` (e.g., `DecodeType.QR`,
      `DecodeType.Code128`). * Combine multiple decoded segments to reconstruct the
      original document. * Use the `BarCodeGenerator` class to create test PDF417
      barcodes on the fly.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Hoe PDF417-barcodes te decoderen in C# en barcode‑afbeelding te lezen in C#
url: /nl/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcodes te decoderen in C# en barcode‑afbeelding lezen C#

Als je **how to decode pdf417** in een .NET‑applicatie nodig hebt, biedt deze gids een kant‑klaar werkende oplossing. Je ziet precies hoe je **read barcode image c#** kunt gebruiken met de Aspose.BarCode‑bibliotheek, macro‑PDF417‑velden kunt extraheren en ze in de console kunt weergeven.

Het decoderen van PDF417-barcodes komt vaak voor in logistiek, ticketing en identiteits‑verificatiesystemen. Aan het einde van deze tutorial kun je elke afbeelding die een Macro PDF417‑barcode bevat laden, decoderen en toegang krijgen tot de bestands‑ID, segment‑ID en segment‑aantal‑waarden die essentieel zijn voor het samenstellen van multi‑segment documenten.

## Vereisten

* .NET 6.0 SDK of later geïnstalleerd  
* Visual Studio 2022 (of een andere C#‑IDE)  
* Een Aspose.BarCode for .NET NuGet‑pakket (`Aspose.BarCode`)  
* Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (het voorbeeld gebruikt `ExtPDF417Meta.png`)

Je kunt het NuGet‑pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Het project opzetten en namespaces importeren

Maak een nieuw console‑project aan en importeer de benodigde namespaces. De `using`‑directieven geven je toegang tot `BarCodeReader`, `DecodeType` en de result‑extension objecten.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

> **Waarom deze stap belangrijk is** – Het importeren van de juiste namespaces voorkomt compile‑time fouten en maakt de API‑functionaliteit beschikbaar voor de daaropvolgende decodering‑logica.

## Stap 2: Het afbeeldingspad opgeven

Definieer het volledige of relatieve pad naar de barcode‑afbeelding. Het pad in een variabele bewaren maakt de code herbruikbaar voor verschillende afbeeldingen.

```csharp
// Step 2: Specify the path to the image that contains a Macro PDF417 barcode
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

> **Tip:** Gebruik `Path.Combine` als je het pad uit meerdere delen samenstelt; het behandelt map‑scheidingstekens op verschillende besturingssystemen.

## Stap 3: Een `BarCodeReader` maken geconfigureerd voor Macro PDF417‑decodering

Instantieer `BarCodeReader` met het afbeeldingspad en de `DecodeType.MacroPdf417`‑vlag. Hiermee geef je de bibliotheek aan specifiek naar Macro PDF417‑symbolen te zoeken.

```csharp
// Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
```

> **Waarom deze stap belangrijk is** – Het kiezen van de juiste `DecodeType` verbetert de prestaties omdat de engine ongewenste barcode‑formaten overslaat.

## Stap 4: Lees alle barcodes en toon macro‑informatie

Loop door elk `BarCodeResult` dat wordt geretourneerd door `reader.ReadBarCodes()`. Het result‑object bevat zowel generieke velden (`CodeTypeName`, `CodeText`) als Macro PDF417‑specifieke extensies (`MacroPdf417FileID`, `MacroPdf417SegmentID`, `MacroPdf417SegmentsCount`).

```csharp
    // Step 4: Read all barcodes in the image and display the most relevant macro information
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Code Type : {result.CodeTypeName}");
        Console.WriteLine($"Code Text : {result.CodeText}");

        // Macro PDF417 specific fields
        Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
    }
}
```

### Wat elke regel doet

| Regel | Uitleg |
|------|-------------|
| `result.CodeTypeName` | Menselijke leesbare naam van het gedetecteerde barcode‑type (bijv. “MacroPdf417”). |
| `result.CodeText` | De ruwe data die in de barcode is gecodeerd. |
| `result.Extended.Pdf417.MacroPdf417FileID` | Identifier die alle segmenten van een macro PDF417‑document met elkaar verbindt. |
| `result.Extended.Pdf417.MacroPdf417SegmentID` | Index van het huidige segment binnen het volledige document. |
| `result.Extended.Pdf417.MacroPdf417SegmentsCount` | Totaal aantal verwachte segmenten voor het document. |

> **Pro tip:** Sla de macro‑velden op in een database als je later het volledige document moet reconstrueren. De `File ID` stelt je in staat segmenten die tot dezelfde bron behoren te groeperen.

## Stap 5: Voer het programma uit en controleer de output

Bouw en voer de console‑applicatie uit:

```bash
dotnet run
```

Typische console‑output ziet er als volgt uit:

```
Code Type : MacroPdf417
Code Text : 0123456789ABCD
File ID   : 101
Segment ID: 1
Segments  : 3
```

Als de afbeelding meerdere Macro PDF417‑symbolen bevat, print de lus elk symbool opeenvolgend.

### Veelvoorkomende randgevallen afhandelen

| Situatie | Aanbevolen afhandeling |
|-----------|----------------------|
| **Geen barcode gevonden** | Controleer `reader.ReadBarCodes().Any()` vóór de lus en toon een vriendelijke melding. |
| **Beschadigde afbeelding** | Plaats de creatie van `BarCodeReader` in een `try/catch`‑blok voor `BarCodeException`. |
| **Meerdere barcode‑formaten** | Gebruik `DecodeType.AllSupported` en filter de resultaten op `result.CodeTypeName == "MacroPdf417"`. |
| **Grote afbeeldingen** | Schaal de afbeelding naar beneden vóór het decoderen om de prestaties te verbeteren; de bibliotheek accepteert een `Bitmap`‑object. |

## Volledige broncode

Hieronder staat het volledige, zelfstandige programma. Kopieer het naar `Program.cs` van een nieuw console‑project en vervang `YOUR_DIRECTORY/ExtPDF417Meta.png` door het daadwerkelijke pad naar jouw afbeelding.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Specify the path to the image that contains a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 3: Create a BarCodeReader configured for MacroPdf417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Step 4: Read all barcodes in the image and display the most relevant macro information
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific fields
                    Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments  : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                }
            }
        }
    }
}
```

## Conclusie

Je weet nu **how to decode pdf417** barcodes in C# en hoe je **read barcode image c#** kunt gebruiken met Aspose.BarCode. De tutorial heeft je stap voor stap door projectconfiguratie, het laden van afbeeldingen, reader‑configuratie, result‑extractie en afhandeling van randgevallen geleid. Met deze basis kun je PDF417‑decodering integreren in voorraad‑systemen, ticket‑validators of elke workflow die afhankelijk is van macro‑gecodeerde data.

### Volgende stappen

* Ontdek andere barcode‑formaten door `DecodeType` te wijzigen (bijv. `DecodeType.QR`, `DecodeType.Code128`).  
* Combineer meerdere gedecodeerde segmenten om het originele document te reconstrueren.  
* Gebruik de `BarCodeGenerator`‑klasse om test‑PDF417‑barcodes on‑the‑fly te maken.  

Voel je vrij om te experimenteren met verschillende afbeeldingsbronnen, de console‑output aan te passen, of de decodering‑logica in een web‑API te integreren voor realtime verwerking. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to decode PDF417 in C# with a barcode reader example](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [How to generate PDF417 barcodes in C# with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}