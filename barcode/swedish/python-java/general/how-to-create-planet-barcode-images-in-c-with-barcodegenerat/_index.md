---
category: general
date: 2026-09-26
description: Lär dig hur du snabbt skapar Planet-streckkod i C#. Den här guiden täcker
  fyllda och tomma Planet-streckkoder, X‑dimensionsinställningar och bildexport.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode C#
- filled planet barcode
- empty planet barcode
- barcode generator parameters
language: sv
lastmod: 2026-09-26
og_description: Skapa Planet-streckkod i C# med ett komplett kodexempel. Generera
  både fyllda och tomma Planet-streckkoder, ställ in streckbredd och spara som PNG.
og_image_alt: Screenshot showing generated filled and empty planet barcode PNG files
og_title: Skapa planetstreckkodsbilder i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create planet barcode in C# quickly. This guide covers
    filled and empty Planet barcodes, X‑dimension settings, and image export.
  headline: How to create planet barcode images in C# with BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man skapar planetstreckkodsbilder i C# med BarcodeGenerator
url: /sv/python-java/general/how-to-create-planet-barcode-images-in-c-with-barcodegenerat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du planet streckkodsbilder i C# med BarcodeGenerator

Om du behöver **create planet barcode**-bilder i en .NET-applikation visar den här handledningen de exakta stegen. Du kommer att lära dig hur du genererar både en fylld och en tom Planet-streckkod, justerar stapelbredden och exporterar resultaten som PNG-filer—allt med Aspose.BarCode for .NET-biblioteket.

