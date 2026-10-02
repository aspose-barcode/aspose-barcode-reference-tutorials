---
category: general
date: 2026-10-02
description: Skapa staplad databars‑streckkod i C# snabbt. Lär dig att ställa in XDimension,
  justera bildförhållandet och exportera PNG‑bilder med en streckkodsgenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: sv
lastmod: 2026-10-02
og_description: Skapa staplade databars‑streckkod i C# med ett komplett kodexempel.
  Justera XDimension, ändra bildförhållandet och spara PNG‑filer på bara några rader.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Skapa staplade databars streckkod i C# – snabb handledning
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Skapa staplad databars streckkod i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa staplade databars streckkod i C# – steg‑för‑steg‑guide

Om du behöver **skapa staplade databars streckkod** i ett .NET‑projekt visar den här handledningen exakt hur du gör. Du får se hur du konfigurerar X‑dimensionen, byter aspektförhållanden och sparar resultatet som PNG‑filer – allt med Aspose.BarCode‑biblioteket.

Att generera en staplad DataBar‑streckkod kräver ingen komplicerad grafik‑pipeline. I slutet av den här guiden har du två färdiga PNG‑bilder som illustrerar olika aspektförhållanden, och du förstår varför dessa parametrar är viktiga för skanningspålitlighet.

## Vad du behöver

- .NET 6.0 eller senare (koden fungerar också med .NET Framework 4.6+)
- Visual Studio 2022 eller någon C#‑IDE
- **Aspose.BarCode for .NET** NuGet‑paket  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Skrivbehörighet till en mapp där PNG‑filerna ska sparas

## Steg 1: Skapa projektet och importera namnrymder

Skapa en ny konsolapplikation (eller lägg till koden i ett befintligt projekt) och importera de nödvändiga namnrymderna:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Varför detta är viktigt:** `Aspose.BarCode.Generation` tillhandahåller klassen `BarcodeGenerator`, medan `Aspose.BarCode` innehåller uppräkningen `BarCodeImageFormat` som används för att spara bilder.

## Steg 2: Initiera generatorn för en staplad omnidirektionell DataBar

Värdet `EncodeTypes.DatabarStackedOmniDirectional` väljer den staplade DataBar‑symboliken. Datat strängen måste följa GS1 Application Identifier (AI)‑formatet; här använder vi ett dummy‑GTIN‑14‑värde.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Varför detta är viktigt:** Den valda kodningstypen talar om för biblioteket att rendera en *staplad* streckkod, vilket är avgörande för högdensitets‑etiketter där vertikalt utrymme är begränsat.

## Steg 3: Definiera modul‑ (X‑dimension)‑storleken i pixlar

X‑dimensionen styr bredden på den minsta stapeln (”modulen”). Ett värde på 2 pixlar fungerar bra för de flesta skärm‑upplösningsutdata.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför detta är viktigt:** Skannrar tolkar modulbredden som den grundläggande måttenheten. Ett för litet värde kan ge suddiga utskrifter; ett för stort slösar utrymme.

## Steg 4: Spara den första bilden med ett aspektförhållande på 15

Egenskapen `AspectRatio` påverkar förhållandet mellan höjd och bredd för varje staplad segment. Ett aspektförhållande på 15 är ett vanligt standardvärde för detaljhandelsapplikationer.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Varför detta är viktigt:** Ett lägre aspektförhållande ger en plattare streckkod, vilket kan vara lättare att skanna på vissa etikettmaterial. PNG‑formatet bevarar förlustfri kvalitet för testning.

## Steg 5: Ändra aspektförhållandet till 30 och spara den andra bilden

Att öka aspektförhållandet gör varje staplat segment högre, vilket kan förbättra skanningspålitligheten på lågkontrast‑bakgrunder.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Varför detta är viktigt:** Olika återförsäljare eller logistikpartners kan kräva specifika streckkodsdimensioner. Genom att tillhandahålla båda versionerna kan du snabbt jämföra skanningsprestanda.

## Fullt, körbart exempel

Nedan är hela programmet som du kan kopiera‑klistra in i `Program.cs`. Det kompileras och körs utan ändringar efter att Aspose.BarCode‑NuGet‑paketet installerats.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Förväntad output

När programmet körs skapas två filer i körningsmappen:

| Filnamn                       | Aspektförhållande | Visuell beskrivning |
|-------------------------------|-------------------|---------------------|
| `DatabarAspectRatio15.png`    | 15                | Kortare, plattare staplad streckkod |
| `DatabarAspectRatio30.png`    | 30                | Högre, mer utdragen staplad streckkod |

Du kan öppna PNG‑filerna med någon bildvisare för att verifiera att streckkoden renderas korrekt.

![Create stacked databars barcode example](placeholder-image.png){alt="Skapa staplade databars streckkod exempel"}

## Vanliga frågor och kantfall

| Fråga | Svar |
|----------|--------|
| **Kan jag använda en annan X‑dimension?** | Ja. Typiska värden ligger mellan 1 och 4 pixlar. Större värden ökar streckkodens storlek men kan förbättra läsbarheten på lågupplösta skrivare. |
| **Vad händer om jag behöver en annan symbolik?** | Byt ut `EncodeTypes.DatabarStackedOmniDirectional` mot ett annat `EncodeTypes`‑värde, t.ex. `DatabarStacked` (icke‑omnidirektionell) eller `DatabarLimited`. |
| **Hur ändrar jag utdataformatet?** | Använd `BarCodeImageFormat.Jpeg`, `Gif` eller `Bmp` i `Save`‑anropet. |
| **Är GTIN‑14‑formatet obligatoriskt?** | DataBar‑symboliken förväntar sig en numerisk sträng med ett lämpligt AI‑prefix (t.ex. `(01)` för GTIN‑14). Anpassa datan efter ditt användningsfall. |
| **Vad gäller DPI‑inställningarna?** | Generatorn respekterar egenskapen `Resolution`. För högupplösta utskrifter, sätt `barcodeGen.Parameters.ImageResolution.DpiX` och `DpiY` enligt behov. |

## Pro‑tips

- **Batch‑generering:** Lägg in sparlogiken i en loop och mata in en lista med GTIN‑nummer för att automatiskt producera tusentals streckkoder.
- **Validering:** Anropa `barcodeGen.Validate()` innan du sparar för att fånga felaktiga data tidigt.
- **Prestanda:** Återanvänd samma `BarcodeGenerator`‑instans (ändra bara parametrar) – det är snabbare än att skapa ett nytt objekt för varje bild.

## Nästa steg

Nu när du kan **skapa staplade databars streckkod** med anpassade aspektförhållanden, fundera på att utforska:

- Lägga till mänskligt läsbar text under streckkoden (`barcodeGen.Parameters.Barcode.CodeText`).
- Exportera till **PDF** för utskrivbara etikettark (`BarCodeImageFormat.Pdf`).
- Integrera generatorn i ett web‑API för att leverera streckkoder på begäran.
- Experimentera med andra **sekundära nyckelord** såsom *C# barcode generator* och *barcode aspect ratio* för att finjustera din implementation för specifik hårdvara.

Lycka till med kodningen, och njut av den flexibilitet som Aspose.BarCode ger dina C#‑streckkodprojekt!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to create databar PNG images with C# and Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}