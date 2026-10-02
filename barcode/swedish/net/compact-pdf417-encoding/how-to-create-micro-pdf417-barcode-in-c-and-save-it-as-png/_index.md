---
category: general
date: 2026-10-02
description: Lär dig hur du skapar en micro‑pdf417‑streckkod i C# och snabbt genererar
  en PNG‑bild av streckkoden. Inkluderar steg‑för‑steg‑kod och bästa praxis.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- barcode generation C#
- MicroPdf417 settings
- C# image export
language: sv
lastmod: 2026-10-02
og_description: Skapa micro‑pdf417‑streckkod i C# och generera en streckkod som PNG‑bild.
  Följ den här kompletta guiden för att producera högkvalitativa streckkods‑filer.
og_image_alt: C# code generating a MicroPdf417 barcode saved as PNG
og_title: Skapa mikro‑PDF417‑streckkod i C# – komplett guide för att generera PNG
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create micro pdf417 barcode in C# and generate a barcode
    PNG image quickly. Includes step‑by‑step code and best practices.
  headline: How to create micro pdf417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Hur man skapar en micro‑pdf417‑streckkod i C# och sparar den som PNG
url: /sv/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar micro pdf417 streckkod i C# och sparar den som PNG

Om du behöver **skapa micro pdf417 streckkod** för en etikett, biljett eller mobilskanning, visar den här guiden exakt hur du gör det i C#. Du får också lära dig **hur du genererar barcode png**‑filer som kan bäddas in i webbsidor eller skrivas ut direkt från din applikation.

Vi går igenom alla nödvändiga inställningar, från att initiera generatorn till att välja rätt X‑dimension och kolumnantal. I slutet av tutorialen har du ett färdigt C#‑exempel som producerar en skarp PNG‑bild av en MicroPdf417‑streckkod.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Core 3.1+)
* Visual Studio 2022 eller någon C#‑kompatibel IDE
* **Aspose.BarCode for .NET** NuGet‑paketet (eller ett bibliotek som stödjer `EncodeTypes.MicroPdf417`). Installera det med:

```bash
dotnet add package Aspose.BarCode
```

* Skrivbehörighet till den mapp där du avser att spara PNG‑filen.

Ingen extra konfiguration krävs; biblioteket hanterar all låg‑nivå bildbehandling.

## Steg 1: Initiera generatorn för en MicroPdf417‑streckkod

Den första raden skapar en `BarcodeGenerator`‑instans som vet att den ska koda en MicroPdf417‑symbol. Texten du anger kan innehålla Unicode‑tecken, som biblioteket kodar automatiskt.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator with the desired text
var generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 barcode type
    "Åspóse.Barcóde©");               // Sample data containing special characters
```

*Varför detta är viktigt*: Att välja `EncodeTypes.MicroPdf417` talar om för motorn att använda den kompakta MicroPdf417‑specifikationen, vilket är idealiskt för små etiketter samtidigt som felkorrigering stöds.

## Steg 2: Definiera X‑dimensionen (modulstorlek) i pixlar

X‑dimensionen bestämmer bredden på den minsta stapeln (”modulen”). Ett värde på `2` pixlar ger en tät men fortfarande läsbar streckkod.

```csharp
// Set the module size (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tips*: Större X‑dimensioner ökar den totala bildstorleken, vilket kan vara användbart för lågupplösta skrivare. Håll den på 2–4 px för de flesta skärm‑display‑scenarier.

## Steg 3: Ange antal kolumner (maximalt 4 för MicroPdf417)

MicroPdf417 tillåter upp till fyra kolumner. Fler kolumner ger en kortare streckkodshöjd men en bredare bild.

```csharp
// Configure the number of columns (max 4 for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Varför du kan vilja justera detta*: Om din etikettbredd är begränsad, minska kolumnantalet. Omvänt, öka antalet kolumner för att förkorta streckkoden när höjden är begränsande.

## Steg 4: Spara den genererade streckkoden som en PNG‑bild

Till sist exporterar du streckkoden till en PNG‑fil. PNG bevarar exakt pixeldata utan komprimeringsartefakter, vilket gör den perfekt för skarp streckkodsrendering.

```csharp
using Aspose.BarCode;

// Define the output path (ensure the directory exists)
string outputPath = Path.Combine(
    Environment.CurrentDirectory, "MicroPdf417.png");

// Save as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to: {outputPath}");
```

**Förväntat resultat** – Efter att programmet har körts hittar du `MicroPdf417.png` i din projektmapp. När du öppnar filen ser du en tydlig MicroPdf417‑streckkod som kodar strängen `Åspóse.Barcóde©`.

## Hur man genererar barcode PNG med olika bildformat (valfritt)

Även om PNG är det vanligaste formatet för streckkodsbilder, stödjer samma `Save`‑metod JPEG, BMP och TIFF. För att **how to generate barcode png** i ett annat format, ändra bara `BarCodeImageFormat`‑enum:

```csharp
// Save as JPEG instead of PNG
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

Kom ihåg att JPEG introducerar förlustkomprimering, vilket kan sudda ut de minsta staplarna. Använd PNG för alla produktions‑klassade skanningsapplikationer.

## Skapa streckkodsbilder i C# – bästa praxis och kantfall

Nedan följer några praktiska tips som gör ditt **create barcode image c#**‑arbetsflöde robust:

| Situation | Rekommendation |
|-----------|----------------|
| **Stort datainnehåll** | Dela upp data i flera MicroPdf417‑symboler och sätt ihop dem visuellt. |
| **Lågupplösta skrivare** | Öka `XDimension.Pixels` till 3‑4 px för att undvika saknade staplar. |
| **Dynamisk utdatamapp** | Använd `Path.GetTempPath()` eller en användarvald mapp via en `SaveFileDialog`. |
| **Trådsäker generering** | Skapa en ny `BarcodeGenerator` per tråd; klassen är inte trådsäker. |
| **Felfångst** | Omge genereringskoden med ett `try/catch`‑block för att fånga `BarCodeException`. |

```csharp
try
{
    // generation code from steps 1‑4
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Fullt, körbart exempel

När allt har satts ihop ser ett komplett konsolprogram ut så här:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Initialize generator with MicroPdf417 type and sample text
        var generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2. Set module size (X‑dimension) to 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3. Use the maximum of 4 columns for a compact shape
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4. Define output path and save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory, "MicroPdf417.png");

        // Ensure the directory exists
        Directory.CreateDirectory(Path.GetDirectoryName(outputPath)!);

        // Save the barcode image
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode successfully created at: {outputPath}");
    }
}
```

Kör programmet med `dotnet run`. Konsolen skriver ut den fullständiga sökvägen, och PNG‑filen visas bredvid den körbara filen.

## Slutsats

Du vet nu **hur man skapar micro pdf417 streckkod** i C# och **hur man genererar barcode png**‑filer för vilket .NET‑projekt som helst. Stegen – initiering av generatorn, konfiguration av X‑dimension och kolumner samt export till PNG – täcker de viktigaste inställningarna för pålitlig streckkodsskapning.

Härifrån kan du utforska:

* **Create barcode image c#** för andra symbologier (QR, Code128, DataMatrix) genom att ändra `EncodeTypes`.
* Lägga till färg eller bakgrundsbilder via `generator.Parameters.Barcode.Image`.
* Integrera streckkodsgenereringen i ASP.NET Core‑endpoints för att leverera bilder på begäran.

Experimentera med inställningarna, testa resultatet på riktiga skannrar och anpassa koden efter ditt specifika arbetsflöde. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande tutorialerna behandlar närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [How to generate micro pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}