---
category: general
date: 2026-11-14
description: Hur man sparar streckkod med Aspose.BarCode och lär sig att skapa streckkod
  med Aspose på några få steg. Följ den kompletta .NET‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- create barcode with aspose
language: sv
lastmod: 2026-11-14
og_description: Hur man sparar streckkod med Aspose.BarCode för .NET. Denna handledning
  visar hur du skapar en streckkod med Aspose och exporterar den till PNG.
og_image_alt: Screenshot showing how to save barcode as a PNG file
og_title: Hur man sparar streckkod som en bild – komplett Aspose.BarCode-guide
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: How to save barcode with Aspose.BarCode and learn to create barcode
    with Aspose in a few steps. Follow the complete .NET guide.
  headline: How to save barcode as an image using Aspose.BarCode for .NET
  type: TechArticle
tags:
- barcode
- Aspose
- .NET
title: Hur man sparar streckkod som en bild med Aspose.BarCode för .NET
url: /sv/net/one-dimensional-barcode-types/how-to-save-barcode-as-an-image-using-aspose-barcode-for-net/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man sparar streckkod som en bild med Aspose.BarCode för .NET

Om du behöver veta **hur man sparar streckkod** som genereras av Aspose.BarCode, så ger den här guiden en färdig‑till‑körning‑lösning. Du kommer att se hur du **skapar streckkod med Aspose**, konfigurerar MacroPdf417‑alternativ och skriver resultatet till en PNG‑fil på bara några rader C#.

Guiden täcker allt du behöver för att få en streckkodsbild på disk, från installation av biblioteket till hantering av Unicode‑data och verifiering av resultatet. Ingen extern dokumentation krävs—kopiera koden, kör den, så har du en `MacroPdf417.png`‑fil redo för vidare bearbetning.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat.
* Visual Studio 2022 (eller någon IDE som stödjer .NET).
* En NuGet‑licens för **Aspose.BarCode for .NET** (gratis provversion fungerar för utvärdering).

Du behöver också skrivrättigheter till den mapp där bilden ska sparas.

## Steg 1: Installera Aspose.BarCode

Lägg till Aspose.BarCode‑paketet i ditt projekt via NuGet:

```bash
dotnet add package Aspose.BarCode
```

Kommandot laddar ner den senaste stabila versionen och uppdaterar projektfilen. Genom att använda det officiella NuGet‑paketet får du alla nödvändiga beroenden och framtida säkerhetsuppdateringar.

## Steg 2: Skapa streckkod med Aspose.BarCode

Det första funktionella steget är att skapa en `BarcodeGenerator` som vet vilken symbologi som ska användas och vilka data som ska kodas. I detta exempel genererar vi en **MacroPdf417**‑streckkod som innehåller strängen `"Åspóse.Barcóde©"`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Create a MacroPdf417 barcode generator
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is ready for further configuration
```

*Varför detta är viktigt*: Värdet `EncodeTypes.MacroPdf417` talar om för Aspose.BarCode att producera en två‑dimensionell streckkod som stödjer segmenterade filer. Datat strängen innehåller Unicode‑tecken, vilket visar att API:et hanterar internationell text utan extra steg.

## Steg 3: Konfigurera MacroPdf417‑specifika egenskaper

MacroPdf417 lägger till metadata som låter en läsare återskapa en större fil från flera streckkodsegment. Du sätter dessa egenskaper via objektet `Parameters.Barcode.Pdf417`.

```csharp
    // Set the module width (pixel dimension of a single bar)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // MacroPdf417 configuration
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;            // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;        // bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Förklaring av nyckelfält**

| Egenskap | Syfte |
|----------|-------|
| `XDimension.Pixels` | Styr den visuella densiteten; ett värde på 2 ger en tydlig bild på de flesta skärmar. |
| `Columns` | Antal kolumner per rad; lägre värden ger en högre streckkod. |
| `MacroPdf417FileID` | Unik identifierare för hela filen över alla segment. |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 0). |
| `MacroPdf417SegmentsCount` | Totalt antal segment som utgör filen. |
| `MacroPdf417FileName` | Logiskt namn på den ursprungliga filen. |
| `MacroPdf417Checksum` | Valfri CRC‑16 för integritetsverifiering. |
| `MacroPdf417FileSize` | Förväntad storlek på den ursprungliga filen i byte. |
| `MacroPdf417TimeStamp` | Tidsstämpel som kan användas för versionering. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Mänskligt läsbara avsändar‑ och mottagaridentifierare. |
| `MacroPdf417Terminator` | Anger om streckkoden markerar slutet på filen. |

