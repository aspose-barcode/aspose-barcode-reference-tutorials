---
category: general
date: 2026-10-21
description: Skapa databar staplad streckkod snabbt med C#. Lär dig att ställa in
  X‑dimension, justera bildförhållandet och spara PNG‑bilder i den här kompletta handledningen.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode generator C#
- set aspect ratio
- save barcode image
language: sv
lastmod: 2026-10-21
og_description: Skapa staplad databar-kod i C# med Aspose.BarCode. Följ den här guiden
  för att konfigurera X‑dimension, ändra bildförhållande och exportera PNG‑filer.
og_image_alt: C# generated DataBar stacked barcode saved as PNG with aspect ratio
  15
og_title: Skapa staplad Databar-streckkod i C# – komplett programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: create databar stacked barcode quickly using C#. Learn to set X‑dimension,
    adjust aspect ratio, and save PNG images in this complete tutorial.
  headline: How to create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- DataBar
title: Hur man skapar staplad databar‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så skapar du databar staplad streckkod i C# – steg‑för‑steg‑guide

Om du behöver **create databar stacked barcode** i en .NET‑applikation visar den här guiden exakt hur du gör. Du kommer att se hur du konfigurerar X‑dimensionen, ändrar bildförhållandet och sparar streckkoden som PNG‑filer.

Att generera en DataBar staplad streckkod kräver ingen komplex byggpipeline. Denna handledning täcker allt du behöver: nödvändiga paket, kod‑för‑kod‑förklaring och tips för vanliga fallgropar. I slutet kan du producera flera streckkodsbilder med olika bildförhållanden i en enda metod.

## Vad du behöver

