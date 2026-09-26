---
category: general
date: 2026-09-26
description: Barcodegeneratorns C#‑guide visar hur man anger rader och hur man anger
  kolumner när man skapar Databar Expanded Stacked‑streckkoder i C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to set rows
- how to set columns
- Databar Expanded Stacked barcode
- C# barcode library
language: sv
lastmod: 2026-09-26
og_description: Streckkodsgenerator C#‑handledning förklarar hur man sätter rader
  och hur man sätter kolumner för Databar Expanded Stacked‑streckkoder, med fullständig
  kod och tips.
og_image_alt: Barcode generator C# example showing rows and columns settings
og_title: Streckkodsgenerator C# – ställ in rader och kolumner steg för steg
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  headline: How to use barcode generator C# for rows and columns
  type: TechArticle
- description: barcode generator C# guide shows how to set rows and how to set columns
    when creating Databar Expanded Stacked barcodes in C#.
  name: How to use barcode generator C# for rows and columns
  steps:
  - name: Create a generator for a Databar Expanded Stacked barcode
    text: '```csharp // Create a generator for a Databar Expanded Stacked barcode
      with sample text BarcodeGenerator barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: How to set columns – configure the barcode to use 4 columns
    text: '```csharp // How to set columns: set the Columns property to 4 barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image with the column setting
    text: '```csharp // Save the PNG image that reflects the column configuration
      barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
      ```'
  - name: Re‑initialize the generator for a different layout
    text: When you need a separate barcode with a different visual arrangement, create
      a new instance rather than re‑using the previous one. This guarantees that previous
      settings (like columns) do not bleed into the new configuration.
  - name: How to set rows – configure the barcode to use 3 rows
    text: '```csharp // How to set rows: assign the Rows property to 3 barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that includes the row setting
    text: '```csharp // Save the PNG image that reflects the row configuration barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'Running the program produces two PNG files:'
  - name: Pro tip
    text: 'If you need to generate many barcodes with varying rows and columns, wrap
      the configuration logic in a helper method:'
  type: HowTo
tags:
- barcode
- C#
- code example
title: Hur man använder streckkodsgenerator i C# för rader och kolumner
url: /sv/python-java/general/how-to-use-barcode-generator-c-for-rows-and-columns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så använder du barcode generator C# för rader och kolumner

Om du behöver en **barcode generator C#** som låter dig kontrollera den visuella layouten för en Databar Expanded Stacked‑streckkod, ger den här handledningen dig en komplett, körbar lösning. Du kommer att lära dig **hur du ställer in rader** och **hur du ställer in kolumner** så att den genererade bilden matchar exakt den design du kräver.

Att generera streckkoder programatiskt känns ofta som att gissa vilken egenskap som gör vad. I slutet av den här guiden kommer du att förstå API‑ytan, undvika vanliga fallgropar och ha ett färdigt kodexempel som du kan kopiera in i ditt eget projekt.

## Förutsättningar

* .NET 6.0 eller senare installerat (koden fungerar även med .NET Core och .NET Framework)
* En referens till barcode‑genereringsbiblioteket som tillhandahåller `BarcodeGenerator` och `EncodeTypes` (t.ex. Aspose.BarCode, Dynamsoft eller något kompatibelt SDK)
* En IDE såsom Visual Studio eller VS Code
* Skrivbehörighet till en mapp där PNG‑filerna ska sparas

Inga ytterligare NuGet‑paket krävs utöver själva barcode‑SDK‑et.

## Barcode generator C# – ställa in rader och kolumner

Följande avsnitt går igenom varje konfigurationssteg. Kodsnuttarna är kompletta och kan klistras in direkt i en konsolapplikations `Main`‑metod.

### Steg 1: Skapa en generator för en Databar Expanded Stacked‑streckkod

```csharp
// Create a generator for a Databar Expanded Stacked barcode with sample text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

*Varför detta är viktigt:* Att instansiera `BarcodeGenerator` är den första åtgärden du gör i någon **barcode generator C#**‑arbetsflöde. Konstruktorn tar emot kodningstypen och datasträngen som ska kodas.

### Steg 2: Hur du ställer in kolumner – konfigurera streckkoden att använda 4 kolumner

```csharp
// How to set columns: set the Columns property to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

Att sätta egenskapen `Columns` ändrar antalet vertikala moduler som DataBar använder. Ett värde på `4` skapar en tätare, mer kompakt streckkod, vilket är användbart när du har begränsat horisontellt utrymme.

### Steg 3: Spara streckkodbilden med kolumninställningen

