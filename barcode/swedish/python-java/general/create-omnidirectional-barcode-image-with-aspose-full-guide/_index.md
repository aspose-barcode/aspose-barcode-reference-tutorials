---
category: general
date: 2026-07-27
description: Skapa en omnidirektionell streckkodsbild med Aspose.BarCode. Lär dig
  hur du genererar streckkod med Aspose, justerar bildförhållandet och sparar PNG-filer.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: sv
lastmod: 2026-07-27
og_description: Skapa en omnidirektionell streckkodbild med Aspose. Följ den här guiden
  för att generera streckkod med Aspose, justera bildförhållanden och exportera PNG-filer.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Skapa omnidirektionell streckkodbild med Aspose – steg för steg
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Skapa omnidirektionell streckkodbild med Aspose – Fullständig guide
url: /sv/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa omnidirektionell streckkodbild med Aspose – Fullständig guide

Har du någonsin behövt **skapa en omnidirektionell streckkodbild** men varit osäker på vilket bibliotek du ska välja? Du är inte ensam. I många logistik- och detaljhandelsprojekt är DataBar Stacked Omnidirectional‑formatet den hemliga ingrediensen för kompakt, högdensitetskodning.

Den goda nyheten? Med **Aspose.BarCode** kan du generera den streckkoden på några få rader, justera dess bildförhållande och spara PNG‑filen direkt på disk. Nedan kommer du att se exakt hur du **genererar streckkod med Aspose**, varför varje inställning är viktig och vad du bör vara uppmärksam på när du ändrar bildförhållandet.

---

## Vad den här handledningen täcker

Vi går igenom hela livscykeln:

1. Ställa in utdatamappen.
2. Instansiera en DataBar Stacked Omnidirectional‑generator.
3. Konfigurera pixelmått och bildförhållanden.
4. Spara streckkoden som PNG‑filer.
5. Utöka exemplet för andra format och kantfall.

När du är klar har du en färdig C#‑konsolapp som skapar två olika streckkodsbilder. Inga externa verktyg, bara ren Aspose‑kod.

**Förutsättningar**

- .NET 6.0 SDK eller senare (koden fungerar även på .NET Framework 4.7.2).
- Aspose.BarCode för .NET NuGet‑paket (`Install-Package Aspose.BarCode`).
- En mapp på disken där bilderna kan skrivas.

Om du redan har detta, låt oss dyka in.

---

## Steg 1: Förbered utdatamappen

Först och främst – tala om för programmet var PNG‑filerna ska sparas. Att hårdkoda en sökväg fungerar för ett demo, men i produktion läser du troligen in den från konfiguration.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Varför detta är viktigt:* `Directory.CreateDirectory` är idempotent; den kastar inget fel om mappen redan finns, vilket sparar dig ett try‑catch‑block.

---

## Steg 2: Skapa en DataBar Stacked Omnidirectional‑generator

Nu startar vi generatorn med den specifika kodningstypen och exempeldata. Strängen `"(01)12345678901231"` följer GS1 Application Identifier‑syntaxen för ett 14‑siffrigt GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Förklaring:* `EncodeTypes.DatabarStackedOmniDirectional` talar om för Aspose att använda den omnidirektionella varianten, som kan läsas från vilken riktning som helst – perfekt för små etiketter som kan roteras.

---

## Steg 3: Ställ in gemensamma streckkodparametrar

Innan vi renderar något definierar vi den minsta elementstorleken (X‑Dimension). Ett värde på **2 pixlar** ger en skarp bild utan att filstorleken blåser upp.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tips:* Om du behöver högre upplösning för utskrift, öka detta till 3 eller 4. Kom bara ihåg att större X‑Dimensioner ökar både bredd och höjd proportionellt.

---

## Steg 4: Generera och spara med bildförhållande 15