Genom att ställa in dessa alternativ säkerställer du att vilken streckkodsläsare som helst som förstår MacroPdf417 kan återskapa det ursprungliga dokumentet korrekt.

## Steg 4: Så sparar du streckkod

Nu kan du skriva den genererade bilden till disk. Metoden `Save` accepterar en filsökväg och en bildformat‑enumeration.

```csharp
    // Save the barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

*Varför detta är viktigt*: Att använda `BarCodeImageFormat.Png` ger en förlustfri bild som är lämplig för vidare bearbetning (t.ex. inbäddning i PDF‑filer eller utskick till en skrivare). `using`‑blocket disponerar generatorn automatiskt och frigör inhemska resurser.

**Förväntat resultat**

När programmet är klart visas filen `MacroPdf417.png` i körningsmappen. När du öppnar den i någon bildvisare ser du en högkontrast‑MacroPdf417‑streckkod som kodar de angivna data och den konfigurerade metadata.

## Steg 5: Verifiera den sparade streckkoden (valfritt)

Du kan snabbt verifiera att bilden innehåller en läsbar streckkod genom att ladda den med Aspose.BarCode:s `BarCodeReader`.

```csharp
using Aspose.BarCode.ReadRecognition;

// Load the saved image
using (BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.MacroPdf417))
{
    if (reader.Read())
    {
        Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        Console.WriteLine($"File ID: {reader.GetMacroPdf417FileId()}");
        Console.WriteLine($"Segment ID: {reader.GetMacroPdf417SegmentId()}");
    }
    else
    {
        Console.WriteLine("No MacroPdf417 barcode was detected.");
    }
}
```

Att köra detta kodsnutt skriver ut den ursprungliga strängen och de macro‑specifika fälten, vilket bekräftar att **hur man sparar streckkod** fungerade korrekt.

## Vanliga fallgropar och praktiska tips

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Ogiltig filsökväg | `Save` kastar `DirectoryNotFoundException` om mappen inte finns. | Skapa katalogen först: `Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!)`. |
| Unicode‑tecken visas felaktigt | Standard‑code‑page kanske inte stödjer tecknen. | Säkerställ att projektfilen riktar mot UTF‑8 (`<GenerateRuntimeConfigurationFiles>true</GenerateRuntimeConfigurationFiles>`). |
| Streckkoden är för tät för en skrivare | Mycket liten `XDimension` ger en streckkod som skannrar inte kan läsa. | Öka `XDimension.Pixels` till 3 eller 4 för högupplöst utskrift. |
| Minnesläcka i långvariga tjänster | Att inte disponera generatorn kan hålla kvar inhemska handtag. | Behåll `using`‑satsen eller anropa `generator.Dispose()` manuellt. |

## Fullt fungerande exempel

Nedan är det kompletta programmet som kombinerar alla steg. Kopiera det till ett nytt konsolprojekt och kör det.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Define output path
        string outputPath = Path.Combine(Environment.CurrentDirectory, "MacroPdf417.png");

        // Step 1–4: Generate and save the barcode
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            generator.Save(outputPath, BarCodeImageFormat.Png);
        }

        Console.WriteLine($"Barcode saved to: {outputPath}");

        // Step 5: Verify the saved image (optional)
        using (BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.MacroPdf417))
        {
            if (reader.Read())
            {
                Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
                Console.WriteLine($"File ID: {reader.Get


## Vad du bör lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar Code 128-streckkod och sparar streckkodbild med Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [Hur man skapar PDF417-streckkod och sparar den som PNG i C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Hur man skapar streckkodsbild med Aspose.Barcode – steg‑för‑steg‑guide](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}