---
category: general
date: 2026-08-15
description: Streckkodbild PNG i C# – lär dig hur du genererar poststreckkoder, skapar
  en Planet‑streckkod och ändrar streckkodens höjd med en enkel generator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: sv
lastmod: 2026-08-15
og_description: Barcode image PNG i C#‑handledning visar hur man genererar poststreckkoder,
  skapar en Planet‑streckkod och ändrar streckkodens höjd med BarcodeGenerator API.
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: Streckkodsbild PNG i C# – generera och justera streckkoder
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: Barcode‑bild PNG i C# generera streckkoder, ändra höjd
url: /sv/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode‑bild PNG i C# – generera streckkoder, ändra höjd

Om du behöver en **barcode image PNG** i C#, guidar den här handledningen dig genom hela processen. Du kommer att lära dig hur du genererar poststreckkoder, skapar en Planet‑streckkod och ändrar streckkodens höjd utan att lämna din IDE.

Att generera pålitliga PNG‑streckkoder är ett vanligt krav för fraktsedlar, lagersystem och automatiserade postlösningar. I slutet av den här handledningen har du ett återanvändbart kodsnutt som producerar högkvalitativa PNG‑filer för både Planet‑ och RM4SCC‑format, och du förstår hur du justerar stapelhöjden för att uppfylla postens specifikationer.

## Vad du behöver

- .NET 6+ eller .NET Framework 4.7.2 (BarcodeGenerator‑API:n fungerar med alla moderna .NET‑runtime‑miljöer)  
- En referens till NuGet‑paketet **Aspose.BarCode for .NET** (eller något kompatibelt bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`)  
- Grundläggande kunskap om C#‑syntax och fil‑I/O  

Inga extra verktyg krävs; koden körs i Visual Studio, Rider eller `dotnet`‑CLI:n.

## Barcode image PNG – grundläggande generering

Det första steget är att skapa en **barcode image PNG** med standarddimensioner. Detta etablerar grundfilen som du senare kan anpassa.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Varför detta fungerar:**  
- `EncodeTypes.Planet` talar om för generatorn att använda Planet‑symbologi, vilket krävs av många posttjänster.  
- `XDimension.Pixels` styr bredden på den minsta stapeln; ett värde på 4 px ger en läsbar streckkod vid vanliga etikettstorlekar.  
- `Save`‑metoden skriver en **barcode image PNG**‑fil till disk och bevarar all vektorinformation som raster‑pixlar.

## Ändra streckkodens höjd – anpassa den visuella vikten

Postens riktlinjer kräver ofta en specifik stapelhöjd. Följande kodsnutt visar hur du anger en anpassad höjd på 100 pixlar för samma Planet‑streckkod.

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Varför du ändrar höjden:**  
En högre stapel förbättrar skanningspålitligheten på lågupplösta skrivare, medan en kortare stapel minskar etikettutrymmet. `BarHeight.Pixels`‑egenskapen låter dig finjustera detta attribut utan att påverka X‑dimensionen.

## Generera poststreckkod – skapa ett RM4SCC‑exempel

RM4SCC‑formatet är en annan vanlig poststreckkod som används i Storbritannien. Genereringsstegen speglar Planet‑exemplet och förstärker **barcode generator c#**‑mönstret.

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## Ändra streckkodens höjd – RM4SCC‑variation

Liksom Planet‑streckkoden kan du justera RM4SCC‑stapelhöjden. Koden nedan sätter höjden till 100 px och producerar en andra **barcode image PNG** för samma datasträng.

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## Fullt, körbart exempel

Genom att kombinera alla steg får du ett enda, självständigt program som skapar fyra PNG‑filer:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [Skapa streckkod med anpassad höjd – En-dimensionella streckkoder](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Skapa streckkod PNG – DataMatrix bildförhållande – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [Skapa streckkod bild C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}