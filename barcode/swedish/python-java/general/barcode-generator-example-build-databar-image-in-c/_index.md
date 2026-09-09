---
category: general
date: 2026-07-18
description: Exempel på streckkodsgenerator som visar hur man ställer in dimensioner
  och genererar en DataBar Stacked Omni‑Directional‑streckkodsbild i C#. Lär dig snabbt
  streckkodskodningstyper.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set dimensions
- how to generate databar
- barcode encode types
- create barcode image c#
language: sv
lastmod: 2026-07-18
og_description: Barcode‑generatorexemplet guidar dig genom hur du ställer in dimensioner,
  väljer kodningstyper för streckkoder och skapar streckkodsbilder i C#‑projekt med
  minimal kod.
og_image_alt: Barcode generator example output showing DataBar barcode with aspect
  ratio 15
og_title: Exempel på streckkodsgenerator – Snabb skapande av DataBar-bild i C#
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Barcode generator example showing how to set dimensions and generate
    a DataBar Stacked Omni‑Directional barcode image in C#. Learn barcode encode types
    quickly.
  headline: Barcode Generator Example – Build DataBar Image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
- image generation
title: Exempel på streckkodsgenerator – Skapa DataBar-bild i C#
url: /sv/python-java/general/barcode-generator-example-build-databar-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode Generator‑exempel – Skapa DataBar‑bild i C#

Har du någonsin behövt ett **barcode generator example** som faktiskt skriver ut en riktig streckkod utan att dra i håret? Du är inte ensam. De flesta utvecklare stöter på problem när de försöker lista ut **hur man ställer in dimensioner** för en DataBar Stacked Omni‑Directional streckkod, särskilt när dokumentationen är begravd under lager av jargong.

I den här handledningen går vi igenom ett komplett, färdigt‑att‑köra C#‑program som visar **how to generate databar** bilder, väljer rätt **barcode encode types**, och slutligen **create barcode image c#** filer som du kan släppa in i vilket projekt som helst. Inga onödigheter—bara koden du kan kopiera‑klistra, plus resonemanget bakom varje rad.

## Vad du behöver

- **.NET 6** (eller någon nyare .NET‑version) – API‑et vi använder riktar sig mot .NET Standard, så det fungerar även på .NET Framework.  
- **Aspose.BarCode for .NET** – biblioteket som tillhandahåller `BarcodeGenerator`. Du kan hämta det från NuGet med `Install-Package Aspose.BarCode`.  
- En **C# IDE** – Visual Studio, Rider eller VS Code räcker.  
- En mapp på disken där PNG‑filerna sparas (koden skapar `DatabarAspectRatio15.png` och `DatabarAspectRatio30.png`).  

Har du allt? Bra—låt oss dyka ner.

## Barcode Generator‑exempel – Initiera generatorn

Först och främst: vi behöver en instans av `BarcodeGenerator` konfigurerad för **DataBar Stacked Omni‑Directional**‑symbologi. Detta är den **barcode encode type** vi kommer att arbeta med.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Stacked Omni‑Directional barcode generator
        // with the desired GTIN content.
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

> **Varför detta är viktigt:** `EncodeTypes.DatabarStackedOmniDirectional` talar om för Aspose exakt vilken symbologi som ska renderas. Om du väljer fel typ kommer skannern inte att känna igen streckkoden, oavsett hur snygg bilden ser ut.

## Hur man ställer in dimensioner för streckkoden

En streckkods läsbarhet beror på dess **X‑dimension** (bredden på den smalaste stapeln). I de flesta fall fungerar ett värde på 2 pixlar bra, men du kan justera det för att passa din skrivare eller skärm.

```csharp
        // Step 2: Set a common X‑dimension (pixel width of the narrowest bar)
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proffstips:** Om du någonsin undrar **hur man ställer in dimensioner** för en annan streckkodsfamilj, gäller samma egenskapskedja (`Parameters.Barcode.XDimension`)—byt bara `Pixels`‑värdet.

## Hur man genererar DataBar Stacked Omni‑Directional streckkod

Nu när generatorn är klar kommer vi att leka med egenskapen **aspect ratio**. Den styr förhållandet mellan höjd och bredd för DataBar, så att du kan skapa en kort, kvadratisk symbol eller en hög, smal.

```csharp
        // Step 3: Generate and save a barcode with aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Vad händer?** `AspectRatio = 15` instruerar motorn att göra staplarna 15  gånger högre än de är breda. Den resulterande PNG‑filen sparas precis bredvid ditt körbara program.