* .NET 6.0 SDK eller senare installerat  
* Visual Studio 2022 (eller någon IDE som stödjer C#)  
* **Aspose.BarCode for .NET** NuGet‑paket – biblioteket som tillhandahåller `BarcodeGenerator` och `EncodeTypes`  

Du kan lägga till paketet med följande kommando:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Ställ in projektet och importera namnrymder

Skapa ett nytt konsolprojekt eller lägg till koden i ett befintligt. Importera de nödvändiga namnrymderna så att kompilatorn känner igen streckkodsklasserna.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa `using`‑satser exponerar `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat` som används senare i exemplet.

## Steg 2: Definiera utdatamappen

Välj en mapp där de genererade PNG‑filerna ska skrivas. Att använda en absolut eller relativ sökväg fungerar på samma sätt; exemplet använder en relativ mapp som heter `Barcodes`.

```csharp
// Step 1: Define the output folder
string path = "Barcodes/";

// Ensure the folder exists
if (!System.IO.Directory.Exists(path))
{
    System.IO.Directory.CreateDirectory(path);
}
```

Att skapa mappen programatiskt förhindrar körningstidfel när katalogen saknas.

## Steg 3: Initiera **create databar stacked barcode**‑generatorn

Skapa en `BarcodeGenerator`‑instans med `EncodeTypes.DatabarStackedOmniDirectional`. Exempeldata `(01)12345678901231` följer GS1‑128‑formatet som krävs av DataBar.

```csharp
// Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

Generator‑objektet innehåller alla parametrar som påverkar streckkodens visuella utseende.

## Steg 4: Ställ in X‑dimensionen (pixelbredden på den minsta stapeln)

X‑dimensionen styr den övergripande storleken på streckkoden utan att ändra den kodade datan. Ett värde på `2` pixlar ger en tydlig, läsbar bild för de flesta skärmupplösningar.

```csharp
// Step 3: Set the X-dimension (pixel width of the smallest bar)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Justera detta värde om du behöver en större eller mindre streckkod; behåll förhållandet mellan bredd och höjd konsekvent.

## Steg 5: Konfigurera bildförhållandet och spara den första bilden

Bildförhållandet bestämmer förhållandet mellan höjd och bredd för en DataBar staplad streckkod. Ett bildförhållande på `15` är en vanlig standard som ger en kompakt visuell bild.

```csharp
// Step 4: Configure an aspect ratio of 15 and save the barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

`Save`‑metoden skriver en PNG‑fil till den tidigare definierade mappen. Filnamnet visar tydligt vilket bildförhållande som använts.

### Förväntad output för bildförhållande 15

Den genererade `DatabarAspectRatio15.png` ser liknande ut som illustrationen nedan.

![Barcode image generated with aspect ratio 15](https://example.com/images/databar-aspect15.png "Barcode image generated with aspect ratio 15")

*Alt‑text:* `create databar stacked barcode image saved with aspect ratio 15`

## Steg 6: Ändra bildförhållandet och spara en andra bild

Du kan återanvända samma `BarcodeGenerator`‑instans för att skapa variationer. Att ändra `AspectRatio` till `30` fördubblar höjden på varje stapel, vilket kan krävas för högupplöst utskrift.

```csharp
// Step 5: Change the aspect ratio to 30 and save the new barcode image
generator.Parameters.Barcode.DataBar.AspectRatio = 30;
generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

### Förväntad output för bildförhållande 30

`DatabarAspectRatio30.png`‑bilden är högre, behåller samma bredd samtidigt som läsbarheten för avlägsna skannrar ökas.

![Barcode image generated with aspect ratio 30](https://example.com/images/databar-aspect30.png "Barcode image generated with aspect ratio 30")

*Alt‑text:* `create databar stacked barcode image saved with aspect ratio 30`

## Fullständig källkod

Att sätta ihop alla steg ger ett fristående program som du kan köra omedelbart.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the output folder
            string path = "Barcodes/";
            if (!System.IO.Directory.Exists(path))
                System.IO.Directory.CreateDirectory(path);

            // Initialize the generator with DataBar Stacked Omnidirectional encoding
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");

            // Set X‑dimension (pixel width of the smallest bar)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: aspect ratio 15
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            generator.Save($"{path}DatabarAspectRatio15.png", BarCodeImageFormat.Png);

            // Second image: aspect ratio 30
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            generator.Save($"{path}DatabarAspectRatio30.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images created successfully.");
        }
    }
}
```

Kompilera och kör programmet. Efter körning innehåller `Barcodes`‑katalogen två PNG‑filer, var och en representerar en **create databar stacked barcode** med ett annat bildförhållande.

## Pro‑tips och vanliga fallgropar

* **Pro tip:** Håll X‑dimensionen mellan 1 px och 4 px för de flesta skärm‑baserade användningsfall. Större värden ökar filstorleken utan att förbättra skanningspålitligheten.  
* **Pitfall:** Att ändra `EncodeTypes`‑värdet efter att generatorn har skapats uppdaterar inte den interna kodningen. Ange alltid rätt `EncodeTypes` i konstruktorn.  
* **Pro tip:** När du behöver fler än två bildförhållanden, loopa över en array av heltalsvärden och anropa `Save` inuti loopen. Detta minskar kodduplicering.  
* **Pitfall:** Att spara till en sökväg utan skrivbehörighet kastar ett `UnauthorizedAccessException`. Säkerställ att applikationen körs med lämpliga filsystemsrättigheter.

## Slutsats

Du vet nu hur du **create databar stacked barcode** i C# med Aspose.BarCode. Guiden täckte hur du ställer in miljön, konfigurerar X‑dimensionen, justerar bildförhållandet och sparar PNG‑filer. Med detta grundlag kan du generera ytterligare variationer, integrera streckkodsskapande i webb‑API:er eller bädda in bilderna i PDF‑rapporter.

Nästa steg är att utforska relaterade ämnen som **DataBar Stacked Omnidirectional**‑skanningsbästa praxis, inbäddning av streckkoder i **ASP.NET Core**‑svar eller generering av **QR‑koder** med samma bibliotek. Experimentera med olika `EncodeTypes` och bildformat för att passa din applikations behov.

Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man skapar databar PNG‑bilder med C# och Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Hur man ställer in kolumner för en Databar Expanded Stacked‑streckkod – komplett C#‑guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar staplad omnidirektionell streckkod i C# – komplett guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}