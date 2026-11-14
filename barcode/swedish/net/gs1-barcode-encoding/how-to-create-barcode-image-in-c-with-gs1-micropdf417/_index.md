---
category: general
date: 2026-11-14
description: Lär dig hur du skapar streckkodsbilder i C# med Aspose.BarCode. Denna
  steg‑för‑steg‑guide täcker inställning av streckkodsgenerator i C#, GS1‑formattering
  och PNG‑export.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: sv
lastmod: 2026-11-14
og_description: Skapa streckkodbild i C# snabbt. Följ den här guiden för att lära
  dig hur du genererar streckkod, använder streckkodsgenerator i C# och exporterar
  en GS1 MicroPDF417 PNG.
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: Skapa streckkodbild i C# – fullständig guide för GS1 MicroPDF417
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Hur man skapar en streckkodbild i C# med GS1 MicroPDF417
url: /sv/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar streckkodbild i C# med GS1 MicroPDF417

Om du behöver **create barcode image** i C#, visar den här guiden en komplett, färdig‑att‑köra lösning. Du kommer att se **how to generate barcode** data som följer GS1‑standarden, konfigurera generatorn och exportera en högkvalitativ PNG‑fil.

Tutorialen täcker allt från att installera det erforderliga biblioteket till att hantera vanliga fallgropar med dataformat. I slutet kommer du att kunna producera en **barcode image from data** med bara några rader kod, och du kommer att förstå varför varje inställning är viktig.

## Förutsättningar

* .NET 6.0 eller senare installerat (koden fungerar också med .NET Framework 4.7+).
* En IDE såsom Visual Studio 2022 eller Visual Studio Code.
* **Aspose.BarCode for .NET** NuGet‑paketet. Installera det med:

```bash
dotnet add package Aspose.BarCode
```

* Grundläggande kunskap om C#‑syntax och GS1 Application Identifier (AI)-formatet.

> **Pro tip:** Håll biblioteksversionen uppdaterad; den senaste releasen lägger till stöd för nyare streckkodssymboler och prestandaförbättringar.

## Skapa streckkodbild med BarcodeGenerator

Detta avsnitt innehåller kärnimplementationen. Koden skapar en **barcode generator c#**‑instans, konfigurerar X‑dimensionen för läsbarhet och sparar resultatet som en PNG‑fil.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### Varför varje rad är viktig

* **EncodeTypes.MicroPdf417** talar om för biblioteket att använda GS1 MicroPDF417‑symbolen, som är kompakt och idealisk för mobilskanning.
* **data string** måste börja med GS1 AI `(01)` för Global Trade Item Number (GTIN) följt av `(21)` för serienumret. Om formatet är felaktigt kastar generatorn ett undantag.
* **XDimension.Pixels** styr bredden på den minsta stapeln. Ett större värde ökar läsbarheten på lågupplösta skärmar, medan ett mindre värde minskar bildstorleken.
* **BarCodeImageFormat.Png** producerar en förlustfri bild, vilket bevarar de skarpa kanterna som krävs för pålitlig skanning.

När programmet körs skapas `GS1MicroPdf417.png` på ditt skrivbord. När du öppnar filen visas en tät, svart‑på‑vit streckkod som kodar GTIN `12345678901234` och serien `ABC123`.

## Hur man genererar streckkod med GS1 MicroPDF417

Om du är ny på GS1‑formatering, här är de grundläggande reglerna:

| GS1 AI | Betydelse                     | Exempel               |
|--------|-----------------------------|-----------------------|
| (01)   | Global Trade Item Number    | 12345678901234        |
| (21)   | Serial number (optional)    | ABC123                |

När du sammanfogar AI‑erna med deras värden, omsluter du varje AI med parenteser och placerar värdena direkt efter. Den resulterande strängen kan skickas till **barcode generator c#** utan ytterligare kodning.

### Vanliga fallgropar

