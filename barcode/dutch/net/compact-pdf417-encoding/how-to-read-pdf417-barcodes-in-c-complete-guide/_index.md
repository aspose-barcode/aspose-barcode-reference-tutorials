---
category: general
date: 2026-08-22
description: Hoe PDF417‑barcodes te lezen in C# met een stap‑voor‑stap‑gids, inclusief
  hoe meerdere barcodes uit een afbeelding te lezen en MacroPdf417‑details te extraheren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: nl
lastmod: 2026-08-22
og_description: Hoe PDF417‑barcodes snel te lezen in C#. Deze tutorial laat zien hoe
  je meerdere barcodes uit een afbeelding kunt lezen en MacroPdf417‑uitgebreide informatie
  kunt ophalen.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Hoe PDF417-barcodes te lezen in C# – volledige programmeerhandleiding
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe PDF417-barcodes te lezen in C# – volledige gids
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 barcodes lezen in C# – volledige gids

Als je **hoe PDF417 te lezen** bars in een .NET‑applicatie nodig hebt, biedt deze tutorial een kant‑klaar‑te‑gebruiken oplossing. Je leert hoe je meerdere barcodes uit één afbeelding kunt lezen, de volledige MacroPdf417‑dataset kunt extraheren en deze in de console kunt weergeven. De aanpak werkt met de Aspose.BarCode for .NET‑bibliotheek en vereist slechts een paar regels code.

Barcodes lezen uit een afbeelding is een veelvoorkomende taak in voorraadsystemen, ticketvalidatie en documentbeheer. Aan het einde van deze gids kun je elke PDF417‑ of MacroPdf417‑barcode decoderen, meerdere codes in één afbeelding verwerken en de uitgebreide velden die MacroPdf417 biedt begrijpen.

## Vereisten

- .NET 6.0 SDK of later (de code compileert ook met .NET Framework 4.7+)
- Visual Studio 2022 of een andere C#‑editor naar keuze
- Aspose.BarCode for .NET NuGet‑pakket (`Install-Package Aspose.BarCode`)
- Een voorbeeldafbeelding die een MacroPdf417‑barcode bevat (bijv. `MacroPdf417.png`)

Er is geen extra configuratie nodig; de bibliotheek verwerkt het laden en decoderen van afbeeldingen intern.

## Hoe PDF417 barcodes lezen uit een afbeelding in C#

De kern van de oplossing is de `BarCodeReader`‑klasse. Deze opent de afbeelding, detecteert alle barcodes van het opgegeven type en retourneert een collectie van `BarCodeResult`‑objecten. De onderstaande code toont een volledig console‑programma.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Waarom elke regel belangrijk is

| Stap | Doel |
|------|------|
| **1️⃣ Initialiseren** | Maakt een `BarCodeReader` aan die is gekoppeld aan het afbeeldingsbestand en beperkt de detectie tot de MacroPdf417‑symbologie, wat de verwerking versnelt. |
| **2️⃣ Itereren** | `ReadBarCodes()` retourneert **alle** barcodes die overeenkomen met het gevraagde type, waardoor je **meerdere barcodes kunt lezen** zonder extra lussen. |
| **3️⃣ Basisuitvoer** | Toont de generieke `CodeTypeName` en de mens‑leesbare `CodeText`. Dit is nuttig voor logging of snelle validatie. |
| **4️⃣ Uitgebreide data** | MacroPdf417 bevat extra metadata (bestand‑ID, segment‑aantal, tijdstempels, enz.). Het `Extended.Pdf417`‑object maakt elk veld direct beschikbaar, zodat je het volledige datapakket kunt opslaan of verifiëren. |

Het uitvoeren van het programma met een geldige MacroPdf417‑afbeelding levert console‑output op die lijkt op het volgende:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

De output bevestigt dat de bibliotheek de barcode succesvol heeft gelezen, de tekst heeft geëxtraheerd en elk MacroPdf417‑veld heeft geleverd.

## Meerdere barcodes lezen uit één afbeelding

