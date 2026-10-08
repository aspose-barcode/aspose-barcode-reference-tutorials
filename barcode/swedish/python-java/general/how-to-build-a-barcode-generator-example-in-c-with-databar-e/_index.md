---
category: general
date: 2026-09-19
description: Exempel på streckkodsgenerator i C# som visar hur man genererar streckkod
  i C# med Aspose.BarCode för kolumn‑ och radlayouter.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: sv
lastmod: 2026-09-19
og_description: Exempel på streckkodsgenerator visar hur man genererar streckkod i
  C# med kolumn‑ och radlayouter med hjälp av Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: exempel på streckkodsgenerator – skapa DataBar Expanded Stacked‑streckkoder
  i C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example in C# showing how to generate barcode C#
    using Aspose.BarCode for column and row layouts
  headline: How to build a barcode generator example in C# with DataBar Expanded Stacked
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Hur man bygger ett exempel på en streckkodsgenerator i C# med DataBar Expanded
  Stacked
url: /sv/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# exempel på streckkodsgenerator – skapa DataBar Expanded Stacked streckkoder i C#

Om du behöver ett **barcode generator example** som fungerar i ett .NET‑projekt, visar den här guiden exakt hur du genererar barcode C# med hjälp av Aspose.BarCode‑biblioteket. Du kommer att se hur du konfigurerar en DataBar Expanded Stacked‑streckkod för både en kolumnbaserad layout och en radbaserad layout, och du får färdig‑körbar kod som producerar PNG‑bilder.

Handledningen täcker allt från att installera NuGet‑paketet till att spara de slutliga bilderna, så att du kan kopiera koden till din egen lösning utan ytterligare forskning.

## Vad du kommer att lära dig

* Hur du installerar och refererar Aspose.BarCode i ett C#‑projekt.  
* Hur du skapar ett **barcode generator example** som kodar en lång datasträng.  
* Hur du ställer in en 4‑kolumns layout och en 3‑raders layout på samma streckkodstyp.  
* Hur du sparar de genererade bilderna som PNG‑filer.  

I slutet av den här artikeln kommer du att ha två färdiga PNG‑filer: `ExpandedStackedCols4.png` (fyra kolumner) och `ExpandedStackedRows3.png` (tre rader).

## Förutsättningar