## Skapa streckkodsbilder i C# – Ändra aspect ratio

Låt oss bevisa flexibiliteten genom att byta ratio till 30 och spara en andra fil.

```csharp
        // Step 4: Change the aspect ratio to 30 and save another barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been saved successfully.");
    }
}
```

När du kör programmet får du två PNG‑filer:

| Fil | Aspect Ratio | Ungef. storlek |
|------|--------------|----------------|
| `DatabarAspectRatio15.png` | 15 | 120 × 180 px |
| `DatabarAspectRatio30.png` | 30 | 120 × 360 px |

Öppna dem i någon bildvisare—du bör se rena, skannbara DataBar‑symboler.

## Översikt över barcode encode types (Valfritt men praktiskt)

Om du är nyfiken på andra **barcode encode types** som stöds av Aspose, här är ett snabbt fusklapp:

| EncodeTypes Enum | Beskrivning |
|------------------|-------------|
| `EncodeTypes.Code128` | High‑density alphanumeric |
| `EncodeTypes.QR` | 2‑D matrix code |
| `EncodeTypes.DatabarExpanded` | GS1 DataBar for retail |
| `EncodeTypes.DatabarStackedOmniDirectional` | **Our focus** – compact, omnidirectional |

Att känna till rätt enum sparar dig från mycket trial‑and‑error när du byter projekt.

## Vanliga fallgropar & hur man undviker dem

- **Missing NuGet package** – Koden kommer inte att kompilera utan `Aspose.BarCode`. Kör `dotnet add package Aspose.BarCode` först.  
- **Wrong file path** – Om du använder en absolut sökväg, dubbelkolla bakstrecken (`\\`) på Windows. Relativa sökvägar (som visas) håller det portabelt.  
- **Aspect ratio too extreme** – Ratio över 50 kan göra streckkoden för hög för vanliga skannrar. Håll dig till 15‑30 för de flesta användningsfall.

## Fullständig källkod (Klar att kopiera‑klistra)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator with DataBar Stacked Omni‑Directional type
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GTIN‑14 sample

        // 2️⃣ Set X‑dimension (how to set dimensions) – 2 pixels is a safe default
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First barcode: aspect ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);

        // 4️⃣ Second barcode: aspect ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("✅ Two barcode images saved – check your project folder.");
    }
}
```

Kör programmet (`dotnet run` eller tryck **F5** i Visual Studio) så ser du konsolmeddelandet som bekräftar att filerna finns på disken.

![Barcode generator example output showing DataBar barcode with aspect ratio 15](placeholder/path/to/image.png){: .align-center alt="Barcode generator‑exempelutdata som visar DataBar‑streckkod med aspect ratio 15"}

## Sammanfattning

Vi har just avslutat ett **barcode generator example** som demonstrerar **how to set dimensions**, väljer rätt **barcode encode types**, och slutligen **create barcode image c#** filer som du kan bädda in var som helst. Koden är liten, koncepten är kristallklara, och du har nu en solid grund för att utöka lösningen—kanske lägga till textbeskrivningar, rotera bilden, eller byta till en annan symbologi.

### Vad blir nästa?

- Experimentera med **different X‑dimensions** för att se hur skannertolerans förändras.  
- Prova andra **EncodeTypes** som `Code128` eller `QR` för att bredda ditt verktygssats.  
- Automatisera batch‑generering: loopa över en CSV med produkt‑ID:n och skapa en PNG för varje.

Om du stöter på problem, lämna en kommentar nedan eller kolla Aspose.BarCode‑dokumentationen—den är full av exempel som kompletterar det vi gick igenom här.

Lycka till med kodningen, och må dina streckkoder alltid skannas på första försöket!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur man genererar streckkod – En-dimensionella streckkodstyper](/barcode/english/net/one-dimensional-barcode-types/)
- [Skapa streckkodsbilder i C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Hur man genererar DataMatrix‑streckkoder (ECC 200) med Aspose.BarCode för .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}