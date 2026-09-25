---
category: general
date: 2026-08-22
description: Lär dig hur du genererar poststreckkod i C# och styr stapelhöjd, X‑dimension
  och bildformat med barcode‑generatorbiblioteket för C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: sv
lastmod: 2026-08-22
og_description: Generera poststreckkod i C# med full kontroll över stapelhöjd, X-dimension
  och bildformat. Följ den här steg‑för‑steg‑handledningen för att skapa perfekta
  postsymboler.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Generera poststreckkod i C# – fullständig guide med anpassad storlek
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Hur man genererar poststreckkod i C# med anpassade dimensioner
url: /sv/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så genererar du poststreckkod i C# med anpassade dimensioner

Om du behöver generera poststreckkod i C# visar den här guiden hela arbetsflödet. Du får se hur du styr stapelhöjden, justerar streckkodens X‑dimension och väljer rätt bildformat för streckkoden.

Poststreckkoder används av posttjänster världen över, och en pålitlig implementation måste producera konsekventa dimensioner över olika symbologier. I den här handledningen lär du dig att använda **BarcodeGenerator**‑klassen, ändra streckkodens bredd och spara resultatet som PNG, JPEG eller andra stödda format.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* En referens till **Aspose.BarCode**‑paketet från NuGet (eller något kompatibelt streckkodsgenereringsbibliotek för C#)  
* Grundläggande kunskap om C#‑syntax och Visual Studio eller din föredragna IDE  

Du behöver inga externa tjänster; koden körs helt på klientmaskinen.

## Steg 1: Skapa projektet och importera namnrymder

Skapa ett nytt konsolprogram och lägg till streckkodsbiblioteket. Följande `using`‑satser ger dig åtkomst till generatorn och bildformat‑enum‑värdena.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

`BarcodeGenerator`‑klassen är kärnan i streckkodsgeneratorns C#‑API. Den skapar ett objekt som innehåller alla renderingsparametrar.

## Steg 2: Generera en grundläggande poststreckkod med standarddimensioner

Det första exemplet skapar en Planet‑streckkod med standard stapelhöjd. Detta demonstrerar den minsta konfiguration som krävs för att generera en poststreckkod.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Varför detta fungerar*: När du utelämnar egenskapen `BarHeight` använder biblioteket den standardhöjd som definierats för den valda symbologin. `XDimension` styr **streckkodens X‑dimension**, vilket direkt påverkar symbolens totala bredd.

## Steg 3: Ändra streckkodens bredd och öka stapelhöjden

Ofta behöver du en högre stapel för att uppfylla specifika postkrav. Följande kod sätter en anpassad stapelhöjd på 100 pixlar samtidigt som X‑dimensionen behålls.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Varför justera höjden*: Egenskapen `BarHeight` styr den vertikala storleken på varje stapel. För posttjänster som kräver en minsta höjd säkerställer detta värde efterlevnad utan att påverka kodningen.

## Steg 4: Generera en RM4SCC‑streckkod med standardinställningar

RM4SCC är en annan vanlig post‑symbologi. Koden nedan speglar Planet‑exemplet men byter `EncodeTypes`‑enum.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Eftersom biblioteket automatiskt väljer rätt standardhöjd för RM4SCC får du en standard‑kompatibel bild med en enda kodrad.

## Steg 5: Ändra stapelhöjden för en RM4SCC‑streckkod

Om ett postningssystem kräver en högre stapel kan du ändra höjden exakt som du gjorde för Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Tips*: **Streckkodsbildformat**‑enumerationen innehåller `Jpeg`, `Bmp`, `Tiff` och `Gif`. Välj det format som matchar din efterföljande behandlingspipeline.

## Steg 6: Utforska andra bildformat och finjustera dimensioner

Nedan är ett kompakt kodsnutt som visar hur du byter utdataformat och experimenterar med olika X‑dimensioner.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Varför iterera*: Denna loop producerar en matris av bilder som illustrerar hur **ändra streckkodens bredd** (via X‑dimension) påverkar det övergripande utseendet. Den visar också att samma generator kan leverera flera **streckkodsbildformat** utan extra kodändringar.

## Vanliga fallgropar och hur du undviker dem

| Problem | Orsak | Lösning |
|---------|-------|---------|
| Staplarna är för tunna | X‑dimension satt till 1 pixel eller lägre | Sätt `XDimension.Pixels` till minst 2 för läsbarhet |
| Bilden är suddig | Sparas som JPEG med hög kompression | Använd `BarCodeImageFormat.Png` för förlustfri output |
| Oväntad storlek vid utskrift | DPI beaktas inte | Sätt `barcodeGenerator.Parameters.ImageResolution.Dpi` om skrivaren kräver en specifik DPI |
| Fel symbologi | Använder `EncodeTypes.Planet` för RM4SCC‑data | Välj rätt `EncodeTypes`‑värde som matchar posttjänstens specifikation |

## Verifiera resultatet

Efter att ha kört koden, öppna någon av de genererade PNG‑filerna. Du bör se en klar, rektangulär streckkod med jämna vertikala staplar. Stapelhöjden kommer att motsvara det värde du angav (t.ex. 100 pixel) och den totala bredden speglar **streckkodens X‑dimension** som du konfigurerade.

Om du behöver bädda in bilden i en webbsida fungerar PNG‑formatet nativt i webbläsare. För PDF‑rapporter kan du konvertera PNG‑filen till en byte‑array och infoga den med ett PDF‑bibliotek.

## Komplett exempel – alla steg i ett program

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

När du kör programmet skapas fyra PNG‑filer i `C:\Barcodes\`. Varje fil demonstrerar en annan kombination av **generera poststreckkod**, **streckkodens X‑dimension** och **streckkodsbildformat**.

## Slutsats

Du vet nu hur du genererar poststreckkod i C# och fullt kontrollerar stapelhöjd, modulbredd och utdataformat. Genom att justera **streckkodens X‑dimension** och använda rätt **streckkodsbildformat** kan du uppfylla alla postningsspecifikationer och integrera symbolerna i skrivbords‑, webb‑ eller mobilapplikationer.

Nästa steg är att utforska avancerade funktioner som att lägga till mänskligt läsbar text, tillämpa färgpaletter eller bädda in streckkoden i PDF‑dokument. Dessa ämnen bygger på samma **barcode generator C#**‑koncept som du just har bemästrat, så du kan utöka denna grund med självförtroende.

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närliggande ämnen som bygger vidare på teknikerna i den här guiden. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}