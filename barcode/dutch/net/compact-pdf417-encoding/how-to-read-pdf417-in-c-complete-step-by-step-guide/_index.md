---
category: general
date: 2026-07-15
description: Hoe PDF417‑barcode te lezen in C# en meerdere barcodes uit een afbeelding
  te lezen. Leer barcode‑afbeelding lezen in C# met gedetailleerde code en tips.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: nl
lastmod: 2026-07-15
og_description: Hoe lees je snel PDF417‑barcode in C#. Deze gids laat zien hoe je
  meerdere barcodes uit één afbeelding kunt lezen en elke eigenschap kunt decoderen.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Hoe PDF417 te lezen in C# – Volledig codevoorbeeld en uitleg
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
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
title: Hoe PDF417 lezen in C# – Complete stap‑voor‑stap gids
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 lezen in C# – Complete stap‑voor‑stap gids

Heb je je ooit afgevraagd **hoe je PDF417** uit een afbeelding kunt lezen met C#? Je bent niet de enige. De meeste ontwikkelaars lopen tegen een muur aan wanneer ze de uitgebreide Macro‑PDF417‑velden uit een gescand document moeten halen. Het goede nieuws? Met slechts een paar regels code kun je een PDF417 decoderen, meerdere barcodes in dezelfde afbeelding lezen, en elke verborgen eigenschap die de specificatie biedt ophalen.

In deze tutorial lopen we een praktijkvoorbeeld door dat laat zien **hoe je PDF417 leest**, hoe je **meerdere barcodes** uit één bestand kunt **lezen**, en waarom de **read barcode image C#**‑code er zo uitziet. Aan het einde heb je een kant‑klaar console‑applicatie die elke informatie die je nodig zou kunnen hebben afdrukt – bestands‑ID, segment‑ID, controlesom, tijdstempels, noem maar op.

## Vereisten

* .NET 6.0 SDK of later (de code werkt ook met .NET Core en .NET Framework).  
* Visual Studio 2022 (of een andere editor naar keuze).  
* Het **Aspose.BarCode for .NET** NuGet‑pakket – dit is de bibliotheek die daadwerkelijk PDF417 parseert.  
* Een voorbeeldafbeelding die een Macro‑PDF417‑barcode bevat (bijvoorbeeld `ExtPDF417Meta.png`).  

Er is geen extra configuratie nodig; de bibliotheek wordt geleverd met alle decoders die je nodig hebt.

## Stap 1: Installeer Aspose.BarCode

Open je projectmap in een terminal en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Dat commando haalt de nieuwste stabiele versie op (vanaf juli 2026 is het 23.12). Als je de Package Manager Console binnen Visual Studio verkiest, gebruik dan:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** vergrendel de versie (`23.12.0`) in je `.csproj` om later per ongeluk brekende wijzigingen te voorkomen.

## Stap 2: Maak een console‑app‑skelet

Maak een nieuw console‑project aan als je er nog geen hebt:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Vervang de automatisch gegenereerde `Program.cs` door de onderstaande code. We zullen elk blok in de volgende secties uitleggen.

## Stap 3: Schrijf de volledige “Hoe PDF417 lezen” code

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

### Waarom deze code werkt

* **`BarCodeReader`** is de kernklasse die de afbeelding streamt, barcodes detecteert en een collectie van `BarCodeResult`‑objecten retourneert.  
* Het doorgeven van **`DecodeType.MacroPdf417`** vertelt de bibliotheek om Macro‑PDF417 speciaal te behandelen; hij retourneert nog steeds gewone PDF417‑symbolen, wat voldoet aan de **read multiple barcodes**‑vereiste.  
* Het **`Extended.Pdf417.MacroPdf417`**‑object bevat elk optioneel veld gedefinieerd door de ISO/IEC 15438‑standaard – daar krijg je `FileID`, `SegmentID`, `Checksum`, enz.  
* Het `using`‑blok garandeert dat de native resources worden vrijgegeven, waardoor geheugenlekken in langdurige services worden voorkomen.

## Stap 4: Voer de applicatie uit en controleer de output

Vanuit de terminal:

```bash
dotnet run
```

Je zou iets moeten zien zoals:

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

Als de afbeelding meer dan één barcode bevat, zal de lus een scheidingslijn (`----------------------------------------`) afdrukken en doorgaan met het volgende resultaat – precies wat **read multiple barcodes** in de praktijk betekent.

## Veelgestelde vragen & randgevallen

### Wat als de afbeelding zowel Macro‑PDF417 als gewone PDF417‑symbolen bevat?

Dezelfde `BarCodeReader`‑aanroep zal beide retourneren. Je kunt ze onderscheiden door `result.CodeType` te controleren (`MacroPdf417` vs `Pdf417`). De uitgebreide eigenschappen zullen `null` zijn voor een gewone PDF417, dus de `if (macro != null)`‑guard voorkomt een `NullReferenceException`.

### Mijn barcode is gedraaid of scheef—zal de lezer nog steeds werken?

Aspose.BarCode bevat ingebouwde rotatie‑ en vervormingscompensatie. Zolang de barcode minstens 30 % van de afbeeldingsbreedte beslaat, zal de decoder meestal slagen. Voor extreme gevallen kun je `reader.Options.AllowInvertedBarcodes = true;` inschakelen voordat je `ReadBarCodes()` aanroept.

### Hoe verwerk ik grote batches van afbeeldingen?

Omhul de leeslogica in een `foreach (var file in Directory.GetFiles(folder, "*.png"))`‑lus. Het `using`‑patroon zorgt ervoor dat de native resources van elke afbeelding worden vrijgegeven vóór de volgende iteratie, waardoor het geheugenverbruik laag blijft.

## Volledige broncode (klaar om te kopiëren‑plakken)

Hieronder staat het volledige programma in één blok voor snelle copy‑paste. Geen verborgen afhankelijkheden – alleen het Aspose.BarCode NuGet‑pakket.

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

## Samenvatting – Wat we hebben behandeld

* **Hoe PDF417 lezen** met Aspose.BarCode in C#.  
* De exacte stappen om **meerdere barcodes** uit één afbeelding te **lezen**.  
* Hoe **read barcode image C#** uit te voeren en elk Macro‑PDF417‑veld te extraheren.  
* Tips voor rotatie, batchverwerking en het omgaan met ontbrekende uitgebreide gegevens.

## Volgende stappen & gerelateerde onderwerpen

* **Encode PDF417** – genereer je eigen Macro‑PDF417‑barcodes met `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – met dezelfde `BarCodeReader`‑klasse.  
* **Integrate with ASP.NET Core** – exposeer een web‑endpoint dat een geüploade afbeelding accepteert en JSON retourneert met de gedecodeerde velden.  

Voel je vrij om te experimenteren: wijzig het afbeeldingspad, plaats een gewone PDF417 in dezelfde map, of pas de `DecodeType`‑vlaggen aan om te zien hoe de bibliotheek zich gedraagt. Hoe meer je speelt, hoe comfortabeler je wordt met **read barcode image C#**‑scenario's.

Heb je een lastig beeld dat niet wil decoderen? Laat een reactie achter of open een issue in de GitHub‑repo van het voorbeeldproject. Veel plezier met coderen!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes lezen met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hoe een barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [DataMatrix‑barcode lezen C# – DataMatrix‑modus genereren (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}