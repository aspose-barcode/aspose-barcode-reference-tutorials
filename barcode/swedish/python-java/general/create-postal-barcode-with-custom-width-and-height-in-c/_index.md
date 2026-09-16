---
category: general
date: 2026-09-16
description: Skapa poststreckkod i C# och lär dig hur du ställer in bredden och ändrar
  streckkodens höjd för perfekt skanning.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- how to set width
- change barcode height
- barcode generator C#
- postal barcode image
language: sv
lastmod: 2026-09-16
og_description: Skapa poststreckkod i C# med den här steg‑för‑steg‑guiden, som visar
  hur du ställer in bredd och ändrar streckkodens höjd för pålitlig postskanning.
og_image_alt: C# generated postal barcode image with custom width and height
og_title: Skapa poststreckkod med anpassad bredd och höjd i C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Create postal barcode in C# and learn how to set width and change barcode
    height for perfect scanning.
  headline: Create postal barcode with custom width and height in C#
  type: TechArticle
tags:
- barcode
- C#
- postal
title: Skapa poststreckkod med anpassad bredd och höjd i C#
url: /sv/python-java/general/create-postal-barcode-with-custom-width-and-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa poststreckkod med anpassad bredd och höjd i C#

Om du behöver **skapa poststreckkod**-bilder i C# visar den här guiden hur du genererar Planet- och RM4SCC-streckkoder med exakta mått. Efter de två första meningarna vet du exakt vilka API‑anrop som används för att **ange bredd** och **ändra streckkodens höjd**, så att du kan producera läsbara streckkoder som matchar posttjänstens specifikationer.

Du kommer att lära dig:
* Hur man instansierar en streckkodsgenerator för Planet- och RM4SCC-format.  
* Den exakta egenskapen för att **ange bredd** (X‑dimension) i pixlar.  
* Hur man **ändrar streckkodens höjd** för en specifik streckkodstyp.  
* Var de genererade PNG‑filerna sparas och hur de ser ut.

Det enda förutsättningen är en referens till `Aspose.BarCode`‑biblioteket (eller liknande) som tillhandahåller `BarcodeGenerator`‑klassen. Inga ytterligare NuGet‑paket krävs utöver själva streckkod‑SDK:n.

---

## Skapa poststreckkod med anpassade dimensioner

Börja med att lägga till de nödvändiga `using`‑direktiven och skapa ett enkelt konsolprogram. Det kompletta, körbara exemplet presenteras efter steg‑för‑steg‑förklaringen.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for BarcodeGenerator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Generate a Planet barcode (height auto‑determined)
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            // Step 2: Set the module width (X‑dimension) to 4 px
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 3: Save the Planet barcode image
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // Step 4: Generate an RM4SCC barcode (requires explicit height)
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            // Step 5: Apply the same X‑dimension (width) of 4 px
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            // Step 6: Fix the barcode height to 100 px
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            // Step 7: Save the RM4SCC barcode image
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

**Varför detta fungerar:**  
* `EncodeTypes.Planet` och `EncodeTypes.RM4SCC` talar om för generatorn vilken poststandard som ska följas.  
* `XDimension.Pixels` styr **bredden** på varje streckkodmodul (det minsta svart/vita elementet).  
* `BarHeight.Pixels` låter dig **ändra streckkodens höjd** för format som inte beräknar höjden automatiskt, såsom RM4SCC.

När programmet körs skapas två PNG‑filer i den körbara filens arbetskatalog:
* `PostalPlanetBarWidth4.png` – en Planet‑streckkod med en modulbredd på 4 px.  
* `PostalRM4SCCHeight100.png` – en RM4SCC‑streckkod med en bredd på 4 px och en fast höjd på 100 px.

---

## Hur man anger bredd för en poststreckkod

Steget för **hur man anger bredd** är detsamma för alla stödda postformat:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = desiredWidth;
```

* `desiredWidth` är ett heltal som representerar pixelstorleken för en enskild modul.  
* Ett typiskt värde för poststreckkoder är **4 px**, men du kan öka det för utskrift med högre upplösning.

**Proffstips:** När du skriver ut på en DPI‑styrd skrivare, multiplicera pixelbredden med skrivarens DPI‑faktor för att behålla de fysiska dimensionerna.

---

## Ändra streckkodens höjd för RM4SCC‑poststreckkod

Endast en delmängd av post‑symboler (t.ex. RM4SCC) kräver en explicit höjd. Använd egenskapen för **ändra streckkodens höjd**:

```csharp
generator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

* `desiredHeight` är den totala höjden på streckkodsbilden, inte höjden på en enskild modul.  
* Att sätta `BarHeight` till **100 px** ger en hög, lättläst streckkod som följer många posttjänsters riktlinjer.

**Edge case:** Om du anger en höjd som är för liten kan streckkoden bli oläslig för skannrar. Testa alltid med ett fysiskt utskrivet prov innan massdistribution.

---

## Fullständig källkod för snabb kopiering

Nedan är hela programmet som du kan kopiera in i ett nytt konsolprojekt. Ingen annan kod behövs.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Planet barcode – auto height, custom width
            var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            planetGenerator.Save("PostalPlanetBarWidth4.png", BarCodeImageFormat.Png);

            // RM4SCC barcode – custom width and explicit height
            var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both postal barcodes have been saved.");
        }
    }
}
```

**Förväntad output** (konsol):

```
Both postal barcodes have been saved.
```

Och två PNG‑filer visas i utmatningsmappen, var och en visar en tydlig poststreckkod redo för utskrift eller inbäddning.

---

## Vanliga frågor och felsökning

| Fråga | Svar |
|----------|--------|
| *Vad händer om jag behöver en annan X‑dimension för varje streckkod?* | Skapa separata `BarcodeGenerator`‑instanser och tilldela ett eget `XDimension.Pixels`‑värde innan du anropar `Save`. |
| *Varför ignorerar Planet‑streckkoden `BarHeight`?* | Planet‑formatet beräknar automatiskt höjden utifrån X‑dimensionen, så att sätta `BarHeight` har ingen effekt. |
| *Kan jag exportera SVG istället för PNG?* | Ja. Byt ut `BarCodeImageFormat.Png` mot `BarCodeImageFormat.Svg`. |
| *Vad händer om bilden blir suddig vid utskrift?* | Öka X‑dimensionen (t.ex. till 6 px) och generera bilden med högre DPI via `Resolution`‑inställningarna på generatorn. |

---

## Slutsats

Du vet nu hur du **skapar poststreckkod**‑bilder i C# och exakt **anger bredd** samt **ändrar streckkodens höjd** med `BarcodeGenerator`‑API:n. Exemplet täcker både automatiskt storleksbestämda (Planet) och manuellt storleksbestämda (RM4SCC) format, vilket ger dig en solid grund för alla post‑automatiseringsprojekt.

Nästa steg kan vara att utforska:
* Lägga till mänskligt läsbar text under streckkoden (`CodeTextParameters`).  
* Exportera till andra format som SVG eller PDF för vektorbaserad utskrift.  
* Integrera generatorn i ett webb‑API för att leverera streckkoder på begäran.

Känn dig fri att experimentera med olika dimensioner, kodningar och utdataformat för att passa ditt specifika postflöde. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närliggande ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa poststreckkod bild i C# – Fullständig steg‑för‑steg‑guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [Skapa poststreckkod i C# – Fullt generator‑exempel](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [Streckkodsgenerator‑exempel i C# – ange bredd och höjd](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}