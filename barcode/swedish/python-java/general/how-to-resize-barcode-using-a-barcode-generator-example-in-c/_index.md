---
category: general
date: 2026-10-08
description: Lär dig hur du ändrar storlek på streckkodsbilder med ett C#‑streckkodsgeneratorexempel,
  justerar stapelhöjden från 30 px till 60 px på bara några rader kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: sv
lastmod: 2026-10-08
og_description: Hur du snabbt ändrar storlek på en streckkod med ett C#‑streckkodsgeneratorexempel.
  Justera balkhöjd, spara PNG‑filer och undvik vanliga fallgropar.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Hur man ändrar storlek på streckkod i C# – steg‑för‑steg generatorexempel
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Hur man ändrar storlek på streckkod med ett streckkodsgeneratorexempel i C#
url: /sv/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så ändrar du storlek på streckkod med ett streckkodsgeneratorexempel i C#

Om du behöver **hur man ändrar storlek på streckkod**‑bilder i ett .NET‑projekt, visar den här guiden den kompletta lösningen. Du får se ett koncist **barcode generator example C#** som ändrar stapelhöjden från 30 px till 60 px och sparar varje version som en PNG‑fil.

Att ändra storlek på en streckkod är ofta nödvändigt när samma data måste visas på kvitton, etiketter eller produktsidor i olika visuella skalor. Istället för att redigera rasterbilden i ett externt verktyg kan du justera streckkodens dimensioner programmässigt, vilket bevarar dataintegriteten.

I den här handledningen kommer du att:

* Ställa in en DataBar Omni‑Directional streckkodsgenerator.
* Ändra X‑dimensionen och stapelhöjdsparametrarna.
* Spara två bilder med olika höjder.
* Förstå varför förändring av stapelhöjden fungerar och vilka kantfall du bör vara uppmärksam på.

