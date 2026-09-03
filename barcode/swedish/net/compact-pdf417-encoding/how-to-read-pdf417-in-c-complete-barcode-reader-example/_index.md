---
category: general
date: 2026-07-21
description: Hur man läser PDF417‑streckkod i C# med ett koncist streckkodsläsarexempel.
  Lär dig snabbt hur du läser streckkod från en bild med steg‑för‑steg‑kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: sv
lastmod: 2026-07-21
og_description: Hur man läser PDF417‑streckkod i C# med ett praktiskt exempel. Upptäck
  hur du läser streckkod från en bild och integrerar C#‑streckkodsläsarexemplet omedelbart.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Hur man läser PDF417 i C# – Fullständig genomgång av streckkodsläsare
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
title: Hur man läser PDF417 i C# – Komplett exempel på streckkodsläsare
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417 i C# – Komplett Barcode Reader‑exempel

Har du någonsin undrat **hur man läser PDF417** i ett .NET‑projekt utan att leta igenom ändlösa dokument? Du är inte ensam. Oavsett om du skannar körkort, boardingkort eller anpassade lageretiketter, är det ett verkligt behov att extrahera den datan på ett pålitligt sätt.  

I den här guiden går vi igenom ett **c# barcode reader‑exempel** som hämtar varje del av Macro PDF417‑metadata från en enda bildfil. När du är klar har du en färdig‑att‑köra konsolapp som **läser streckkod från bild** och skriver ut alla de utökade fälten du kan behöva.

## Vad du behöver

- .NET 6.0 SDK eller senare (du kan också rikta in dig på .NET Framework 4.7+ – koden fungerar på samma sätt)
- Visual Studio 2022, VS Code eller någon C#‑redigerare du föredrar
- NuGet‑paketet **Aspose.BarCode for .NET** (klassen `BarCodeReader` kommer från detta bibliotek)
- En bildfil som innehåller en Macro PDF417‑streckkod (för demo använder vi `ExtPDF417Meta.png`)

> **Proffstips:** Om du inte har ett PDF417‑exempel till hands, levererar Aspose några testbilder i deras GitHub‑repo – ladda bara ner en och lägg den i din projektmapp.

## Steg 1: Installera Barcode‑biblioteket

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till `BarCodeReader`, `DecodeType` och `Extended`‑egenskapen som vi kommer att behöva senare. Ingen extra konfiguration krävs; biblioteket fungerar direkt för de flesta bildformat (PNG, JPEG, BMP, osv.).

## Steg 2: Skapa en minimal konsolapp

Skapa ett nytt konsolprojekt om du inte redan har gjort det:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Ersätt den genererade `Program.cs` med koden nedan. Lägg märke till hur varje sektion är kommenterad så att du kan följa logiken även om du är ny på streckkodshantering.

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

### Varför detta fungerar

- **`DecodeType.MacroPdf417`** talar om för läsaren att förvänta sig det utökade Macro PDF417‑formatet, som innehåller extra metadata (fil‑ID, segmentantal, tidsstämplar, osv.).
- Objektet **`Extended.Pdf417`** fylls endast i för Macro PDF417‑streckkoder, så det är säkert att komma åt dessa egenskaper efter anropet `ReadBarCodes()`.
- Genom att använda ett **`using`**‑block garanteras att filhandtag frigörs, vilket förhindrar fil‑lås‑problem på Windows.

## Steg 3: Kör applikationen

Kompilera och kör:

```bash
dotnet run
```

Om bilden innehåller en giltig Macro PDF417‑streckkod bör du se en utskrift liknande:

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

Om inget skrivs ut, dubbelkolla att bildsökvägen är korrekt och att streckkoden faktiskt är en Macro PDF417‑variant. Vanlig PDF417 (utan macro‑tillägget) kommer fortfarande att avkodas, men `Extended`‑egenskaperna blir tomma.

## Hantera kantfall

### Flera streckkoder i en bild

Ibland innehåller en enda skanning mer än ett PDF417‑segment (tänk på ett flersidigt dokument kodad över flera symboler). `foreach`‑loopen enumererar redan *alla* upptäckta streckkoder, så du behöver ingen extra logik – samla bara segmenten och sätt ihop dem senare om det behövs.

### Saknad utökad data

Inte varje PDF417 innehåller macro‑information. I det fallet kommer `result.Extended.Pdf417` att instansieras men dess fält får standardvärden (noll, tom sträng eller `false`). Du kan skydda dig mot detta så här:

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

### Prestandatips

- **Batch‑behandling:** Om du har en mapp med bilder, omslut skapandet av `BarCodeReader` i en loop som återanvänder samma instans med `barcodeReader.SetImage(imagePath)`. Detta minskar allokeringskostnaden.
- **Parallellism:** För stora arbetsbelastningar, överväg `Parallel.ForEach` på fillistan, men kom ihåg att Aspose‑läsaren är trådsäker endast när varje tråd använder sin egen `BarCodeReader`‑instans.

## Fullständig källkod (Klar att kopiera‑klistra)

Nedan är hela programmet igen, redo att klistra in i `Program.cs`. Inga extra filer behövs förutom bilden.

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

## Sammanfattning: Så läser du PDF417 i C# snabbt

- Installera **Aspose.BarCode** via NuGet.
- Peka en `BarCodeReader` på din bild med `DecodeType.MacroPdf417`.
- Loopa genom `ReadBarCodes()` och hämta både grundläggande och utökade fält.
- Hantera saknad macro‑data på ett smidigt sätt och överväg prestandajusteringar för massskanningar.

## Nästa steg & relaterade ämnen

- **Läs streckkod från bild** med andra format (QR, DataMatrix) – byt bara `DecodeType`‑enum.
- **Koda PDF417** med `BarCodeGenerator` om du behöver skapa streckkoder programatiskt.
- Utforska **felkorrigeringsnivåer** och hur de påverkar skanningspålitlighet.
- Integrera denna logik i ett ASP.NET Core‑API för att exponera streckkodsläsning som en webbtjänst.

Känn dig fri att experimentera: byt bild, lek med `DecodeType`‑flaggan, eller mata in macro‑data i en databas. Kärnmönstret förblir detsamma, och nu har du ett gediget **c# barcode reader‑exempel** i din verktygslåda.

Lycka till med kodningen, och må dina skanningar alltid vara rena!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser DataMatrix‑streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hur man skapar streckkod – Compact PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man skapar tyst zon för Code 16K med Aspose.BarCode för .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}