---
category: general
date: 2026-11-17
description: Skapa streckkodbild i C# med Barcode Generator‑biblioteket. Följ den
  här guiden för att lära dig hur du genererar DataBar staplade omnidirektionella
  koder steg för steg.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: sv
lastmod: 2026-11-17
og_description: Skapa streckkodbild i C# med ett kortfattat exempel. Lär dig hur du
  genererar DataBar staplade omnidirektionella streckkoder med Barcode Generator‑biblioteket.
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: Skapa streckkodbild i C# – komplett guide för DataBar‑koder
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man skapar en streckkodbild i C# med DataBar staplad omnidirektionell
url: /sv/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du en streckkodbild i C# med DataBar staplad omnidirektionell

Om du behöver **create barcode image** i en .NET‑applikation visar den här handledningen en komplett, färdig‑att‑köra lösning. Du kommer att se exakt hur du använder **Barcode Generator C#** API för att producera en staplad omnidirektionell DataBar, vilket är formatet som täcks av *how to generate databar*-frågan.

Guiden går igenom varje nödvändigt steg – från installation av biblioteket till finjustering av bildförhållandet – så att du kan kopiera koden, köra den och omedelbart få en PNG‑fil. Ingen extern dokumentationsuppslagning behövs.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6.0 SDK eller senare installerat (exemplet fungerar även med .NET Framework 4.7+)
* En utvecklingsmiljö som Visual Studio 2022 eller VS Code
* **Aspose.BarCode for .NET** NuGet‑paketet (biblioteket som tillhandahåller `BarcodeGenerator`)

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Använd flaggan `--version` för att låsa paketet till den senaste stabila versionen, t.ex. `dotnet add package Aspose.BarCode --version 23.9`.

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt och referera de nödvändiga namnrymderna. Detta steg förbereder miljön för **barcode generator c#**‑koden som följer.

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
            // All barcode generation logic lives here
```

`Aspose.BarCode.Generation`‑namnrymden innehåller klassen `BarcodeGenerator`, som är kärnan i **create barcode image**‑arbetsflödet.

## Steg 2: Initiera BarcodeGenerator för en staplad omnidirektionell DataBar

Generatorn behöver två uppgifter: streckkodstypen och data att koda. `EncodeTypes.DatabarStackedOmniDirectional`‑enum‑värdet väljer exakt den DataBar‑variant som krävs i *how to generate databar*-scenarier.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*Varför detta är viktigt:* Att välja rätt `EncodeTypes`‑värde säkerställer att den resulterande bilden uppfyller branschspecifikationerna för detaljhandelsavläsning.

## Steg 3: Definiera modulstorlek (X‑dimension) i pixlar

En streckkods visuella densitet styrs av X‑dimensionen. Att sätta ett rimligt pixelvärde garanterar att bilden är läsbar både på skärm och i utskrift.

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Om du behöver en större streckkod för lågupplöst utskrift, öka pixelvärdet därefter.

## Steg 4: Justera DataBar‑bildförhållandet för att göra raderna högre

Den staplade omnidirektionella DataBar‑en består av två rader. Genom att ändra `AspectRatio` kan du kontrollera höjden på varje rad, vilket kan vara användbart när standardstorleken känns trång.

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

Ett bildförhållande på `15` är ett vanligt val för detaljhandelsetiketter; du kan experimentera med värden mellan `10` och `20` för att möta specifika layoutkrav.

## Steg 5: Spara den genererade streckkoden som en PNG‑bild

Skriv slutligen bilden till disk. PNG är förlustfri, vilket gör den idealisk för senare bearbetning eller inbäddning i PDF‑filer.

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

När programmet körs skapas en fil med namnet **DatabarAspectRatio15.png** i projektets utdata‑katalog. Att öppna filen visar en ren, högkontrast‑streckkod redo för avläsning.

### Förväntat resultat

Den sparade bilden ser ut som illustrationen nedan (den faktiska visualiseringen har utelämnats för korthet).

*Alt text för exempelbilden:* **create barcode image** – en PNG‑fil som visar en staplad omnidirektionell DataBar med bildförhållandet 15.

## Vanliga variationer och kantfall

| Situation | Justering |
|-----------|-----------|
| **Olika nyttolastlängd** | Ersätt GTIN‑strängen med valfritt giltigt DataBar‑innehåll (t.ex. `(01)01234567890123`). |
| **Högre upplösning för stora utskrifter** | Öka `XDimension.Pixels` till 4 eller 5 och eventuellt sätt `Resolution` i `Parameters.Image`. |
| **Andra DataBar‑format** | Använd `EncodeTypes.DatabarStacked` för en två‑radig staplad variant utan omnidirektionell funktion. |
| **Spara som JPEG** | Ändra `BarCodeImageFormat.Png` till `BarCodeImageFormat.Jpeg` och eventuellt sätt `Quality`. |

Dessa variationer svarar på den bredare *how to generate databar*-frågan genom att visa att samma generator kan omkonfigureras för flera DataBar‑familjer.

## Fullständig källkodssammanfattning

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
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

Kopiera koden till `Program.cs`, återställ NuGet‑paketen och kör `dotnet run`. Konsolen bekräftar bildens plats, och du kan öppna PNG‑filen för att verifiera **create barcode image**‑resultatet.

## Slutsats

Du vet nu hur du **create barcode image** i C# med Barcode Generator‑biblioteket och hur du **generate DataBar**‑koder med exakt kontroll över storlek och bildförhållande. Det kompletta exemplet demonstrerar alla nödvändiga inställningar – från initiering av `BarcodeGenerator` till export av en PNG‑fil – så att du kan integrera streckkodsskapande i vilken .NET‑applikation som helst utan ytterligare forskning.

### Vad blir nästa steg?

* Utforska andra streckkodssymbologier med `EncodeTypes` (t.ex. QR, Code128) – ett naturligt nästa steg i **barcode generator c#**‑arbetsflödet.  
* Kombinera den genererade bilden med PDF‑ eller Excel‑rapporter med Aspose.PDF eller Aspose.Cells.  
* Justera färg, lägg till marginaler eller bädda in streckkoden i ett web‑API för on‑demand‑generering.

Känn dig fri att experimentera med parametrarna, och låt koden fungera som en pålitlig grund för alla dina framtida streckkod‑relaterade projekt. Lycka till med kodandet!

## Vad bör du lära dig härnäst?

De följande handledningarna täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstreras i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}