In veel praktijksituaties worden meerdere PDF417‑symbolen op één label geplaatst — denk aan een verzendmanifest dat een vervoerderscode, een trackingnummer en een douane‑verklaring bevat. Het bovenstaande code‑blok **leest al meerdere barcodes** omdat `ReadBarCodes()` een enumerable van alle overeenkomsten retourneert. Er is geen extra configuratie nodig; je hoeft alleen door de resultaten te itereren, zoals gedemonstreerd.

Als je de lezer wilt beperken tot standaard PDF417 (niet‑macro) terwijl je toch meerdere codes verwerkt, vervang dan `DecodeType.MacroPdf417` door `DecodeType.Pdf417`. De rest van de logica blijft ongewijzigd.

## MacroPdf417‑uitgebreide data begrijpen

MacroPdf417 is een uitbreiding van de reguliere PDF417‑specificatie. Het splitst grote payloads in meerdere segmenten en voegt een kleine header toe die het hele bestand beschrijft. De meest relevante velden zijn:

- **MacroPdf417FileID** – een unieke identifier die door alle segmenten van hetzelfde bestand wordt gedeeld.
- **MacroPdf417SegmentID** – het volgnummer van het huidige segment.
- **MacroPdf417SegmentsCount** – het totale verwachte aantal segmenten.
- **MacroPdf417FileName** – optionele bestandsnaam die met de barcode wordt verzonden.
- **MacroPdf417Checksum** – fout‑controlewaarde voor het volledige bestand.
- **MacroPdf417FileSize** – grootte van de originele binaire payload.
- **MacroPdf417TimeStamp** – ISO‑8601 tijdstempel wanneer de barcode werd gegenereerd.
- **MacroPdf417Addressee / Sender** – optionele tekstvelden voor routing.
- **MacroPdf417Terminator** – geeft aan of dit segment het laatste is.

Wanneer je alle segmenten hebt ontvangen, kun je het originele bestand reconstrueren door ze te ordenen op `MacroPdf417SegmentID` en de `CodeText`‑waarden samen te voegen. Deze logica is eenvoudig te implementeren zodra de velden beschikbaar zijn.

## Veelvoorkomende valkuilen en pro‑tips

- **Beeldkwaliteit is belangrijk** – lage resolutie of sterk gecomprimeerde PNG/JPEG‑bestanden kunnen gemiste detecties veroorzaken. Gebruik een DPI van minimaal 300 dpi voor afgedrukte barcodes.
- **Gemengde symbologieën** – als de afbeelding zowel MacroPdf417 als reguliere PDF417 bevat, maak dan twee lezers (een voor elke `DecodeType`) of gebruik `DecodeType.AllSupported` en filter de resultaten op `result.CodeTypeName`.
- **Geheugengebruik** – de `using`‑statement verwijdert de `BarCodeReader` direct, waardoor grote afbeeldingsbuffers niet in het geheugen blijven.
- **Thread‑veiligheid** – `BarCodeReader` is niet thread‑safe. Maak een aparte instantie per thread als je afbeeldingen parallel decodeert.
- **Foutafhandeling** – wikkel de `ReadBarCodes()`‑aanroep in een try/catch‑blok om `BarCodeException` op te vangen bij corrupte afbeeldingen.

## Volledige werkende voorbeeld‑overzicht

Hieronder staat het volledige programma dat je kunt kopiëren naar een nieuw console‑project. Het bevat alle `using`‑directieven, een constante voor het afbeeldingspad en het disposingspatroon.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Compileer met `dotnet build` en voer uit met `dotnet run`. De console drukt de basisgegevens van elke barcode en de volledige MacroPdf417‑payload af.

## Volgende stappen

- **Meerdere delen reconstrueren** – verzamel alle segmenten, sorteer op `MacroPdf417SegmentID` en voeg `CodeText` samen tot

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe PDF417 Barcode genereren – Compacte PDF417‑codering](/barcode/english/net/compact-pdf417-encoding/)
- [Hoe PDF417 Barcodes lezen met Turkse tekens in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Hoe Aspose te gebruiken voor PDF417 Barcode (Chinees) in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}