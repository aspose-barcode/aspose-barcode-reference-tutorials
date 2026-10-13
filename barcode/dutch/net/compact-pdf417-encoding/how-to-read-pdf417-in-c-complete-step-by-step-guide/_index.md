---
category: general
date: 2026-09-28
description: Lees PDF417 barcode c# snel met Aspose.BarCode. Decodeer meerdere barcodes
  van één afbeelding, extraheer Macro‑PDF417-velden, en verwerk rotatie of batchverwerking.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Lees PDF417 barcode c# snel met Aspose.BarCode. Deze handleiding toont
  hoe je meerdere barcodes van één afbeelding decodeert, alle Macro‑PDF417‑eigenschappen
  extraheert, en roterende of batchafbeeldingen verwerkt.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: PDF417 barcode c# lezen – volledig codevoorbeeld & handleiding
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Hoe PDF417 barcode c# lezen – volledige stapsgewijze handleiding
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417-barcode c# lezen – volledige stapsgewijze gids

Heb je je ooit afgevraagd **hoe je PDF417** van een afbeelding kunt lezen met C#? Je bent niet de enige. De meeste ontwikkelaars lopen tegen een muur aan wanneer ze de uitgebreide Macro‑PDF417-velden uit een gescand document moeten halen. Het goede nieuws? Met slechts een paar regels code kun je **PDF417-barcode c# lezen**, meerdere barcodes in dezelfde afbeelding decoderen, en elke verborgen eigenschap die de specificatie biedt ophalen.

## Snelle antwoorden
- **Kan Aspose.BarCode Macro‑PDF417 decoderen?** Ja – schakel gewoon `DecodeType.MacroPdf417` in en de bibliotheek retourneert alle uitgebreide velden.  
- **Hoeveel barcodes kunnen er van één afbeelding worden gelezen?** Onbeperkt; de API retourneert een collectie van `BarCodeResult` objecten.  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor productiegebruik; een gratis proefversie werkt voor evaluatie.  
- **Worden gedraaide barcodes gedetecteerd?** Ingebouwde rotatiecompensatie werkt voor barcodes die minstens 30 % van de afbeeldingsbreedte beslaan.  
- **Wordt batchverwerking ondersteund?** Absoluut – wikkel de lezer in een `foreach`-lus en maak elke instantie vrij met `using`.

## Wat is read PDF417 barcode c#?
`read pdf417 barcode c#` verwijst naar het proces van het gebruiken van een .NET-bibliotheek om PDF417 (inclusief Macro‑PDF417) symbolen van afbeeldingsbestanden direct in C#-code te decoderen. De Aspose.BarCode SDK biedt een één‑oproep‑API die het laden van afbeeldingen, barcode‑detectie en het extraheren van alle ISO‑gedefinieerde velden afhandelt.

## Waarom Aspose.BarCode gebruiken voor PDF417-decodering?
Aspose.BarCode ondersteunt **30+ barcode‑symbologieën** en kan afbeeldingen tot **5000 × 5000 px** verwerken in minder dan **0,1 s** op typische serverhardware. Het biedt ook kant‑en‑klare rotatie-, vervormings- en omgekeerde‑barcode‑afhandeling, waardoor aangepaste beeld‑preprocessing overbodig wordt. Bovendien bevat de bibliotheek ingebouwde ondersteuning voor het lezen van Macro‑PDF417‑uitgebreide velden, waardoor het een alles‑in‑één‑oplossing is voor complexe scanscenario's.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

* .NET 6.0 SDK of later (de code werkt ook met .NET Core en .NET Framework).  
* Visual Studio 2022 (of een andere editor naar keuze).  
* Het **Aspose.BarCode for .NET** NuGet‑pakket – dit is de bibliotheek die daadwerkelijk PDF417 parseert.  
* Een voorbeeldafbeelding die een Macro‑PDF417‑barcode bevat (bijvoorbeeld `ExtPDF417Meta.png`).  

Er is geen extra configuratie vereist; de bibliotheek wordt geleverd met alle decoders die je nodig hebt.

## Hoe PDF417-barcode c# lezen?

Laad de afbeelding met `BarCodeReader`, specificeer `DecodeType.MacroPdf417`, en doorloop de geretourneerde `BarCodeResult`‑collectie – dat is de volledige oplossing in minder dan tien regels code. De lezer extraheert automatisch zowel gewone PDF417‑symbolen als Macro‑PDF417‑uitgebreide gegevens, zodat je bestandsidentifiers, segmentnummers, tijdstempels en controlesommen krijgt zonder extra parsing.

### Stap 1: Installeer Aspose.BarCode

Open je projectmap in een terminal en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Dat commando haalt de nieuwste stabiele versie op (vanaf juli 2026 is het 23.12). Als je de Package Manager Console binnen Visual Studio verkiest, gebruik dan:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** vergrendel de versie (`23.12.0`) in je `.csproj` om later per ongeluk brekende wijzigingen te voorkomen.

### Stap 2: Maak een console‑app‑skelet

Maak een nieuw console‑project aan als je er nog geen hebt:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Vervang de automatisch gegenereerde `Program.cs` door de onderstaande code. We zullen elk blok in de volgende secties uitleggen.

### Stap 3: Schrijf de volledige “hoe PDF417 lezen” code

`BarCodeReader` is the core class that streams the image, detects barcodes, and returns a collection of `BarCodeResult` objects.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

* `BarCodeReader` — de primaire klasse die verantwoordelijk is voor het lezen en decoderen van barcodes uit afbeeldingen.  
* `DecodeType.MacroPdf417` — een vlag die de SDK vertelt Macro‑PDF417 speciaal te behandelen terwijl gewone PDF417‑symbolen nog steeds worden geretourneerd.  
* `Extended.Pdf417.MacroPdf417` — het object dat elk optioneel veld bevat dat gedefinieerd is door ISO/IEC 15438, zoals `FileID`, `SegmentID` en `Checksum`.

