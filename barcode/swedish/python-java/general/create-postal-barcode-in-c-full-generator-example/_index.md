---
category: general
date: 2026-07-15
description: Skapa poststreckkod i C# snabbt. Detta exempel på streckkodsgenerator
  visar hur man exporterar streckkoden i PNG-format för Planet- och RM4SCC-streckkoder.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: sv
lastmod: 2026-07-15
og_description: Skapa poststreckkod i C# med den här steg‑för‑steg‑guiden. Lär dig
  exempel på streckkodsgeneratorn som låter dig exportera streckkodsbild i PNG‑format.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Skapa poststreckkod i C# – Komplett guide för generator
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Skapa poststreckkod i C# – Fullt generatorexempel
url: /sv/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa poststreckkod i C# – Fullständigt generatorexempel

Har du någonsin undrat hur man **create postal barcode** i ett .NET‑projekt utan att leta igenom ändlösa dokument? Du är inte ensam. Oavsett om du bygger ett system för postetiketter eller automatiserar masspost, är det en nödvändig färdighet att generera en ren barcode PNG. I den här handledningen går vi igenom ett komplett **barcode generator example** som visar exakt hur man **export barcode image** filer i **barcode PNG format**.

Vi kommer att gå igenom allt från att ställa in utdata‑mappen till att justera modulbredd och stapelhöjd för både Planet‑ och RM4SCC‑standarderna. I slutet har du en färdig‑att‑köra konsolapp som genererar fyra PNG‑filer—två med automatisk höjd och två med en fast höjd på 100 px. Ingen onödig text, bara en praktisk lösning du kan kopiera‑klistra.

## Förutsättningar

- .NET 6 SDK eller senare (koden fungerar med .NET Core och .NET Framework)
- En IDE eller editor du är bekväm med (Visual Studio, VS Code, Rider…)
- Aspose.BarCode for .NET NuGet‑paketet (installera via `dotnet add package Aspose.BarCode`)

Det är allt—inga extra tjänster, inga webb‑API:er. Bara ett lokalt C#‑projekt.

## Skapa poststreckkod – Steg‑för‑steg

Nedan delar vi upp processen i fem tydliga steg. Varje steg har en beskrivande **H2**‑rubrik som innehåller antingen huvud‑ eller sekundärnyckelord, så du snabbt hittar exakt det du behöver.

### Steg 1: Förbered utdata‑katalogen

Först och främst behöver vi en mapp där de genererade PNG‑filerna ska lagras. Att hårdkoda en sökväg fungerar för en demo, men i produktion skulle du förmodligen läsa den från konfiguration.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Pro tip:** Att använda `Path.Combine` gör koden OS‑agnostisk, och `Directory.CreateDirectory` är säkert att anropa även om mappen redan finns.

### Steg 2: Generera en Planet‑streckkod med automatisk höjd

Nu kommer vi till kärnan i **how to generate planet barcode**‑delen. Vi skapar en `BarcodeGenerator`‑instans, sätter modulbredden (X‑dimension), och låter biblioteket bestämma stapelhöjden.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

`EncodeTypes.Planet`‑enumet talar om för Aspose att vi vill ha Planet‑symboliken, som är vanlig för posttjänster i många länder. Eftersom vi inte rörde `BarHeight` väljer generatorn ett rimligt standardvärde som håller streckkoden läsbar.

### Steg 3: Generera en RM4SCC‑streckkod med automatisk höjd

RM4SCC är den kanadensiska poststreckkodformatet. Koden speglar Planet‑exemplet, vilket illustrerar **barcode generator example**‑mönstret du kan återanvända för vilken stödjande symbolik som helst.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Återigen förlitar vi oss på automatisk höjd, vilket är perfekt för snabba prototyper eller när du låter skrivaren hantera skalning.

### Steg 4: Generera en Planet‑streckkod med fast höjd (100 px)

Ibland kräver postningssystemet en strikt stapelhöjd—kanske förväntar sig skrivaren exakt 100 px. Här är hur du **export barcode image** med en tvingad höjd.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Genom att sätta `BarHeight.Pixels` åsidosätts den automatiska beräkningen. Resten av inställningarna förblir desamma, vilket säkerställer visuell konsistens mellan både automatiska och fasta‑höjdsbilder.

### Steg 5: Generera en RM4SCC‑streckkod med fast höjd (100 px)

Vi upprepar den fasta höjd‑metoden för RM4SCC. Detta demonstrerar flexibiliteten i **barcode generator example**: du kan blanda och matcha automatisk och manuell inställning per symbolik.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Fullständig källkodslista

När allt sätts ihop, här är det kompletta, körbara programmet. Kopiera blocket nedan till ett nytt konsolprojekt och tryck på **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

När du kör programmet skapas följande filer (alla i **barcode PNG format**):

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Varje bild är en skarp, svart‑på‑vitt representation klar för utskrift eller vidare bearbetning.

## Varför detta tillvägagångssätt fungerar

- **Consistency:** Genom att fixera `XDimension.Pixels` till 4 för alla streckkoder garanterar du samma modulbredd, vilket är avgörande för skannrar som förväntar sig en specifik punktstorlek.
- **Flexibility:** Samma kodbas låter dig växla mellan automatisk och fast höjd utan att skriva om generatorlogiken—perfekt för lösningar med flera transportörer.
- **Performance:** Att generera en PNG är en lättviktig operation; Aspose‑biblioteket strömmar bilden direkt till disk, vilket undviker onödig minnesbelastning.
- **Portability:** Anropen `Path.Combine` och `Directory.CreateDirectory` håller koden plattformsoberoende, så samma källa fungerar på Windows, Linux och macOS.

## Vanliga fallgropar & hur man undviker dem

| Issue | Why it Happens | Fix |
|------|----------------|-----|
| Streckkoden ser suddig ut | Användning av en mycket låg X‑dimension (t.ex. 1 px) | Öka `XDimension.Pixels` till minst 3‑4 för poststreckkoder |
| Skannern avvisar bilden | Stapelhöjden är för liten eller för stor för skrivaren | Använd `BarHeight.Pixels` för att matcha skrivarens specifikationer |
| PNG‑filen är korrupt | Glömmer att stänga strömmen (sällsynt med Aspose) | Låt `Save`‑metoden hantera disposal; undvik manuell strömhante­ring om det inte är nödvändigt |
| Utdatamappen hittades inte | Hårdkodad sökväg pekar på en icke‑existerande katalog | Anropa alltid `Directory.CreateDirectory` innan du sparar |

## Utöka exemplet

Nu när du behärskar grunderna i **create postal barcode** kan du vilja utforska:

- **Adding human‑readable text** under streckkoden (`DisplayText`‑egenskapen)
- **Changing colors** (`ForeColor`, `BackColor`) för varumärkesprofilering
- **Batch processing** av en CSV‑lista med postkoder (loopa över generatorn)
- **Exporting to other formats** som SVG eller PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Var och en av dessa utökningar följer samma mönster som demonstrerats i detta **barcode generator example**, så du kan experimentera utan att börja från början.

## Slutsats

Du

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Skapa streckkodsbild C# – GS1 DataMatrix‑exempel](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Hur man skapar dotcode med utökad kodtext med Aspose.BarCode för .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Hur man skapar Aztec‑streckkod med felkorrigering i .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}