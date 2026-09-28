---
category: general
date: 2026-07-27
description: Hur man läser PDF417‑streckkod i C# snabbt. Lär dig att läsa flera streckkoder,
  avkoda bilder och hämta Macro PDF417‑metadata i ett komplett C#‑streckkodsexempel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: sv
lastmod: 2026-07-27
og_description: Hur man läser PDF417‑streckkod i C# med den här steg‑för‑steg‑guiden.
  Avkoda bilder, hantera flera streckkoder och extrahera Macro PDF417‑metadata i ett
  färdigt exempel.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Hur man läser PDF417 i C# – Fullt streckkodsexempel
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
title: Hur man läser PDF417 i C# – Komplett streckkodsexempel
url: /sv/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man läser PDF417 i C# – Komplett streckkodsexempel

Har du någonsin undrat **hur man läser PDF417**-streckkoden i en C#‑applikation utan att rycka ur håret? Du är inte ensam. Oavsett om du bygger en logistikskanner, en biljettvaliderare eller bara behöver hämta data från ett PDF417‑kodad ID, kan processen kännas lite mystisk i början.  

I den här handledningen går vi igenom ett **c# barcode example** som läser en PDF417‑bild, hanterar **read multiple barcodes** om de finns, och extraherar all praktisk Macro PDF417‑metadata du kan behöva.

## Vad du kommer att bygga

När du är klar med guiden har du ett litet konsolprogram som:

1. Laddar en streckkodsbild från disk.  
2. Avkodar **PDF417** (inklusive Macro PDF417) streckkoder.  
3. Skriver ut grundläggande information såsom kodtyp och text.  
4. Returnerar hela uppsättningen av Macro PDF417‑fält (file ID, segment ID, checksum, osv.).  

Inga externa tjänster, bara ett enda NuGet‑paket och några rader C#.

## Förutsättningar – Vad du behöver innan du börjar

- **.NET 6.0** eller senare (koden fungerar även på .NET Framework 4.6+).  
- En aktuell version av **Aspose.BarCode for .NET**‑biblioteket – installera via NuGet (`Install-Package Aspose.BarCode`).  
- En bildfil som innehåller en PDF417‑streckkod (demot använder `ExtPDF417Meta.png`).  
- Grundläggande förståelse för C#‑konsolappar (om du har skrivit “Hello World”, är du redo).

> **Pro tip:** Om du inte har ett PDF417‑exempel till hands, generera ett på Aspose‑demowebbplatsen eller använd en smartphone‑app som kan skapa PDF417‑taggar.

## Steg 1: Skapa projektet och installera biblioteket

Börja med att skapa ett nytt konsolprojekt:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Detta hämtar de **c# barcode example**‑beroenden vi behöver. Öppna `Program.cs` och ersätt standardkoden med skelettet nedan:

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

## Steg 2: Initiera Barcode Reader för PDF417

Kärnan i lösningen är klassen `BarCodeReader`. Vi talar om för den vilken fil som ska skannas och vilken streckkodstyp vi är intresserade av – i detta fall `DecodeType.Pdf417` eller macro‑varianten `DecodeType.MacroPdf417`. Genom att använda macro‑typen säkerställer vi att de utökade fälten fångas.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Varför använda `MacroPdf417` istället för vanlig `Pdf417`? Macro PDF417 bär med sig extra metadata (file ID, segmentantal, tidsstämplar osv.) som många verkliga applikationer förlitar sig på – tänk fraktmanifest som är uppdelade på flera sidor.

## Steg 3: Läs alla streckkoder som finns i bilden

En enda bild kan innehålla **read multiple barcodes** – kanske en QR‑kod bredvid en PDF417. Metoden `ReadBarCodes()` returnerar ett `IEnumerable<BarCodeResult>` som vi kan iterera över.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Om bilden bara innehåller en PDF417 körs loopen fortfarande en gång, vilket gör koden flexibel för framtida scenarier där du kan behöva **read multiple barcodes** från samma skanning.

## Steg 4: Visa grundläggande streckkodsinformation

Innan du dyker ner i macro‑fälten är det bra att visa streckkodstypen och den avkodade texten. Detta hjälper dig verifiera att läsaren faktiskt identifierade en PDF417 och inte någon annan symbol.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` kommer att visa *MacroPdf417* (eller *Pdf417* om macro‑flaggan inte är satt), medan `CodeText` innehåller de råa data som kodats i streckkoden.

## Steg 5: Extrahera Macro PDF417‑metadata

Egenskapen `Extended` ger dig en djupdykning i PDF417‑specifik struktur. Varje fält vi skriver ut nedan motsvarar direkt macro‑specifikationen för PDF417.

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

Varje rad hämtar en annan del av macro‑payloaden:

- **FileID** – en unik identifierare för hela dokumentuppsättningen.  
- **SegmentID** – vilken del av den flerdelade filen du tittar på.  
- **SegmentsCount** – totalt antal förväntade segment.  
- **FileName, Checksum, FileSize** – användbara för att validera integriteten hos den överförda filen.  
- **TimeStamp, Addressee, Sender** – valfria fält som många logistiksystem bäddar in.  

Om något av dessa fält saknas i källstreckkoden returnerar biblioteket `null` eller `0`, vilket du kan hantera efter behov.

## Steg 6: Kör det kompletta exemplet

Sätter vi ihop allt får du följande färdiga, körklara program:

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

### Förväntad utskrift

När du kör programmet mot en giltig `ExtPDF417Meta.png` bör du se något i stil med:

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

Om bilden innehåller mer än en streckkod,


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar PDF417-streckkoder – Kompakt PDF417-kodning](/barcode/english/net/compact-pdf417-encoding/)
- [Hur man skapar streckkod – Kompakt PDF417 med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hur man läser DataMatrix-streckkoder med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}