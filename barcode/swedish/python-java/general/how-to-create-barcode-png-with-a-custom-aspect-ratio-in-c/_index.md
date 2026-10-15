---
category: general
date: 2026-10-05
description: Skapa streckkod‑PNG i C# och lär dig hur du ställer in bildförhållandet
  15 för staplade DataBar‑omnidirektionella streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: sv
lastmod: 2026-10-05
og_description: Skapa streckkod PNG i C# och upptäck hur du ställer in bildförhållandet
  15 för staplade DataBar‑omnidirektionella streckkoder i några steg.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Skapa streckkod PNG i C# – sätt bildförhållandet till 15 handledning
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Hur man skapar en streckkod‑PNG med ett anpassat bildförhållande i C#
url: /sv/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkod PNG med ett anpassat bildförhållande i C#

Om du behöver **skapa streckkod PNG** i C#, visar den här guiden **hur du ställer in bildförhållandet** 15 för en staplad DataBar omnidirektionell streckkod. Vi går igenom varje API‑anrop, förklarar varför bildförhållandet är viktigt, och ger dig ett komplett, körbart exempel som du kan lägga in i vilket .NET‑projekt som helst.

Att generera en streckkodsbild är ett vanligt krav för lagerhanteringssystem, fraktetiketter och detaljhandels‑point‑of‑sale‑applikationer. I slutet av den här handledningen kommer du att ha en PNG‑fil som uppfyller de exakta visuella specifikationerna som din affärspartner kräver. Inga externa verktyg, ingen manuell bildredigering—bara kod.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare (exemplet använder .NET 6 men fungerar med .NET 5+)
* Visual Studio 2022 (eller någon IDE som stöder .NET)
* NuGet‑paketet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Skrivbehörighet till den mapp där du vill spara PNG‑filen

Dessa krav är minimala; samma kod fungerar i .NET Core, .NET Framework eller en konsolapplikation.

## Skapa streckkod PNG med Aspose.BarCode

Det första steget är att instansiera klassen `BarcodeGenerator` med rätt streckkodstyp. I det här fallet använder vi `EncodeTypes.DatabarStackedOmniDirectional`, som producerar en staplad DataBar som kan läsas från vilken riktning som helst.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Varför detta är viktigt:* Konstruktorn tar två argument—**streckkodssymbologin** och **datat strängen**. DataBar‑formatet förväntar sig en GS1‑applikationsidentifierare, vilket är anledningen till att exempeldata börjar med `(01)`.

## Hur man ställer in bildförhållandet för en staplad DataBar

Den visuella bredden på en DataBar styrs av egenskapen **aspect ratio**. Ett högre förhållande gör staplarna bredare, vilket kan förbättra skanningspålitligheten på lågupplösta skrivare.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` definierar storleken på en enskild modul (den minsta stapeln eller mellanrummet). Att hålla detta på 2 px ger en skarp, högupplöst bild som passar de flesta etikett‑skrivare.

## Ställ in bildförhållande 15 – kodgenomgång

Nu tillämpar vi kravet **set aspect ratio 15**. Detta är kärnan i handledningen och demonstrerar det exakta API‑anropet du behöver.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Varför 15?* Standard‑aspect ratio för staplad DataBar är 12. Att höja den till 15 ökar bredden på varje stapel med 25 %, vilket ofta matchar specifikationerna hos logistikleverantörer som kräver en bredare streckkod för snabbare skanning.

## Spara streckkoden som PNG

När generatorn är konfigurerad är sista steget att skriva bilden till disk. Metoden `Save` accepterar en filsökväg och en bildformat‑enum.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG‑formatet bevarar förlustfri kvalitet, vilket säkerställer att streckkoden återges exakt som designad på vilken skärm eller skrivare som helst.

## Fullständigt exempel och förväntad output

Nedan är hela programmet som du kan kopiera in i en konsolapps `Main`‑metod. Det inkluderar alla stegen som beskrivits ovan, plus ett litet verifieringsmeddelande.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Förväntad output**

När programmet körs skapas en fil med namnet `DatabarAspectRatio15.png` som innehåller en tydlig, bred staplad DataBar‑streckkod. När du öppnar PNG‑filen bör du se en horisontellt utsträckt streckkod som fortfarande följer GS1 DataBar‑specifikationerna.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **skapa streckkod PNG som visar en staplad DataBar med bildförhållande 15**

### Tips och vanliga fallgropar

| Situation | Rekommendation |
|-----------|----------------|
| **Bilden ser suddig ut** | Öka `XDimension.Pixels` till 3 px eller högre, men håll den totala bildstorleken under 500 px för att undvika för stora filer. |
| **Skannern kan inte läsa koden** | Verifiera att datasträngen följer GS1‑formatet (`(01)`‑prefix). Säkerställ också att skrivarlösningen är minst 300 dpi. |
| **Behöver ett annat filformat** | Byt ut `BarCodeImageFormat.Png` mot `Jpeg`, `Bmp` eller `Gif`—API‑et stödjer alla större rasterformat. |
| **Kör i en webbapplikation** | Använd `generator.Save(Stream, BarCodeImageFormat.Png)` för att skriva direkt till HTTP‑svaret utan att röra filsystemet. |

### Utöka exemplet

* **Flera streckkoder i en bild:** Skapa ytterligare `BarcodeGenerator`‑instanser och rita dem på en enda `Bitmap` med `Graphics`.  
* **Lägga till mänskligt läsbar text:** Sätt `generator.Parameters.Caption.Visible = true` och anpassa teckensnittet via `generator.Parameters.Caption.Font`.  
* **Dynamiskt bildförhållande:** Hämta förhållandets värde från en konfigurationsfil eller databas för att generera streckkoder med varierande bredd i realtid.

## Slutsats

I den här handledningen lärde du dig hur du **skapar streckkod PNG** i C# och exakt **ställer in bildförhållandet** 15 för en staplad DataBar omnidirektionell streckkod. Den kompletta, körbara koden demonstrerar varje nödvändigt API‑anrop, förklarar varför varje inställning är viktig, och ger praktiska tips för verkliga implementationer.  

Nästa steg kan vara att utforska **hur man ställer in bildförhållandet** för andra streckkodstyper (t.ex. QR‑kod eller Code 128) eller integrera generatorn i en ASP .NET Core‑tjänst som returnerar streckkods‑bilder på begäran. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar databar PNG‑bilder med C# och Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hur man skapar staplad databar‑streckkod i C# med Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Anpassa staplad omnidirektionell databar‑aspect ratio i .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}