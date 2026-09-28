---
category: general
date: 2026-07-21
description: Hur man snabbt genererar streckkod med Aspose.BarCode för C#. Lär dig
  skapa streckkod med Aspose, justera bildförhållanden och spara PNG-filer på några
  minuter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: sv
lastmod: 2026-07-21
og_description: Hur man genererar streckkod med Aspose.BarCode för C#. Denna steg‑för‑steg‑guide
  visar hur du skapar streckkod med Aspose, justerar inställningar och exporterar
  bilder.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Hur man genererar streckkod i C# – Snabb Aspose.BarCode-handledning
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Hur man genererar streckkod i C# – Komplett guide till Aspose.BarCode
url: /sv/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man genererar streckkod i C# – Komplett Aspose.BarCode‑guide

Har du någonsin undrat **hur man genererar streckkod** i en .NET‑app utan att kämpa med låg‑nivå bildkod? Du är inte ensam. I många företagsprojekt måste vi **skapa streckkod med Aspose** för fakturor, fraktetiketter eller lagerhantering, och biblioteket gör det förvånansvärt smärtfritt.

I den här handledningen går vi igenom ett verkligt exempel som bygger en DataBar Stacked Omnidirectional‑streckkod, justerar dess bildförhållande och sparar två PNG‑filer. I slutet har du ett färdigt konsolprogram och en klar förståelse för de viktigaste egenskaperna du kan styra.

## Vad du kommer att lära dig

- Installera Aspose.BarCode i ett C#‑projekt (NuGet, licensgrunder)
- Initiera en **DataBar stacked omnidirectional**‑generator
- Justera X‑dimensionen (pixelstorlek) och bildförhållandet
- Spara streckkoden som PNG‑bilder
- Utöka exemplet till andra streckkodstyper eller utdataformat

Ingen förkunskap om Aspose krävs – bara en fungerande .NET 6 (eller senare) SDK och en favorit‑IDE.

## Förutsättningar

| Krav | Orsak |
|------|-------|
| .NET 6 SDK eller nyare | Moderna språkfunktioner och enkel projekt‑skapning |
| Visual Studio 2022 (eller VS Code) | IDE för byggning och felsökning |
| Aspose.BarCode for .NET NuGet‑paket | Kärnbiblioteket som gör det tunga arbetet |
| En giltig Aspose‑licens (eller utvärdering) | Tar bort vattenstämpeln och låser upp alla funktioner |

Om du ännu inte har installerat NuGet‑paketet, kör:

```bash
dotnet add package Aspose.BarCode
```

Nu när vi är klara, låt oss dyka ner i koden.

## Steg 1: Skapa ett nytt konsolprojekt

Börja med att starta ett nytt konsol‑app‑projekt. Öppna en terminal och skriv:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Detta skapar `Program.cs` och en `.csproj`‑fil. Öppna projektet i din editor och lägg till Aspose‑referensen som visas ovan.

## Steg 2: Initiera BarcodeGenerator

Kärnan i processen är klassen `BarcodeGenerator`. Vi begär en **DataBar stacked omnidirectional**‑symbologi och matar in en exempel‑GS1‑128‑sträng.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Varför detta är viktigt:** `EncodeTypes.DatabarStackedOmniDirectional` producerar en kompakt, högdensitets‑streckkod som är idealisk för små etiketter. Datatstringen följer GS1 Application Identifier `(01)` för ett GTIN‑14‑värde, vilket många leveranskedjesystem förväntar sig.

## Steg 3: Justera bildförhållandet och spara bilder

Aspose.BarCode låter dig finjustera **bildförhållandet** för DataBar‑symboler via `Parameters.Barcode.DataBar.AspectRatio`. Att ändra detta värde förändrar den visuella bredd‑till‑höjd‑proportionen, vilket kan vara avgörande för att få streckkoden att passa i en etikett med fast storlek.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Förklaring av varje rad**

- `outputPath` pekar på en mapp där PNG‑filerna kommer att hamna. `Directory.CreateDirectory` garanterar att mappen finns även på en ny maskin.
- `AspectRatio = 15` ger en relativt hög streckkod; `AspectRatio = 30` sträcker den horisontellt.
- `generator.Save(...)` skriver bilden till disk. Enum‑värdet `BarCodeImageFormat.Png` säkerställer förlustfri kvalitet.
- `Console.WriteLine` ger dig omedelbar återkoppling när du kör programmet.

### Förväntad utdata

När du kör `dotnet run` bör du se något liknande:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Öppna de två PNG‑filerna sida‑vid‑sida; du kommer att märka att den andra bilden är märkbart bredare samtidigt som den behåller samma höjd. Båda bilderna kan läsas av vanliga streckkodsläsare.

## Steg 4: Kör det kompletta exemplet

Här är den **fullständiga, körbara källkoden** i ett block för enkel kopiering och inklistring:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Kompilera och kör:

```bash
dotnet run
```

Voilà—två perfekt renderade streckkod‑PNG‑filer dyker upp i `GeneratedBarcodes/`.

## Steg 5: Utöka exemplet (valfritt)

Nu när du **vet hur man genererar streckkod** med Aspose kanske du undrar: *Vad mer kan jag justera?* Här är några snabba idéer:

| Egenskap | Vad den gör | Typiskt användningsfall |
|----------|-------------|--------------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Ändrar storleken på den mänskligt läsbara texten | Större teckensnitt för handhållna skannrar |
| `generator.Parameters.Barcode.ImageFormat` | Globalt utdataformat (PNG, JPEG, BMP, osv.) | JPEG för webbvänlig storlek |
| `generator.Parameters.Barcode.Color` | Ställer in förgrundsfärgen | Färgkodade kategorier |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Vektorutdata för oändlig skalning | Utskriftsklara PDF‑filer |

För att experimentera, lägg bara till motsvarande rader före varje `Save`‑anrop.

## Vanliga fallgropar & Pro‑tips

- **Licensplacering:** Om du använder en betald licens, anropa `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` innan du skapar generatorn. Att glömma detta lämnar en vattenstämpel på bilden.
- **Ogiltig datatsträng:** DataBar‑symbologier förväntar sig numerisk GS1‑data. Att ange alfanumeriska tecken kastar `ArgumentException`.
- **Trådsäkerhet:** `BarcodeGenerator`‑instanser är **inte** trådsäkra. Skapa en ny instans per tråd om du genererar streckkoder parallellt.
- **Bildstorlek vs. skanningskapacitet:** En mycket hög `XDimension.Pixels` kan producera en enorm bild som vissa skannrar har svårt att läsa. Testa med din mål‑hardware.

## Slutsats

Vi har precis gått igenom **hur man genererar streckkod** i C# med Aspose.BarCode, från projektuppsättning till sparande av två bilder med olika bildförhållanden. De viktigaste stegen – initiera generatorn, konfigurera X‑dimension och bildförhållande samt anropa `Save` – bildar ett återanvändbart mönster som du kan tillämpa på vilken streckkodstyp Aspose stödjer.

Nu kan du **skapa streckkod med Aspose** för fakturor, fraktetiketter eller lageretiketter, och du har en solid grund för att utforska mer avancerade funktioner som färg, anpassade teckensnitt eller SVG‑utdata. Känn dig fri att justera koden, experimentera med andra `EncodeTypes` och integrera generatorn i dina befintliga tjänster.

Har du frågor eller vill se en specifik streckkodsstil? Lämna en kommentar nedan, och lycka till med kodandet!


## Vad bör du lära dig härnäst?


Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerades i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}