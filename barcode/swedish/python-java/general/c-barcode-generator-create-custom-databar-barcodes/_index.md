---
category: general
date: 2026-08-19
description: C#-barcodegeneratorhandledning visar hur man genererar DataBar Expanded
  Stacked-streckkoder, anpassar streckkodens storlek och konfigurerar rader och kolumner.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: sv
lastmod: 2026-08-19
og_description: C#-barcodegeneratorhandledning lär dig hur du genererar DataBar-streckkoder,
  anpassar storlek och konfigurerar rader och kolumner för exakt resultat.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: C#-streckkodsgenerator – steg‑för‑steg guide för anpassade DataBar-streckkoder
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: 'C#-streckkodsgenerator: skapa anpassade DataBar-streckkoder'
url: /sv/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# streckkodsgenerator: skapa anpassade DataBar-streckkoder

Om du behöver en **c# barcode generator** som kan producera DataBar Expanded Stacked‑symboler, visar den här guiden exakt hur du genererar streckkods‑bilder med anpassade rader och kolumner. Du kommer att lära dig att konfigurera databar‑parametrar, justera streckkodsstorlek och spara resultatet som PNG‑filer.

Att generera streckkoder programatiskt tar bort manuella designsteg och garanterar konsekvent resultat över plattformar. I den här handledningen kommer du att:

* Installera och referera Aspose.BarCode för .NET‑biblioteket (eller ett kompatibelt paket).
* Skapa en streckkodsgenerator för DataBar Expanded Stacked‑symbologi.
* **How to generate barcode** bilder med specifika kolumn‑ och radinställningar.
* **Customize barcode size** genom att kontrollera DataBar‑rader och -kolumner.
* **Configure databar parameters** såsom text, format och bildkvalitet.

## Förutsättningar

* .NET 6.0 SDK eller senare installerat.
* En C#‑utvecklingsmiljö (Visual Studio, VS Code, Rider, etc.).
* NuGet‑paketet `Aspose.BarCode` (eller ett motsvarande bibliotek som tillhandahåller `BarcodeGenerator`, `EncodeTypes` och `BarCodeImageFormat`).

Add the package with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## Använda C# streckkodsgenerator för att skapa DataBar‑streckkoder

Följande avsnitt guidar dig genom varje steg. Huvudfokus ligger på **c# barcode generator**‑API:et, men samma mönster gäller för andra streckkodsbibliotek som exponerar liknande egenskaper.

### Steg 1: Initiera streckkodsgeneratorn med exempeltext

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Varför detta steg?*  
`BarcodeGenerator` är ingångspunkten för alla streckkodsskapande‑uppgifter. Genom att ange enum‑värdet `EncodeTypes.DatabarExpandedStacked` talar du om för biblioteket vilken symbologi som ska användas, medan textargumentet blir det mänskligt läsbara värdet som kodas i symbolen.

### Steg 2: Ställ in antalet kolumner (standardrader används)

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*Varför detta steg?*  
DataBar Expanded Stacked‑symboler består av staplade linjära element. Genom att justera egenskapen `Columns` ändras den horisontella densiteten, vilket gör att du kan passa längre datasträngar utan att öka den totala höjden. Detta anpassar direkt **customizes barcode size**.

### Steg 3: Spara streckkodsbilden som använder fyra kolumner

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*Vad du ser:*  
Den sparade bilden `DatabarCols4.png` visar en DataBar‑streckkod som är bredare än standard eftersom den innehåller fyra kolumner. Du kan öppna filen i valfri bildvisare för att verifiera resultatet.

### Steg 4: Åter‑initiera generatorn för en ny konfiguration

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Varför åter‑initiera?*  
Att ändra egenskapen `Rows` samtidigt som den tidigare kolumninställningen behålls kan leda till en oväntad kombination. Genom att börja med en ny instans säkerställer du att endast den avsedda parametern (`Rows`) påverkar nästa bild.

