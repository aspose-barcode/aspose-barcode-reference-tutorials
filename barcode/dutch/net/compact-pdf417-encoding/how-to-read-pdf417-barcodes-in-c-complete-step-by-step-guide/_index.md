---
category: general
date: 2026-09-22
description: Leer hoe je PDF417-barcodes kunt lezen in C# met een volledig barcodelezer‑voorbeeld.
  Deze tutorial laat zien hoe je barcode‑afbeeldingen in C# snel en betrouwbaar kunt
  lezen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: nl
lastmod: 2026-09-22
og_description: Hoe PDF417-barcodes te lezen in C# met een beknopt barcodelezer-voorbeeld.
  Volg de gids om Macro PDF417-afbeeldingen te decoderen en metadata te extraheren.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Hoe PDF417-barcodes te lezen in C# – volledig barcodelezer‑voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Hoe PDF417-barcodes lezen in C# – volledige stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcodes lezen in C# – volledige stapsgewijze gids

Als je **hoe pdf417 te lezen** in een .NET‑applicatie nodig hebt, laat deze gids je de exacte code en redenering zien die je nodig hebt. Aan het einde van de eerste twee zinnen weet je hoe je een barcode‑afbeelding in C# kunt lezen met de populaire `BarCodeReader`‑klasse, en heb je een kant‑klaar voorbeeld dat elk onderdeel van de Macro PDF417‑metadata extraheert.

PDF417 barcodes lezen is een veelvoorkomende eis bij het verwerken van verzendetiketten, instapkaarten of beveiligde documenten. Deze tutorial behandelt alles, van het instellen van de lezer tot het afhandelen van randgevallen, zodat je barcode‑scannen met vertrouwen kunt integreren.

## Wat je zult bereiken

- Decodeer een Macro PDF417‑afbeeldingsbestand.
- Print basisbarcode‑informatie (type en tekst).
- Toegang tot alle uitgebreide Macro PDF417‑velden zoals bestand‑ID, segment‑aantal en tijdstempel.
- Begrijp veelvoorkomende valkuilen bij het werken met multi‑segment PDF417‑codes.

**Prerequisites**

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+).
- Een referentie naar de barcode‑SDK die `BarCodeReader`, `DecodeType` en `BarCodeResult` levert (bijv. Aspose.BarCode, Dynamsoft, of elke bibliotheek die dezelfde API exposeert).
- Een afbeeldingsbestand (`ExtPDF417Meta.png`) dat een Macro PDF417‑barcode bevat.

> **Pro tip:** Plaats de afbeelding in een map relatief ten opzichte van de project‑root en stel de eigenschap **Copy to Output Directory** in op *Copy if newer* zodat het pad werkt tijdens het debuggen.

![Hoe PDF417 barcode lezen met C#](https://example.com/placeholder-image.png)

## Hoe PDF417 barcode lezen in C# – de volledige code

Hieronder staat een zelfstandige programma‑snippet die je in een console‑applicatie kunt plakken. Het maakt een barcode‑lezer aan, doorloopt elk gedecodeerd resultaat en print zowel standaard‑ als uitgebreide Macro PDF417‑velden.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
}
```

### Waarom elke stap belangrijk is

1. **De lezer maken met `DecodeType.MacroPdf417`** – Macro PDF417 is een speciale variant die metadata op bestandsniveau kan dragen. Het specificeren van het decodeertype zorgt ervoor dat de SDK die extra velden parseert in plaats van de code te behandelen als een gewone PDF417.
2. **Itereren over `ReadBarCodes()`** – Een afbeelding kan meer dan één barcode bevatten (bijv. een QR‑code naast een PDF417). De lus garandeert dat je elk resultaat vastlegt.
3. **Printen van `CodeTypeName` en `CodeText`** – Dit zijn de meest gebruikte eigenschappen; ze geven je de symbologie‑naam en de mens‑leesbare payload.
4. **Toegang tot `Extended.Pdf417`** – Het `Extended`‑object verschijnt alleen voor PDF417‑gerelateerde decodeertypes. Elke eigenschap mappt direct naar de Macro PDF417‑specificatie, waardoor je het originele bestand kunt reconstrueren of de segmentvolgorde kunt valideren.

## Veelvoorkomende variaties en randgevallen

### Een niet‑macro PDF417 barcode lezen

Als je bron‑afbeeldingen reguliere PDF417‑codes bevatten (geen macro‑metadata), vervang dan `DecodeType.MacroPdf417` door `DecodeType.Pdf417`. De rest van de code blijft identiek, maar het `Extended.Pdf417`‑blok zal leeg zijn omdat die velden simpelweg niet bestaan.

### Multi‑segment PDF’s afhandelen

Macro PDF417 kan een groot document over meerdere barcode‑segmenten verdelen. Om het originele bestand opnieuw samen te stellen moet je:

1. Elk segment’s `Pdf417MacroSegmentID` verzamelen.
2. Segmenten sorteren op hun ID.
3. Verifiëren dat `Pdf417MacroSegmentsCount` overeenkomt met het aantal ontvangen segmenten.
4. De `CodeText` van elk segment in volgorde concatenëren.
5. Optioneel `Pdf417MacroChecksum` valideren.

Hieronder staat een beknopte snippet die de reassemblage‑logica demonstreert:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Omgaan met corrupte afbeeldingen

- **Lage contrast** – Verhoog de beeld‑preprocessing (bijv. histogram‑equalisatie) voordat je het aan `BarCodeReader` doorgeeft.
- **Rotatie** – Gebruik `barcodeReader.SetRotateAngle(90)` of schakel auto‑rotate in als de SDK dit ondersteunt.
- **Gedeeltelijke scans** – Zorg dat de beeldresolutie minimaal 300 dpi is; anders kan de SDK kleine segmenten missen.

## c# barcode reader voorbeeld – best practices

| Praktijk | Reden |
|----------|-------|
| **Dispose de lezer met `using`** | Garandeert dat native resources direct worden vrijgegeven, waardoor geheugenlekken worden voorkomen. |
| **Valideer dat `result.Extended` niet null is** | Sommige SDK’s retourneren `null` voor niet‑macro codes; controle voorkomt een `NullReferenceException`. |
| **Log de `Pdf417MacroFileID`** | Deze identifier is uniek per bestand en nuttig voor audit‑trails. |
| **Omring decodering met try/catch** | I/O‑fouten (ontbrekend bestand) of niet‑ondersteunde formaten veroorzaken uitzonderingen die netjes afgehandeld moeten worden. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Verwachte output

Het uitvoeren van het volledige programma tegen een correct geformatteerde `ExtPDF417Meta.png` levert een output vergelijkbaar met:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Bevat de afbeelding meerdere segmenten, dan print de lus de metadata van elk segment opeenvolgend.

## Conclusie

Je weet nu **hoe pdf417 te lezen** barcodes in C# en hebt een **c# barcode reader voorbeeld** dat elk Macro PDF417‑veld extraheert. De oplossing behandelt basis‑decodering, metadata‑extractie, multi‑segment reassemblage en foutafhandeling, en biedt een productie‑klare basis voor elke document‑verwerkingsworkflow.

### Volgende stappen

- Verken **read barcode image C#** technieken voor andere symbologieën (QR, DataMatrix) met dezelfde `BarCodeReader`‑API.
- Integreer de barcode‑decoder in een ASP.NET Core‑service om uploads on‑the‑fly te verwerken.
- Experimenteer met beeld‑preprocessing bibliotheken (bijv. `OpenCvSharp`) om het slagingspercentage bij lage‑kwaliteit scans te verhogen.

Happy coding, and feel free to adapt the example to fit your specific use case!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}