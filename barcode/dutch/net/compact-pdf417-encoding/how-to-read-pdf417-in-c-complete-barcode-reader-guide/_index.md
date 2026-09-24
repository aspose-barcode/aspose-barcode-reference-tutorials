---
category: general
date: 2026-08-09
description: Hoe PDF417 te lezen in C# met de BarCodeReader. Leer barcode‑PNG‑bestanden
  te lezen, meerdere barcodes te verwerken en uitgebreide metadata te extraheren.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: nl
lastmod: 2026-08-09
og_description: Hoe PDF417 te lezen in C# met Aspose.BarCode. Deze tutorial laat zien
  hoe je barcode‑PNG‑bestanden kunt lezen, meerdere barcodes in één afbeelding kunt
  verwerken en uitgebreide PDF417‑metadata kunt ophalen.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Hoe PDF417 te lezen in C# – barcodelezer tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Hoe PDF417 lezen in C# – volledige gids voor barcodelezers
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 lezen in C# – complete barcode lezer gids

Als je **PDF417 wilt lezen** in een .NET‑applicatie, biedt deze gids een kant‑klaar‑te‑gebruiken oplossing. Je ziet hoe je een barcode‑PNG kunt lezen, meerdere barcodes in dezelfde afbeelding kunt verwerken, en de uitgebreide PDF417‑velden kunt ophalen die veel scanners verbergen.

Het lezen van PDF417‑barcodes is gebruikelijk in logistiek, ticketverkoop en documentbeheer. Aan het einde van deze tutorial kun je een Macro PDF417‑afbeelding decoderen, elk resultaat weergeven, en de extra informatie (file ID, segment count, timestamps, enz.) gebruiken in je eigen bedrijfslogica.

## Prerequisites

- .NET 6.0 of later (de code werkt ook met .NET Framework 4.7+)
- Visual Studio 2022 of een andere C#‑IDE
- **Aspose.BarCode for .NET** (gratis proefversie of gelicentieerd NuGet‑pakket)
- Een PNG‑afbeelding die een Macro PDF417‑barcode bevat (het voorbeeldbestand heet `ExtPDF417Meta.png`)

> **Pro tip:** Installeer de bibliotheek via de NuGet‑console:  
> `dotnet add package Aspose.BarCode`

## Hoe PDF417 lezen met BarCodeReader in C#

De kern van de oplossing is de `BarCodeReader`‑klasse. Deze accepteert een pad naar een afbeelding en een `DecodeType`‑enum die de engine vertelt welke symbologie gezocht moet worden.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Waarom dit werkt

- **`DecodeType.MacroPdf417`** vertelt de lezer om te zoeken naar de Macro PDF417‑variant, die de extra velden opslaat die je ziet in stap 4.
- Het `using`‑blok ruimt de lezer automatisch op en sluit bestands­handles.
- `ReadBarCodes()` retourneert **alle** barcodes die overeenkomen met het gevraagde type, waardoor de *read multiple barcodes*‑vereiste wordt vervuld, zelfs als de afbeelding slechts één barcode bevat.

Het uitvoeren van het programma geeft een output weer die er ongeveer zo uitziet:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## C# barcode lezer gebruiken om meerdere barcodes te lezen

Bevat een afbeelding meerdere Macro PDF417‑symbolen (bijvoorbeeld een gescande pagina met een batch tickets), dan verwerkt dezelfde `foreach`‑lus elk exemplaar. Er is geen extra code nodig; de lezer verzamelt de resultaten intern.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Veelvoorkomende valkuilen

- **Image format:** De lezer ondersteunt PNG, JPEG, BMP en TIFF. Als je een formaat probeert dat niet kan worden gedecodeerd, krijg je een lege collectie. Daarom benadrukt de tutorial *read barcode PNG*.
- **Resolution:** Low‑resolution afbeeldingen (< 300 dpi) kunnen gemiste segmenten veroorzaken. Upscale of vraag een scan van hogere kwaliteit aan wanneer mogelijk.
- **Macro flag:** Het vergeten van `DecodeType.MacroPdf417` beperkt de engine tot gewone PDF417 en negeert de uitgebreide data. Specificeer altijd het macro‑type wanneer je *read barcode extended*‑velden nodig hebt.

## Barcode PNG‑bestanden lezen – best practices

Werken met PNG‑bestanden is eenvoudig omdat het formaat verliesvrije pixeldata behoudt. Hier is een snelle checklist:

1. Controleer of het bestand bestaat voordat je de lezer maakt.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Gebruik `Image.FromFile` alleen wanneer je vooraf moet bewerken (roteren, bijsnijden). De `BarCodeReader` kan het bestand direct openen, waardoor extra geheugenallocatie wordt vermeden.
3. Als de PNG transparantie bevat, werkt de lezer nog steeds omdat de barcode op ondoorzichtige pixels wordt gerenderd.

## Toegang tot uitgebreide PDF417‑metadata

Het `Extended.Pdf417`‑object maakt elk optioneel veld uit de PDF417‑specificatie beschikbaar. Je kunt deze velden naar een domeinmodel mappen, opslaan in een database, of gebruiken voor validatie.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Vul het model:



## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden gedemonstreerd. Elke bron bevat volledige werkende code‑voorbeelden met stap‑voor‑stap uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes lezen met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Hoe een barcode maken – Compact PDF417 met Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [DataMatrix‑barcode lezen C# – DataMatrix‑modus genereren (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}