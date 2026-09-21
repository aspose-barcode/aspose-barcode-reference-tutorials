---
category: general
date: 2026-08-06
description: Skapa staplad databar-kod i C# snabbt. Lär dig att ställa in X-dimensionen,
  justera bildförhållandet och exportera PNG-filer med DataBar Stacked Omnidirectional‑generatorn.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: sv
lastmod: 2026-08-06
og_description: Skapa en staplad databar‑streckkod i C# med Aspose.BarCode. Denna
  handledning visar hur du konfigurerar X‑dimensionen, ändrar bildförhållandet och
  sparar PNG‑bilder.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Skapa staplad databar-streckkod i C# – komplett programmeringsguide
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Skapa staplad databar‑streckkod i C# – steg‑för‑steg‑guide
url: /sv/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa databar staplad streckkod i C# – steg‑för‑steg‑guide

Om du behöver **create databar stacked barcode** bilder i C#, visar den här guiden exakt hur du gör det med Aspose.BarCode‑biblioteket. Du kommer att lära dig att ställa in X‑dimensionen, ändra streckkodens bildförhållande och spara resultatet som PNG‑filer – allt i några korta steg.

Att generera en DataBar Stacked streckkod är vanligt när du måste koda GS1‑128‑data för detaljhandelsavläsning eller logistikkontroll. I avsnitten som följer täcker vi allt från projektuppsättning till verifiering av resultatet, så att du kan integrera lösningen i vilken .NET‑applikation som helst utan att missa någon detalj.

## Förutsättningar

Innan du börjar, se till att du har:

* **.NET 6.0** (eller senare) installerat – koden riktar sig mot den moderna SDK:n.
* En **licensierad** kopia av **Aspose.BarCode for .NET**. Den kostnadsfria utvärderingen fungerar för testning men lägger till ett vattenmärke.
* En IDE såsom **Visual Studio 2022** eller **VS Code** med C#‑tillägget.
* Grundläggande kunskap om **C#**‑syntax och konceptet GS1 Application Identifiers.

> **Proffstips:** Om du använder NuGet‑pakethanteraren löser kommandot `dotnet add package Aspose.BarCode` alla beroenden automatiskt.

## Steg 1: Skapa ett nytt konsolprojekt

Öppna en terminal eller Package Manager Console och kör:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

`dotnet new console`‑kommandot skapar en minimal **Program.cs**‑fil. Att lägga till **Aspose.BarCode**‑paketet gör `BarcodeGenerator`‑klassen tillgänglig.

## Steg 2: Initiera DataBar Stacked Omnidirectional‑generatorn

Öppna **Program.cs** och ersätt standardinnehållet med följande kod. Den första raden skapar en **BarcodeGenerator** konfigurerad för **DataBar Stacked Omnidirectional**‑symbologi och levererar en GS1‑128‑payload.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Varför detta är viktigt:** Enum‑värdet `EncodeTypes.DatabarStackedOmniDirectional` talar om för biblioteket att producera en **databar stacked barcode**, vilket är den staplade varianten av den omnidirektionella DataBar‑familjen. Denna symbologi kan innehålla upp till 14 numeriska tecken, vilket gör den idealisk för GTIN‑14‑koder.

## Steg 3: Ställ in X‑dimensionen (modulbredd)

X‑dimensionen styr bredden på den minsta stapeln (modulen). Ett värde som är för litet kan renderas dåligt på lågupplösta skrivare, medan ett för stort värde kan överskrida etikettutrymmet.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tips:** `Pixels`‑egenskapen är praktisk för skärm‑baserad testning. För utskrifts‑fokuserade scenarier, använd `generator.Parameters.Barcode.XDimension.Millimeters` istället.

## Steg 4: Justera bildförhållandet och spara den första bilden

