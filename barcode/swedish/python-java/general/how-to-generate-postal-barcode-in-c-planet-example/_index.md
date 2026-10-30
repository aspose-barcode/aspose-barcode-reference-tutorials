---
category: general
date: 2026-10-28
description: Generera poststreckkod i C# med Planet-formatet. Detta exempel på en
  Planet-streckkod visar hur du ställer in streckkodens bredd och sparar både fyllda
  och tomma staplar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: sv
lastmod: 2026-10-28
og_description: Generera poststreckkod i C# med ett komplett planetstreckkodsexempel.
  Lär dig att ställa in streckkodens bredd, producera fyllda staplar och skapa tomma
  stapelbilder.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Skapa poststreckkod i C# – steg‑för‑steg guide
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man genererar poststreckkod i C# – planetexempel
url: /sv/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar poststreckkod i C# – planetexempel

Om du behöver generera poststreckkod i C# guidar den här guiden dig genom en komplett lösning. Du får se ett praktiskt planet‑streckkodsexempel som kodar en numerisk sträng, låter dig ställa in streckkodens bredd och sparar både fyllda och tomma stapelbilder.

Att skapa en poststreckkod kräver ingen komplex byggpipeline. I slutet av den här handledningen kan du integrera streckkodsgenerering i vilken .NET‑applikation som helst, anpassa X‑dimensionen och välja om staplarna ska visas fyllda eller tomma.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat  
* En C#‑utvecklingsmiljö (Visual Studio, VS Code eller Rider)  
* NuGet‑paketet **Aspose.BarCode for .NET** (version 23.10 eller nyare)  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

Kodsnuttarna nedan förutsätter att du har lagt till `using Aspose.BarCode.Generation;` högst upp i din fil.

## Generera poststreckkod med Planet‑symbologi

Det första steget är att skapa en `BarcodeGenerator`‑instans som använder Planet‑symbologi. Planet är ett poststreckkodformat som används av flera nationella posttjänster.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta är viktigt:**  
`EncodeTypes.Planet` talar om för biblioteket att använda Planet‑streckkodstandarden, som kodar numerisk data i en serie staplar och mellanslag. Konstruktorn tar emot datasträngen (`"123456"` i detta fall) som du vill koda.

När programmet körs skapas två PNG‑filer i den körbara filens arbetskatalog:

* **PostalPlanetFilledBars.png** – staplarna renderas som solida svarta rektanglar.  
* **PostalPlanetEmptyBars.png** – staplarna renderas som vita rektanglar med en svart kontur, användbart för utskrift på mörka bakgrunder.

## Ställ in streckkodens bredd (X‑dimension) i pixlar

Den visuella storleken på en streckkod styrs av X‑dimensionen, som definierar bredden på en enskild stapel. Att justera detta värde säkerställer att streckkoden skannas korrekt vid den avsedda utskriftsupplösningen.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Varför du bör sätta den:**  
En större X‑dimension gör streckkoden lättare att skanna med lågupplösta skannrar, medan ett mindre värde minskar den totala bildstorleken för högdensitetsutskrifter. Standardbredden är 2 pixlar; 4 pixlar är en vanlig kompromiss för de flesta skrivbordsskrivare.

Du kan experimentera med olika värden:

| Pixlar | Typiskt användningsfall |
|--------|------------------------|
| 2      | Högdensitetsetiketter |
| 4      | Standard kontorsutskrift |
| 6‑8    | Storskalig skyltning |

**Tips:** Testa alltid den genererade streckkoden med din målskanner efter att du har ändrat X‑dimensionen.

## Planet‑streckkodsexempel – fyllda vs tomma staplar

En Planet‑streckkod kan renderas med antingen solida (fyllda) staplar eller konturerade (tomma) staplar. `FilledBars`‑egenskapen växlar detta beteende.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Varför du kan välja tomma staplar:**  
Tomma staplar förbättrar kontrasten på mörkt tonad förpackning, eftersom den vita insidan av varje stapel framträder mot en mörk bakgrund. Fyllda staplar är standard och fungerar bra på ljusa medier.

**Förväntad output:**  

*Båda bilderna visar samma kodade data (`123456`).* Den enda visuella skillnaden är stapelstilen. Nedan följer en textuell beskrivning av vad du kommer att se:

* **Fylld stapelbild:** Solida svarta vertikala staplar på en vit bakgrund.  
* **Tom stapelbild:** Svarta konturer som bildar samma mönster, med vita insidor.

Du kan öppna PNG‑filerna i någon bildvisare för att verifiera att mönstret matchar Planet‑specifikationen.

## Anpassa ytterligare streckkodsegenskaper (valfritt)

Även om kärnstegen ovan täcker de flesta scenarier kan du vilja finjustera andra inställningar:

| Property | Beskrivning | Typiskt värde |
|----------|-------------|---------------|
| `Barcode.Color` | Förgrundsfärg på staplarna | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Bakgrundsfyllnadsfärg | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Mänskligt läsbar text som visas under streckkoden | Samma som kodad data eller en anpassad etikett |
| `Barcode.ImageFormat` | Utdataformat (PNG, JPEG, BMP, etc.) | `BarCodeImageFormat.Png` |

Exempel på att sätta en anpassad förgrundsfärg:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Dessa valfria justeringar hjälper dig att matcha företagets varumärke eller uppfylla specifika utskriftskrav.

## Vanliga fallgropar och hur man undviker dem

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Barcode is unreadable | X‑dimension too small for the printer’s DPI | Increase `XDimension.Pixels` to 4 or higher |
| Image file is corrupted | Missing write permissions in the target folder | Use an absolute path or ensure the directory exists |
| Wrong symbology used | Passing `EncodeTypes.Code128` instead of `EncodeTypes.Planet` | Verify the `EncodeTypes` argument matches the postal format |

**Pro‑tips:** Generera alltid en teststreckkod och skanna den med den avsedda hårdvaran innan du går i produktion.

## Fullt, körbart exempel

Nedan följer en fristående konsolapplikation som innehåller alla stegen som diskuterats. Kopiera koden till ett nytt .NET‑konsolprojekt och kör det för att se de två PNG‑filerna dyka upp i utskriftsmappen.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Verifieringssteg:**  

1. Bygg projektet (`dotnet build`).  
2. Kör den körbara filen (`dotnet run`).  
3. Hitta `PostalPlanetFilledBars.png` och `PostalPlanetEmptyBars.png` i mappen `bin/Debug/net6.0`.  
4. Öppna varje bild; du bör se en serie vertikala staplar som representerar den numeriska strängen

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar planet‑streckkod med fyllda och tomma staplar](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Hur man ställer in bredd och genererar en Planet‑streckkod i C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Skapa poststreckkod i C# – fullständigt generatorexempel](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}