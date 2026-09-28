---
category: general
date: 2026-07-21
description: Hoe PDF417‑barcode te lezen in C# met een beknopt barcode‑lezer‑voorbeeld.
  Leer snel hoe je een barcode uit een afbeelding leest met stap‑voor‑stap code.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: nl
lastmod: 2026-07-21
og_description: Hoe PDF417-barcode te lezen in C# met een praktisch voorbeeld. Ontdek
  hoe je een barcode uit een afbeelding kunt lezen en het C#-barcodelezer‑voorbeeld
  direct kunt integreren.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Hoe PDF417 te lezen in C# – Volledige barcodelezer walkthrough
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Hoe PDF417 lezen in C# – Volledig barcodelezer voorbeeld
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 te lezen in C# – Volledig barcode lezer voorbeeld

Heb je je ooit afgevraagd **hoe je PDF417 kunt lezen** in een .NET‑project zonder eindeloos door documentatie te zoeken? Je bent niet de enige. Of je nu rijbewijzen, instapkaarten of aangepaste voorraadlabels scant, het betrouwbaar extraheren van die gegevens is een praktijkbehoefte.  

In deze gids lopen we een **c# barcode lezer voorbeeld** stap voor stap door dat elke stuk Macro PDF417‑metadata uit één afbeeldingsbestand haalt. Aan het einde heb je een kant‑klaar console‑applicatie die **barcode van afbeelding leest** en alle uitgebreide velden afdrukt die je mogelijk nodig hebt.

## Wat je nodig hebt

- .NET 6.0 SDK of later (je kunt ook .NET Framework 4.7+ targeten – de code werkt hetzelfde)
- Visual Studio 2022, VS Code, of elke C#‑editor die je wilt
- Het **Aspose.BarCode for .NET** NuGet‑pakket (de `BarCodeReader`‑klasse komt uit deze bibliotheek)
- Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (voor de demo gebruiken we `ExtPDF417Meta.png`)

> **Pro tip:** Als je geen PDF417‑voorbeeld bij de hand hebt, levert Aspose een paar test‑afbeeldingen in hun GitHub‑repo – download er gewoon één en plaats deze in je projectmap.

## Stap 1: Installeer de barcode‑bibliotheek

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket voegt de `BarCodeReader`, `DecodeType` en de `Extended`‑eigenschap toe die we later nodig hebben. Geen extra configuratie is vereist; de bibliotheek werkt direct uit de doos voor de meeste afbeeldingsformaten (PNG, JPEG, BMP, enz.).

## Stap 2: Maak een minimale console‑app

Maak een nieuw console‑project aan als je dat nog niet hebt gedaan:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Vervang de gegenereerde `Program.cs` door de onderstaande code. Let op hoe elke sectie is gecommentarieerd zodat je de logica kunt volgen, zelfs als je nieuw bent met barcode‑verwerking.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
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
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Waarom dit werkt

- **`DecodeType.MacroPdf417`** vertelt de lezer dat hij het uitgebreide Macro PDF417‑formaat moet verwachten, dat extra metadata bevat (bestand‑ID, segment‑aantal, tijdstempels, enz.).
- Het **`Extended.Pdf417`**‑object wordt alleen gevuld voor Macro PDF417‑barcodes, dus het benaderen van die eigenschappen is veilig na de `ReadBarCodes()`‑aanroep.
- Het gebruik van een **`using`**‑blok garandeert dat bestands‑handles worden vrijgegeven, waardoor bestands‑vergrendelingsproblemen op Windows worden voorkomen.

## Stap 3: Voer de applicatie uit

Compileer en voer uit:

```bash
dotnet run
```

Als de afbeelding een geldige Macro PDF417‑barcode bevat, zie je een output vergelijkbaar met:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Als er niets wordt afgedrukt, controleer dan of het afbeeldingspad correct is en of de barcode inderdaad een Macro PDF417‑variant is. Een gewone PDF417 (zonder de macro‑extensie) wordt nog steeds gedecodeerd, maar de `Extended`‑eigenschappen zullen leeg zijn.

## Omgaan met randgevallen

### Meerdere barcodes in één afbeelding

Soms bevat een enkele scan meer dan één PDF417‑segment (denk aan een meer‑pagina document gecodeerd over meerdere symbolen). De `foreach`‑lus enumerateert al *alle* gedetecteerde barcodes, dus je hebt geen extra logica nodig – verzamel gewoon de segmenten en zet ze later eventueel weer samen.

### Ontbrekende uitgebreide data

Niet elke PDF417 bevat macro‑informatie. In dat scenario wordt `result.Extended.Pdf417` wel aangemaakt, maar zijn velden hebben standaardwaarden (nul, lege string, of `false`). Je kunt hierop controleren als volgt:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Prestatie‑tips

- **Batch‑verwerking:** Als je een map met afbeeldingen hebt, plaats de creatie van `BarCodeReader` in een lus die dezelfde instantie hergebruikt met `barcodeReader.SetImage(imagePath)`. Dit vermindert toewijzings‑overhead.
- **Parallelisme:** Voor grote workloads, overweeg `Parallel.ForEach` op de bestandslijst, maar onthoud dat de Aspose‑lezer alleen thread‑safe is wanneer elke thread zijn eigen `BarCodeReader`‑instantie gebruikt.

## Volledige broncode (klaar om te kopiëren en plakken)

Hieronder staat het volledige programma opnieuw, klaar om in `Program.cs` te plaatsen. Geen extra bestanden nodig, behalve de afbeelding.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
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

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Samenvatting: PDF417 snel lezen in C#

- Installeer **Aspose.BarCode** via NuGet.
- Richt een `BarCodeReader` op je afbeelding met `DecodeType.MacroPdf417`.
- Loop door `ReadBarCodes()` en haal zowel basis‑ als uitgebreide velden op.
- Handel ontbrekende macro‑data elegant af en overweeg prestatie‑aanpassingen voor bulk‑scans.

## Volgende stappen & gerelateerde onderwerpen

- **Barcode van afbeelding lezen** met andere formaten (QR, DataMatrix) – verwissel gewoon de `DecodeType`‑enum.
- **PDF417 coderen** met `BarCodeGenerator` als je barcodes programmatisch moet maken.
- Verken **foutcorrectieniveaus** en hoe ze de scan‑betrouwbaarheid beïnvloeden.
- Integreer deze logica in een ASP.NET Core API om barcode‑lezen als een webservice beschikbaar te maken.

Voel je vrij om te experimenteren: wijzig de afbeelding, speel met de `DecodeType`‑vlag, of voer de macro‑data in een database in. Het kernpatroon blijft hetzelfde, en nu heb je een solide **c# barcode lezer voorbeeld** in je gereedschapskist.

Veel programmeerplezier, en moge je scans altijd schoon zijn!

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes lezen met Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hoe een barcode te maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hoe een barcode‑rustzone te maken voor Code 16K met Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}