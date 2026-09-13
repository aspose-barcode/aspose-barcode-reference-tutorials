---
category: general
date: 2026-09-13
description: Skapa streckkodbild med Aspose.Barcode i C#. Lär dig att generera streckkod
  i PNG, ange anpassade streckkodsdimensioner och spara streckkodsfiler effektivt.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate barcode png
- how to save barcode
- aspose barcode generator
- custom barcode dimensions
language: sv
lastmod: 2026-09-13
og_description: Skapa streckkodbild med Aspose.Barcode i C#. Denna guide visar hur
  man genererar streckkod‑PNG, styr anpassade dimensioner och sparar streckkodsfiler.
og_image_alt: Screenshot of a barcode image created with Aspose.Barcode in C#
og_title: Skapa streckkodbild med Aspose.Barcode – steg‑för‑steg C#‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create barcode image using Aspose.Barcode in C#. Learn to generate
    barcode PNG, set custom barcode dimensions, and save barcode files efficiently.
  headline: How to create barcode image with Aspose.Barcode in C#
  type: TechArticle
- description: Create barcode image using Aspose.Barcode in C#. Learn to generate
    barcode PNG, set custom barcode dimensions, and save barcode files efficiently.
  name: How to create barcode image with Aspose.Barcode in C#
  steps:
  - name: Initialise the Aspose barcode generator
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.Generation;'
  - name: Set common barcode parameters (pixel‑size of the smallest bar)
    text: '```csharp // Set the X‑dimension – the width of the narrowest bar element,
      in pixels. barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;'
  - name: Generate barcode PNG with a 30 px height
    text: '```csharp // Configure a 30 px high barcode. barcodeGenerator.Parameters.Barcode.BarHeight.Pixels
      = 30;'
  - name: Change the height to 60 px and save a second image
    text: '```csharp // Adjust the bar height to 60 px for a larger visual representation.
      barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;'
  - name: Full, runnable example
    text: Below is a complete console application that puts all the steps together.
      Copy the code into a new `.csproj` project and run it.
  type: HowTo
tags:
- Aspose.Barcode
- C#
- barcode generation
- PNG
- custom dimensions
title: Hur man skapar streckkodbild med Aspose.Barcode i C#
url: /sv/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du streckkodsbilder med Aspose.Barcode i C#

Om du behöver **skapa streckkodsbilder** i en .NET‑applikation, gör Aspose.Barcode det enkelt. Denna handledning visar hur du **genererar streckkod PNG**, anpassar streckkodens dimensioner och korrekt **sparar streckkod**‑filer till disk.

Du kommer att lära dig att:

* Initiera **Aspose barcode generator** för en DataBar Omni‑directional‑symbol.  
* Justera X‑dimensionen och stapelhöjden för att uppfylla ditt krav på **custom barcode dimensions**.  
* Exportera resultatet som en PNG‑fil, vilket täcker steget **how to save barcode** för både 30 px och 60 px höjder.  

Inga externa verktyg krävs—endast Aspose.Barcode för .NET NuGet‑paketet och en .NET 6+‑runtime.

---

## Vad du behöver innan du börjar