* **Missing parentheses** – Generatorn behandlar strängen som rådata och kommer inte att tillämpa GS1‑kontroller.
* **Exceeding length limits** – MicroPDF417 stöder upp till 155 tecken. Trimma onödig blanksteg.
* **Invalid characters** – Endast numeriska tecken är tillåtna för GTIN; serien kan innehålla versala bokstäver och siffror.

## Anpassa streckkodbilden från data

Utöver den grundläggande X‑dimensionen erbjuder Aspose.BarCode många visuella justeringar. Nedan är några anpassningar du kan tillämpa beroende på ditt projekts krav.

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

Varje inställning är valfri; standardvärdena producerar redan en ren, skannbar **barcode image**. Experimentera med färger och upplösningar först efter att ha bekräftat att skannrarna fortfarande kan läsa koden.

## Spara streckkoden i andra format

Även om PNG är det vanligaste formatet för webb och mobil, kan du behöva JPEG, BMP eller SVG. `Save`‑metoden accepterar vilket `BarCodeImageFormat`‑värde som helst.

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG minskar filstorleken men introducerar komprimeringsartefakter som kan påverka läsbarheten.
* SVG bevarar vektor­kvaliteten och är idealiskt för responsiva webbdesigner.

## Verifiera den genererade streckkoden

Ett snabbt sätt att bekräfta att steget **create barcode image** lyckades är att använda en mobilskannerapp som stödjer GS1 MicroPDF417. Skanna den sparade PNG‑filen; appen bör visa:

```
GTIN: 12345678901234
Serial: ABC123
```

Om skannern rapporterar ett fel, dubbelkolla AI‑formateringen och X‑dimensionens värde.

## Fullständigt exempel – ett fristående konsolprogram

Nedan är ett komplett program som du kan kopiera, klistra in och köra utan ändringar (förutom NuGet‑installationssteget).

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

När du kör programmet skriver konsolen ut hela filsökvägen, och PNG‑filen visas på ditt skrivbord. Detta exempel demonstrerar **how to generate barcode** data, anpassar utseendet och exporterar en **barcode image from data** i ett enda, sammanhängande arbetsflöde.

## Vanliga frågor

| Fråga | Svar |
|----------|--------|
| *Kan jag generera andra GS1‑symboler?* | Ja. Ersätt `EncodeTypes.MicroPdf417` med `EncodeTypes.Pdf417`, `EncodeTypes.DataMatrix` osv., och justera datasträngen därefter. |
| *Vad händer om min data överskrider MicroPDF417‑kapaciteten?* | Byt till den vanliga PDF417‑symbolen, som stödjer längre data. |
| *Behöver jag en licens för Aspose.BarCode?* | En gratis utvärderingslicens fungerar för utveckling. För produktion, köp en licens för att ta bort utvärderingsvattenstämpeln. |
| *Är PNG‑filen lämplig för utskrift på etiketter?* | Öka `ImageResolution` till 300 dpi eller högre, och överväg att spara som TIFF för industriella skrivare. |

## Slutsats

Du vet nu hur du **create barcode image** i C# med **barcode generator c#**‑metoden, formaterar data för ett **create gs1 barcode**‑scenario, och exporterar resultatet som en PNG‑ eller annan bildtyp. Det fullständiga exemplet demonstrerar varje steg—från datapreparering till visuell anpassning—så att du kan integrera streckkodsskapande i vilken .NET‑applikation som helst.

Nästa steg är att utforska relaterade ämnen som **barcode image from data** för QR‑koder, lägga till flera streckkoder i en enda PDF, eller automatisera batch‑generering för lagersystem. Experimentera med olika X‑dimension‑värden och bildformat för att hitta den optimala balansen för din specifika skannermiljö.

Lycka till med kodningen, och låt dina applikationer börja **creating barcode images** som fungerar pålitligt i den verkliga världen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Hur man skapar streckkodbild med Aspose.Barcode i C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Hur man skapar poststreckkodbild i C# med Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [Hur man skapar PDF417‑streckkodbild i C# – komplett guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}