Att generera en **Planet barcode C#**-lösning är enkelt när du förstår de viktigaste **barcode generator parameters**. I avsnitten som följer går vi igenom den kompletta, körbara koden, förklarar varför varje inställning är viktig och pekar på vanliga fallgropar så att du kan undvika dem redan på första försöket.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat.
* Visual Studio 2022 (eller någon C#-IDE du föredrar).
* NuGet‑paketet **Aspose.BarCode for .NET** (`Aspose.BarCode`) tillagt i ditt projekt.

Du kan lägga till paketet via NuGet Package Manager Console:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Ställ in BarcodeGenerator

`BarcodeGenerator`‑klassen är startpunkten för alla streckkodsskapande uppgifter. Den kräver två argument: streckkodstypen (`EncodeTypes.Planet`) och data som ska kodas.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // Create a generator for a filled Planet barcode
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Varför detta är viktigt:* Att instansiera generatorn med `EncodeTypes.Planet` talar om för biblioteket att använda **Planet barcode**‑symbologi, som vanligtvis används för posttjänster i vissa länder. Strängen `"123456"` är den data som kommer att visas i streckkoden.

## Steg 2: Konfigurera X‑dimensionen (stapelbredd)

X‑dimensionen styr den fysiska bredden på varje stapel. Ett typiskt värde för rendering på skärm är 4 pixlar, men du kan justera det för att möta utskriftskrav.

```csharp
        // Define the bar width (X dimension) in pixels
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

*Varför detta är viktigt:* Att sätta `XDimension.Pixels` säkerställer att den genererade streckkoden varken blir för tunn (vilket kan leda till skanningsfel) eller för tjock (slösar utrymme). Samma inställning kommer att återanvändas för den tomma streckkoden.

## Steg 3: Spara den fyllda Planet-streckkoden

Exportera streckkoden till en PNG‑fil med `Save`‑metoden. `BarCodeImageFormat.Png`‑enumet talar om för biblioteket att producera en förlustfri bild som är lämplig för vidare bearbetning.

```csharp
        // Save the filled barcode as a PNG image
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Efter att programmet har körts hittar du `PostalPlanetFilledBars.png` i utdata‑mappen. Öppna den för att verifiera att staplarna är solida (fyllda).

## Steg 4: Skapa en generator för en tom Planet-streckkod

En **empty planet barcode** visar samma data men med ofyllda (vita) staplar. Detta är användbart för visuella designer som lägger streckkoden över färgade bakgrunder.

```csharp
        // Create a generator for an empty Planet barcode (unfilled bars)
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Konstruktörsanropet är identiskt med den fyllda versionen; skillnaden ligger i den parameter vi kommer att ändra härnäst.

## Steg 5: Återanvänd samma X‑dimension

För att hålla den visuella storleken konsekvent, tillämpa samma stapelbredd på den tomma streckkoden.

```csharp
        // Use the same bar width as before
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
```

Att återanvända **barcode generator parameters** garanterar att båda bilderna aligneras perfekt när de placeras sida‑vid‑sida.

## Steg 6: Byt till ofyllda staplar

`FilledBars`‑flaggan bestämmer om staplarna renderas som solid svart (standard) eller transparent vit.

```csharp
        // Configure the generator to produce empty (unfilled) bars
        emptyPlanet.Parameters.Barcode.FilledBars = false;
```

*Varför detta är viktigt:* Att sätta `FilledBars = false` vänder renderingsläget, vilket är den avgörande skillnaden mellan en fylld och en tom Planet-streckkod.

## Steg 7: Spara den tomma Planet-streckkoden

Slutligen, exportera den tomma versionen till PNG.

```csharp
        // Save the empty barcode as a PNG image
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

När du kör programmet visas två filer:

* `PostalPlanetFilledBars.png` – solida svarta staplar.
* `PostalPlanetEmptyBars.png` – transparenta (ofyllda) staplar.

Båda bilderna innehåller samma data (`123456`) och delar samma X‑dimension, vilket gör dem utbytbara i de flesta UI‑scenarier.

## Fullt, körbart exempel

Sätt ihop allt, här är den kompletta källfilen som du kan kopiera‑och‑klistra in i ett nytt konsolprojekt:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PlanetBarcodeDemo
{
    static void Main()
    {
        // ----------- Filled Planet barcode -----------
        BarcodeGenerator filledPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        filledPlanet.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // ----------- Empty Planet barcode ------------
        BarcodeGenerator emptyPlanet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyPlanet.Parameters.Barcode.XDimension.Pixels = 4;
        emptyPlanet.Parameters.Barcode.FilledBars = false;
        emptyPlanet.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Förväntat resultat**

När programmet körs skapas två PNG‑filer i den körbara filens arbetskatalog. Öppna dem med någon bildvisare:

* **Fylld version** – mörka, solida staplar som är lätt läsbara av standardskannrar.
* **Tom version** – staplar visas som vita luckor på en svart bakgrund, användbart för överlagringseffekter.

## Vanliga fallgropar och pro‑tips

| Problem | Varför det händer | Hur man åtgärdar det |
|---------|-------------------|----------------------|
| Staplar ser för tunna ut | X‑dimension lämnades på standard (1 pixel) | Sätt `XDimension.Pixels` till 3‑5 pixlar för skärmbruk; öka för högupplösta utskrifter. |
| Tom streckkod visas helt svart | `FilledBars` är inte satt till `false` | Se till att `emptyPlanet.Parameters.Barcode.FilledBars = false;` körs **efter** att X‑dimensionen har satts. |
| PNG‑fil saknas | Utdatavägen är felaktig eller katalogen finns inte | Ange en fullständig sökväg (`@"C:\Barcodes\PostalPlanetFilledBars.png"`) eller skapa katalogen i förväg med `Directory.CreateDirectory`. |
| Streckkoden går inte att skanna | Datat strängen innehåller otillåtna tecken för Planet‑symbologi | Planet‑streckkoder accepterar endast numeriska payloads; validera indata med `int.TryParse`. |

**Pro‑tips:** Om du behöver bädda in streckkoden i en PDF kan du ladda den genererade PNG‑filen i ett `PdfDocument` med Aspose.PDF, eller direkt lägga till streckkoden som en bildström utan att skriva till disk.

## Nästa steg

Nu när du kan **create planet barcode**-bilder, överväg att utforska dessa relaterade ämnen:

* **Planet barcode C#** – anpassa färger, lägga till mänskligt läsbar text, eller bädda in streckkoden i en PDF.
* **Barcode generator parameters** – justera felkorrigeringsnivå, tyst zon, eller rotation.
* **Batch generation** – loopa över en lista med postkoder för att producera en zip‑fil med PNG‑filer.
* **Alternative formats** – exportera till SVG eller JPEG för webb‑vänlig leverans.

Experimentera med olika `XDimension`‑värden och `FilledBars`‑flaggan för att se hur de påverkar skanningspålitlighet och visuell stil. När du är redo, integrera genereringskoden i ditt web‑API eller skrivbordsprogram för att automatiskt skapa poststreckkoder i realtid.

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa Planet Barcode i C# – Fullständig steg‑för‑steg‑guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Barcode generator C# – skapa Planet barcode och RM4SCC‑exempel](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [Generera poststreckkod i C# – Komplett guide med Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}