---
category: general
date: 2026-11-20
description: Leer hoe je een macro‑PDF417‑barcode maakt in C# met Aspose.BarCode.
  Deze gids behandelt metadata, parameters en het opslaan van de afbeelding.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: nl
lastmod: 2026-11-20
og_description: Maak een macro PDF417-barcode in C# met Aspose.BarCode. Volg deze
  volledige tutorial om metadata in te stellen, parameters te configureren en een
  PNG te exporteren.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Macro PDF417‑barcode maken in C# – stapsgewijze handleiding
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Hoe een macro‑PDF417‑barcode te maken met Aspose.BarCode in C#
url: /nl/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe macro PDF417 barcode te maken met Aspose.BarCode in C#

Als je een **macro PDF417 barcode** moet maken in een .NET‑applicatie, laat deze tutorial de exacte stappen zien. Je ziet hoe je macro‑specifieke metadata configureert, visuele instellingen aanpast en het resultaat opslaat als een PNG‑bestand.

Het genereren van een macro PDF417 barcode is handig wanneer je een grote dataset over meerdere symbolen wilt verdelen terwijl je een bestand‑brede identifier behoudt. In het onderstaande voorbeeld gebruiken we de Aspose.BarCode‑bibliotheek, die een vloeiende API biedt voor alle PDF417‑functies.

Aan het einde van deze gids heb je een kant‑en‑klaar console‑programma dat een barcode‑afbeelding genereert met volledige macro‑informatie.

## Prerequisites

Before you start, make sure you have:

* .NET 6.0 SDK of later geïnstalleerd.
* Visual Studio 2022 (of een IDE die C# ondersteunt).
* Het **Aspose.BarCode for .NET** NuGet‑pakket (`Aspose.BarCode`).

Je kunt het pakket toevoegen met het volgende commando:

```bash
dotnet add package Aspose.BarCode
```

## Stap 1: Initialiseert de barcode‑generator voor macro PDF417

De eerste stap is om een `BarcodeGenerator` te instantieren met de enum‑waarde `EncodeTypes.MacroPdf417`. Hiermee vertelt u de bibliotheek de barcode als een macro PDF417‑symbool te behandelen.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Waarom dit belangrijk is*: Het selecteren van `MacroPdf417` schakelt alle macro‑gerelateerde eigenschappen in op het `Pdf417`‑parameterobject.

## Stap 2: Basis‑visuele weergave instellen

Een leesbare barcode begint met een geschikte module‑grootte en kolomaantal. De eigenschap `XDimension.Pixels` bepaalt de breedte van één module, terwijl `Pdf417.Columns` aangeeft hoeveel datakolommen elke rij bevat.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Het aanpassen van deze waarden beïnvloedt zowel de betrouwbaarheid van de scanner als de afbeeldingsgrootte.

## Stap 3: Macro‑bestand‑identificatiedetails definiëren

Macro PDF417 vereist een bestand‑identifier, een segment‑identifier en het totale aantal segmenten. Deze drie velden stellen een scanner in staat om de oorspronkelijke dataset opnieuw samen te stellen.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Deze **macro PDF417‑parameters** vormen de kern van de macro‑functionaliteit. Zonder hen kan een scanner de symbolen niet aan elkaar koppelen.

## Stap 4: Optionele macro‑metadata toevoegen

Naast de verplichte identifiers ondersteunt het macro‑formaat extra velden zoals checksum, bestandsgrootte, tijdstempel, geadresseerde, afzender en een terminator‑vlag. Het leveren van deze gegevens verbetert foutdetectie en biedt context voor downstream‑systemen.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Pro tip*: Als je workflow een bepaald veld niet nodig heeft, kun je het op de standaardwaarde laten staan. De bibliotheek zal het overeenkomstige data‑element uit de barcode weglaten.

## Stap 5: De barcode‑afbeelding opslaan

Na het configureren van alle parameters roep je `Save` aan om de barcode te exporteren. Het voorbeeld slaat het PNG‑bestand op in een door de gebruiker opgegeven map.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Wanneer het programma eindigt, bevat `ExtPDF417Meta.png` een macro PDF417 barcode die de tekst `"Åspóse.Barcóde©"` codeert samen met alle macro‑metadata.

## Volledige broncode

Hieronder staat het volledige, zelfstandige programma. Kopieer het naar een nieuw console‑project en voer het uit na het installeren van het Aspose.BarCode NuGet‑pakket.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Verwachte output

Het uitvoeren van het programma print een bevestigingsregel die lijkt op:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Het openen van het PNG‑bestand toont een dichte, hoog‑contrast barcode. Het scannen ervan met een PDF417‑compatibele scanner geeft de oorspronkelijke tekst terug plus alle macro‑velden.

## Veelgestelde vragen en randgevallen

### Wat als ik meer dan 20 segmenten nodig heb?

De eigenschap `MacroPdf417SegmentsCount` kan worden ingesteld tot `255`. Zorg ervoor dat het ontvangende systeem het grotere aantal segmenten aankan, en overweeg de data te splitsen in een beheersbaar aantal symbolen.

### Hoe beïnvloedt de checksum het scannen?

De CCITT‑16 checksum (`MacroPdf417Checksum`) biedt een extra fout‑detectielaag. Als een scanner een mismatch detecteert, zal hij de barcode weigeren. Je kunt de checksum weglaten als je workflow deze niet vereist.

### Kan ik een PDF417 macro barcode genereren zonder Aspose?

Ja, andere bibliotheken (bijv. ZXing.Net, Dynamsoft) ondersteunen PDF417, maar macro‑specifieke velden ontbreken vaak. Aspose.BarCode biedt de meest volledige implementatie voor macro‑metadata.

### Welke afbeeldingsformaten worden ondersteund voor opslaan?

De `Save`‑methode accepteert elk formaat dat is gedefinieerd in `BarCodeImageFormat`, zoals `Png`, `Jpeg`, `Gif`, `Bmp` en `Tiff`. Kies een formaat dat past bij je downstream‑verwerkingspipeline.

## Conclusie

Je weet nu hoe je een **macro PDF417 barcode** kunt maken in C# met Aspose.BarCode. De tutorial behandelde generator‑initialisatie, visuele instellingen, macro‑bestand‑identifiers, optionele metadata en het exporteren van de afbeelding. Met deze basis kun je macro‑PDF's in voorraadsystemen, documenttracking of elke situatie die gesegmenteerde datatransmissie vereist, embedden.

Volgende stappen omvatten experimenteren met verschillende `XDimension`‑waarden voor hogere resolutie, het toevoegen van fout‑correctieniveau‑aanpassingen, of het integreren van de barcode in een web‑API die de PNG‑stream direct retourneert. Voor gerelateerde onderwerpen, zie tutorials over **barcode generator example**, **PDF417 macro parameters**, en **macro PDF417 metadata** handling.

Veel programmeerplezier!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 barcode‑afbeelding te maken in C# met Macro PDF417‑opties](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Barcode lezen van afbeelding C# – volledige gids met Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Hoe PDF417 Barcode te maken met Aspose – Complete stap‑voor‑stap gids](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}