* .NET 6.0 SDK eller senare (koden fungerar också med .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code, eller någon C#‑IDE du föredrar.  
* Internetåtkomst för att ladda ner **Aspose.BarCode**‑NuGet‑paketet.  

Inga ytterligare externa tjänster krävs.

## Steg 1: Installera Aspose.BarCode‑NuGet‑paketet

Öppna en terminal i din projektmapp och kör:

```bash
dotnet add package Aspose.BarCode
```

Kommandot lägger till den senaste stabila versionen av Aspose.BarCode till din projektfil. Efter att paketet har återställts kan du referera till dess namnrymder i dina C#‑källfiler.

## Steg 2: Lägg till de nödvändiga using‑direktiven

Skapa en ny C#‑konsolapplikation (eller lägg till koden i ett befintligt projekt) och inkludera följande `using`‑satser högst upp i filen:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Dessa direktiv ger dig åtkomst till klassen `BarcodeGenerator` och uppräkningen `EncodeTypes` som används i **barcode generator example**.

## Steg 3: Skapa ett barcode generator example med en 4‑kolumns layout

Den första delen av exemplet bygger en DataBar Expanded Stacked‑streckkod som använder en fyrakolumns‑arrangemang. Koden nedan följer exakt de steg som visas i det ursprungliga kodavsnittet, men lägger till kommentarer som förklarar varför varje rad är nödvändig.

```csharp
// Step 3.1: Initialise the generator with the desired barcode type and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,   // DataBar Expanded Stacked type
    "Long data string");                  // The data you want to encode

// Step 3.2: Configure the barcode to use a 4‑column layout
generator.Parameters.Barcode.DataBar.Columns = 4;

// Step 3.3: Save the image as a PNG file
generator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
```

**Varför detta fungerar**

* `EncodeTypes.DatabarExpandedStacked` talar om för Aspose.BarCode att generera en DataBar Expanded Stacked‑symbol, som är lämplig för detaljhandelsapplikationer.  
* Genom att sätta `DataBar.Columns` till `4` tvingas generatorn att dela symbolen i fyra vertikala sektioner, vilket förbättrar läsbarheten på smala etiketter.  
* `Save` skriver streckkoden till disk; argumentet `BarCodeImageFormat.Png` säkerställer förlustfri bildkvalitet.  

När du kör detta block skapas `ExpandedStackedCols4.png` i applikationens arbetskatalog. Filen innehåller en högupplöst streckkod som kan läsas av vilken standard‑DataBar‑läsare som helst.

## Steg 4: Återinitiera generatorn för en annan layout

För att demonstrera en radbaserad layout behöver du en ny `BarcodeGenerator`‑instans. Återinitiering garanterar att den tidigare kolumninställningen inte påverkar den nya konfigurationen.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Steg 5: Konfigurera streckkoden för att använda en 3‑raders layout

DataBar‑API:et stödjer också en radarrangemang. Genom att sätta egenskapen `Rows` definierar du hur många horisontella segment symbolen ska innehålla.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Varför du kanske väljer rader framför kolumner**

Rader är användbara när etikettens höjd är begränsad men bredden är generös. En tre‑raders layout komprimerar streckkoden vertikalt samtidigt som den behåller den nödvändiga mängden data.

## Komplett källfil

Nedan finns en fullständig, fristående `Program.cs` som du kan kompilera och köra direkt. Den innehåller både kolumn- och radexemplen, så du får två PNG‑filer med ett enda körning.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeGeneratorExample
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – replace with your own value if needed
            const string data = "Long data string";

            // ---------- Column layout (4 columns) ----------
            var columnGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 4‑column layout
            columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column image
            columnGenerator.Save("ExpandedStackedCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedCols4.png (4‑column layout)");

            // ---------- Row layout (3 rows) ----------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                data);

            // Set 3‑row layout
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row image
            rowGenerator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved ExpandedStackedRows3.png (3‑row layout)");
        }
    }
}
```

### Förväntad output

Efter att ha kört programmet kommer du att se två konsolmeddelanden som bekräftar att filerna skapats:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Båda PNG‑filerna visar en DataBar Expanded Stacked‑streckkod som kodar strängen "Long data string". Att skanna någon av bilderna med en standardstreckkodsläsare returnerar den ursprungliga datan.

## Vanliga frågor och edge cases

| Question | Answer |
|----------|--------|
| **Kan jag ändra bildformatet?** | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Tiff` beroende på dina krav. |
| **Vad händer om datasträngen är kortare?** | DataBar‑formatet justerar automatiskt symbolstorleken; du behöver inte ändra layoutinställningarna. |
| **Hur ställer jag in streckkodens storlek (bredd/höjd)?** | Använd `generator.Parameters.Image.Width` och `generator.Parameters.Image.Height` innan du anropar `Save`. |
| **Är det möjligt att lägga till en mänskligt läsbar rubrik?** | Sätt `generator.Parameters.Barcode.CodeText` och aktivera `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Vilka .NET‑versioner stöds?** | Aspose.BarCode stöder .NET Standard 2.0, .NET 5/6 och .NET Framework 4.6.1+. |

Att hantera dessa variationer gör **barcode generator example** robust nog för produktionsbruk.

## Pro‑tips

* **Återanvänd generatorobjektet endast när layouten förblir densamma.** Att skapa en ny instans för varje layout, som visas i Steg 4‑5, förhindrar oavsiktlig överföring av egenskaper.  
* **Validera den genererade streckkoden** med `generator.Validate()` om du behöver säkerställa efterlevnad av ISO/GS1‑standarder.  
* **Batch‑behandling:** Omge kolumn‑ och radlogiken i en loop som itererar över en lista med layoutkonfigurationer. Detta minskar kodduplicering när du behöver många variationer.

## Slutsats

Detta **barcode generator example** demonstrerar hur man **genererar barcode C#**‑kod som producerar både en 4‑kolumns och en 3‑raders DataBar Expanded Stacked‑streckkod. Du har nu ett komplett, körbart program, en förståelse för nyckelegenskaperna (`Columns`, `Rows`) och praktiska tips för att utöka lösningen.

Nästa, utforska relaterade ämnen som **anpassa streckkodsfärger**, **bädda in streckkoder i PDF‑dokument** eller **generera QR‑koder med Aspose.BarCode**. Varje ämne bygger på samma API‑principer som behandlats här.

Känn dig fri att experimentera med olika datasträngar, bildformat och layoutkombinationer. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}