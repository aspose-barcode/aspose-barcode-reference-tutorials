---
category: general
date: 2026-09-07
description: C#‑tutorial för streckkodsgenerator som visar hur du genererar streckkod‑PNG‑filer
  och skapar DataBar‑streckkoder med anpassningsbara rader och kolumner
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: sv
lastmod: 2026-09-07
og_description: 'streckkodsgenerator C#‑handledning: lär dig att generera streckkod‑PNG‑filer
  och skapa DataBar‑streckkoder med anpassade rader och kolumner på bara några minuter'
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: streckkodsgenerator C# – skapa DataBar-streckkoder och PNG-bilder
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: Hur man använder en streckkodsgenerator i C# för att skapa DataBar‑streckkoder
url: /sv/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Så här använder du en barcode generator C# för att skapa DataBar‑streckkoder

Om du behöver en **barcode generator C#** för att skapa högkvalitativa streckkoder, visar den här guiden hur du **genererar barcode PNG**‑filer och **skapar DataBar‑streckkoder** med anpassade rader och kolumner. Oavsett om du bygger ett detaljhandelslagerhanteringssystem eller en biljettplattform, låter stegen nedan dig producera en DataBar Expanded Stacked‑streckkod i ett enda, självständigt exempel.

I den här handledningen kommer du att lära dig:

* Hur du instansierar `BarcodeGenerator` för DataBar Expanded Stacked‑symbologi.  
* Hur du justerar kolumn- och radinställningar för att uppfylla ISO / GS1‑specifikationerna.  
* Hur du sparar resultatet som en PNG‑bild som kan bäddas in i webbsidor eller skrivas ut på etiketter.  

Inga externa tjänster krävs—bara Aspose.BarCode för .NET‑biblioteket (eller något kompatibelt bibliotek som följer samma API). Koden körs på .NET 6+ och fungerar i Visual Studio, Rider eller någon IDE som stödjer C#.

## Förutsättningar

Innan du börjar, se till att du har:

* .NET 6 SDK eller senare installerat.  
* En referens till `Aspose.BarCode` NuGet‑paketet (eller ett motsvarande bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`).  
* Grundläggande kunskap om C#‑syntax och projektstruktur.  

Du kan lägga till paketet via kommandoraden:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Initiera barcode generator C# för DataBar Expanded Stacked

Det första steget är att skapa en `BarcodeGenerator`‑instans som riktar sig mot **DataBar Expanded Stacked**‑symbologi. Detta objekt innehåller alla renderingsparametrar, inklusive texten som ska kodas.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**Varför detta är viktigt:** Enum‑värdet `EncodeTypes.DatabarExpandedStacked` talar om för biblioteket vilken streckkodstandard som ska tillämpas. Att använda rätt enum säkerställer att den genererade bilden följer GS1 DataBar‑specifikationerna.

## Steg 2: Konfigurera antalet kolumner (standardrader används)

DataBar Expanded Stacked kan delas upp i flera kolumner. Justering av kolumnantalet förändrar den visuella densiteten och kan hjälpa till att få plats med längre datasträngar i begränsat utrymme.

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**Proffstips:** Standardantalet kolumner är 1. Att sätta det till 4 skapar fyra staplade kolumner, vilket är idealiskt för längre numeriska strängar samtidigt som streckkodens höjd hålls hanterbar.

## Steg 3: Generera barcode PNG med kolumninställningen tillämpad

Spara nu streckkoden som en PNG‑bild. PNG bevarar de skarpa kanterna som behövs för skannrar och fungerar bra både på webben och i tryckt media.

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Filen `DatabarCols4.png` innehåller en **barcode PNG** som du kan bädda in direkt i HTML:

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## Steg 4: Skapa en separat generatorinstans för radkonfiguration

Om du behöver kontrollera antalet rader istället för kolumner, instansiera en ny `BarcodeGenerator`. Att återanvända samma instans efter att ha ändrat en dimension kan leda till oväntade layoutartefakter, så ett nytt objekt är det säkraste tillvägagångssättet.

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Steg 5: Ställ in antalet rader (standardkolumner används)

Rader påverkar den vertikala staplingen av streckkodens moduler. Att öka antalet rader kan göra streckkoden högre, vilket kan krävas för vissa etikettstorlekar.

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**Varför rader vs. kolumner:** Kolumner delar streckkoden horisontellt, medan rader förlänger den vertikalt. Välj den orientering som bäst passar din etikettdesign.

## Steg 6: Generera barcode PNG med radinställningen tillämpad

Spara slutligen den radjusterade streckkoden som en PNG‑fil.

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Du har nu två distinkta PNG‑filer:

* `DatabarCols4.png` – 4 kolumner, 1 rad.  
* `DatabarRows3.png` – 1 kolumn, 3 rader.

Båda bilderna är redo för omedelbar användning i applikationer, rapporter eller tryckta etiketter.

## Hur man genererar barcode PNG‑filer i C# med anpassade dimensioner

Mönstret som visas ovan kan återanvändas för vilken DataBar‑variant som helst eller andra symbologier som stöds av biblioteket. Här är en kompakt mall som du kan kopiera‑klistra in i en verktygsklass:

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Anropa metoden så här:

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**Särskilda fall att beakta**

* **Data length** – DataBar Expanded Stacked kan koda upp till 74 numeriska tecken. Att överskrida denna gräns kastar ett undantag. Validera indata­längden innan du anropar generatorn.  
* **Invalid dimensions** – Biblioteket begränsar kolumner till 1‑4 och rader till 1‑3 för denna symbologi. Att ange värden utanför dessa intervall kommer att ignoreras eller orsaka ett fel.  
* **Image DPI** – Om du behöver högre upplösning för utskrift, sätt `generator.Parameters.ImageResolution` innan du sparar.

## Förväntat resultat

När du öppnar `DatabarCols4.png` eller `DatabarRows3.png` bör du se en tydlig, högkontrast DataBar‑streckkod. Skannar du bilden med en GS1‑kompatibel scanner returneras den ursprungliga texten "Databar Expanded Stacked long".

![Exempel på DataBar Expanded Stacked‑streckkod sparad som PNG med barcode generator C#](image.png)

*Alt‑text: Exempel på DataBar Expanded Stacked‑streckkod sparad som PNG med barcode generator C#*

## Slutsats

Denna handledning visade hur en **barcode generator C#** kan användas för att **skapa DataBar‑streckkoder** och **generera barcode PNG**‑filer med anpassade rad‑ och kolumninställningar. Genom att följa de sex stegen—initiera generatorn, konfigurera kolumner eller rader och spara som PNG—får du produktionsklara bilder som är lämpliga för lagersystem, biljettförsäljning eller någon situation som kräver pålitlig streckkodsgenerering.

Nästa steg kan vara att utforska:

* Lägga till färg eller bakgrundsbilder i PNG‑filen (fortfarande kompatibel med de flesta skannrar).  
* Använda andra symbologier som QR, Code 128 eller PDF417 via samma `BarcodeGenerator`‑API.  
* Bädda in den genererade PNG‑filen direkt i ASP.NET Core MVC‑vyer eller Blazor‑komponenter.

Känn dig fri att experimentera med olika datasträngar, dimensioner och bildformat (t.ex. JPEG, BMP). Samma mönster gäller, vilket gör **barcode generator C#** till ett mångsidigt verktyg i alla .NET‑utvecklares verktygslåda. Lycka till med kodningen!

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger vidare på teknikerna som demonstrerats i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [Generera streckkod C# – Skapa DataBar‑streckkod](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator‑exempel – Bygg DataBar‑bild i C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator‑exempel i C# – Ställ in kolumner, rader & exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}