**Bildförhållandet** påverkar förhållandet mellan höjd och bredd för den staplade streckkoden. DataBar Stacked Omnidirectional‑typen stödjer förhållanden från 10 till 30. Vi kommer att generera två bilder för att illustrera den visuella effekten.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Anropet till `generator.Save` skriver en **PNG**‑fil till den aktuella arbetskatalogen. Enum‑värdet `BarCodeImageFormat.Png` säkerställer förlustfri kompression, vilket är idealiskt för vidare bearbetning eller inbäddning i PDF‑filer.

## Steg 5: Ändra bildförhållandet till 30 och spara den andra bilden

Nu ökar vi höjden på de staplade staplarna genom att ändra bildförhållandet till **30**. Detta gör streckkoden högre utan att ändra X‑dimensionen.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Kör programmet nu skapar två PNG‑filer:

* **DatabarAspectRatio15.png** – en kompakt streckkod lämplig för små etiketter.
* **DatabarAspectRatio30.png** – en högre streckkod som förbättrar skanningspålitlighet på lågkontrastytor.

Du kan öppna bilderna i vilken visare som helst för att verifiera att staplarna är korrekt staplade och att den kodade datan matchar den ursprungliga GS1‑strängen.

## Steg 6: Verifiera det kodade värdet (valfritt)

Om du behöver bekräfta att streckkoden verkligen representerar inmatningssträngen kan du avkoda den med samma bibliotek:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Avkodaren bör skriva ut `(01)12345678901231`, vilket bevisar att **create databar stacked barcode**‑processen bevarade datan.

## Vanliga fallgropar och hur du undviker dem

| Problem | Varför det händer | Lösning |
|---------|-------------------|---------|
| Streckkoden blir suddig | X‑dimensionen är för låg för utskriftsupplösningen | Öka `XDimension.Pixels` eller använd `Millimeters` för utskrift |
| Skannern rapporterar “symbol not found” | Bildförhållandet ligger utanför det stödjade intervallet 10‑30 | Håll förhållandet mellan 10 och 30; 15 och 30 är säkra standardvärden |
| PNG‑filen innehåller ett vattenmärke | Användning av den kostnadsfria utvärderingslicensen för Aspose.BarCode | Köp en full licens eller använd provversionen endast för testning |
| Avkodning misslyckas på den andra bilden | Avkodaren var konfigurerad för fel symbologi | Använd `DecodeType.DatabarStackedOmniDirectional` när du läser staplade streckkoder |

## Nästa steg

Nu när du kan **create databar stacked barcode** bilder kanske du vill:

* **Bädda in PNG‑filerna i PDF‑fakturor** med ett PDF‑bibliotek som **Aspose.PDF**.
* **Generera streckkoder i realtid i ett web‑API** – returnera PNG‑bytarna direkt från en ASP.NET Core‑controller.
* **Experimentera med andra DataBar‑varianter** (t.ex. `DatabarExpanded`, `DatabarLimited`) genom att ändra `EncodeTypes`‑enum.
* **Justera färger** genom att sätta `generator.Parameters.Barcode.ForeColor` och `BackColor` för varumärkes‑specifika designer.

Varje av dessa ämnen bygger på samma grundläggande koncept som behandlats här: initiering av `BarcodeGenerator`, konfiguration av visuella parametrar och sparande av resultatet med `BarCodeImageFormat`.

---

### Slutsats

Denna handledning demonstrerade hur man **create databar stacked barcode** bilder i C# med Aspose.BarCode. Du lärde dig att ställa in **X‑dimensionen**, ändra **streckkodens bildförhållande** och exportera resultatet som **PNG**‑filer med `BarcodeGenerator`. Med det valfria avkodningssteget kan du även verifiera att den kodade GS1‑datan är korrekt. Använd dessa mönster i dina egna lager-, frakt- eller kassa‑applikationer, och utforska de många anpassningsalternativen som biblioteket erbjuder. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i denna guide. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementeringsmetoder i dina egna projekt.

- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}