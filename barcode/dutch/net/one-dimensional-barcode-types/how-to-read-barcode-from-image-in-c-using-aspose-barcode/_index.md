---
category: general
date: 2026-10-18
description: Leer hoe je een barcode uit een afbeelding kunt lezen in C# met Aspose.BarCode,
  inclusief het extraheren van Macro PDF417-metadata en volledige voorbeeldcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: nl
lastmod: 2026-10-18
og_description: Hoe lees je een barcode uit een afbeelding met C# Aspose.BarCode.
  Volg deze stap‑voor‑stap tutorial om Macro PDF417‑metadata te extraheren en veelvoorkomende
  scenario’s af te handelen.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Hoe lees je een barcode uit een afbeelding in C# – volledige Aspose.BarCode-gids
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hoe een barcode lezen uit een afbeelding in C# met Aspose.BarCode
url: /nl/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een barcode uit een afbeelding lezen in C# met Aspose.BarCode

Als je **hoe een barcode uit een afbeelding te lezen** in een .NET‑applicatie nodig hebt, laat deze gids de exacte stappen zien met Aspose.BarCode. Of je nu gescande documenten, bonnen of voorraadlabels verwerkt, je ziet hoe je de barcode leest, Macro PDF417‑metadata ophaalt en typische randgevallen afhandelt.

Het lezen van een barcode uit een afbeelding is een routinetaken, maar het extraheren van de uitgebreide Macro PDF417‑velden voegt een extra complexiteitslaag toe. Deze tutorial behandelt de volledige workflow, van projectconfiguratie tot een volledig uitvoerbaar voorbeeld, zodat je de code kunt kopiëren‑plakken en direct resultaten ziet.

## Wat je zult leren

- Hoe je Aspose.BarCode instelt voor C#‑projecten.  
- De juiste manier om de **C# barcode reader** te instantieren voor een Macro PDF417‑afbeelding.  
- Hoe je over elke gedetecteerde barcode itereren en basisinformatie weergeven.  
- Hoe je **Macro PDF417‑metadata** zoals bestand‑ID, segment‑ID en checksum kunt benaderen.  
- Tips voor het omgaan met ontbrekende metadata, grote afbeeldingen en veelvoorkomende decodeerfouten.  

**Voorvereisten**

- .NET 6.0 (of later) geïnstalleerd.  
- Basiskennis van C# en Visual Studio (elke IDE werkt).  
- Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (bijv. `ExtPDF417Meta.png`).  

## Stap 1: Installeer Aspose.BarCode

Open een terminal in je projectmap en voer uit:

```bash
dotnet add package Aspose.BarCode
```

Het pakket bevat de **BarCodeReader class**, die de **C# barcode reader**‑functionaliteit implementeert die nodig is voor deze tutorial.

## Stap 2: Zet de ontwikkelomgeving op

Maak een nieuwe console‑applicatie aan als je er nog geen hebt:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Voeg de `using`‑directieven toe aan de bovenkant van `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Deze namespaces maken de **BarCodeReader class** en de `DecodeType`‑enumeratie beschikbaar die nodig zijn voor Macro PDF417‑decodering.

## Stap 3: Initialiseert de BarCodeReader voor Macro PDF417

De kern van **hoe een barcode uit een afbeelding te lezen** is het aanmaken van een `BarCodeReader`‑instantie die zich richt op de specifieke `DecodeType`. Voor Macro PDF417 moet je `DecodeType.MacroPdf417` doorgeven:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Waarom dit belangrijk is:**  
Het kiezen van `DecodeType.MacroPdf417` vertelt de bibliotheek om te zoeken naar het uitgebreide Macro PDF417‑formaat, dat extra velden bevat bovenop de basis‑barcode‑gegevens. Als je een generieke `DecodeType.Pdf417` gebruikt, worden die extra velden genegeerd.

## Stap 4: Itereer over gedetecteerde barcodes

Eén afbeelding kan meerdere barcodes bevatten. De `ReadBarCodes()`‑methode retourneert een doorloopbare collectie van `BarCodeResult`‑objecten. Loop erdoorheen om de basisinformatie van elke barcode weer te geven:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` geeft je de exacte barcode‑symbologie (bijv. “MacroPdf417”), terwijl `CodeText` de gedecodeerde string bevat.

## Stap 5: Extraheer en toon Macro PDF417‑metadata

Wanneer de barcode een Macro PDF417 is, biedt de `Extended.Pdf417`‑eigenschap een rijke set metadata‑velden. Benader ze direct zoals hieronder getoond:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Deze velden geven je alles wat je nodig hebt om het oorspronkelijke multi‑segment‑bestand te reconstrueren, de integriteit te verifiëren en de barcode te koppelen aan een specifiek document of afzender.

### Verwachte console‑output

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Als de afbeelding geen Macro PDF417‑barcode bevat, zal het `Extended.Pdf417`‑object `null` zijn. Bescherm hiertegen om een `NullReferenceException` te voorkomen:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Stap 6: Veelvoorkomende fouten en randgevallen afhandelen

### Grote afbeeldingen

Het lezen van zeer grote afbeeldingen kan veel geheugen verbruiken. Gebruik de `BarcodeReader`‑overload die `ReaderParameters` accepteert om de maximale afbeeldingsgrootte te beperken:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Ontbrekende of corrupte metadata

Als een van de Macro‑velden ontbreekt, retourneert de bijbehorende eigenschap `null` of `0`. Log deze gevallen en bepaal of je de barcode als onvolledig wilt behandelen.

### Meerdere barcode‑typen in één afbeelding

Als een afbeelding andere barcode‑formaten kan bevatten, kun je een array van `DecodeType`‑waarden doorgeven:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Deze aanpak houdt de **hoe een barcode uit een afbeelding te lezen**‑logica flexibel zonder prestaties op te offeren.

## Stap 7: Volledige broncode

Hieronder staat het volledige, kant‑klaar programma. Vervang `YOUR_DIRECTORY/ExtPDF417Meta.png` door het pad naar je eigen afbeelding.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Voer het programma uit met:

```bash
dotnet run
```

Je zou het barcode‑type, de gedecodeerde tekst en alle beschikbare Macro PDF417‑velden in de console moeten zien afgedrukt.

## Conclusie

In deze tutorial heb je **hoe een barcode uit een afbeelding te lezen** geleerd met Aspose.BarCode voor C#. De gids behandelde het instellen van de **C# barcode reader**,

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}