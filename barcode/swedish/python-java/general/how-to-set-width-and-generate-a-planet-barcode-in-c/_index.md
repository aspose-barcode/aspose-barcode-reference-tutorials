---
category: general
date: 2026-09-16
description: Lär dig hur du ställer in bredd, hur du skapar tomma staplar och hur
  du fyller staplar när du genererar Planet‑streckkod med Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: sv
lastmod: 2026-09-16
og_description: Hur du ställer in bredd, skapar tomma staplar och fyller staplar när
  du genererar Planet‑streckkod med Aspose.BarCode – komplett steg‑för‑steg‑guide.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Hur man ställer in bredd och genererar en Planet-streckkod i C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man anger bredd och genererar en Planet‑streckkod i C#
url: /sv/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in bredd och genererar en Planet-streckkod i C#

Om du behöver **how to set width** för en Planet-streckkod, visar den här guiden hela processen. Du kommer också att se **how to make empty** staplar, **how to fill bars**, och de exakta stegen för att **generate Planet barcode** med Aspose.BarCode för .NET.

Att generera en post‑stil Planet-streckkod är vanligt när man bygger applikationer för postetiketter eller integrationer med posttjänster. I slutet av den här handledningen kommer du att ha ett färdigt konsolprogram som skapar både en bild med fyllda staplar och en bild med tomma staplar, båda med samma datasträng.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
- Visual Studio 2022 eller någon C#‑kompatibel IDE
- Aspose.BarCode för .NET NuGet‑paket (`Aspose.BarCode`)  
  Installera med:

```bash
dotnet add package Aspose.BarCode
```

Ingen ytterligare konfiguration krävs; biblioteket hanterar bildkodning internt.

## Steg 1: Skapa ett konsolprojekt och lägg till biblioteket

Öppna en terminal och kör:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Detta skapar en `Program.cs`‑fil där vi kommer att skriva streckkodlogiken.

## Steg 2: Skriv koden – how to set width and generate Planet barcode

Öppna `Program.cs` och ersätt dess innehåll med följande kompletta exempel:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Varför varje steg är viktigt

- **How to set width**: `XDimension.Pixels`‑egenskapen påverkar direkt den fysiska storleken på varje stapel. Att välja ett värde mellan 2 och 6 pixlar balanserar läsbarhet på skärmen och utskriftskvalitet.
- **How to make empty**: Att sätta `FilledBars = false` instruerar generatorn att bara rita konturerna av staplarna. Denna stil är användbar för “light‑on‑dark”-utskrift eller när du vill att papperets underliggande textur ska synas.
- **How to fill bars**: Standardvärdet `FilledBars = true` skapar solida svarta staplar, vilket är standard för de flesta postskannrar.
- **Generate Planet barcode**: Att använda `EncodeTypes.Planet` väljer den specifika kodning som krävs av United States Postal Service (USPS) för Planet‑streckkoder.

## Steg 3: Bygg och kör programmet

Från projektmappen kör:

```bash
dotnet run
```

Du bör se konsolutdata liknande:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Två PNG‑filer visas i projektkatalogen:

- `PostalPlanetFilledBars.png` – solida svarta staplar (standardstil)
- `PostalPlanetEmptyBars.png` – konturstaplar (tom stil)

Öppna dem i någon bildvisare för att verifiera att stapelbredden matchar 4‑pixelinställningen och att den tomma versionen visar ofyllda staplar.

## Vanliga frågor och specialfall

| Fråga | Svar |
|----------|--------|
| *Kan jag använda ett annat bildformat?* | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` efter behov. |
| *Vad händer om streckkoden blir för bred för min etikett?* | Minska `XDimension.Pixels` (t.ex. till `2`) eller öka modulbredden på etikettskrivaren. |
| *Behöver jag sätta `Height` manuellt?* | Biblioteket beräknar automatiskt höjden baserat på kodningen. Du kan åsidosätta med `Parameters.Barcode.BarHeight`. |
| *Stöds tom‑staplar‑stilen på alla skrivare?* | De flesta moderna termiska skrivare hanterar både fyllda och tomma stilar, men verifiera med ett testutskrift om du använder en äldre enhet. |
| *Hur lägger man till en mänskligt läsbar bildtext under streckkoden?* | Använd `Parameters.Caption` för att aktivera och styla en bildtext; sätt `CaptionAbove` till `false` för att placera den nedanför. |

## Proffstips

- **Reuse the same generator** endast när du behåller alla parametrar identiska. Att ändra `FilledBars` efter en sparning påverkar inte den redan sparade bilden, så en ny instans (som visat) garanterar en ren start.
- **Batch generation**: Omge koden med en loop och ändra `data` varje iteration för att skapa en serie Planet‑streckkoder för massutskick.
- **Performance**: För tusentals streckkoder, skapa en enda `BarcodeGenerator`‑instans, justera `XDimension` och `FilledBars` efter behov, och återanvänd objektet för att minska minnesallokeringar.

## Slutsats

Du vet nu **how to set width**, **how to make empty**, **how to fill bars**, och de exakta stegen för att **generate Planet barcode** med Aspose.BarCode i C#. Det kompletta, körbara exemplet producerar både fyllda‑staplar och tomma‑staplar PNG‑filer, redo för integration i vilket postetikett‑arbetsflöde som helst.

Nästa, utforska relaterade ämnen såsom **how to add QR codes to the same label**, **customizing barcode colors**, eller **embedding the barcode into a PDF document**. Var och en av dessa bygger på samma grunder som behandlats här. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa Planet-streckkodsbild i C# – Hur man genererar poststreckkod](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Hur man skapar Code128-streckkod med tomma staplar i Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Hur man genererar streckkodsbild i Java med Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}