DataBar‑familjen låter dig justera **bildförhållandet**, som styr förhållandet mellan höjd och bredd. Ett bildförhållande på **15** är ett vanligt standardvärde för omnidirektionella streckkoder.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Vad du kommer att se:* En relativt hög streckkod som fortfarande får plats bekvämt på en 2 × 1 cm‑etikett. PNG‑formatet bevarar förlustfri kvalitet, idealiskt för vidare bearbetning eller utskrift.

---

## Steg 5: Ändra bildförhållandet till 30 och spara igen

Vill du ha en kortare streckkod? Ändra bara `AspectRatio`‑egenskapen och anropa `Save` igen. Ingen anledning att skapa en ny generator.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Varför återanvända samma generator?* Aspose‑objekt är lätta; att ändra en egenskap och spara igen är snabbare än att konstruera en ny instans, och det garanterar att samma kodningsinställningar (t.ex. X‑Dimension) förblir konsistenta.

---

## Fullständigt fungerande exempel

Sätter vi ihop allt får du det kompletta, självständiga programmet som du kan kopiera‑klistra in i ett nytt konsolprojekt.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Förväntad output**

När programmet körs skapas en `Barcodes`‑undermapp som innehåller:

- `DatabarAspectRatio15.png` – högre, klassisk look.
- `DatabarAspectRatio30.png` – plattare, bättre för breda etiketter.

Båda bilderna renderar samma GTIN‑data; endast de visuella proportionerna skiljer sig.

---

## Utöka exemplet (kantfall & variationer)

### 1. Olika bildformat

Aspose stöder BMP, JPEG, TIFF och SVG utöver PNG. Byt bara enum‑värdet:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG är vektorbaserat, vilket betyder att du kan skala det utan att förlora skärpa – praktiskt för responsiva webbappar.

### 2. Anpassa färger

Du kan behöva en vit streckkod på mörk bakgrund. Ställ in `ForeColor` och `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Hantera ogiltiga bildförhållanden

Aspose validerar intervallet (vanligtvis 5‑50). Om du anger ett värde utanför intervallet kastas ett `ArgumentException`. Omge spara‑anropet med ett try‑catch för att ge ett vänligt meddelande:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Batch‑generering

När du har en lista med GTIN‑nummer, loopa över dem, uppdatera `CodeText` och spara varje fil med ett unikt namn. Generator‑objektet kan återanvändas, vilket håller minnesanvändningen låg.

---

## Vanliga fallgropar & pro‑tips

- **Glöm aldrig att sätta `XDimension`** innan du sparar; standardvärdet (0,33 mm) kan ge suddiga bilder på lågupplösta skärmar.
- **Bildförhållandet är höjd‑till‑bredd**, inte tvärtom. Ett större tal gör streckkoden *kortare* vertikalt.
- **Sökvägar:** Använd `Path.Combine` för att undvika plattforms‑specifika separatorer – särskilt om koden körs i Linux‑containrar.
- **Licensiering:** Aspose.BarCode är kommersiell. I provläge visas ett vattenstämpel på bilden. Registrera en licens tidigt för att undvika överraskningar i produktion.

---

## Slutsats

Du vet nu hur du **skapar en omnidirektionell streckkodbild** med Aspose, justerar bildförhållandet och exporterar PNG‑filer – allt på under 30 rader C#. Denna handledning visade steg‑för‑steg‑processen, förklarade varför varje inställning är viktig och tog upp utökningar som olika format, färger och batch‑bearbetning.

Redo för nästa utmaning? Prova att generera QR‑koder, bädda in streckkoden i en PDF, eller integrera utskriften i ett ASP.NET Core‑API. Samma **generate barcode with Aspose**‑principer gäller för alla streckkodstyper, så du kan återanvända det du lärt dig idag.

Har du frågor eller vill dela dina egna justeringar? Lämna en kommentar nedan – lycka till med kodningen!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationssätt i dina egna projekt.

- [Hur man genererar Aztec‑streckkod med anpassat bildförhållande med Aspose.BarCode för .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Hur man skapar streckkod Aspose Java – justera bildkvalitet](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Hur man genererar streckkodsbilder i Java med Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}