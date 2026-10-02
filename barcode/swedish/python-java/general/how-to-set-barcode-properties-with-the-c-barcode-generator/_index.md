---
category: general
date: 2026-09-10
description: Hur man ställer in en streckkod i C# med en streckkodsgenerator. Justera
  modulbredden för streckkoden, generera streckkodsbilder och lär dig hur du sparar
  streckkodsfiler.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: sv
lastmod: 2026-09-10
og_description: Hur man ställer in en streckkod i C# med en streckkodsgenerator. Lär
  dig att justera modulbredd, generera en streckkod och spara streckkodsbilden effektivt.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Hur man ställer in streckkodsegenskaper med C# Barcode Generator
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Hur man ställer in streckkodsegenskaper med C#‑streckkodsgeneratorn
url: /sv/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in streckkodsegenskaper med C# Barcode Generator

Att ställa in streckkodsegenskaper är viktigt när du behöver exakt kontroll över en streckkods visuella stil. Denna guide visar hur du genererar en Planet‑streckkod, justerar streckkodens modulbredd och sparar streckkodsbilden med C# Barcode Generator.

Du får ett komplett, körbart exempel som täcker varje steg från att skapa streckkodobjektet till att skriva PNG‑filerna till disk. Ingen extern dokumentation behövs – bara koden nedan och Aspose.BarCode‑biblioteket (eller något kompatibelt barcode‑SDK). I slutet av handledningen kan du svara på frågor som “hur genererar man streckkod med anpassade dimensioner?” och “hur sparar man streckkod i olika format?”.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 eller senare installerat  
* Visual Studio 2022 (eller någon annan C#‑IDE)  
* **Aspose.BarCode**‑NuGet‑paketet (eller ett annat bibliotek som tillhandahåller `BarcodeGenerator`)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Hur man ställer in modulbredd för streckkoden

*Modulbredden* (även kallad X‑dimension) bestämmer pixelstorleken för varje smal stapel i streckkoden. Genom att sätta detta värde kan du kontrollera den övergripande storleken och läsbarheten på bilden.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Varför detta är viktigt*: En större X‑dimension ger en större streckkod som är lättare för skannrar att läsa på avstånd, medan ett mindre värde minskar filstorleken för rendering på skärm.

## Generera en streckkod med fyllda staplar

Standardstilen för Planet‑streckkoden använder **fyllda staplar** (solida svarta staplar). Följande kod skapar bilden och sparar den som PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Resultat**: `PostalPlanetFilledBars.png` innehåller en standard Planet‑streckkod där varje stapel är fylld.

## Skapa en streckkod med tomma staplar

Ibland behöver du en streckkod som bara visar konturerna av staplarna (tomma staplar). För att uppnå detta duplicerar du generatorn, behåller samma modulbredd och stänger av flaggan `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Resultat**: `PostalPlanetEmptyBars.png` visar samma data men med oifyllda staplar, användbart för designintensiva dokument där du vill att streckkoden ska smälta in i bakgrunden.

## Hur man sparar streckkod i olika format

`Save`‑metoden accepterar alla format som stöds av SDK:t, såsom **Jpeg**, **Bmp**, **Gif** eller **Svg**. Att byta format kräver bara att du byter värdet i `BarCodeImageFormat`‑enum.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Tips*: Använd SVG när du behöver en vektorgrafik som kan skalas utan pixling, särskilt för utskriftsklara PDF‑filer.

## Fullt, körbart exempel

När du sätter ihop alla bitar får du ett självständigt program som du kan klistra in i en konsolapp.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Förväntad utdata**

| Filnamn                       | Beskrivning                               |
|-------------------------------|-------------------------------------------|
| `PostalPlanetFilledBars.png`  | Planet‑streckkod med solida svarta staplar |
| `PostalPlanetEmptyBars.png`   | Samma data, staplar renderade som konturer |
| `PostalPlanet.svg`            | Vektorversion för skalning utan förlust    |

Kör programmet, öppna de genererade filerna och verifiera att streckkoderna matchar den numeriska strängen “123456”.

## Vanliga variationer och kantfall

| Situation                               | Justering                                                               |
|----------------------------------------|-------------------------------------------------------------------------|
| Behöver en tjockare streckkod          | Öka `XDimension.Pixels` (t.ex. `8`)                                      |
| Vill ha en mindre filstorlek           | Använd `BarCodeImageFormat.Jpeg` eller minska X‑dimensionen              |
| Generera andra symbologier             | Byt `EncodeTypes.Planet` mot `EncodeTypes.Code128`, `QR` osv.            |
| Skriver ut på högupplösta skrivare      | Spara som `BarCodeImageFormat.Tiff` för förlustfri rasterutdata          |
| Kör på en huvudlös server               | Ingen UI‑kod behövs; generatorn fungerar i en konsol‑ eller tjänstekontext |

**Proffstips**: Validera alltid den genererade streckkoden med en skanner eller ett verifieringsverktyg innan du använder den i produktion. Fel modulbredd eller fel format kan leda till skanningsfel.

## Slutsats

Du vet nu hur du ställer in streckkodsegenskaper med C# Barcode Generator, hur du kontrollerar modulbredden, hur du genererar både fyllda och tomma stapelstilar samt hur du sparar streckkoden i PNG‑ eller SVG‑format. Dessa steg ger dig en solid grund för att lägga till streckkodsskapande i vilken .NET‑applikation som helst.

Fortsätt sedan med relaterade ämnen som **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, och **creating QR codes with custom colors**. Experimentera med olika `EncodeTypes` och bildformat för att hitta den bästa lösningen för ditt projekt.

## Vad bör du lära dig härnäst?

De följande handledningarna täcker nära besläktade ämnen som bygger vidare på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man sparar streckkod i C# – Generera PDF417‑streckkoder](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Barcode Generator‑handledning: Hur man genererar PDF417‑streckkod i C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Hur man ställer in felnivå i PDF417‑streckkod – Komplett guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}