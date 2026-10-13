---
category: general
date: 2026-10-02
description: Lär dig hur du ställer in kolumner och rader i en C#‑streckkodsgenerator
  för att skapa DataBar‑streckkoder. Steg‑för‑steg‑guide med komplett kod.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: sv
lastmod: 2026-10-02
og_description: C#-barcodegeneratorguide – lär dig hur du ställer in kolumner och
  rader för att skapa DataBar-streckkoder med kompletta kodexempel.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'C#-streckkodsgenerator: ange kolumner och rader för DataBar-streckkoder'
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: Hur man använder en C#‑streckkodsgenerator för att skapa DataBar‑streckkoder
  med anpassade kolumner och rader
url: /sv/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man använder en C# streckkodsgenerator för att skapa DataBar-streckkoder med anpassade kolumner och rader

Om du behöver en **c# barcode generator** som kan producera DataBar-streckkoder med exakta kolumn- och radkonfigurationer, visar den här handledningen exakt hur. Du kommer att se varför justering av kolumner och rader är viktigt, och du får ett komplett, färdigt‑att‑köra exempel som skapar både en 4‑kolumns och en 3‑rad DataBar Expanded Stacked‑streckkod.

I avsnitten som följer täcker vi:

* Förutsättningarna för att använda Aspose.BarCode for .NET‑biblioteket.
* Hur man ställer in kolumner (`how to set columns`) och rader (`how to set rows`) på en DataBar‑streckkod.
* Ett komplett C#‑konsolprogram som du kan kopiera, kompilera och köra.
* Förväntade output‑filer och tips för felsökning.

När du är klar med den här guiden kommer du att kunna **create databar barcode**‑bilder anpassade efter dina layout‑krav.

## Förutsättningar

Innan du börjar, se till att du har:

| Krav | Orsak |
|------|-------|
| .NET 6.0 SDK or later | Tillhandahåller runtime för C#‑koden. |
| Visual Studio 2022 (or any IDE that supports .NET) | Gör projekt‑skapande och felsökning enklare. |
| Aspose.BarCode for .NET NuGet package | Tillhandahåller `BarcodeGenerator`‑klassen som används i exemplen. |
| Write permission to a folder for the output PNG files | Generatorn skriver streckkodsbilderna till disk. |

Install the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Steg 1: Skapa en grundläggande DataBar Expanded Stacked‑streckkod

The first step is to instantiate a **c# barcode generator** with the `EncodeTypes.DatabarExpandedStacked` format. This format is a two‑dimensional DataBar barcode that can encode up to 74 numeric characters.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

The constructor receives two arguments:

* `EncodeTypes.DatabarExpandedStacked` – tells the library which symbology to use.
* `"Databar Expanded Stacked long"` – the text that will be encoded.

## Steg 2: Hur man ställer in kolumner

Columns affect the horizontal density of the DataBar barcode. Increasing the column count makes the barcode wider, which can improve scan reliability on low‑resolution printers.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Varför 4 kolumner?**  
Four columns give a good balance between size and readability for most retail applications. You can experiment with values from 1 to 8; the library will automatically adjust the module width.

## Steg 3: Spara den kolumn‑konfigurerade streckkoden

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

The image is saved as a PNG file, which preserves the crisp edges required for barcode scanners.

## Steg 4: Skapa en separat generator för radkonfiguration

Row configuration works the same way but influences the vertical density. To avoid mixing column and row settings, we create a new generator instance.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Steg 5: Hur man ställer in rader

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**När bör man använda fler rader?**  
Adding rows makes the barcode taller, which can be useful when the printed space is limited horizontally but ample vertically (e.g., on a product label that is taller than it is wide).

## Steg 6: Spara den rad‑konfigurerade streckkoden

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Both PNG files (`DatabarCols4.png` and `DatabarRows3.png`) will appear in the `C:\Barcodes` folder.

## Fullt, körbart exempel

Below is a self‑contained console application that incorporates every step described above. Copy the code into a new .NET console project and run it.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### Vad koden gör

| Avsnitt | Syfte |
|---------|-------|
| **Namespace imports** | Hämtar `Aspose.BarCode` och `Aspose.BarCode.Generation`. |
| **Utdatamapp** | Centraliserar sökvägen så du bara behöver redigera en rad om du flyttar mappen. |
| **Kolumngenerator** | Visar **how to set columns** på en `c# barcode generator`. |
| **Raggenerator** | Visar **how to set rows** på en `c# barcode generator`. |
| **Spara‑anrop** | Skriver PNG‑filerna till disk, vilket gör dem redo för skanning eller inkludering i rapporter. |
| **Konsolutdata** | Ger omedelbar återkoppling, användbart under utveckling. |

## Förväntat resultat

After running the program you should see two PNG files:

* **DatabarCols4.png** – en bredare streckkod som visar fyra kolumner.
* **DatabarRows3.png** – en högre streckkod som visar tre rader.

Both images contain the text *“Databar Expanded Stacked long”* encoded in the DataBar Expanded Stacked symbology. You can open them in any image viewer or feed them to a barcode scanner to verify readability.

## Vanliga fallgropar och hur man undviker dem

| Problem | Orsak | Lösning |
|---------|-------|---------|
| **File‑access exception** | The output folder does not exist or you lack write permission. | Create the folder manually or run the program with elevated privileges. |
| **Incorrect column/row values** | The library only accepts values 1‑8 for columns and 1‑4 for rows. | Validate the values before assigning, e.g., `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | The generated image is too small for the scanner’s resolution. | Increase the `ImageHeight` or `ImageWidth` using `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | The encoded text exceeds the maximum length for the chosen DataBar variant. | Use a shorter string or switch to `EncodeTypes.DatabarExpanded` if you need more capacity. |

## Pro‑tips

* **Cache the generator** – If you need to create many barcodes with the same column/row settings, reuse the same `BarcodeGenerator` instance and only change the `CodeText` property.
* **Batch processing** – Loop over a collection of product identifiers, set `generator.CodeText` inside the loop, and call `Save` with a unique filename each iteration.
* **Performance** – For high‑volume scenarios, disable anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) to speed up image generation without affecting scan quality.

## Nästa steg

Now that you know **how to set columns** and **how to set rows** with a **c# barcode generator**, you might want to explore:

* **Adding human‑readable text** below the barcode (`generator.Parameters.Barcode.CodeTextLocation`).
* **Changing colors** (`generator.Parameters.Image.ForegroundColor` and `BackgroundColor`).
* **Generating other DataBar variants** such as `DatabarLimited` or `DatabarExpanded`.
* **Embedding barcodes in PDF reports** using Aspose.PDF.

Each of these topics builds on the foundation covered here and helps you create richer, production‑ready barcode solutions.

---

*Happy coding! If you run into any issues, feel free to leave a comment or check the Aspose.BarCode documentation for deeper API details.*

## Vad bör du lära dig härnäst?

The following tutorials cover closely related topics that build on the techniques demonstrated in this guide. Each resource includes complete working code examples with step-by-step explanations to help you master additional API features and explore alternative implementation approaches in your own projects.

- [Hur man ställer in streckkodskolumner och -rader med C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Barcode Generator‑exempel i C# – Ställ in kolumner, rader & exportera bild](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Hur man använder en streckkodsgenerator C# för att skapa DataBar‑streckkoder](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}