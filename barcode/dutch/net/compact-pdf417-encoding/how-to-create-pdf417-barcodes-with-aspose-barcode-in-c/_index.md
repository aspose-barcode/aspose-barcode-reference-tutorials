---
category: general
date: 2026-11-17
description: Hoe PDF417‑barcodes te maken met Aspose.BarCode – stapsgewijze handleiding
  die ook laat zien hoe je een barcode maakt met Aspose in C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: nl
lastmod: 2026-11-17
og_description: Hoe PDF417-barcodes te maken met Aspose.BarCode. Deze tutorial leidt
  je door de exacte stappen om een barcode met Aspose te maken, Macro PDF417-metadata
  te configureren en de afbeelding op te slaan.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Hoe PDF417-barcodes te maken met Aspose.BarCode – volledige C#-gids
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Hoe PDF417-barcodes te maken met Aspose.BarCode in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcodes te maken met Aspose.BarCode in C#

Als je **PDF417** barcodes moet maken voor voorraad, verzending of documenttracking, laat deze gids je de exacte stappen zien met Aspose.BarCode. Je ziet hoe je een barcode maakt met Aspose, Macro PDF417‑velden configureert en het resultaat exporteert als een PNG‑afbeelding — alles in één uitvoerbaar C#‑programma.

Het maken van een PDF417 barcode is gebruikelijk wanneer je grote hoeveelheden data moet coderen in een compact, machinaal leesbaar formaat. Aspose.BarCode maakt het proces eenvoudig, zodat je dimensies, kolommen en de volledige Macro PDF417‑metadata kunt afstemmen. Aan het einde van deze tutorial heb je een compleet, zelfstandig voorbeeld dat je in elk .NET‑project kunt gebruiken.

## Vereisten

Voordat je begint, zorg dat je het volgende hebt:

* .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+).
* Een geldige Aspose.BarCode for .NET‑licentie (de gratis evaluatie werkt voor testen).
* Visual Studio 2022, VS Code, of een andere C#‑compatibele IDE.
* Basiskennis van C#‑syntaxis en de `using`‑statement.

> **Pro tip:** Als je het voorbeeld zonder licentie uitvoert, voegt Aspose een klein watermerk toe aan de gegenereerde afbeelding.

## Hoe een PDF417 barcode te maken met Aspose.BarCode

De volgende secties splitsen de implementatie op in vier duidelijke stappen. Elke stap bevat een code‑fragment, een uitleg **waarom** de code nodig is, en praktische tips die je op je eigen projecten kunt toepassen.

### Stap 1: Het project opzetten en Aspose.BarCode importeren

Maak een nieuw console‑project aan en voeg het Aspose.BarCode NuGet‑pakket toe:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Open vervolgens `Program.cs` en voeg de benodigde namespaces toe:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

**Waarom dit belangrijk is:** Het importeren van `Aspose.BarCode.Generation` geeft je toegang tot `BarcodeGenerator` en de `EncodeTypes`‑enumeratie, die de kernklassen zijn voor het maken van barcodes.

### Stap 2: Initialiseert de `BarcodeGenerator` voor Macro PDF417

De constructor van `BarcodeGenerator` neemt het barcode‑type en de tekst die je wilt coderen. Voor Macro PDF417 gebruik je `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

**Waarom dit belangrijk is:** De `using`‑statement zorgt ervoor dat onbeheerde resources (zoals GDI+‑handles) direct worden vrijgegeven, waardoor geheugenlekken in langdurige services worden voorkomen.

### Stap 3: Configureer uiterlijk en Macro PDF417‑metadata

#### 3.1 Pas visuele parameters aan

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Vul Macro PDF417‑velden in

Macro PDF417 stelt je in staat een groot document op te splitsen in meerdere barcode‑segmenten. De onderstaande velden zijn optioneel maar vaak vereist voor logistieke of documentbeheersystemen.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

**Waarom deze velden nuttig zijn:**  
* **FileID** koppelt alle segmenten aan elkaar, waardoor reconstructie mogelijk is.  
* **SegmentID** en **SegmentsCount** laten de scanner de volgorde weten en wanneer de reeks compleet is.  
* **Checksum** en **FileSize** bieden snelle integriteitscontroles zonder de volledige payload te decoderen.

> **Let op:** De `MacroPdf417FileID` moet uniek zijn per logisch document. Het hergebruiken van dezelfde ID voor niet‑gerelateerde bestanden kan reconstructiefouten veroorzaken.

### Stap 4: Sla de barcode‑afbeelding op

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

**Waarom PNG?** PNG behoudt de exacte pixelgegevens zonder compressie‑artefacten, wat ideaal is voor barcodescanners die afhankelijk zijn van scherpe randen.

### Volledig, uitvoerbaar voorbeeld

Alles bij elkaar, hier is het complete programma dat je direct kunt compileren en uitvoeren:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Verwachte output:** Na het uitvoeren van het programma vind je `MacroPdf417.png` in de projectmap. Het openen van de afbeelding toont een dichte, hoog‑contrast PDF417 barcode die “Sample text for PDF417” codeert, samen met de macro‑metadata die je hebt opgegeven.

## Veelgestelde vragen en afhandeling van randgevallen

| Vraag | Antwoord |
|----------|--------|
| *Kan ik meerdere segmenten in een lus genereren?* | Ja. Verhoog `MacroPdf417SegmentID` voor elke iteratie, houd `MacroPdf417FileID` constant, en werk `MacroPdf417SegmentsCount` pas bij nadat je het totale aantal segmenten kent. |
| *Wat als de data een enkel PDF417 symbool overschrijdt?* | Macro |

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe maak je een macro PDF417 barcode in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Hoe maak je een micro PDF417 barcode in C# met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [Hoe een Barcode – Compact PDF417 te configureren met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}