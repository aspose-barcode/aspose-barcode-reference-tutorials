---
category: general
date: 2026-10-21
description: Vygenerujte obrázek rozšířeného vrstveného databar čárového kódu v C#
  pomocí BarcodeGenerator. Postupujte podle tohoto krok‑za‑krokem průvodce, abyste
  vytvořili obrázky čárových kódů, přizpůsobili řádky a sloupce a exportovali soubory
  PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: cs
lastmod: 2026-10-21
og_description: Vygenerujte rozšířený vrstvený datový čárový kód v C# s tímto návodem.
  Naučte se používat BarcodeGenerator, nastavit řádky a sloupce a ukládat PNG obrázky.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Vytvořte rozšířený vrstvený databar čárový kód v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vygenerovat rozšířený databar vrstvený čárový kód v C#
url: /cs/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat rozšířený databar stacked čárový kód v C#

Pokud potřebujete v C# vygenerovat **databar expanded stacked** čárový kód, tento návod vám ukáže jak. Symbolika databar expanded stacked je ideální pro kódování velkého množství dat v kompaktní podobě a obrázek můžete vytvořit pomocí několika řádků kódu. Také se naučíte, jak **generovat obrázky čárových kódů** v různých formátech a přizpůsobit řádky nebo sloupce tak, aby vyhovovaly vašemu skenovacímu prostředí.

Tento tutoriál pokrývá vše, co potřebujete k zahájení výroby databar čárových kódů: instalaci požadované knihovny, přípravu výstupní složky, vytvoření čárového kódu s vlastními řádky nebo sloupci a uložení výsledku jako PNG soubor. Na konci budete schopni **vytvořit obrázky databar čárových kódů** programově a přizpůsobit kód pro jiné formáty obrázků nebo běhové scénáře.

## Požadavky

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Core 3.1 a .NET Framework 4.7+)
* Vývojové prostředí jako Visual Studio 2022, Visual Studio Code nebo Rider
* Přístup k internetu pro instalaci NuGet balíčku **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Tip:** Pokud používáte CI/CD pipeline, přidejte odkaz na NuGet balíček do souboru projektu, aby byly sestavení reprodukovatelné.

## Instalace knihovny Barcode Generator C# 

Příklad používá knihovnu Aspose.BarCode, která poskytuje třídu `BarcodeGenerator` a výčtový typ `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi do vašeho projektu. Po instalaci můžete importovat jmenný prostor ve svých C# souborech:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Připravte výstupní složku

Spolehlivá cesta k souboru zabraňuje chybám za běhu, když se knihovna pokouší zapsat obrázek. Následující kód vytvoří adresář, pokud neexistuje:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Proč je to důležité:** Pokus o uložení do neexistujícího adresáře vyvolá `IOException`. Vytvoření složky předem činí kód odolným jak pro lokální vývoj, tak pro produkční prostředí.

## Generování obrázku databar expanded stacked čárového kódu

### Základní generování čárového kódu

Nejjednodušší způsob, jak vygenerovat obrázek **databar expanded stacked**, je vytvořit instanci `BarcodeGenerator` s požadovanou hodnotou `EncodeTypes` a jednoduchým textovým obsahem.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Spuštěním úryvku se vytvoří soubor `DatabarBasic.png` ve složce *Barcodes*. Obrázek obsahuje standardní symbol databar expanded stacked s výchozím rozložením (4 sloupce × 4 řádky).

### Přizpůsobení sloupců – vytvoření databar čárového kódu se 4 sloupci

Počet sloupců můžete řídit pomocí vlastnosti `Parameters.Barcode.DataBar.Columns`. Následující příklad vytvoří čárový kód s **4 sloupci**, přičemž zachová výchozí počet řádků.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

Výsledný soubor, **DatabarCols4.png**, vypadá takto:

![Databar expanded stacked čárový kód se 4 sloupci](databar_cols4.png "Databar expanded stacked čárový kód se 4 sloupci – vygenerováno v C#")

*Text alternativního obrázku (og_image_alt):* **Ukázkový obrázek databar expanded stacked čárového kódu vygenerovaný v C#** – to splňuje SEO požadavek na alternativní text obrázku.

### Přizpůsobení řádků – vytvoření databar čárového kódu se 3 řádky

Podobně můžete upravit počet řádků pomocí `Parameters.Barcode.DataBar.Rows`. Níže uvedený kód vygeneruje čárový kód s **3 řádky** a výchozím počtem sloupců (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

Soubor **DatabarRows3.png** obsahuje symbol databar expanded stacked, který je vertikálně o něco kratší, což může být užitečné pro štítky s omezeným prostorem.

### Export do jiných formátů

Pokud potřebujete jiný typ obrázku (např. JPEG, BMP nebo SVG), nahraďte `BarCodeImageFormat.Png` odpovídající hodnotou výčtu:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Knihovna také podporuje vektorové formáty jako SVG, které jsou ideální pro tisk ve vysokém rozlišení.

## Pokročilé scénáře

### Ukládání do paměťového proudu

Někdy chcete vložit čárový kód přímo do webové odpovědi nebo PDF, aniž byste se dotkli souborového systému. Použijte `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Zpracování neplatného vstupu

`BarcodeGenerator` ověřuje vstupní data vůči zvolené symbolice. Pokud data obsahují zakázané znaky, je vyvolána `ArgumentException`. Zabalte kód generování do bloku try‑catch, aby se zobrazila přátelská chybová zpráva:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Škálování obrázku čárového kódu

Můžete změnit velikost obrázku, aniž byste měnili kódovaná data, nastavením `Parameters.Image.Width` a `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Škálování je užitečné, když čárový kód musí splňovat konkrétní požadavek na DPI pro skenery.

## Kompletní funkční příklad

Níže je kompletní, připravená ke spuštění konzolová aplikace, která demonstruje všechny probírané kroky:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Očekávaný výstup**


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak nastavit sloupce pro Databar Expanded Stacked čárový kód – kompletní C# návod](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Jak vytvořit příklad generátoru čárových kódů v C# s DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [databar expanded stacked čárový kód – jak jej vygenerovat a nastavit velikost v C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}