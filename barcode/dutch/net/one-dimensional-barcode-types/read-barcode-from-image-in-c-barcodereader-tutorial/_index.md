---
category: general
date: 2026-08-15
description: Lees een barcode van een afbeelding in C# met BarCodeReader. Leer hoe
  je meerdere barcodes in C# kunt lezen, een PDF417‑barcode kunt lezen, en bekijk
  een volledig C# BarCodeReader‑voorbeeld.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: nl
lastmod: 2026-08-15
og_description: Lees een barcode van een afbeelding in C# met een stapsgewijze handleiding.
  Ontdek hoe je meerdere barcodes in C# kunt lezen, PDF417‑symbolen kunt decoderen
  en een volledig C# BarCodeReader‑voorbeeld kunt uitvoeren.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Barcode lezen van afbeelding in C# – BarCodeReader tutorial
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Barcode lezen uit afbeelding in C# – BarCodeReader‑tutorial
url: /nl/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode lezen van afbeelding in C# – BarCodeReader tutorial

Als je een **barcode van afbeelding** moet lezen in een .NET‑applicatie, laat deze gids je precies zien hoe je dat doet met de `BarCodeReader`‑klasse. Je ziet ook hoe je **meerdere barcodes C#** kunt lezen, een PDF417‑symbool decodeert, en een volledige **C# BarCodeReader‑voorbeeld** krijgt die je in je project kunt kopiëren.

De tutorial behandelt elke stap — van het toevoegen van het vereiste NuGet‑pakket tot het afdrukken van uitgebreide PDF417‑velden — zodat je eindigt met een uitvoerbaar console‑programma. Er is geen externe documentatie nodig; alle code en uitleg zijn inbegrepen.

## Wat je nodig hebt

* .NET 6.0 SDK of later (de code werkt met .NET Core en .NET Framework)
* Visual Studio 2022 of een C#‑compatible editor
* Het `Aspose.BarCode` NuGet‑pakket (of de equivalente bibliotheek die `BarCodeReader` levert)
* Een afbeeldingsbestand dat een Macro PDF417‑barcode bevat (bijv. `ExtPDF417Meta.png`)

Het hebben van deze vereisten zorgt ervoor dat het voorbeeld compileert zonder extra configuratie.

## Barcode lezen van afbeelding met BarCodeReader

De eerste stap is het aanmaken van een `BarCodeReader`‑instantie die naar het afbeeldingsbestand wijst en de bibliotheek vertelt naar welk barcode‑type gezocht moet worden.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Waarom dit werkt:**  
`BarCodeReader` opent de afbeelding, scant naar het opgegeven `DecodeType` en retourneert een collectie van `BarCodeResult`‑objecten. Elk resultaat bevat de generieke barcode‑gegevens (`CodeTypeName`, `CodeText`) en, voor Macro PDF417, een `Extended.Pdf417`‑object dat alle extra velden die door de standaard zijn gedefinieerd, blootlegt.

## Meerdere barcodes C# lezen in één afbeelding

Soms bevat een afbeelding meer dan één barcode (bijv. een QR‑code naast een PDF417). Om dat scenario te behandelen, laat je eenvoudigweg de expliciete `DecodeType` weg of geef je `DecodeType.AllSupported` door en loop je door de resultaten.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Waarom je dit nodig hebt:**  
Het specificeren van `AllSupported` vertelt de engine om elk barcode‑formaat dat hij kent te proberen, wat garandeert dat je elk symbool in de afbeelding vastlegt. Dit is de aanbevolen aanpak wanneer je de barcode‑types van tevoren niet kunt voorspellen.

## Hoe PDF417‑barcode te lezen met C#

Als je alleen geïnteresseerd bent in het klassieke PDF417 (niet‑macro) formaat, wijzig je de `DecodeType` naar `Pdf417`. De rest van de code blijft identiek, behalve dat de uitgebreide velden niet beschikbaar zijn.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Waarom dit belangrijk is:**  
Klassiek PDF417 exposeert de macro‑specifieke eigenschappen niet, dus het `Extended.Pdf417`‑blok is overbodig. Het gebruik van de precieze `DecodeType` versnelt ook het scannen omdat de bibliotheek niet‑ondersteunde algoritmen overslaat.

## Volledig C# BarCodeReader‑voorbeeld dat je kunt kopiëren

Hieronder staat het volledige programma dat de drie scenario's combineert in één gemakkelijk uit te voeren console‑applicatie. Vervang `YOUR_DIRECTORY/ExtPDF417Meta.png` door het daadwerkelijke pad naar je afbeelding.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Verwachte output

Wanneer de voorbeeldafbeelding een Macro PDF417‑barcode bevat, print de console iets vergelijkbaars met:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Als de afbeelding alleen een reguliere PDF417 bevat, zal de “Macro PDF417” sectie leeg zijn, en zal de “Classic PDF417” sectie de gedecodeerde tekst weergeven.

## Conclusie

Je weet nu hoe je **barcode van afbeelding** kunt lezen in C# met `BarCodeReader`, hoe je **meerdere barcodes C#** kunt lezen in één bestand, en de exacte stappen om **PDF417‑barcode** te lezen — zowel macro‑ als klassieke varianten. Het volledige **C# BarCodeReader‑voorbeeld** is klaar om in elk .NET‑project te plakken, en je kunt het uitbreiden om andere formaten te verwerken of te integreren in een grotere beeld‑verwerkings‑pipeline.

**Volgende stappen**

* Verken foutafhandelings‑patronen zoals `try / catch` rond het reader‑blok.  
* Experimenteer met het `ReaderParameters`‑object om detectiesnelheid en nauwkeurigheid af te stemmen.  
* Combineer barcode‑lezen met beeld‑preprocessing‑bibliotheken (

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat volledige werkende code‑voorbeelden met stapsgewijze uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [Hoe DataMatrix‑barcodes te lezen met Aspose.BarCode voor .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix‑barcode lezen C# – DataMatrix‑modus genereren (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Barcode lezen van afbeelding – Barcode‑regio‑extractie beheersen in Java met Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}