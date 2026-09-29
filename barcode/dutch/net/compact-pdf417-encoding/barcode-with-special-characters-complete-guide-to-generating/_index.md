---
category: general
date: 2026-07-27
description: De tutorial Barcode met speciale tekens laat zien hoe je PDF417‑barcodes
  genereert met Aspose. Leer stap‑voor‑stap het maken en verwerken van Unicode‑gegevens.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode with special characters
- how to generate pdf417
- create barcode with aspose
- Aspose PDF417 macro
- Unicode barcode generation
language: nl
lastmod: 2026-07-27
og_description: Barcode met speciale tekens tutorial legt uit hoe je PDF417-barcodes
  genereert met Aspose, met aandacht voor Unicode‑afhandeling en macro‑metadata.
og_image_alt: Screenshot of a PDF417 barcode containing special characters generated
  with Aspose
og_title: Barcode met speciale tekens – Genereer PDF417 met Aspose
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  headline: Barcode with Special Characters – Complete Guide to Generating PDF417
    Using Aspose
  type: TechArticle
- description: Barcode with special characters tutorial shows how to generate PDF417
    barcodes with Aspose. Learn step‑by‑step creation and handling of Unicode data.
  name: Barcode with Special Characters – Complete Guide to Generating PDF417 Using
    Aspose
  steps:
  - name: Expected Output
    text: If you open the PNG, you’ll see a rectangular barcode with a series of black
      and white bars. Scanning it with a PDF417‑compatible scanner (or a mobile app
      like “Barcode Scanner”) will return the exact text `"Åspóse.Barcóde©"` along
      with the macro metadata we set. In other words, the barcode faithful
  - name: What if my text contains emojis or non‑BMP characters?
    text: Aspose.BarCode supports full UTF‑16, so emojis work as long as the target
      scanner can decode them. Just pass the string directly; the library handles
      the encoding internally.
  - name: Do I need to set a specific character set?
    text: No. Unlike older barcode SDKs that required `CodePage` settings, Aspose
      automatically detects Unicode. However, if you target a legacy device that only
      understands ASCII, you’ll need to strip or replace special characters before
      generation.
  - name: How does this differ from a regular PDF417 barcode?
    text: The `MacroPdf417` variant adds extra fields (file ID, segment count, etc.)
      that help split large payloads across multiple barcodes. If you don’t need those,
      you can switch `EncodeTypes.Pdf417` and drop the macro‑specific properties.
  - name: Can I generate the barcode as a vector (SVG) instead of PNG?
    text: 'Absolutely. Change the `BarCodeImageFormat` to `Svg`:'
  type: HowTo
tags:
- barcode
- Aspose
- PDF417
- .NET
title: Barcode met speciale tekens – Complete gids voor het genereren van PDF417 met
  Aspose
url: /nl/net/compact-pdf417-encoding/barcode-with-special-characters-complete-guide-to-generating/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode met speciale tekens – Complete gids voor het genereren van PDF417 met Aspose

Heb je je ooit afgevraagd hoe je een **barcode met speciale tekens** maakt die accenten, symbolen of zelfs copyright‑tekens bevat? Je bent niet de enige. Veel ontwikkelaars lopen tegen een muur wanneer hun data tekens bevat zoals “Å”, “é” of “©”, en standaardvoorbeelden laten zelden zien hoe je hiermee omgaat. In deze tutorial lopen we een concreet voorbeeld door dat niet alleen dat probleem oplost, maar ook **hoe je PDF417**‑barcodes genereert met de Aspose.BarCode‑bibliotheek.

We beginnen met het opzetten van een eenvoudige .NET‑console‑app, duiken daarna in de code die een PDF417‑barcode produceert met de tekenreeks `"Åspóse.Barcóde©"`. Onderweg zie je waarom elke instelling belangrijk is, hoe je macro‑PDF417‑metadata configureert, en waar je op moet letten bij Unicode. Aan het einde kun je **barcode met Aspose** maken in elk van je projecten, of het nu gaat om voorraadbeheer, ticketing of veilige documenttracking.

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