| Förutsättning | Orsak |
|--------------|--------|
| Visual Studio 2022 (or any C# IDE) | För att kompilera och köra exempel‑konsolapplikationen |
| .NET 6 SDK or later | Tillhandahåller runtime för koden |
| Aspose.Barcode for .NET NuGet package | Biblioteket som innehåller `BarcodeGenerator` |
| Write permission to a folder on disk | Krävs för **how to save barcode**‑bilder |

Installera NuGet‑paketet med följande kommando:

```bash
dotnet add package Aspose.Barcode
```

---

## Så skapar du streckkodsbilder med Aspose.Barcode

Följande avsnitt går igenom varje steg och förklarar **varför** koden är skriven på det sättet, inte bara **vad** den gör.

### Steg 1: Initiera Aspose barcode generator

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Create a DataBar Omni‑directional barcode generator with the desired data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

// Why this matters:
// * `EncodeTypes.DatabarOmniDirectional` selects the specific symbology.
// * The string "(01)12345678901231" follows GS1 Application Identifier (01) for GTIN.
// * Instantiating `BarcodeGenerator` prepares all subsequent parameter settings.
```

### Steg 2: Ställ in vanliga streckkodparametrar (pixel‑storlek på den minsta stapeln)

```csharp
// Set the X‑dimension – the width of the narrowest bar element, in pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Why this matters:
// The X‑dimension controls overall visual density. A value of 2 px is a good default for screen display.
```

### Steg 3: Generera streckkod PNG med 30 px höjd

```csharp
// Configure a 30 px high barcode.
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the barcode as a PNG image.
string output30 = @"C:\Barcodes\DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
```

**Hur detta uppfyller “generate barcode png”**:  
`BarCodeImageFormat.Png` talar om för Aspose att rendera streckkoden som en förlustfri PNG‑fil, idealisk för vidare bearbetning eller utskrift.

### Steg 4: Ändra höjden till 60 px och spara en andra bild

```csharp
// Adjust the bar height to 60 px for a larger visual representation.
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image.
string output60 = @"C:\Barcodes\DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
```

**Hur detta täcker “how to save barcode”**:  
`Save`‑metoden skriver bilden till filsystemet med den sökväg du anger. Du kan upprepa anropet med olika parametrar för att skapa flera bilder från samma generator‑instans.

### Fullständigt, körbart exempel

Nedan är ett komplett konsolprogram som samlar alla steg. Kopiera koden till ett nytt `.csproj`‑projekt och kör det.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for a DataBar Omni‑directional barcode.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (width of the smallest bar).
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create a 30 px high PNG.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"C:\Barcodes\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // 4️⃣ Create a 60 px high PNG.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"C:\Barcodes\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

**Förväntad output** (konsol):

```
Saved 30 px barcode to C:\Barcodes\DatabarBarHeight30Pixels.png
Saved 60 px barcode to C:\Barcodes\DatabarBarHeight60Pixels.png
```

Efter körning hittar du två PNG‑filer i `C:\Barcodes`. Båda filerna innehåller en giltig DataBar Omni‑directional‑symbol, som bara skiljer sig i stapelhöjd.

---

## Generera streckkod PNG med anpassade dimensioner (avancerat)

Du kan behöva mer exakt kontroll över streckkodens visuella storlek, särskilt när du integrerar den i PDF‑filer eller tryckta etiketter. Aspose.Barcode exponerar många parametrar:

| Parameter | Typisk användning |
|-----------|-------------------|
| `XDimension.Pixels` | Styr den smalaste stapelbredden. |
| `BarHeight.Pixels` | Ställer in den totala stapelhöjden. |
| `Margins` | Lägger till vitt utrymme runt streckkoden. |
| `Resolution` | Bestämmer DPI för rasterbilder (påverkar PNG‑kvaliteten). |

Exempel på att sätta en upplösning på 300 dpi och 5 px marginaler:

```csharp
generator.Parameters.ImageResolution = 300; // 300 DPI
generator.Parameters.Barcode.Margins.All = 5; // 5 px on every side
```

---

## Hur man sparar streckkodsfiler i olika format

Medan PNG är vanligt för webb‑ och UI‑scenarier, kan Aspose.Barcode också exportera **JPEG**, **BMP**, **TIFF** och **SVG**. Att byta format kräver bara att du ändrar `BarCodeImageFormat`‑enumet:

```csharp
generator.Save(@"C:\Barcodes\barcode.svg", BarCodeImageFormat.Svg);
```

Samma **how to save barcode**‑logik gäller oavsett format, så att du kan återanvända samma generator‑instans.

---

## Vanliga fallgropar och pro‑tips

* **Återanvänd inte samma generator utan att återställa dimensionerna** – Att ändra `BarHeight.Pixels` efter ett `Save`‑anrop fungerar, men om du också behöver justera `XDimension.Pixels` bör du återställa dem innan nästa sparning för att undvika oavsiktlig skalning.  
* **Filvägen måste vara absolut eller ha skrivrättighet** – Relativa sökvägar löses mot arbetskatalogen, vilket kan skilja sig när du kör från Visual Studio jämfört med en kompilerad exe.  
* **Kontrollera returvärdet från `Save`** – Den kastar `ArgumentException` om sökvägen är ogiltig, så omslut anropen med `try / catch` i produktionskod.  

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Slutsats

Du vet nu hur du **skapar streckkodsbilder** med Aspose.Barcode, **genererar streckkod PNG** med precisa **custom barcode dimensions**, och korrekt **how to save barcode**‑filer i olika storlekar. Genom att justera `XDimension` och `BarHeight` kan du uppfylla de exakta visuella kraven för vilket märknings‑ eller utskriftsflöde som helst.

Nästa steg är att utforska relaterade ämnen som **infoga streckkodsbilder i PDF‑dokument**, **batch‑generera flera streckkoder**, eller **använda andra symboler** som QR‑Code eller Code 128. Varje scenario bygger på samma grunder som behandlats här.

Lycka till med kodningen, och njut av den flexibilitet som Aspose.Barcode‑generatorn erbjuder!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkodsbilder med anpassning av extra utrymme med hjälp av Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Skapa DotCode‑streckkodsbilder – rader & kolumner (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}