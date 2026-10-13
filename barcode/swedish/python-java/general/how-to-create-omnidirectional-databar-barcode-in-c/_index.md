---
category: general
date: 2026-09-29
description: Lär dig hur du skapar en omnidirektionell Databar‑streckkod i C# med
  Aspose.BarCode. Justera X‑dimension, ställ in bildförhållandet och spara PNG‑bilder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: sv
lastmod: 2026-09-29
og_description: Skapa omnidirektionell Databar‑streckkod i C# med Aspose.BarCode.
  Lär dig att ställa in X‑dimension, justera bildförhållandet och exportera PNG‑filer.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Skapa omnidirektionell Databar-streckkod i C# – steg‑för‑steg‑guide
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Hur man skapar en omnidirektionell Databar‑streckkod i C#
url: /sv/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du en omnidirektionell Databar streckkod i C#

Om du behöver **skapa en omnidirektionell Databar streckkod** i en .NET-applikation, visar den här guiden de exakta stegen. Du kommer att se hur du initierar en DataBar stacked omnirectional streckkod, konfigurerar dess X‑dimension, ändrar bildförhållandet och genererar PNG‑bilder med Aspose.BarCode.

Att generera en **DataBar stacked omnirectional streckkod** är vanligt när du måste koda produktidentifierare för detaljhandels‑scannrar. I den här handledningen lär du dig att **ange streckkodens bildförhållande**, kontrollera modulstorlek och exportera resultatet utan att lämna IDE:n.

## Förutsättningar

- .NET 6.0 eller senare installerat
- Visual Studio 2022 (eller någon C#‑kompatibel IDE)
- **Aspose.BarCode for .NET** NuGet‑paketet (version 23.12 eller nyare)

Du kan lägga till paketet via NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Initiera den omnidirektionella Databar streckkoden

Det första steget är att skapa en `BarcodeGenerator`‑instans som riktar sig mot **DataBar stacked omnirectional**‑symbologin. Konstruktorn tar emot kodningstypen och datasträngen.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Varför detta är viktigt:** Värdet `EncodeTypes.DatabarStackedOmniDirectional` talar om för Aspose.BarCode att rendera det specifika omnidirektionella Databar‑formatet, vilket krävs för skanning i båda riktningarna.

## Steg 2: Definiera X‑dimensionen (modulstorlek)

X‑dimensionen styr bredden på en enskild streckkodmodul i pixlar. Ett värde på `2` pixlar fungerar bra för rendering på skärm och de flesta skrivare.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Varför detta är viktigt:** En konsekvent X‑dimension säkerställer att streckkoden uppfyller minimistorleks‑specifikationerna för detaljhandels‑scannrar samtidigt som bildfilens storlek hålls hanterbar.

## Steg 3: Ange det första bildförhållandet och spara bilden

**Bildförhållandet** bestämmer förhållandet mellan höjd och bredd för DataBar. Ett bildförhållande på `15` ger en kompakt, hög streckkod som är idealisk för smala etikettutrymmen.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Varför detta är viktigt:** Genom att justera bildförhållandet kan du passa streckkoden i olika etikettlayouter utan att offra läsbarhet. Den sparade PNG‑filen kan granskas i vilken bildvisare som helst.

## Steg 4: Ändra bildförhållandet och generera en andra bild

Ibland behövs en bredare streckkod — till exempel när etiketten har mer horisontellt utrymme. Att ändra förhållandet till `30` skapar ett plattare utseende.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Varför detta är viktigt:** Genom att exponera egenskapen **set barcode aspect ratio** kan du skapa flera streckkodvariationer från en enda kodbas, vilket förenklar automatiserade pipelines för etikettgenerering.

## Förväntat resultat

När programmet körs produceras två PNG‑filer i applikationens output‑mapp:

| Filnamn                | Aspect Ratio | Visuell beskrivning |
|--------------------------|--------------|--------------------|
| `DatabarAspectRatio15.png` | 15           | Hög, smal streckkod lämplig för smala etiketter |
| `DatabarAspectRatio30.png` | 30           | Bredare streckkod som fyller mer horisontellt utrymme |

Du kan bädda in dessa bilder i rapporter, skriva ut dem på produktförpackningar eller skicka dem till en webbtjänst för vidare bearbetning.

![Skapa omnidirektionell Databar streckkod exempel](databar-example.png "Skapa omnidirektionell Databar streckkod exempel")

*Skärmbilden visar de två genererade PNG‑filerna sida‑vid‑sida.*

## Vanliga frågor och edge‑cases

### Vad händer om jag behöver en annan X‑dimension?

Du kan tilldela vilket heltal som helst till `XDimension.Pixels`. Värden under `1` ignoreras, och värden över `10` kan skapa för stora moduler som överskrider skrivarmarginaler. Testa den visuella utskriften efter varje ändring.

### Hur kodar jag annan AI‑genererad data (t.ex. UPC, EAN)?

Byt ut datasträngen i `BarcodeGenerator`‑konstruktorn mot rätt Application Identifier (AI). För en UPC‑A‑kod, använd `"012345678905"` utan AI‑prefix.

### Kan jag exportera till andra format än PNG?

Ja. `Save`‑metoden accepterar `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` och `BarCodeImageFormat.Bmp`. Välj det format som matchar ditt efterföljande arbetsflöde.

## Pro‑tips: återanvänd generatorn för batch‑bearbetning

Om du behöver generera dussintals streckkoder med varierande bildförhållanden, håll `BarcodeGenerator`‑instansen levande och ändra bara `DataBar.AspectRatio` före varje `Save`. Detta undviker overheaden av att återinstansiera generatorn för varje bild.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Slutsats

Du vet nu hur du **skapar en omnidirektionell Databar streckkod** i C# med Aspose.BarCode. Genom att initiera en `BarcodeGenerator`, ange X‑dimensionen, justera **set barcode aspect ratio** och spara PNG‑filer kan du producera streckkodsbilder som uppfyller olika etikettkrav.  

Nästa steg är att utforska relaterade ämnen såsom **generate barcode image** för QR‑koder, **DataBar stacked omnidirectional barcode**‑validering, eller att integrera de genererade PNG‑filerna i PDF‑fakturor med Aspose.PDF. Experimentera med olika bildförhållanden och modulstorlekar för att hitta den optimala konfigurationen för din specifika utskrifts‑hardware.

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man använder en streckkodsgenerator C# för att skapa DataBar Omni‑directional streckkoder](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional streckkod i C# – Komplett guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Hur man genererar streckkod i C# – skapa streckkodsbild c# med DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}