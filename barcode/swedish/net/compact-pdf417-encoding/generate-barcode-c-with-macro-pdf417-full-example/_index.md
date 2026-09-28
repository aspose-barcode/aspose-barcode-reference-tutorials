---
category: general
date: 2026-08-19
description: Generera streckkod i C# med Aspose.BarCode för att skapa en Macro PDF417
  med anpassad text och spara den som en bildfil.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: sv
lastmod: 2026-08-19
og_description: Generera streckkod i C# med Aspose.BarCode, lär dig hur du genererar
  PDF417, lägg till anpassad text och spara streckkodens bildfil.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Generera streckkod C# – Macro PDF417‑guide
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generera streckkod C# med Macro PDF417 – fullständigt exempel
url: /sv/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generera streckkod C# med Macro PDF417 – fullständigt exempel

Om du behöver **generera streckkod C#** för ett Macro PDF417‑format, visar den här guiden en färdig‑att‑köra‑lösning. Du får se hur du **genererar pdf417**, bäddar in anpassad text och **genererar streckkod bildfil** i ett enda, självständigt program.

Handledningen täcker allt från installation av Aspose.BarCode‑biblioteket till konfiguration av Macro PDF417‑metadata, så att du kan kopiera koden direkt in i ditt projekt och se resultatet omedelbart.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
- Visual Studio 2022 (eller någon IDE som stödjer C#)
- En Aspose.BarCode för .NET‑licens (den kostnadsfria provversionen fungerar för utvärdering)
- Grundläggande kunskap om C#‑syntax

> **Proffstips:** Installera NuGet‑paketet via CLI för att undvika versionskonflikter:  
> `dotnet add package Aspose.BarCode`

## Steg 1: Ställ in projektet och importera biblioteket

Skapa en ny konsolapplikation och lägg till de nödvändiga `using`‑direktiven.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Varför detta steg är viktigt:**  
`Aspose.BarCode.Generation`‑namnutrymmet tillhandahåller `BarcodeGenerator`‑klassen, som är ingångspunkten för att skapa vilken streckkodstyp som helst, inklusive Macro PDF417. Genom att importera `System` får du tillgång till `DateTime` för tidsstämpel‑metadata.

## Steg 2: Skapa en Macro PDF417‑generator med anpassad text

Ersätt platshållarkommentaren med generatorns initiering. Detta demonstrerar **skapa streckkod anpassad text** samtidigt som rätt kodningstyp väljs.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Förklaring:**  
- `EncodeTypes.MacroPdf417` talar om för Aspose att producera en PDF417‑streckkod som stödjer makro‑funktioner (filsegmentering, kontrollsumma osv.).  
- Texten `"Åspóse.Barcóde©"` visar att Unicode‑tecken stöds fullt ut, vilket ofta krävs för internationella applikationer.

## Steg 3: Konfigurera utseende och Macro PDF417‑metadata

Finjustera streckkodens dimensioner och ange de makro‑specifika fälten som krävs för hantering av segmenterade filer.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Varför dessa inställningar är viktiga:**

| Inställning | Syfte |
|-------------|-------|
| `XDimension.Pixels` | Styr den visuella densiteten; 2 px ger en klar, avläsbar bild. |
| `Columns` | Bestämmer hur många datakolumner som visas per rad, vilket påverkar streckkodens storlek. |
| `MacroPdf417FileID` | Identifierar den logiska filen unikt över alla segment. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Möjliggör återuppbyggnad av den ursprungliga filen från flera streckkoder. |
| `MacroPdf417FileName` | Mänskligt läsbart namn lagrat i streckkoden för efterföljande bearbetning. |
| `MacroPdf417Checksum` | Ger felupptäckt med CCITT‑16 CRC‑algoritmen. |
| `MacroPdf417FileSize` | Hjälper avkodaren att veta när hela filen har mottagits. |
| `MacroPdf417TimeStamp` | Registrerar när streckkoden genererades, användbart för revisionsspår. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Valfria fält som kan användas i affärsarbetsflöden. |
| `MacroPdf417Terminator` | Indikerar att detta segment är det sista (`Set`). |

## Steg 4: Spara streckkoden som en bildfil

Slutligen, skriv streckkoden till en PNG‑fil så att du kan visa eller bädda in den någon annanstans.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Vad du kommer att se:**  
En PNG‑bild med namnet `ExtPDF417Meta.png` som innehåller en Macro PDF417‑streckkod som kodar den anpassade texten och alla metadatafält du angav ovan. Bilden kan öppnas med vilken standardvisare som helst eller infogas i PDF‑filer, rapporter eller webbsidor.

## Fullständig källkod (klar för kopiering och inklistring)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Förväntat resultat

När programmet körs skrivs:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

När du öppnar `ExtPDF417Meta.png` visas en ren Macro PDF417‑streckkod som skannas korrekt med vilken PDF417‑läsare som helst, och bevarar den anpassade texten `"Åspóse.Barcóde©"` samt den makro‑metadata du definierade.

## Vanliga frågor och specialfall

- **Kan jag generera ett annat bildformat?**  
  Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` efter behov.

- **Vad händer om mina data överskrider en enda streckkod?**  
  Macro PDF417 är designad för segmentering. Justera `MacroPdf417SegmentsCount` och `MacroPdf417SegmentID` för varje del, och sammanfoga sedan de skannade resultaten.

- **Är Unicode‑stöd garanterat?**  
  Aspose.BarCode stödjer Unicode fullt ut. Se till att din källfil sparas med UTF‑8‑kodning för att undvika teckenkorruption.

- **Behöver jag en licens för produktion?**  
  En licensierad version tar bort utvärderingsvattenstämpeln och ger full funktionalitet. Provanvändningen fungerar för testning och lärande.

## Slutsats

Du vet nu hur du **genererar streckkod C#** för en Macro PDF417, **genererar pdf417** med rik metadata, **skapar streckkod anpassad text** och **genererar streckkod bildfil** med Aspose.BarCode. Det kompletta, körbara exemplet demonstrerar varje nödvändigt steg — från projektuppsättning till att spara den slutliga PNG‑bilden.

### Nästa steg

- Experimentera med andra PDF417‑inställningar såsom `ErrorCorrectionLevel` och `CompactPdf417` för mindre symboler.  
- Integrera den genererade streckkoden i en PDF‑rapport med Aspose.PDF.  
- Utforska batch‑generering: loopa över en samling filer och producera en serie av segmenterade Macro PDF417‑streckkoder.

Känn dig fri att anpassa koden för ditt eget arbetsflöde, och låt streckkodsgenereringen bli en sömlös del av dina C#‑applikationer. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Generera streckkod bild – Code 93 med Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Hur man genererar och justerar streckkodshöjd för endimensionell Databar med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}