### Steg 5: Ställ in antalet rader (standardkolumner används)

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*Varför detta steg?*  
Egenskapen `Rows` styr vertikal stapling. Att öka antalet rader gör streckkoden högre, vilket kan vara användbart när horisontellt utrymme är begränsat men vertikalt finns gott om plats. Detta är ett annat sätt att **customize barcode size**.

### Steg 6: Spara streckkodsbilden som använder tre rader

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*Resultat:*  
`DatabarRows3.png` visar en högre streckkod med tre staplade rader, vilket demonstrerar hur **configure databar parameters** påverkar det visuella utseendet.

## Fullt körbart exempel

Nedan finns ett komplett program som du kan kopiera, klistra in och köra. Det innehåller alla importeringar, felhantering och kommentarer för tydlighet.

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**Förväntat resultat**

Kör programmet så skapas två PNG‑filer:

* `DatabarCols4.png` – en bred DataBar‑streckkod med fyra kolumner.
* `DatabarRows3.png` – en hög DataBar‑streckkod med tre rader.

Öppna bilderna för att bekräfta att streckkodens dimensioner matchar de konfigurerade parametrarna.

## Vanliga frågor och hantering av kantfall

| Question | Answer |
|----------|--------|
| *Vad händer om jag behöver både anpassade rader **och** kolumner?* | Ange `Rows` **och** `Columns` på samma `BarcodeGenerator`‑instans innan du anropar `Save`. Biblioteket kombinerar båda värdena för att skapa ett rutnät med den begärda storleken. |
| *Kan jag ändra bildformatet?* | Ja. Ersätt `BarCodeImageFormat.Png` med `Jpeg`, `Bmp` eller `Gif` för att passa ditt arbetsflöde. |
| *Vad händer när texten är längre än vad symbolen kan rymma?* | Generatorn kastar ett `ArgumentException`. Förkorta texten eller öka `Columns`/`Rows` för att ge mer kapacitet. |
| *Finns det ett sätt att ange DPI eller bildupplösning?* | Använd `generator.Parameters.ImageResolution` för att ange önskad DPI innan du sparar. Detta anpassar ytterligare **customizes barcode size** för högupplöst utskrift. |
| *Stöder biblioteket andra DataBar‑varianter?* | Ja. Ersätt `EncodeTypes.DatabarExpandedStacked` med `DatabarExpanded`, `DatabarLimited` osv., samtidigt som du behåller samma parameterstruktur. |

## Tips för pålitlig streckkodsgenerering

* **Pro tip:** Verifiera alltid den genererade bilden med en scanner eller en mobilapp innan du distribuerar den i produktion.  
* **Watch out for:** Null‑ eller tomma utdatamappar—`Save` kastar ett undantag om sökvägen inte finns. Skapa mappen programatiskt om det behövs.  
* **Performance note:** Återanvändning av en enda `BarcodeGenerator`‑instans och endast ändring av `Rows` eller `Columns` kan minska objekt‑skapande‑kostnaden när många streckkoder genereras i en loop.

## Slutsats

Du vet nu hur du använder en **c# barcode generator** för att **create databar barcode**‑bilder, **customize barcode size** och **configure databar parameters** såsom rader och kolumner. Genom att justera dessa inställningar kan du anpassa streckkoder till alla layoutkrav samtidigt som du upprätthåller skanningspålitlighet.

Nästa steg är att utforska relaterade ämnen som **how to generate barcode**‑PDF:er, inbäddning av streckkoder i rapporter eller byte till andra symbologier (QR, Code‑128 osv.). Experimentera med olika `Rows`, `Columns` och bildupplösningar för att hitta den optimala konfigurationen för ditt specifika användningsområde.

---

## Vad bör du lära dig härnäst?

Följande handledningar täcker närbesläktade ämnen som bygger på teknikerna som demonstreras i den här guiden. Varje resurs innehåller kompletta fungerande kodexempel med steg‑för‑steg‑förklaringar för att hjälpa dig bemästra ytterligare API‑funktioner och utforska alternativa implementationsmetoder i dina egna projekt.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [Generate Aspose.BarCode Databar barcode using .NET API – Row & Column Configuration](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}