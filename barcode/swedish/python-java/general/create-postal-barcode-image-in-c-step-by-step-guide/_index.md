---
category: general
date: 2026-08-03
description: Skapa poststreckkodbild i C# snabbt. Lär dig hur du genererar en poststreckkod,
  ställer in streckkodens dimensioner och genererar en Planet‑streckkod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: sv
lastmod: 2026-08-03
og_description: Skapa en poststreckkodsbild i C# med den här kompletta handledningen;
  lär dig hur du ställer in streckkodens dimensioner, genererar en Planet‑streckkod
  och producerar RM4SCC‑streckkoder.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Skapa poststreckkodbild i C# – fullständig programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Skapa poststreckkodsbild i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa poststreckkod bild i C# – steg‑för‑steg guide

Om du behöver **skapa poststreckkod bild** i C#, visar den här guiden exakt hur du gör. Vi går igenom **hur man genererar poststreckkod**, **hur man ställer in streckkodens dimensioner**, och hur man **genererar planet‑streckkod** för vanliga poststandarder.

Du avslutar med två färdiga PNG‑filer – en Planet‑streckkod och en RM4SCC‑streckkod – båda 100 px höga. Inga extra verktyg behövs utöver Aspose.BarCode för .NET‑biblioteket.

## Förutsättningar

* .NET 6 SDK eller senare (koden fungerar också med .NET Framework 4.7+)
* Visual Studio 2022 eller någon C#‑IDE
* NuGet‑paketet **Aspose.BarCode** (biblioteket som tillhandahåller `BarcodeGenerator`)

## Steg 1: Installera streckkodsbiblioteket

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Paketet lägger till `Aspose.BarCode`‑namnutrymmet, som innehåller `BarcodeGenerator` och uppräkningen `EncodeTypes` som behövs för poststreckkoder.

## Steg 2: Definiera utdatamappen

Att skapa en pålitlig sökväg för utdata förhindrar körningsfel när mappen inte finns.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Varför detta är viktigt*: `Directory.CreateDirectory` är idempotent – den skapar mappen endast om den ännu inte finns, vilket undviker undantag vid efterföljande körningar.

## Steg 3: Konfigurera vanliga streckkodsdimensioner

Genom att ange X‑dimensionen (bredden på en enskild stapel) och den totala stapelhöjden kan du kontrollera den visuella storleken på den genererade bilden.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Hur man ställer in streckkodsdimensioner**: Egenskapen `Parameters.Barcode.XDimension.Pixels` definierar den smala stapelns bredd, medan `Parameters.Barcode.BarHeight.Pixels` definierar den fulla höjden. Justera dessa värden för att uppfylla specifikationerna för din posttjänst.

## Steg 4: Generera en Planet‑streckkod

Planet är en mycket använd poststreckkod i Storbritannien. Följande kod skapar en 100 px‑hög Planet‑streckkod och sparar den som PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Varför detta fungerar**: `EncodeTypes.Planet` talar om för generatorn att använda Planet‑symboliken. Metoden `Save` skriver en PNG‑fil till den angivna sökvägen och bevarar de dimensioner vi satte tidigare.

## Steg 5: Generera en RM4SCC‑streckkod

RM4SCC är den nederländska poststreckkodstandarden. Koden nedan speglar Planet‑exemplet och visar **hur man genererar poststreckkod** av en annan typ med identiska dimensioner.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Båda PNG‑filerna ligger nu i mappen `Barcodes`. När du öppnar dem ser du rena, 100 px‑höga streckkoder som är redo för utskrift eller inbäddning i dokument.

## Fullständig källkod

Nedan finns det kompletta, körbara programmet som **skapar poststreckkod bild**‑filer för både Planet‑ och RM4SCC‑standarderna.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Förväntad output

När programmet körs skrivs filvägarna ut och två PNG‑filer skapas:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Varje bild är 100 px hög, med en 4‑pixel bred smal stapel, vilket matchar de dimensioner vi satte.

## Praktiska tips och vanliga fallgropar

* **Mappbehörigheter** – Om programmet körs under ett begränsat konto, se till att mål‑mappen är skrivbar.
* **Olika dimensioner** – För att skapa en högre streckkod, öka `barHeightPixels`. För finare upplösning, minska `xDimensionPixels`, men håll den ≥ 2 för att undvika renderingsartefakter.
* **Andra post‑symboliker** – Aspose.BarCode stödjer även `EncodeTypes.Postnet` och `EncodeTypes.AustralianPost`. Byt ut värdet på `EncodeTypes` och behåll samma dimensionslogik.
* **Bildformat** – Använd `BarCodeImageFormat.Jpeg` för mindre filstorlek när förlustfri kvalitet inte krävs.

## Slutsats

Du vet nu hur du **skapar poststreckkod bild**‑filer i C# genom att konfigurera dimensioner, välja rätt symbolik och spara resultatet som PNG. Handledningen täckte **hur man genererar poststreckkod**, demonstrerade **generera planet‑streckkod**, och förklarade **hur man ställer in streckkodsdimensioner** för konsekvent output.

Nästa steg: utforska **anpassning av streckkodsfärger**, lägga till **mänskligt läsbar text**, eller integrera bilderna i PDF‑fakturor. Samma mönster gäller för alla andra streckkodstyper som stöds av Aspose.BarCode, så att du kan utöka denna lösning till ett komplett postautomatiseringsflöde.


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to generate barcode java – Australia Post Barcode with Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}