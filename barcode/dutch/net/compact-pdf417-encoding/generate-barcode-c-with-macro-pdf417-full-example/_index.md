---
category: general
date: 2026-08-19
description: Genereer een barcode in C# met Aspose.BarCode om een Macro PDF417 met
  aangepaste tekst te maken en op te slaan als een afbeeldingsbestand.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: nl
lastmod: 2026-08-19
og_description: Genereer barcode C# met Aspose.BarCode, leer hoe je PDF417 genereert,
  voeg aangepaste tekst toe en sla het barcode‑afbeeldingsbestand op.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Barcode genereren C# – Macro PDF417 gids
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Barcode genereren in C# met Macro PDF417 – volledig voorbeeld
url: /nl/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode genereren C# met Macro PDF417 – volledig voorbeeld

Als je **barcode C# wilt genereren** voor een Macro PDF417‑formaat, laat deze gids je een kant‑klaar werkende oplossing zien. Je ziet hoe je **pdf417 kunt genereren**, aangepaste tekst kunt insluiten, en **barcode‑afbeeldingsbestand kunt genereren** in één zelf‑containend programma.

De tutorial behandelt alles, van het installeren van de Aspose.BarCode‑bibliotheek tot het configureren van Macro PDF417‑metadata, zodat je de code direct in je project kunt kopiëren en het resultaat meteen ziet.

## Vereisten

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 (of een IDE die C# ondersteunt)
- Een Aspose.BarCode voor .NET‑licentie (de gratis proefversie werkt voor evaluatie)
- Basiskennis van C#‑syntaxis

> **Pro tip:** Installeer het NuGet‑pakket via de CLI om versieconflicten te voorkomen:  
> `dotnet add package Aspose.BarCode`

## Stap 1: Het project opzetten en de bibliotheek importeren

Maak een nieuwe console‑applicatie aan en voeg de benodigde `using`‑directieven toe.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Waarom deze stap belangrijk is:**  
De `Aspose.BarCode.Generation`‑namespace levert de `BarcodeGenerator`‑klasse, die het startpunt is voor het maken van elk barcode‑type, inclusief Macro PDF417. Het importeren van `System` geeft je toegang tot `DateTime` voor tijdstempel‑metadata.

## Stap 2: Een Macro PDF417‑generator maken met aangepaste tekst

Vervang de tijdelijke opmerking door de generator‑initialisatie. Dit toont **barcode‑aangepaste tekst maken** terwijl je ook het juiste coderings‑type selecteert.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Uitleg:**  
- `EncodeTypes.MacroPdf417` vertelt Aspose een PDF417‑barcode te produceren die macro‑functies ondersteunt (bestandsegmentatie, controlesom, enz.).  
- De tekst `"Åspóse.Barcóde©"` laat zien dat Unicode‑tekens volledig worden ondersteund, wat vaak vereist is voor internationale toepassingen.

## Stap 3: Uiterlijk en Macro PDF417‑metadata configureren

Stel de barcode‑afmetingen nauwkeurig af en stel de macro‑specifieke velden in die nodig zijn voor het verwerken van gesegmenteerde bestanden.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Waarom deze instellingen belangrijk zijn:**

| Instelling | Doel |
|------------|------|
| `XDimension.Pixels` | Regelt de visuele dichtheid; 2 px geeft een duidelijke, scanbare afbeelding. |
| `Columns` | Bepaalt hoeveel datakolommen per rij verschijnen, wat de barcode‑grootte beïnvloedt. |
| `MacroPdf417FileID` | Identificeert het logische bestand uniek over alle segmenten. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Maakt reconstructie van het oorspronkelijke bestand mogelijk uit meerdere barcodes. |
| `MacroPdf417FileName` | Menselijk leesbare naam opgeslagen in de barcode voor verdere verwerking. |
| `MacroPdf417Checksum` | Biedt foutdetectie met het CCITT‑16 CRC‑algoritme. |
| `MacroPdf417FileSize` | Helpt de decoder te weten wanneer het volledige bestand is ontvangen. |
| `MacroPdf417TimeStamp` | Registreert wanneer de barcode is gegenereerd, nuttig voor audit‑trails. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Optionele velden die door bedrijfsprocessen kunnen worden gebruikt. |
| `MacroPdf417Terminator` | Geeft aan dat dit segment het laatste is (`Set`). |

## Stap 4: De barcode opslaan als afbeeldingsbestand

Schrijf tenslotte de barcode naar een PNG‑bestand zodat je deze kunt bekijken of elders kunt insluiten.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Wat je zult zien:**  
Een PNG‑afbeelding met de naam `ExtPDF417Meta.png` die een Macro PDF417‑barcode bevat die de aangepaste tekst en alle metadata‑velden die je hierboven hebt ingesteld codeert. De afbeelding kan worden geopend met elke standaardviewer of worden ingevoegd in PDF‑bestanden, rapporten of webpagina's.

## Volledige broncode (klaar om te kopiëren en plakken)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma geeft het volgende weer:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Het openen van `ExtPDF417Meta.png` toont een schone Macro PDF417‑barcode die correct wordt gescand met elke PDF417‑lezer, waarbij de aangepaste tekst `"Åspóse.Barcóde©"` en de macro‑metadata die je hebt gedefinieerd behouden blijven.

## Veelgestelde vragen en randgevallen

- **Kan ik een ander afbeeldingsformaat genereren?**  
  Ja. Vervang `BarCodeImageFormat.Png` door `Jpeg`, `Bmp` of `Gif` indien nodig.

- **Wat als mijn data een enkele barcode overschrijdt?**  
  Macro PDF417 is ontworpen voor segmentatie. Pas `MacroPdf417SegmentsCount` en `MacroPdf417SegmentID` voor elk deel aan, en concateneer vervolgens de gescande resultaten.

- **Is Unicode‑ondersteuning gegarandeerd?**  
  Aspose.BarCode ondersteunt Unicode volledig. Zorg ervoor dat je bronbestand is opgeslagen met UTF‑8‑codering om tekencorruptie te voorkomen.

- **Heb ik een licentie nodig voor productie?**  
  Een gelicentieerde versie verwijdert het evaluatiewatermerk en biedt volledige functionaliteit. De proefversie werkt voor testen en leren.

## Conclusie

Je weet nu hoe je **barcode C# kunt genereren** voor een Macro PDF417, **hoe je pdf417 kunt genereren** met rijke metadata, **barcode‑aangepaste tekst kunt maken**, en **barcode‑afbeeldingsbestand kunt genereren** met Aspose.BarCode. Het volledige, uitvoerbare voorbeeld toont elke benodigde stap — van projectconfiguratie tot het opslaan van de uiteindelijke PNG‑afbeelding.

### Volgende stappen

- Experimenteer met andere PDF417‑instellingen zoals `ErrorCorrectionLevel` en `CompactPdf417` voor kleinere symbolen.  
- Integreer de gegenereerde barcode in een PDF‑rapport met behulp van Aspose.PDF.  
- Verken batchgeneratie: loop over een verzameling bestanden en produceer een reeks gesegmenteerde Macro PDF417‑barcodes.

Voel je vrij de code aan te passen aan je eigen workflow, en laat de barcode‑generatie een naadloos onderdeel worden van je C#‑applicaties. Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe een Aztec‑barcode te genereren met aangepaste beeldverhouding met Aspose.BarCode voor .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Barcode‑afbeelding genereren – Code 93 met Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Hoe de barcode‑hoogte te genereren en aan te passen voor One‑Dimensional Databar met Aspose.BarCode voor .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}