- .NET 6.0 SDK of later (de code werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 (of een IDE naar keuze)
- Een geldige Aspose.BarCode for .NET‑licentie (je kunt starten met een gratis proefversie)
- Basiskennis van C#‑syntaxis

Als een van deze items onbekend klinkt, geen paniek—installeer gewoon de .NET SDK en haal het NuGet‑pakket `Aspose.BarCode` op, dan ben je klaar om te gaan.

## Stap 1: Installeer Aspose.BarCode en zet het project op

Om een **barcode met speciale tekens** te genereren, heb je eerst de Aspose.BarCode‑bibliotheek nodig. Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Dit haalt de nieuwste versie op (vanaf juli 2026, versie 23.12) die volledige Unicode‑ondersteuning biedt. Nadat het pakket is hersteld, maak je een nieuw C#‑bestand aan genaamd `Program.cs` en voeg je de gebruikelijke `using`‑directieven toe:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Waarom `using Aspose.BarCode.Generation`? Het geeft ons toegang tot de `BarcodeGenerator`‑klasse, het hart van **hoe je PDF417**‑barcodes genereert met Aspose.

## Stap 2: Initialiseert de Barcode Generator met Unicode‑tekst

Nu volgt het deel dat daadwerkelijk een **barcode met speciale tekens** maakt. Merk op dat de tekenreeks die we aan de constructor doorgeven een “Å”, een “ó” en een “©” bevat. Aspose detecteert automatisch het Unicode‑bereik, dus je hebt geen extra coderingsstappen nodig—geef gewoon de gewone .NET‑string door:

```csharp
// Step 2: Create a barcode generator for Macro PDF417 with Unicode text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`EncodeTypes.MacroPdf417` vertelt Aspose dat we een PDF417‑barcode willen die macro‑informatie kan dragen (handig voor het opsplitsen van grote payloads). De generator bevat nu een **barcode met speciale tekens** klaar voor verdere afstemming.

## Stap 3: Fijn afstellen van uiterlijk en macro‑metadata

Een eenvoudige barcode werkt, maar de meeste real‑world scenario's vereisen controle over grootte, kolomaantal en macro‑velden. Hieronder passen we de X‑dimensie, het aantal kolommen en een reeks macro‑PDF417‑eigenschappen aan. Elke regel is becommentarieerd zodat je ziet *waarom* het belangrijk is.

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns (affects width)

    // Define macro PDF417 metadata (file ID, segment info, etc.)
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Een snelle tip: als je merkt dat de gegenereerde barcode te breed wordt, verlaag dan de waarde van `Columns` of verhoog `XDimension`. Beide beïnvloeden de uiteindelijke afbeeldingsgrootte, wat cruciaal is bij het embedden van de barcode in PDF‑bestanden of afgedrukte labels.

## Stap 4: Sla de barcode op als afbeelding

Tot slot slaan we de barcode op als een PNG‑bestand. De `Save`‑methode rendert automatisch de **barcode met speciale tekens** naar een rasterformaat dat je kunt weergeven op een website, embedden in een rapport, of naar een printer sturen.

```csharp
    // Save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Vervang `YOUR_DIRECTORY` door een absoluut of relatief pad dat op jouw machine bestaat. Nadat het programma is voltooid, zie je `ExtPDF417Meta.png` met een scherpe PDF417‑barcode die de Unicode‑tekenreeks codeert.

### Verwachte output

Als je de PNG opent, zie je een rechthoekige barcode met een reeks zwarte en witte strepen. Scan je deze met een PDF417‑compatibele scanner (of een mobiele app zoals “Barcode Scanner”), dan krijg je exact de tekst `"Åspóse.Barcóde©"` terug, samen met de macro‑metadata die we hebben ingesteld. Met andere woorden, de barcode behoudt de speciale tekens zonder gegevensverlies.

## Veelgestelde vragen & randgevallen

### Wat als mijn tekst emoji’s of non‑BMP‑tekens bevat?

Aspose.BarCode ondersteunt volledige UTF‑16, dus emoji’s werken zolang de doel‑scanner ze kan decoderen. Geef de tekenreeks gewoon door; de bibliotheek handelt de codering intern af.

### Moet ik een specifiek karakterset instellen?

Nee. In tegenstelling tot oudere barcode‑SDK’s die `CodePage`‑instellingen vereisten, detecteert Aspose automatisch Unicode. Als je echter een legacy‑apparaat target dat alleen ASCII begrijpt, moet je speciale tekens eerst verwijderen of vervangen vóór generatie.

### Hoe verschilt dit van een gewone PDF417‑barcode?

De `MacroPdf417`‑variant voegt extra velden toe (file ID, segment count, enz.) die helpen grote payloads over meerdere barcodes te verdelen. Als je die niet nodig hebt, kun je `EncodeTypes.Pdf417` gebruiken en de macro‑specifieke eigenschappen weglaten.

### Kan ik de barcode genereren als vector (SVG) in plaats van PNG?

Zeker. Verander `BarCodeImageFormat` naar `Svg`:

```csharp
barcodeGenerator.Save("ExtPDF417Meta.svg", BarCodeImageFormat.Svg);
```

Vector‑output schaalt zonder kwaliteitsverlies—handig voor high‑resolution afdrukken.

## Volledig werkend voorbeeld

Hieronder staat het complete, kant‑klaar programma. Kopieer‑en‑plak het in `Program.cs`, pas het output‑pad aan, en druk op **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeSpecialCharsDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel size of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns

                // Step 3: Define macro PDF417 metadata (file ID, segment info, etc.)
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode as a PNG image
                barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Barcode with special characters generated successfully!");
        }
    }
}
```

Wanneer je dit programma uitvoert, wordt een bevestigingsregel geprint en wordt `ExtPDF417Meta.png` in de map van het uitvoerbare bestand geplaatst. Open het bestand, scan het, en controleer dat de speciale tekens de round‑trip overleven.

## Pro‑tips voor productie

- **Cache de generator** als je veel barcodes in een lus maakt; het hergebruiken van dezelfde `BarcodeGenerator`‑instantie vermindert geheugen‑churn.
- **Stel `Resolution` in** (`barcodeGenerator.Parameters.ImageResolution`) wanneer je een hogere DPI nodig hebt voor print‑ready assets.
- **Valideer invoer**: verwijder controle‑tekens die macro‑velden kunnen breken. Een eenvoudige regex zoals `^[\u0020-\u007E\u00A0-\u00FF]+$` werkt voor de meeste Latin‑1‑scenario’s.
- **Thread‑veiligheid**: elke thread moet zijn eigen `BarcodeGenerator` hebben. De klasse is niet thread‑safe.

## Conclusie

Je hebt nu een solide, end‑to‑end recept voor het maken van een **barcode met speciale tekens** met Aspose, en je hebt ook gezien **hoe je PDF417**‑barcodes genereert die macro‑metadata dragen. Het voorbeeld besloeg alles van het installeren van het NuGet‑pakket tot het opslaan van de uiteindelijke PNG, en belichtte veelvoorkomende valkuilen zoals Unicode‑verwerking en afbeeldingsgrootte.

Klaar voor de volgende stap? Probeer het afbeeldingsformaat te wijzigen naar SVG, experimenteer met grotere payloads


## Wat moet je hierna leren?


De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Recognizing PDF417 Barcode with Chinese Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)
- [Recognizing PDF417 Barcode with Turkish Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}