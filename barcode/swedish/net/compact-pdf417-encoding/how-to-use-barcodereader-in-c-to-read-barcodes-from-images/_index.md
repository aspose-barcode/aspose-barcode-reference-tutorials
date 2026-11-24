---
category: general
date: 2026-11-23
description: Lär dig hur du använder BarCodeReader i C# för att läsa streckkoder från
  en bild, inklusive Macro PDF417‑avkodning, med ett komplett kodexempel och tydliga
  förklaringar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: sv
lastmod: 2026-11-23
og_description: Hur man använder BarCodeReader i C# för att läsa streckkoder från
  en bild. Följ den här steg‑för‑steg‑guiden för att avkoda Macro PDF417 och andra
  format med färdig‑körbar kod.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Hur man använder BarCodeReader i C# – läs streckkoder från bilder snabbt
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Hur man använder BarCodeReader i C# för att läsa streckkoder från bilder
url: /sv/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder BarCodeReader i C# för att läsa streckkoder från bilder

Om du behöver **how to use BarCodeReader** för en snabb streckkodsskanning, visar den här guiden exakt det. Oavsett om du bygger ett kassasystem eller automatiserar dokumentintag, kommer du att lära dig hur du läser streckkoder från bild‑C#‑projekt med bara några rader kod.

I den här handledningen kommer du att se ett komplett, körbart exempel som avkodar en Macro PDF417‑streckkod, extraherar dess utökade egenskaper och skriver ut användbar information till konsolen. Ingen extern dokumentation krävs – allt du behöver finns här.

## Förutsättningar

* .NET 6.0 (eller senare) installerat – koden riktar sig mot den senaste LTS‑versionen.
* En referens till **Aspose.BarCode** (eller någon kompatibel) NuGet‑paket som tillhandahåller `BarCodeReader`.
* En bildfil som innehåller en Macro PDF417‑streckkod (exemplet använder `ExtPDF417Meta.png`).

> **Pro tip:** Om du använder Visual Studio, lägg till paketet via `dotnet add package Aspose.BarCode` eller NuGet Package Manager‑gränssnittet.

## Steg 1: Skapa en BarCodeReader‑instans

Det första du gör när du arbetar med ett streckkodsbibliotek är att instansiera en läsare som pekar på källbilden och talar om för API‑et vilka streckkodstyper som ska sökas efter.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Varför detta steg är viktigt:*  
`BarCodeReader` öppnar bilden, allokerar native minne och förbereder avkodningsalgoritmer för den specificerade `DecodeType`. Genom att begränsa typen till `MacroPdf417` minskar du CPU‑belastningen och förbättrar detekteringsnoggrannheten.

## Steg 2: Läs alla streckkoder som hittas i bilden

En enda bild kan innehålla flera streckkoder, särskilt när du hanterar makro‑kodad data. Metoden `ReadBarCodes` returnerar en enumerable av `BarCodeResult`‑objekt, där varje representerar en upptäckt kod.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Varför detta steg är viktigt:*  
Att iterera över samlingen säkerställer att du fångar varje instans, vilket är avgörande för batch‑behandlingsscenarier eller när ett dokument inbäddar flera koder.

## Steg 3: Åtkomst till de utökade Macro PDF417‑egenskaperna

Macro PDF417 lagrar extra metadata såsom filidentifierare, segmentnummer och totalt antal segment. Dessa värden exponeras via `Extended.Pdf417`‑egenskapen i `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Varför detta steg är viktigt:*  
De utökade fälten låter dig återskapa flerdelade dokument eller validera att alla delar tillhör samma källa. Att hoppa över detta steg ger dig bara den råa texten och förlorar värdefull kontext.

## Steg 4: Skriv ut den mest användbara informationen

Slutligen, skriv data till konsolen (eller någon logger) så att du kan verifiera läsoperationen. Exemplet skriver ut kodtypen, avkodad text och flera makrofält.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Förväntad konsolutmatning**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Obs:** Om bilden inte innehåller en Macro PDF417‑streckkod, returnerar `ReadBarCodes()` en tom samling och loop‑kroppen körs aldrig. Kontrollera alltid att resultatet inte är tomt i produktionskod.

## Läs streckkoder från bild i C# – hantera vanliga scenarier

### 1. Avkoda flera streckkodformat

Om du behöver upptäcka mer än ett format, skicka en kombinerad `DecodeType`‑flagga:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Hantera stora bilder

Stora bilder kan orsaka hög minnesanvändning. Skala ner bilden innan du skickar den till läsaren:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Felhantering

Omslut läslogiken i ett try‑catch‑block för att visa avkodningsfel:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Fullt fungerande exempel

Nedan är det kompletta programmet som du kan kopiera, klistra in och köra. Det inkluderar alla steg, nödvändiga `using`‑direktiv och en enkel felhanteringsstruktur.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Kör programmet** skriver ut varje upptäckt Macro PDF417‑streckkod och dess utökade fält, eller informerar dig om att inga streckkoder hittades.

## Slutsats

Du vet nu **how to use BarCodeReader** för att läsa streckkoder från bild‑C#‑applikationer, inklusive extrahering av Macro PDF417‑metadata. Lösningen täcker initialisering, iteration, åtkomst till utökade egenskaper och praktiska tips för att hantera flera format, stora bilder och fel.

Nästa steg kan du utforska:

* **Reading QR codes** – ersätt `DecodeType.MacroPdf417` med `DecodeType.QR`.
* **Saving decoded data** till en databas eller JSON‑fil för efterföljande bearbetning.
* **Integrating with ASP.NET Core** för att ta emot uppladdade bilder via ett webb‑API.

Känn dig fri att experimentera med olika streckkodstyper och bildkällor. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [c# streckkodsläsarhandledning – läs Macro PDF417‑streckkoder steg för steg med GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Hur man använder en streckkodsgenerator C# för Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Läs streckkod från bild C# – komplett guide med Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}