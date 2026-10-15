---
category: general
date: 2026-10-15
description: Hoe barcode‑afbeeldingen snel te lezen in C# met BarCodeReader. Leer
  meerdere barcodes te lezen en bekijk een C# barcode‑lezer voorbeeld dat werkt met
  Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: nl
lastmod: 2026-10-15
og_description: Hoe barcode te lezen in C# met BarCodeReader. Deze tutorial toont
  een volledig C# barcode-lezer voorbeeld dat meerdere barcodes verwerkt en Macro‑PDF417‑metadata
  extraheert.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Hoe lees je een barcode in C# – stap‑voor‑stap voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe barcode‑afbeeldingen te lezen in C# – volledige voorbeeldgids
url: /nl/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe barcode‑afbeeldingen lezen in C# – volledige voorbeeldgids

Als je **barcode lezen** gegevens uit een afbeelding in een .NET‑applicatie nodig hebt, biedt deze gids een kant‑klaar werkende oplossing. Je ziet een compleet **c# barcode reader example** dat werkt met Macro‑PDF417‑symbolen en **meerdere barcodes kan lezen** van één afbeelding.

Barcode‑lezen is een veelvoorkomende eis voor voorraad‑systemen, ticket‑validatie en documentverwerking. Aan het einde van deze tutorial kun je:

* De `BarCodeReader` initialiseren voor elk ondersteund formaat.  
* Basisinformatie extraheren, zoals code‑type en gedecodeerde tekst.  
* Macro‑PDF417‑specifieke metadata ophalen (bestand‑ID, segment, checksum, …).  
* Afbeeldingen verwerken die meerdere barcodes bevatten zonder extra code.

## Vereisten

Zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later geïnstalleerd.  
* Een ontwikkelomgeving (Visual Studio 2022, VS Code of Rider).  
* Het **Aspose.BarCode for .NET** NuGet‑pakket (`Aspose.BarCode`) – het levert de `BarCodeReader`‑klasse die in het voorbeeld wordt gebruikt.  
* Een afbeeldingsbestand dat een Macro‑PDF417‑barcode bevat (bijv. `MacroPdf417.png`).  

Je kunt het NuGet‑pakket installeren met de volgende opdracht:

```bash
dotnet add package Aspose.BarCode
```

## Hoe barcode lezen met BarCodeReader in C#

De kern van de oplossing bestaat uit vier beknopte stappen. Elke stap staat in een `using`‑blok om te garanderen dat onbeheerste resources direct worden vrijgegeven.

### Stap 1: Initialiseer de `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Waarom dit belangrijk is:**  
`BarCodeReader` accepteert een bestandspad en een `DecodeType`. Door `DecodeType.MacroPdf417` op te geven, vertelt je de bibliotheek alleen naar Macro‑PDF417‑symbolen te zoeken, wat de detectiesnelheid verbetert en valse positieven vermindert.

### Stap 2: Lees alle barcodes in de afbeelding

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Waarom dit belangrijk is:**  
De `ReadBarCodes()`‑methode retourneert een array die één of meerdere `BarCodeResult`‑objecten kan bevatten. Dit is het moment waarop de **read multiple barcodes**‑functionaliteit schittert – je hebt geen aparte lus nodig voor elke mogelijke barcode.

### Stap 3: Toon basisbarcode‑details

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Waarom dit belangrijk is:**  
`CodeTypeName` vertelt je welke symbologie is gedetecteerd (bijv. “MacroPDF417”), terwijl `CodeText` de gedecodeerde payload bevat. Deze twee velden worden het meest gebruikt in downstream‑logica.

### Stap 4: Haal Macro‑PDF417‑specifieke metadata op en toon deze

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Waarom dit belangrijk is:**  
Macro‑PDF417 breidt het reguliere PDF417‑formaat uit met document‑niveau metadata. Toegang tot de `Extended.Pdf417`‑eigenschap geeft je alles wat je nodig hebt om het originele bestand te reconstrueren, de integriteit te valideren of de data naar de juiste ontvanger te routeren.

### Volledig uitvoerbaar programma

Hieronder staat een zelfstandige console‑applicatie die alle vier stappen combineert. Kopieer de code naar een nieuw `.cs`‑bestand, pas `imagePath` aan en voer `dotnet run` uit.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Verwachte console‑output

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Als de afbeelding meer dan één Macro‑PDF417‑symbool bevat, print het programma een apart blok voor elke barcode, waarmee de **read multiple barcodes**‑mogelijkheid wordt gedemonstreerd zonder extra code.

## Veelvoorkomende randgevallen afhandelen

| Situatie | Wat te doen | Reden |
|-----------|------------|--------|
| **File not found** | Plaats de constructie van `BarCodeReader` in een `try/catch (FileNotFoundException)`‑blok en toon een vriendelijke melding. | Voorkomt dat de applicatie crasht en informeert de gebruiker over het ontbrekende bestand. |
| **No barcode detected** | Controleer `results.Length == 0` (zoals getoond in het volledige programma) en handel dit netjes af. | Geeft duidelijke feedback wanneer de afbeelding geen ondersteunde symbologie bevat. |
| **Different barcode type** | Verander `DecodeType.MacroPdf417` naar `DecodeType.AllSupportedTypes` of een andere specifieke enum‑waarde. | Maakt het mogelijk dezelfde codebasis te gebruiken voor QR, Code128, DataMatrix, enz., terwijl **read multiple barcodes** behouden blijft. |
| **Large images** | Stel `reader.AutoSize = true` in of schaal de afbeelding eerst naar beneden voordat je deze aan de reader geeft. | Verbetert de prestaties en vermindert geheugenbelasting op de CLR. |
| **Thread‑safe usage** | Maak per thread een aparte `BarCodeReader`‑instantie; de klasse is niet thread‑safe. | Voorkomt race‑condities in multi‑threaded scanners of webservices. |

## Pro‑tips voor productiecodel

* **Dispose early:** De `using`‑statement zorgt ervoor dat native resources (bijv. image buffers) direct worden vrijgegeven. In langdurige services, maak de reader vrij zodra je klaar bent met het verwerken van elke afbeelding.  
* **Batch processing**

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Barcode lezen vanuit afbeelding C# – volledige gids met Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Hoe een macro PDF417 barcode te maken in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hoe PDF417 te lezen in C# – compleet barcode‑lezer voorbeeld](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}