---
category: general
date: 2026-10-18
description: Lär dig hur du skapar PDF417-streckkod i C# med Aspose.BarCode. Den här
  handledningen täcker grundläggande, kompakt, makro- och mikro-PDF417-generering
  med fullständig kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: sv
lastmod: 2026-10-18
og_description: Skapa PDF417-streckkod i C# med Aspose.BarCode. Följ den här guiden
  för att steg för steg generera grundläggande, kompakta, macro- och mikro-PDF417-streckkoder.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Skapa PDF417-streckkod i C# – komplett Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Skapa PDF417-streckkod i C# med Aspose.BarCode – steg‑för‑steg‑guide
url: /sv/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa PDF417-streckkod i C# med Aspose.BarCode – steg‑för‑steg‑guide

Om du behöver **skapa PDF417-streckkod** i en .NET-applikation, guidar den här handledningen dig genom hela processen. Du kommer att se hur du genererar en grundläggande streckkod, aktiverar kompakt läge, lägger till makro‑metadata och skapar en mikro‑variant — allt med tydliga förklaringar och körbar kod.

Att generera PDF417-streckkoder är vanligt inom logistik, biljettförsäljning och dokumenthantering. I slutet av den här guiden kommer du att kunna integrera streckkodsskapande i vilket C#‑projekt som helst utan externa verktyg.

## Förutsättningar

* .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 eller någon C#‑IDE
* **Aspose.BarCode for .NET** NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Skrivbehörighet till en mapp där de genererade PNG‑filerna kommer att sparas

Ingen ytterligare konfiguration krävs; biblioteket hanterar alla låg‑nivå‑kodningsdetaljer.

## Steg 1: Skapa en grundläggande PDF417-streckkod

Det första steget skapar en vanlig PDF417-streckkod med anpassad storlek och kolumnantal.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Varför dessa inställningar är viktiga**

* `XDimension.Pixels` styr den fysiska storleken på varje streckkodselement. Ett värde på 2 ger en tydlig bild på de flesta skärmar och skrivare.
* `Pdf417.Columns` bestämmer hur många datakolumner streckkoden innehåller. Färre kolumner minskar bredden; fler kolumner ökar datakapaciteten.

När koden körs skapas `Pdf417Basic.png`, som ser ut som en typisk PDF417‑symbol med tre datakolumner och en fullständig metadatakolumn på högra sidan.

## Steg 2: Aktivera kompakt (avkortat) läge

Kompakt läge tar bort den högra metadatakolumnen, vilket gör streckkoden smalare. Detta är användbart när utrymmet är begränsat men datan kan rekonstrueras från de återstående raderna.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Varför avkorta?**  
När `Truncate` är `true` utelämnar generatorn den valfria högra kolumnen som lagrar felkorrigering och fil‑nivå‑metadata. Den resulterande streckkoden tar upp färre kolumner samtidigt som den fortfarande kan läsas av de flesta PDF417‑läsare.

## Steg 3: Skapa en Macro PDF417-streckkod med fil‑nivå‑metadata

Macro PDF417 utökar standardformatet med segmentidentifierare, vilket möjliggör att ett stort dokument delas upp i flera streckkoder. Detta är praktiskt för att koda långa strängar eller fler‑sidiga filer.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Förklaring av makrofält**

| Egenskap | Syfte |
|----------|-------|
| `MacroPdf417FileID` | Unik identifierare för hela filen; alla segment delar detta värde. |
| `MacroPdf417SegmentID` | Index för det aktuella segmentet (börjar på 1). |
| `MacroPdf417SegmentsCount` | Totalt antal segment som utgör den kompletta datamängden. |

En scanner som förstår Macro PDF417 kan återmontera den ursprungliga datan genom att läsa alla segment och använda dessa identifierare.

## Steg 4: Skapa en Micro PDF417-streckkod för kort data

Micro PDF417 är en kompakt version avsedd för små datamängder (upp till 90 tecken). Den begränsar kolumnintervallet till 1‑4, vilket gör streckkoden lämplig för små etiketter eller enheter med begränsat displayområde.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**När du ska använda Micro PDF417**  
Använd denna variant när datamängden är kort och du behöver den minsta möjliga streckkoden. Den är idealisk för lageretiketter, åtkomstkort eller någon situation där skärm‑yta är dyrbar.

## Fullt fungerande exempel

Nedan är ett fristående konsolprogram som genererar alla fyra streckkodstyper i ett körning. Kopiera koden till ett nytt C#‑projekt, ersätt `YOUR_DIRECTORY` med en befintlig sökväg till en mapp och kör det.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Förväntat resultat**

När programmet körs skapas fyra PNG‑filer i den angivna mappen:

* `Pdf417Basic.png` – standard streckkod med tre kolumner
* `CompactPdf417.png` – samma data, avkortad högra kolumn
* `MacroPdf417.png` – makrostreckkod som innehåller segment‑metadata
* `MicroPdf417.png` – kompakt mikro‑streckkod för korta strängar

Öppna någon bild med en bildvisare; du kommer att se de distinkta PDF417‑mönstren. Att skanna dem med en mobil streckkodsläsare (t.ex. ZXing, Scandit) returnerar de ursprungliga textsträngarna.

## Vanliga frågor och tips

* **Vad händer om streckkoden ser suddig ut?**  
  Öka `XDimension.Pixels` till 3 eller 4. Större modulstorlekar ger högre upplösning, men resulterar i en större fil.

* **Kan jag exportera SVG istället för PNG?**  
  Ja. Ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Svg` i `Save`‑anropen.

* **Behöver jag ställa in felkorrigeringsnivå manuellt?**  
  Aspose.BarCode väljer automatiskt en optimal nivå. För specialiserade användningsfall kan du justera `Pdf417.ErrorCorrectionLevel`.

* **Hur bäddar jag in streckkoden i ett PDF‑dokument?**  
  Använd `Aspose.Pdf` för att lägga till den genererade PNG‑ eller SVG‑filen som ett bildelement på en PDF‑sida.

* **Är biblioteket trådsäkert?**  
  Varje `BarcodeGenerator`‑instans är oberoende; du kan skapa generatorer på flera trådar utan delat tillstånd.

## Slutsats

Du vet nu hur du **skapar PDF417-streckkod** i C# med Aspose.BarCode, och täcker grundläggande, kompakta, makro‑ och mikro‑varianter

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar pdf417-streckkod i C# – steg‑för‑steg‑guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Hur man skapar PDF417-streckkod i C# med kompakt läge](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Hur man skapar macro PDF417-streckkod i C# med Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}