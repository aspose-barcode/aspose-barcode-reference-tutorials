---
category: general
date: 2026-07-27
description: Hoe PDF417‑barcode snel te lezen in C#. Leer meerdere barcodes lezen,
  afbeeldingen decoderen en Macro PDF417‑metadata ophalen in een volledig C#‑barcode‑voorbeeld.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: nl
lastmod: 2026-07-27
og_description: Hoe PDF417‑barcode te lezen in C# met deze stap‑voor‑stap gids. Decodeer
  afbeeldingen, verwerk meerdere barcodes en extraheer Macro PDF417‑metadata in een
  kant‑en‑klare voorbeeld.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Hoe PDF417 te lezen in C# – Volledig barcode‑voorbeeld
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Hoe PDF417 in C# te lezen – Volledig barcode‑voorbeeld
url: /nl/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe PDF417 lezen in C# – Volledig Barcode‑voorbeeld

Heb je je ooit afgevraagd **hoe je PDF417**‑barcode kunt lezen in een C#‑applicatie zonder je haar uit te trekken? Je bent niet de enige. Of je nu een logistieke scanner bouwt, een ticket‑validator, of gewoon gegevens wilt halen uit een PDF417‑gecodeerde ID, het proces kan in het begin een beetje mysterieus aanvoelen.  

In deze tutorial lopen we stap voor stap door een **c# barcode example** dat een PDF417‑afbeelding leest, **read multiple barcodes** afhandelt als ze aanwezig zijn, en alle handige Macro PDF417‑metadata extraheert die je mogelijk nodig hebt.

## Wat je gaat bouwen

Aan het einde van deze gids heb je een klein console‑programma dat:

1. Een barcode‑afbeelding van de schijf laadt.  
2. **PDF417** (inclusief Macro PDF417) barcodes decodeert.  
3. Basisinformatie zoals code‑type en tekst afdrukt.  
4. De volledige set Macro PDF417‑velden (file ID, segment ID, checksum, enz.) weergeeft.  

Geen externe services, alleen één NuGet‑pakket en een paar regels C#.

## Voorwaarden – Wat je nodig hebt voordat je begint

- **.NET 6.0** of later (de code werkt ook op .NET Framework 4.6+).  
- Een recente versie van de **Aspose.BarCode for .NET**‑bibliotheek – installeer deze via NuGet (`Install-Package Aspose.BarCode`).  
- Een afbeeldingsbestand dat een PDF417‑barcode bevat (de demo gebruikt `ExtPDF417Meta.png`).  
- Een basisbegrip van C#‑console‑apps (als je “Hello World” hebt geschreven, ben je klaar).

> **Pro tip:** Als je geen PDF417‑voorbeeld bij de hand hebt, genereer er dan één op de Aspose‑demo‑site of gebruik een smartphone‑app die PDF417‑tags kan maken.

## Stap 1: Het project opzetten en de bibliotheek installeren

Maak eerst een nieuw console‑project:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Dit haalt de **c# barcode example**‑afhankelijkheden op die we nodig hebben. Open `Program.cs` en vervang de standaardcode door het onderstaande skelet:

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Stap 2: De Barcode Reader initialiseren voor PDF417

Het hart van de oplossing is de `BarCodeReader`‑klasse. We geven aan welk bestand gescand moet worden en naar welk barcode‑type we zoeken – in dit geval `DecodeType.Pdf417` of de macro‑variant `DecodeType.MacroPdf417`. Het gebruik van het macro‑type zorgt ervoor dat we de uitgebreide velden vastleggen.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Waarom `MacroPdf417` gebruiken in plaats van gewone `Pdf417`? Macro PDF417 bevat extra metadata (file ID, segment‑aantal, tijdstempels, enz.) waar veel real‑world toepassingen op vertrouwen – denk aan verzendmanifesten die over meerdere pagina’s zijn verdeeld.

## Stap 3: Alle barcodes in de afbeelding lezen

Één afbeelding kan **read multiple barcodes** bevatten — bijvoorbeeld een QR‑code naast een PDF417. De methode `ReadBarCodes()` retourneert een `IEnumerable<BarCodeResult>` die we kunnen doorlopen.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Als de afbeelding slechts één PDF417 bevat, wordt de lus nog steeds één keer uitgevoerd, waardoor de code flexibel blijft voor toekomstige scenario’s waarin je **read multiple barcodes** uit dezelfde scan moet halen.

## Stap 4: Basis‑barcode‑informatie weergeven

Voordat we de macro‑velden induiken, is het handig om het barcode‑type en de gedecodeerde tekst te tonen. Dit helpt je te verifiëren dat de lezer daadwerkelijk een PDF417 heeft herkend en niet een andere symboolset.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` zal *MacroPdf417* (of *Pdf417* als de macro‑vlag niet is gezet) lezen, terwijl `CodeText` de ruwe data bevat die in de barcode is gecodeerd.

## Stap 5: Macro PDF417‑metadata extraheren

De eigenschap `Extended` geeft je een diepgaand inzicht in de PDF417‑specifieke structuur. Elk veld dat we hieronder afdrukken komt rechtstreeks uit de PDF417‑macro‑specificatie.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Elke regel haalt een ander onderdeel van de macro‑payload op:

- **FileID** – een unieke identifier voor de volledige documentenset.  
- **SegmentID** – welk deel van het multi‑segment bestand je bekijkt.  
- **SegmentsCount** – totaal aantal verwachte segmenten.  
- **FileName, Checksum, FileSize** – nuttig voor het valideren van de integriteit van het overgebrachte bestand.  
- **TimeStamp, Addressee, Sender** – optionele velden die veel logistieke systemen embedden.  

Als een van deze velden ontbreekt in de bron‑barcode, retourneert de bibliotheek `null` of `0`, wat je naar wens kunt afhandelen.

## Stap 6: Het volledige voorbeeld uitvoeren

Alles bij elkaar, hier is het volledige, kant‑klaar programma:

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Verwachte uitvoer

Wanneer je het programma uitvoert tegen een geldige `ExtPDF417Meta.png`, zou je iets moeten zien dat lijkt op:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Als de afbeelding meer dan één barcode bevat,

## Wat moet je hierna leren?

De volgende tutorials behandelen nauw verwante onderwerpen die voortbouwen op de technieken die in deze gids worden getoond. Elke bron bevat complete werkende code‑voorbeelden met stap‑voor‑stap‑uitleg om je te helpen extra API‑functies onder de knie te krijgen en alternatieve implementatie‑benaderingen in je eigen projecten te verkennen.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}