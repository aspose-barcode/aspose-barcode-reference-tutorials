---
category: general
date: 2026-09-26
description: Lär dig hur du skapar en poststreckkodbild i C#. Den här guiden visar
  hur du genererar planet‑streckkod och ställer in streckkodens höjd för anpassad
  utskrift.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: sv
lastmod: 2026-09-26
og_description: Skapa poststreckkodbild i C# snabbt. Följ den här handledningen för
  att generera planet‑streckkod, ställa in streckkodshöjd och producera högkvalitativa
  PNG‑filer.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Skapa poststreckkodbild med anpassade höjder i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Hur man skapar en poststreckkodsbild med anpassade höjder i C#
url: /sv/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar poststreckkodbild med anpassade höjder i C#

Om du behöver **skapa poststreckkodbild** för postetiketter visar den här handledningen exakt hur du går tillväga. Du lär dig att generera en Planet‑streckkod, justera streckhöjden och spara resultatet som en PNG‑fil – allt med Aspose.BarCode‑biblioteket för .NET.

Att skapa en streckkodbild kräver inget externt designverktyg. När du är klar med den här guiden kan du producera både standard‑höjd och anpassad‑höjd streckkoder för Planet‑ och RM4SCC‑standarder, redo att integreras i vilket fraktflöde som helst.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* Visual Studio 2022 (eller någon annan C#‑IDE)  
* Aspose.BarCode för .NET tillagd via NuGet (`Install-Package Aspose.BarCode`)  

Ingen ytterligare konfiguration krävs; biblioteket hanterar bildrendering internt.

## Steg 1: Skapa projektet och importera namnrymder

Skapa en ny konsolapplikation och lägg till de nödvändiga `using`‑satserna.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Dessa namnrymder exponerar klassen `BarcodeGenerator` och uppräkningen `EncodeTypes` som du kommer att använda för att **generera planet‑streckkod** och andra postformat.

## Steg 2: Skapa en Planet‑streckkod med standardstreckhöjd

Det första exemplet skapar en Planet‑streckkod med bibliotekets standardstreckhöjd. Detta visar grundutdata innan du applicerar någon anpassad storlek.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** Standardhöjden är lämplig för de flesta etikettprinterar, men vissa arbetsflöden kräver högre streck för ökad skanningspålitlighet. Koden ovan ger dig en referensbild att jämföra med versionen med anpassad höjd.

## Steg 3: Applicera en anpassad streckhöjd på Planet‑streckkoden

För att **sätta streckkodshöjd** manuellt, tilldela ett pixelvärde till `BarHeight.Pixels`. Följande kodsnutt skapar en 100‑pixel‑hög Planet‑streckkod.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Proffstips:** Välj en streckhöjd som matchar DPI‑värdet på din printer. För en 300 dpi‑printer motsvarar 100 pixel ungefär 0,33 tum, vilket ofta rekommenderas för postskannrar.

## Steg 4: Generera en RM4SCC‑streckkod med standardhöjd

RM4SCC är en annan vanlig post‑symbologi. Processen speglar Planet‑exemplet men använder `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Detta steg bekräftar att samma **barcode generator custom height**‑logik fungerar över olika postformat.

## Steg 5: Applicera en anpassad höjd på RM4SCC‑streckkoden

Slutligen justerar du streckhöjden för RM4SCC‑streckkoden på samma sätt som för Planet‑streckkoden.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Förväntad output

När du kör hela programmet skapas fyra PNG‑filer i projektets output‑katalog:

| File name                               | Bar height | Symbology |
|----------------------------------------|------------|-----------|
| `PostalPlanetBarHeightDefault.png`     | default    | Planet    |
| `PostalPlanetBarHeight100Pixels.png`   | 100 px     | Planet    |
| `PostalRM4SCCBarHeightDefault.png`     | default    | RM4SCC    |
| `PostalRM4SCCBarHeight100Pixels.png`   | 100 px     | RM4SCC    |

Varje bild visar en tydlig, högkontrast‑streckkod som är klar för utskrift på postetiketter. Du kan öppna PNG‑filerna i valfri bildvisare för att verifiera streckdimensionerna.

## Vanliga frågor och edge cases

**Vad händer om jag behöver en streckhöjd i millimeter istället för pixlar?**  
Biblioteket arbetar i pixlar eftersom det direkt motsvarar bitmap‑upplösningen. Konvertera millimeter till pixlar med printerns DPI:  
`pixels = (mm / 25.4) * DPI`. Sätt `BarHeight.Pixels` till det beräknade värdet.

**Kan jag ändra streckhöjden efter att ha anropat `Save`?**  
Nej. Streckkodsbilden renderas i det ögonblick `Save` anropas. Justera alla parametrar innan du anropar `Save`.

**Krävs en större X‑dimension för högre streck?**  
Att öka `XDimension` gör varje modul bredare, vilket kan förbättra läsbarheten på lågupplösta printerar. Det ökar dock den totala streckkodens bredd. Testa båda värdena för att hitta optimal balans för din etikettstorlek.

**Fungerar samma kod på .NET Framework 4.8?**  
Ja. Aspose.BarCode stödjer .NET Framework 4.6.2 och senare, så du kan rikta mot äldre runtime‑versioner utan förändringar.

## Fullständig källkod för snabb kopiering

Nedan finns det kompletta, körbara programmet som innehåller alla steg som beskrivits ovan.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Kör programmet så bekräftar konsolen att varje bild har sparats. Du kan nu bädda in dessa PNG‑filer i dina postetikettmallar, skriva ut dem eller skicka dem till ett tredjeparts‑logistik‑API.

## Slutsats

Du vet nu hur du **skapar poststreckkodbilder** i C# med Aspose.BarCode. Guiden täckte generering av en Planet‑streckkod, justering av streckhöjden och tillämpning av samma teknik på RM4SCC‑streckkoder. Genom att kontrollera `XDimension` och `BarHeight.Pixels` får du precisa visuella resultat som uppfyller posttjänsternas krav.

Nästa steg är att utforska relaterade ämnen såsom **generering av QR‑koder för spårning**, **inbäddning av streckkoder i PDF‑fakturor**, eller **batch‑bearbetning av flera streckkodsbilder**. Att justera streckhöjden är bara en av många möjligheter; du kan också anpassa färger, lägga till mänskligt läsbar text eller exportera till SVG för webbbruk.

Lycka till med kodningen, och må dina utskick skannas felfritt!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Create postal barcode image in C# – step‑by‑step guide](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Create Postal Barcode Images – Change Barcode Height Easily](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}