---
category: general
date: 2026-09-19
description: Hur man avkodar PDF417 i C# – lär dig att läsa streckkoder från en bild
  med ett koncist streckkodsläsarexempel som extraherar fullständig Macro PDF417-data.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: sv
lastmod: 2026-09-19
og_description: Hur man avkodar PDF417 i C# med ett steg‑för‑steg streckkodsläsarexempel.
  Extrahera varje Macro PDF417‑fält från en bild på några sekunder.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Hur man avkodar PDF417 i C# – fullständig guide för streckkodsläsare
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Hur man avkodar PDF417 i C# med ett exempel på streckkodsläsare
url: /sv/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man avkodar PDF417 i C# med ett streckkodsläsare‑exempel

Om du behöver avkoda PDF417 i C#, visar den här guiden exakt hur du avkodar PDF417 från en bildfil. Du kommer att lära dig att läsa streckkoder från en bild, komma åt de utökade Macro PDF417‑fälten och integrera lösningen i ett .NET‑projekt.

Avkodning av PDF417‑streckkoder är vanligt inom logistik, biljettförsäljning och identitetsverifiering. Denna handledning täcker allt som krävs för en produktionsklar implementation, inklusive förutsättningsbibliotek, fullständig källkod och tips för att hantera kantfall.

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6.0 eller senare installerat  
- Visual Studio 2022 (eller någon IDE som stödjer C#)  
- NuGet‑paketet **Aspose.BarCode for .NET** (version 23.11 eller nyare)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

`BarCodeReader`‑klassen från detta bibliotek stödjer avkodningstypen `MacroPdf417` som behövs för full PDF417‑extraktion.

## Steg 1: Hur man avkodar PDF417 i C# – initiera läsaren

Det första steget skapar en `BarCodeReader`‑instans som riktar sig mot en Macro PDF417‑bild. Flaggan `DecodeType.MacroPdf417` talar om för biblioteket att tolka de utökade Macro‑fälten.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Varför detta är viktigt:** Genom att initiera med `MacroPdf417` aktiveras egenskapen `Extended.Pdf417` på varje `BarCodeResult`, vilket ger dig åtkomst till metadata på filnivå såsom segment‑ID:n och tidsstämplar.

## Steg 2: Läs streckkoder från bild

En PDF417‑bild kan innehålla flera macro‑segment. Metoden `ReadBarCodes()` returnerar en samling av alla upptäckta streckkoder, så du kan iterera över dem på ett säkert sätt.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Tips:** Om du bara förväntar dig en enda streckkod kan du bryta efter den första iterationen, men att iterera över alla resultat garanterar att du fångar varje segment i flersidiga dokument.

## Steg 3: Avkoda PDF417‑streckkod – extrahera grundläggande och utökad data

Inuti loopen, skriv ut både den generiska streckkodsinformationen och de Macro‑specifika fälten. Objektet `Extended.Pdf417` innehåller varje metadata‑del som definieras av PDF417‑standarden.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
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
    }
}
```

**Förklaring av nyckelfält**

| Fält | Betydelse |
|-------|----------|
| `MacroPdf417FileID` | Identifierare som grupperar alla segment som tillhör samma logiska fil |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 0) |
| `MacroPdf417SegmentsCount` | Totalt antal segment som förväntas för filen |
| `MacroPdf417FileName` | Valfritt filnamn inbäddat i macro |
| `MacroPdf417Checksum` | CRC‑16‑kontrollsumma för dataintegritet |
| `MacroPdf417FileSize` | Ursprunglig filstorlek i byte |
| `MacroPdf417TimeStamp` | Tidsstämpel när macro genererades |
| `MacroPdf417Addressee` | Avsedd mottagare av macro‑data |
| `MacroPdf417Sender` | Avsändare av macro‑data |
| `MacroPdf417Terminator` | Boolesk flagga som indikerar sista segmentet |

Genom att ha åtkomst till dessa fält kan du återskapa det ursprungliga dokumentet, verifiera integriteten eller dirigera data baserat på avsändar‑/mottagarinformation.

## Steg 4: Komplett C#‑streckkodsläsarexempel – sätt ihop allt

Nedan är det fullständiga, körbara programmet. Ersätt `YOUR_DIRECTORY` med mappen som innehåller din `MacroPdf417.png`‑fil.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
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

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Förväntad konsolutskrift (exempel)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

De exakta värdena kommer att skilja sig beroende på innehållet i din Macro PDF417‑streckkod.

## Hantera vanliga kantfall

| Situation | Rekommenderad åtgärd |
|-----------|----------------------|
| **Ingen streckkod upptäckt** | Verifiera bildens sökväg, säkerställ att filen inte är korrupt och bekräfta att streckkoden är synlig (tillräcklig kontrast). |
| **Delvisa macro‑segment** | Använd `MacroPdf417SegmentsCount` för att upptäcka saknade delar. Du kan begära de återstående segmenten från källsystemet och köra avkodaren igen. |
| **Stora bilder som orsakar minnespress** | Läs in bilden i en `System.Drawing.Bitmap` med reducerad upplösning innan du skickar den till `BarCodeReader`. |
| **Icke‑Macro PDF417** | Ändra `DecodeType.MacroPdf417` till `DecodeType.Pdf417` om du bara behöver den enkla streckkodstexten. |

## Pro‑tips

- **Batch‑bearbetning:** Packa in läsarlogiken i en metod som accepterar en lista med filsökvägar. Återanvänd en enda `BarCodeReader`‑instans per tråd för att minska allokeringskostnaden.  
- **Prestanda:** För scenarier med hög genomströmning, aktivera egenskapen `ReadQuality` i `ReaderOptions` för att balansera hastighet mot noggrannhet.  
- **Säkerhet:** Validera `CodeText` innan du använder den i filsystemoperationer för att förhindra path‑traversal‑attacker.

## Slutsats

I den här handledningen lärde du dig hur man avkodar PDF417 i C# genom att läsa streckkoder från en bild, extrahera varje Macro PDF417‑fält och bygga ett komplett C#‑streckkodsläsarexempel. Lösningen fungerar med det senaste Aspose.BarCode‑biblioteket, hanterar multi‑segment‑macroer och ger praktisk vägledning för verkliga projekt.

Nästa steg, utforska relaterade ämnen som **läsa QR‑koder**, **batch‑streckkodsbearbetning** och **generera PDF417‑streckkoder** för att bredda ditt verktyg för dokument‑automation. Känn dig fri att experimentera med olika bildkällor, integrera koden i ASP.NET‑tjänster eller utöka den för att lagra den extraherade metadata i en databas. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man läser PDF417 i C# – komplett streckkodsläsarexempel](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Hur man genererar PDF417‑streckkodbild i C# med Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Läs streckkod från bild – C#‑streckkodsläsarexempel](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}