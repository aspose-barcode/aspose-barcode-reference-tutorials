---
category: general
date: 2026-10-28
description: Skapa streckkodbild i C# och lär dig hur du justerar höjden med BarcodeGenerator‑API:t.
  Steg‑för‑steg‑guide för anpassad streckkodshöjd och ändring av stapelhöjd.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: sv
lastmod: 2026-10-28
og_description: Skapa en streckkodbild i C# och se omedelbart hur du justerar höjden.
  Följ detta kompletta exempel för att ange en anpassad streckkodshöjd med BarcodeGenerator.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Skapa streckkodbild med anpassad höjd i C# – fullständig guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Skapa streckkodbild med anpassad höjd i C#
url: /sv/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa streckkodbild med anpassad höjd i C#

Om du behöver **skapa streckkodbild** och kontrollera dess dimensioner, visar den här guiden exakt hur du gör. Med Aspose.BarCode .NET‑biblioteket kan du generera en GS1‑Databar Omni‑Directional‑streckkod, och sedan **hur du justerar höjden** för att uppfylla alla layoutkrav.

Du går igenom ett komplett, körbart program som demonstrerar en **c# barcode generator**, förklarar varje egenskap du sätter och visar två olika resultat—ett med 30‑pixel hög stapel och ett med 60‑pixel hög stapel. I slutet kan du **ändra streckkodens höjd** programatiskt för alla streckkodstyper som stöds av biblioteket.

## Förutsättningar

- .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.6+)
- Visual Studio 2022 eller någon editor som kan bygga C#‑projekt
- Aspose.BarCode för .NET NuGet‑paket (`Install-Package Aspose.BarCode`)
- Grundläggande kunskap om C#‑syntax

> **Proffstips:** Om du använder en CI‑pipeline, lägg till NuGet‑paketet i din `csproj`‑fil så att bygget återställer det automatiskt.

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt och lägg till de nödvändiga `using`‑satserna. Namnrymderna ger dig åtkomst till `BarcodeGenerator`, `EncodeTypes` och bildformatshjälpmedel.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Varför detta är viktigt:** Att importera rätt namnrymder förhindrar kompileringsfel och gör API:t upptäckbart i IntelliSense.

## Steg 2: Initiera **c# barcode generator** för en GS1‑Databar Omni‑Directional‑kod

Konstruktorn tar två argument: streckkodstypen (`EncodeTypes.DatabarOmniDirectional`) och datasträngen. Datasträngen måste följa GS1 Application Identifier‑formatet, t.ex. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Förklaring:** `BarcodeGenerator`‑objektet är ingångspunkten för alla streckkod‑relaterade inställningar. När du har den här instansen kan du justera dimensioner, färger och utdataformat.

## Steg 3: Definiera en gemensam X‑dimension (pixelbredden på den smalaste stapeln)

En X‑dimension på 2 pixel är en bra utgångspunkt för de flesta skärmvisningsscenarier.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Varför sätta X‑dimension?** Den styr den totala bredden på streckkoden. Att hålla den konsekvent säkerställer att förändring av stapelhöjden inte förvränger den visuella balansen.

## Steg 4: **Skapa streckkodbild** med en 30‑pixel stapelhöjd

Nu konfigurerar vi stapelhöjden, sparar den första bilden och ändrar sedan höjden för den andra.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Resultat:** Du får en PNG‑fil där varje vertikal stapel är 30 pixel hög. X‑dimensionen förblir 2 pixel, så den totala bredden är oförändrad.

## Steg 5: **Hur man justerar höjden** – ändra stapelhöjden till 60 pixel

För att demonstrera **anpassad streckkodshöjd**, tilldela helt enkelt ett nytt värde till samma egenskap och spara igen.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Viktig insikt:** `BarHeight`‑egenskapen är muterbar; du behöver inte återskapa `BarcodeGenerator`‑instansen. Detta gör det enkelt att generera flera storlekar i en loop eller batch‑process.

## Steg 6: Verifiera resultatet

Kör konsolprogrammet (`dotnet run`). Efter körning bör du se två PNG‑filer i projektets utdata‑mapp:

- `DatabarBarHeight30Pixels.png` – korta staplar (30 px)
- `DatabarBarHeight60Pixels.png` – långa staplar (60 px)

Båda bilderna innehåller samma kodade data, men den visuella höjden skiljer sig, vilket är användbart när man integrerar streckkoder i formulär, produktetiketter eller UI‑komponenter med varierande utrymmesbegränsningar.

![Skapa streckkodbild med anpassad höjd](barcode-example.png){.align-center width="600" alt="Skapa streckkodbild med anpassad höjd"}

> **Tips:** Öppna PNG‑filerna i någon bildvisare. Den längre streckkoden bör vara exakt dubbelt så hög som den kortare, medan horisontellt avstånd förblir identiskt.

## Steg 7: Vanliga variationer och kantfall

| Situation | Rekommenderad inställning |
|-----------|---------------------------|
| **Utskrift på en högupplöst etikettprinter** | Använd en större X‑dimension (t.ex. 4 px) och öka `BarHeight` proportionellt. |
| **Visning på en låg‑dpi skärm** | Behåll `XDimension` på 1 px och `BarHeight` mellan 20‑40 px för läsbarhet. |
| **Generera QR‑koder eller 2‑D‑streckkoder** | `BarHeight`‑egenskapen ignoreras; använd `EncodeTypes.QR` och justera `ImageHeight` istället. |
| **Batch‑generering av många höjder** | Loopa över en array av höjder och anropa `Save` inuti loopen; ingen behov av att återskapa generatorn varje iteration. |

### Hantera ogiltiga höjder

Biblioteket kastar ett `ArgumentOutOfRangeException` om du sätter `BarHeight` till ett icke‑positivt värde. Skydda mot detta med en enkel kontroll:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Fullständig källkod (klar att kopiera)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Varför detta fungerar:** Alla nödvändiga inställningar (`EncodeTypes`, `XDimension`, `BarHeight`) appliceras innan varje `Save`‑anrop. Samma `BarcodeGenerator`‑instans återanvänds, vilket är både minnes‑effektivt och lättläst.

## Slutsats

Du vet nu hur du **skapar streckkodbilder** i C# och exakt **ändrar streckkodshöjden** med `BarcodeGenerator`‑API:t. Genom att justera `BarHeight.Pixels` får du en **anpassad streckkodshöjd** utan att bygga om generatorn, vilket gör lösningen idealisk för dynamisk etikett‑skapande, UI‑rendering eller batch‑process‑pipelines.

Nästa steg, utforska relaterade ämnen som **hur man justerar bredd**, **lägger till mänskligt läsbar text**, eller **exporterar till SVG för skalbar webb-användning**. Samma mönster—sätt en egenskap, anropa `Save`—gäller för dessa scenarier, så att du kan utöka detta exempel med förtroende.

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man ändrar streckkodshöjd i C# – Komplett guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator‑exempel – skapa Planet‑ och RM4SCC‑streckkoder med anpassad höjd](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [Hur man skapar rm4scc‑streckkod och kontrollerar dess höjd i C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}