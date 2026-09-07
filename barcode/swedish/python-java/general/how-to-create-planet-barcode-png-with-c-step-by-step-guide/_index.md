---
category: general
date: 2026-09-07
description: Skapa planet‑streckkod PNG i C# snabbt. Lär dig hur du genererar planet‑streckkodsbilder
  med Aspose.BarCode med fyllda och tomma staplar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: sv
lastmod: 2026-09-07
og_description: Skapa planet-streckkod PNG i C# snabbt. Följ den här guiden för att
  lära dig hur du genererar planet-streckkodsbilder med fyllda och tomma staplar med
  hjälp av Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Skapa planet‑streckkod PNG i C# – komplett programmeringshandledning
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur du skapar planetstreckkod PNG med C# – steg‑för‑steg‑guide
url: /sv/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du planet streckkod PNG med C# – steg‑för‑steg guide

Om du behöver **skapa planet streckkod PNG**‑filer i C#, visar den här guiden de exakta stegen. Oavsett om du bygger en posttjänst‑integration eller en logistik‑dashboard, kommer du att lära dig **hur du genererar planet streckkod**‑bilder med både fyllda och tomma staplar med hjälp av Aspose.BarCode‑biblioteket.

I den här handledningen kommer du att:

* Ställ in utdata‑mappen för dina bilder.  
* Konfigurera en `BarcodeGenerator` för Planet‑symbologi.  
* Skapa en PNG med standardstil för fyllda staplar.  
* Skapa en PNG med tomma staplar för visuell kontrast.  

Inga externa tjänster krävs—allt körs lokalt på .NET 6 eller senare.

## Förutsättningar

Innan du börjar, se till att du har:

| Krav | Varför det är viktigt |
|------|------------------------|
| .NET 6 SDK (eller nyare) | Tillhandahåller runtime för C#‑konsolappen. |
| Visual Studio 2022 eller VS Code | Valfri IDE som kan kompilera C#‑projekt. |
| Aspose.BarCode för .NET (NuGet‑paketet `Aspose.BarCode`) | Tillhandahåller `BarcodeGenerator`‑klassen som används för att rendera Planet‑streckkoder. |
| Skrivbehörighet till en mapp på disken | PNG‑filerna kommer att sparas på den här platsen. |

Installera NuGet‑paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal och kör:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Det här skapar en minimal C#‑konsolapplikation med namnet **PlanetBarcodeDemo**.

## Steg 2: Definiera utdata‑katalogen

Den första kodsnutten bestämmer var de genererade PNG‑filerna ska lagras. Att använda en absolut eller relativ sökväg fungerar; se bara till att mappen finns eller låt programmet skapa den.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Varför detta steg?* Att separera utdata från källkoden håller ditt projekt prydligt och undviker oavsiktliga överskrivningar.

## Steg 3: Generera en fylld‑staplar Planet‑streckkod

En Planet‑streckkod består av koncentriska cirklar (fyllda som standard). Vi konfigurerar X‑dimensionen (pixelbredden för varje stapel) och sparar sedan bilden som PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Förklaring**

* `EncodeTypes.Planet` talar om för Aspose att använda Planet‑symbologi, vilket är vanligt för posttjänster.  
* `XDimension.Pixels = 4` ger en tydlig, utskrivbar storlek utan manuell skalning.  
* `Save`‑metoden skriver en PNG‑fil; du kan också välja JPEG eller BMP genom att ändra `BarCodeImageFormat`.

## Steg 4: Generera en tom‑staplar Planet‑streckkod

Ibland krävs en visualisering med tomma (transparenta) staplar—till exempel när streckkoden läggs över en färgad bakgrund. Att sätta `FilledBars` till `false` ger denna stil.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Förklaring**

* `FilledBars = false` inaktiverar de solida cirklarna och lämnar bara konturerna.  
* Alla andra inställningar (X‑dimension, datatsträng) förblir identiska, vilket garanterar att båda bilderna representerar samma data.

## Steg 5: Kör programmet och verifiera utdata

Kompilera och kör:

```bash
dotnet run
```

Du bör se konsolmeddelanden som bekräftar de sparade filerna, och mappen `Barcodes` kommer att innehålla:

* `PostalPlanetFilledBars.png` – en klassisk fylld‑staplar Planet‑streckkod.  
* `PostalPlanetEmptyBars.png` – samma data renderad med tomma staplar.

Öppna PNG‑filerna i någon bildvisare. Båda bilderna kodar den numeriska strängen **123456** och kan läsas av vanliga poststreckkodsläsare.

## Vanliga frågor och hantering av kantfall

### Vad händer om jag behöver ett annat dataformat?

Planet‑streckkoder accepterar numeriska strängar upp till 12 siffror. Om du skickar ett icke‑numeriskt värde kastar Aspose ett `ArgumentException`. Validera indata innan du skapar generatorn:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Hur ändrar jag bildstorleken utan att ändra stapelns tjocklek?

Använd egenskapen `Resolution` eller skala den resulterande bitmapen efter sparning:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Kan jag generera andra bildformat?

Ja. Ersätt `BarCodeImageFormat.Png` med `BarCodeImageFormat.Jpeg`, `Bmp` eller `Gif`. API‑et stödjer alla vanliga rasterformat.

### Vad sägs om färganpassning?

Sätt `BarColor` och `BackColor` på `Barcode`‑parametrarna:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Dessa alternativ fungerar för både fyllda och tomma staplar versionerna.

## Pro‑tips för produktionsanvändning

* **Cacha generatorn** när du behöver rendera många streckkoder med samma inställningar—att initiera objektet upprepade gånger ger extra overhead.  
* **Dispose** `BarcodeGenerator`‑objekt om du skapar många i en loop (de implementerar `IDisposable`).  
* **Validera utdata‑mappen** tidigt för att undvika körningsexceptioner på skrivskyddade kataloger.  

## Slutsats

Du vet nu hur du **skapar planet streckkod PNG**‑filer i C# och förstår **hur du genererar planet streckkod**‑bilder med både fyllda och tomma stapelstilar. Det kompletta, körbara exemplet visar hur du ställer in utdata‑katalogen, konfigurerar `BarcodeGenerator` och sparar resultaten som PNG‑filer.

Nästa steg kan du utforska:

* Lägga till **mänskligt läsbar text** under streckkoden (`planetFilled.Parameters.Caption.Visible = true`).  
* Integrera de genererade PNG‑filerna i en **PDF‑faktura** med Aspose.PDF.  
* Byta till andra post‑symbologier såsom **IMB** eller **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Känn dig fri att experimentera med stapelns tjocklek, färger och bildupplösning för att matcha dina specifika applikationskrav. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa Planet‑streckkod bild i C# – Hur man genererar poststreckkod](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Skapa Planet‑streckkod i C# – Fullständig steg‑för‑steg‑guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generera PNG‑streckkod med Aspose.BarCode för .NET: En‑dimensionella fyllda staplar](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}