```csharp
// Save the PNG image that reflects the column configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

`Save`‑metoden skriver den genererade bilden till disk. Verifiera utdatafilen för att bekräfta att den fyrakolumns layouten visas som förväntat.

![Barcode generator C#‑exempel som visar rader och kolumninställningar](./images/barcode-rows-columns.png)

*Bilden ovan illustrerar resultatet av kolumnkonfigurationen.*

### Steg 4: Återinitiera generatorn för en annan layout

När du behöver en separat streckkod med ett annat visuellt arrangemang, skapa en ny instans istället för att återanvända den föregående. Detta garanterar att tidigare inställningar (som kolumner) inte läcker in i den nya konfigurationen.

```csharp
// Re‑initialize to start a fresh configuration
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
```

### Steg 5: Hur du ställer in rader – konfigurera streckkoden att använda 3 rader

```csharp
// How to set rows: assign the Rows property to 3
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

`Rows`‑egenskapen styr den vertikala staplingen av DataBar‑modulerna. En tre‑rads layout är standard för många skanningsenheter, men du kan öka den för högre datatäthet.

### Steg 6: Spara streckkodbilden som inkluderar radinställningen

```csharp
// Save the PNG image that reflects the row configuration
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Öppna `DatabarRows3.png` för att se den tre‑rads arrangemanget. Om streckkoden inte läses, dubbelkolla rad‑/kolumnvärdena mot din skanners specifikationer.

## Fullständig källkod – klar att kopiera

Nedan är det kompletta programmet som kombinerar alla stegen ovan. Ersätt `YOUR_DIRECTORY` med en absolut eller relativ sökväg som finns på din maskin.

```csharp
using System;
using YourBarcodeSdkNamespace;   // Replace with the actual namespace of your SDK

class Program
{
    static void Main()
    {
        // ---------- Columns configuration ----------
        // 1. Create generator
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 2. Set columns (how to set columns)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3. Save image with column setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Rows configuration ----------
        // 4. Re‑initialize generator for a fresh instance
        barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

        // 5. Set rows (how to set rows)
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6. Save image with row setting
        barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### Förväntat resultat

När programmet körs skapas två PNG‑filer:

| Filnamn               | Layoutbeskrivning                         |
|-----------------------|-------------------------------------------|
| `DatabarCols4.png`    | Databar Expanded Stacked med **4 columns** |
| `DatabarRows3.png`    | Databar Expanded Stacked med **3 rows**    |

Båda bilderna bör kunna skannas av standard streckkodsläsare som stödjer Databar Expanded Stacked‑symbologi.

## Vanliga fallgropar och proffstips

| Fallgrop                                   | Varför det händer                                   | Åtgärd / Tips |
|--------------------------------------------|------------------------------------------------------|---------------|
| Att använda samma `BarcodeGenerator`‑instans för både rader och kolumner | SDK‑et behåller den tidigare konfigurationen, så att sätta rader efter kolumner kan ge en oväntad blandning | Återinitiera generatorn (som visas i Steg 4) innan du ändrar den andra dimensionen |
| Att glömma att sätta `EncodeTypes` korrekt | SDK‑et använder som standard en annan symbologi, vilket leder till en ogiltig streckkod | Skicka alltid `EncodeTypes.DatabarExpandedStacked` när du behöver detta specifika format |
| Att spara till en icke‑existerande mapp   | `Save` kastar ett undantag om sökvägen är ogiltig | Säkerställ att `YOUR_DIRECTORY` finns eller använd `Directory.CreateDirectory` innan du anropar `Save` |
| Att använda värden utanför det tillåtna intervallet (t.ex. 0 kolumner) | SDK‑et validerar intervallet och kastar `ArgumentOutOfRangeException` | Giltiga kolumnvärden är 1‑4; giltiga radvärden är 1‑3 för denna symbologi |

### Pro‑tips

Om du behöver generera många streckkoder med varierande rader och kolumner, paketera konfigurationslogiken i en hjälpfunktion:

```csharp
static void GenerateDatabar(string text, int? rows, int? columns, string outputPath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, text);
    if (rows.HasValue)    generator.Parameters.Barcode.DataBar.Rows = rows.Value;
    if (columns.HasValue) generator.Parameters.Barcode.DataBar.Columns = columns.Value;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

## Slutsats

Du har nu ett tydligt, komplett exempel på hur du använder en **barcode generator C#** för att kontrollera både antalet rader och antalet kolumner i en Databar Expanded Stacked‑streckkod. Genom att följa stegen ovan kan du generera precisa streckkodsbilder som uppfyller de exakta layoutkraven för din skanningsutrustning.

Härifrån kan du utforska:

* Justera andra `DataBar`‑egenskaper såsom **AspectRatio** eller **BarHeight**
* Generera andra symbologier (t.ex. QR, Code128) med samma `BarcodeGenerator`‑klass
* Bädda in den genererade PNG‑filen i PDF‑filer eller skriv ut direkt från C#

Känn dig fri att experimentera med olika rad‑/kolumnkombinationer och dela dina resultat i kommentarerna. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Hur du ställer in kolumner för en Databar Expanded Stacked‑streckkod – komplett C#‑guide](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [databar expanded stacked barcode‑guide – hur du genererar och dimensionerar den i C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Barcode Generator‑exempel i C# – Ställ in kolumner, rader & exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}