> **Prerequisite** – Du har en .NET‑utvecklingsmiljö (Visual Studio 2022 eller senare) och streckkodsbiblioteket som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`. Koden fungerar med den senaste versionen av biblioteket från och med oktober 2026.

## Förutsättningar för streckkodsgeneratorexempel C#

Innan du börjar, se till att du har:

| Objekt | Orsak |
|------|--------|
| .NET 6.0 SDK eller nyare | Tillhandahåller runtime och språkfunktioner som används i exemplet. |
| Streckkodsbibliotek (t.ex. Aspose.BarCode, Dynamsoft eller något bibliotek som exponerar `BarcodeGenerator`) | Tillhandahåller `EncodeTypes.DatabarOmniDirectional`‑enum och metoder för bildexport. |
| En mapp du kan skriva till (t.ex. `C:\Temp\Barcodes\`) | Exemplet sparar PNG‑filer till den här platsen. |
| Grundläggande C#‑kunskaper | Handledningen förutsätter kunskap om klasser, egenskaper och stränginterpolering. |

Installera biblioteket via NuGet om du inte redan gjort det:

```bash
dotnet add package Aspose.BarCode
```

Byt ut paketnamnet mot det du faktiskt använder; API‑ytan som visas nedan är gemensam för de flesta streckkod‑SDK:er.

## Så ändrar du storlek på streckkod – steg 1: skapa generatorn

Det första steget är att instansiera en `BarcodeGenerator` med önskad symbologi och data. I detta exempel genererar vi en **DataBar Omni‑Directional**‑streckkod som kodar ett GTIN‑14‑värde.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Varför detta är viktigt:** `EncodeTypes.DatabarOmniDirectional`‑enumet talar om för biblioteket vilken streckkodstandard som ska användas. Data‑strängen följer GS1 Application Identifier `(01)` för ett 14‑siffrigt GTIN, vilket säkerställer att streckkoden följer globala handelsstandarder.

## Så ändrar du storlek på streckkod – steg 2: definiera modulbredd och initial stapelhöjd

Den visuella storleken på en streckkod beror på två parametrar:

* **X‑dimension** – bredden på den minsta stapeln (modulen). Mäts i pixlar eller millimeter.
* **Bar height** – den vertikala längden på staplarna.

Att sätta dessa värden innan du sparar garanterar att den renderade bilden matchar de dimensioner du behöver.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Förklaring:** En X‑dimension på 2 px ger en kompakt streckkod som fortfarande skannas pålitligt. 30 px‑höjden är ett vanligt standardvärde för små etiketter. Du kan justera X‑dimensionen oberoende av höjden om du behöver ett tätare eller mer utspritt mönster.

## Så ändrar du storlek på streckkod – steg 3: spara den första bilden (30 px höjd)

Exportera nu streckkoden till en PNG‑fil. `Save`‑metoden tar emot en filsökväg och en bildformat‑enum.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Resultat:** `DatabarBarHeight30Pixels.png` innehåller en 30 px hög streckkod. Du kan öppna filen i valfri bildvisare för att verifiera dimensionerna.

## Så ändrar du storlek på streckkod – steg 4: ändra stapelhöjden till 60 px

För att skapa en större version, ändra helt enkelt `BarHeight`‑egenskapen. Generatorn återanvänder samma data och X‑dimension, så streckkodens mönster förblir identiskt – bara den visuella storleken ändras.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Varför detta fungerar:** Renderingsmotorn beräknar varje stapels geometri vid behov. När du uppdaterar höjd‑egenskapen innan nästa `Save`‑anrop sker en ny rasterisering med de nya dimensionerna.

## Så ändrar du storlek på streckkod – steg 5: spara den andra bilden (60 px höjd)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Du har nu två PNG‑filer, en liten (30 px) och en större (60 px), redo att användas på olika etikettstorlekar.

## Fullständig källkod för streckkodsgeneratorexempel C#

Nedan finns hela, körbara programmet. Kopiera det till ett nytt konsolprojekt för att testa omedelbart.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Förväntad utskrift i konsolen:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Efter körning, öppna de två PNG‑filerna för att se den visuella skillnaden. Båda streckkoderna kodar samma GTIN‑14‑värde och kommer att skannas identiskt, oavsett höjd.

## Varför justering av stapelhöjd är säkert för skanning

Streckkodsläsare läser mönstret av ljusa och mörka moduler, inte det absoluta pixelantalet. Så länge **X‑dimensionen** ligger inom läsarens tolerans (vanligtvis 0,5 mm till 2 mm i fysiska enheter) påverkar inte förändring av höjden läsbarheten. Biblioteket skalar automatiskt modulerna och bevarar de nödvändiga tysta zonerna och justeringsmönstren.

## Vanliga fallgropar och hur du undviker dem

| Fallgropar | Så fixar du det |
|------------|-----------------|
| **Målmappen finns inte** | Anropa `Directory.CreateDirectory(outputPath)` innan du sparar. |
| **Fel X‑dimension som ger suddiga skanningar** | Håll `XDimension.Pixels` mellan 1 px och 4 px för de flesta skrivare; testa med en fysisk scanner. |
| **Användning av rasterformat för mycket stora streckkoder** | Byt till `BarCodeImageFormat.Svg` för oändlig skalbarhet utan pixling. |
| **Glömmer att återställa `BarHeight` innan andra sparandet** | Se till att du tilldelar den nya höjden **innan** du anropar `Save` igen. |

## Proffstips: generera flera storlekar i en loop

Om du behöver ett spann av höjder (t.ex. 30 px, 45 px, 60 px) minskar en enkel `foreach`‑loop dupliceringen:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Detta mönster skalar bra för batch‑bearbetning av produktkataloger.

## Kantfall: olika bildformat och DPI‑inställningar

* **SVG‑utdata** – Använd `BarCodeImageFormat.Svg` för att producera en vektorfil som kan skalas utan kvalitetsförlust.
* **High‑DPI PNG** – Sätt `generator.Parameters.Image.DpiX` och `DpiY` till 300 eller 600 för utskriftsklara bilder; stapelhöjden mäts fortfarande i pixlar, så öka den proportionellt.
* **Icke‑standard symbologier** – Vissa streckkodstyper (t.ex. QR‑kod) har en separat `Size`‑egenskap istället för `BarHeight`. Konsultera bibliotekets dokumentation för dessa fall.

## Testa den ändrade streckkoden

1. Öppna varje PNG i en bildvisare och verifiera pixeldimensionerna (t.ex. 150 × 30 px vs. 150 × 60 px).  
2. Skriv ut bilderna i 100 % skala.  
3. Skanna med en handhållen streckkodsläsare eller en mobilapp. Den avkodade datan bör vara

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [How to save barcode images with Barcode Generator C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}