Het `using`‑blok garandeert dat de native resources worden vrijgegeven, waardoor geheugenlekken in langdurige services worden voorkomen.

### Stap 4: Voer de applicatie uit en controleer de output

Vanuit de terminal:

```bash
dotnet run
```

Je zou iets moeten zien als:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Als de afbeelding meer dan één barcode bevat, print de lus een scheidingslijn (`----------------------------------------`) en gaat door met het volgende resultaat — precies wat **read multiple barcodes** eruitziet.

## Veelgestelde vragen & randgevallen

### Wat als de afbeelding zowel Macro‑PDF417 als gewone PDF417‑symbolen bevat?

Dezelfde `BarCodeReader`‑aanroep zal beide retourneren. Je kunt ze onderscheiden door `result.CodeType` te controleren (`MacroPdf417` vs `Pdf417`). De uitgebreide eigenschappen zullen `null` zijn voor een gewone PDF417, dus de `if (macro != null)`‑guard voorkomt een `NullReferenceException`.

### Mijn barcode is gedraaid of scheef—werkt de lezer nog steeds?

Aspose.BarCode bevat ingebouwde rotatie‑ en vervormingscompensatie. Zolang de barcode minstens 30 % van de afbeeldingsbreedte beslaat, zal de decoder meestal slagen. Voor extreme gevallen kun je `reader.Options.AllowInvertedBarcodes = true;` inschakelen vóór het aanroepen van `ReadBarCodes()`.

### Hoe ga ik om met grote batches van afbeeldingen?

Wikkel de leeslogica in een `foreach (var file in Directory.GetFiles(folder, "*.png"))`‑lus. Het `using`‑patroon zorgt ervoor dat de native resources van elke afbeelding worden vrijgegeven vóór de volgende iteratie, waardoor het geheugenverbruik laag blijft.

## Volledige broncode (klaar om te kopiëren en te plakken)

Hieronder staat het volledige programma in één blok voor snelle copy‑paste. Geen verborgen afhankelijkheden—alleen het Aspose.BarCode NuGet‑pakket.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Samenvatting – wat we hebben behandeld

* **Hoe PDF417-barcode c# lezen** met Aspose.BarCode.  
* De exacte stappen om **meerdere barcodes lezen** van één afbeelding.  
* Hoe **barcode‑afbeelding c# lezen** en elk Macro‑PDF417‑veld extraheren.  
* Tips voor rotatie, batchverwerking en het omgaan met ontbrekende uitgebreide gegevens.

## Volgende stappen & gerelateerde onderwerpen

* **Encode PDF417** – genereer je eigen Macro‑PDF417‑barcodes met `BarCodeBuilder`.  
* **Lees andere 2‑D‑symbologieën** – QR, DataMatrix, Aztec – met dezelfde `BarCodeReader`‑klasse.  
* **Integreer met ASP.NET Core** – exposeer een web‑endpoint dat een geüploade afbeelding accepteert en JSON retourneert met de gedecodeerde velden.  

### Aanvullende nuttige links
- [Hoe DataMatrix‑barcodes lezen met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Hoe Barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [DataMatrix‑barcode C# lezen – DataMatrix‑modus genereren (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Voel je vrij om te experimenteren: wijzig het afbeeldingspad, plaats een gewone PDF417 in dezelfde map, of pas de `DecodeType`‑vlaggen aan om te zien hoe de bibliotheek zich gedraagt. Hoe meer je speelt, hoe comfortabeler je wordt met **read barcode image c#** scenario's.

Heb je een lastig beeld dat niet wil decoderen? Laat een reactie achter of open een issue in de GitHub‑repo van het voorbeeldproject. Veel plezier met coderen!

## Veelgestelde vragen

**Q: Kan ik dit gebruiken in een commerciële applicatie?**  
A: Ja, je kunt Aspose.BarCode gebruiken in commerciële projecten zolang je een geldige licentie hebt; een gratis proefversie is beschikbaar voor evaluatie.

**Q: Ondersteunt de lezer wachtwoord‑beveiligde afbeeldingen?**  
A: De SDK werkt met elk standaard afbeeldingsformaat; wachtwoordbeveiliging is niet van toepassing op rasterafbeeldingen, alleen op PDF's, die worden afgehandeld door een apart Aspose.PDF‑component.

**Q: Welke .NET‑versies worden ondersteund?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ en .NET 6+ worden allemaal volledig ondersteund door de huidige Aspose.BarCode‑release.

**Q: Hoe kan ik de prestaties verbeteren voor zeer grote batches van afbeeldingen?**  
A: Schakel `reader.Options.Quality = QualityMode.HighPerformance` in en verwerk afbeeldingen parallel met `Parallel.ForEach` terwijl je elke `BarCodeReader` nog steeds in een `using`‑blok wikkelt.

**Q: Is er een manier om alleen de Macro‑PDF417‑velden te krijgen zonder alle resultaten te itereren?**  
A: Ja – na het aanroepen van `ReadBarCodes()`, filter de collectie met `result => result.CodeType == DecodeType.MacroPdf417` en krijg vervolgens toegang tot de `Extended.Pdf417.MacroPdf417`‑eigenschap.

**Laatst bijgewerkt:** 2026-09-28  
**Getest met:** Aspose.BarCode 23.12 voor .NET  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe Pdf417‑barcode‑afbeelding genereren in C met Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Pdf417‑barcode maken met Aspose Barcode stap‑voor‑stap gids](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Meerdere barcodes lezen C volledige gids met Pdf417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}