---
category: general
date: 2026-11-23
description: Lär dig hur du genererar streckkodbild med Aspose.BarCode för .NET med
  MacroPdf417‑metadata i C#. Följ den kompletta steg‑för‑steg‑guiden.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: sv
lastmod: 2026-11-23
og_description: Hur man genererar streckkodsbild med Aspose.BarCode för .NET. Denna
  handledning visar konfiguration av MacroPdf417-metadata och C#-streckkodsgenerering.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Hur man genererar en streckkodsbild med MacroPdf417 i C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Hur man genererar en streckkodsbild med MacroPdf417 i C#
url: /sv/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkodbild med MacroPdf417 i C#

Om du behöver **generera streckkodbild** i en .NET-applikation visar den här guiden exakt hur du gör det med **Aspose.BarCode for .NET**. Vi går igenom att skapa en **MacroPdf417 streckkod**, konfigurera dess metadata och spara resultatet som en PNG‑fil.

Denna handledning täcker allt från installation av biblioteket till att skriva ett komplett, körbart konsolprogram. I slutet har du ett färdigt kodexempel som producerar en högkvalitativ streckkodbild, och du förstår hur du **ställer in streckkodmetadata**, väljer ett **streckkodbildformat** och felsöker vanliga fallgropar. Ingen förhandserfarenhet av Aspose krävs – bara grundläggande kunskap om C#.

## Installera Aspose.BarCode för .NET

Innan du kan **generera streckkodbild** behöver du Aspose.BarCode NuGet‑paketet.

1. Öppna en terminal eller Package Manager Console i Visual Studio.  
2. Kör följande kommando:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till namnutrymmet `Aspose.BarCode.Generation`, som innehåller klassen `BarcodeGenerator` som används för **C# barcode generation**.

> **Proffstips:** Använd den senaste stabila versionen (från och med november 2026 är den aktuella versionen 24.11) för att få de nyaste funktionerna och buggfixarna.

## Skapa BarcodeGenerator‑instansen

Det första kodsteget skapar en `BarcodeGenerator` konfigurerad för **MacroPdf417 streckkod**‑typen och levererar den datasträng du vill koda.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

`using`‑blocket säkerställer att generatorn avyttras korrekt och frigör eventuella ohanterade resurser.

## Konfigurera grundläggande utseende

En läsbar streckkod börjar med rimliga dimensioner. Här sätter vi pixelbredden för varje modul (`XDimension`) och antalet kolumner för PDF417‑matrisen.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Varför dessa värden?*  
- **XDimension** styr hur tjock varje stapel blir; 2 pixlar fungerar bra för skärmvisning och de flesta skrivare.  
- **Columns** påverkar den totala bredden; ett litet kolumnantal håller streckkoden kompakt samtidigt som felkorrigeringskapaciteten bevaras.

## Ställ in streckkodmetadata (MacroPdf417 specifikt)

MacroPdf417 låter dig bädda in fil‑nivåinformation direkt i streckkoden. Här **ställer du in streckkodmetadata** såsom fil‑ID, segment‑ID och tidsstämplar.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Vad varje egenskap betyder

| Egenskap | Syfte |
|----------|-------|
| **MacroPdf417FileID** | Unik identifierare för den logiska filen som streckkoden tillhör. |
| **MacroPdf417SegmentID** | Index för det aktuella segmentet (0‑baserat). |
| **MacroPdf417SegmentsCount** | Totalt antal segment som utgör hela filen. |
| **MacroPdf417FileName** | Mänskligt läsbart namn på källfilen. |
| **MacroPdf417Checksum** | Valfri CCITT‑16 kontrollsumma för verifiering av dataintegritet. |
| **MacroPdf417FileSize** | Förväntad storlek på den ursprungliga filen i byte. |
| **MacroPdf417TimeStamp** | Datum och tid då streckkoden genererades – användbart för versionsspårning. |
| **MacroPdf417Addressee / Sender** | Anpassade strängar som kan innehålla routningsinformation. |
| **MacroPdf417Terminator** | Anger om detta segment är det sista (`Set`) eller inte (`Unset`). |

> **Särskilt fall:** Om du planerar att dela ett stort dokument i många segment, håll `SegmentsCount` konsekvent i alla genererade streckkoder. Mismatchade räknare leder till avkodningsfel.

## Välj streckkodens bildformat och spara

Aspose stödjer många **barcode image formats** (PNG, JPEG, BMP, TIFF, osv.). PNG är förlustfri och fungerar bra för de flesta webb‑ och utskrifts‑scenarier.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Byt ut `YOUR_DIRECTORY` mot en absolut eller relativ mapp där applikationen har skrivbehörighet.

När programmet körs bör du se ett konsolmeddelande som bekräftar filens plats. Öppna PNG‑filen med någon bildvisare – du ser en skarp **MacroPdf417 streckkod** som kodar den angivna texten och den metadata du definierade.

### Förväntat resultat

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Bildfilens storlek blir ungefär 30‑40 KB, beroende på valt `XDimension` och kolumnantal.

## Verifiera streckkoden och felsök

1. **Visuell inspektion** – Streckkoden ska visa en serie staplade kolumner med ett tyst område (vitt marginal) runt omkring.  
2. **Avkodningstest** – Använd en streckkodsläsarapp eller Aspose.BarCode `BarCodeReader`‑klassen för att läsa tillbaka bilden och bekräfta att alla metadatafält är korrekt inbäddade.  



## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera PDF417 streckkodbild med Aspose.BarCode i C# – steg‑för‑steg guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Hur man genererar streckkod med anpassad text med Aspose.BarCode för .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Hur man läser streckkoder från bild med C# och Aspose.BarCode – steg‑för‑steg guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}