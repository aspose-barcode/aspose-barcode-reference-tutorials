---
category: general
date: 2026-10-02
description: Naučte se, jak nastavit sloupce a řádky v generátoru čárových kódů v
  C# pro vytvoření DataBar čárových kódů. Podrobný návod krok za krokem s kompletním
  kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: cs
lastmod: 2026-10-02
og_description: Průvodce generátorem čárových kódů v C# – naučte se nastavit sloupce
  a řádky pro tvorbu DataBar čárových kódů s kompletními ukázkami kódu.
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: 'Generátor čárových kódů v C#: nastavte sloupce a řádky pro DataBar čárové
  kódy'
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
title: Jak použít generátor čárových kódů v C# k vytvoření DataBar čárových kódů s
  vlastními sloupci a řádky
url: /cs/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generátor čárových kódů v C# k vytvoření DataBar čárových kódů s vlastními sloupci a řádky

Pokud potřebujete **c# barcode generator**, který dokáže vytvářet DataBar čárové kódy s přesnými konfiguracemi sloupců a řádků, tento tutoriál vám přesně ukáže, jak na to. Uvidíte, proč je důležité upravovat sloupce a řádky, a získáte kompletní, připravený příklad, který vytvoří jak 4‑sloupcový, tak 3‑řádkový DataBar Expanded Stacked čárový kód.

V následujících sekcích se zabýváme:

* Požadavky pro použití knihovny Aspose.BarCode pro .NET.
* Jak nastavit sloupce (`how to set columns`) a řádky (`how to set rows`) u DataBar čárového kódu.
* Úplný C# konzolový program, který můžete zkopírovat, zkompilovat a spustit.
* Očekávané výstupní soubory a tipy pro odstraňování problémů.

Na konci tohoto průvodce budete schopni **create databar barcode** obrázky přizpůsobené vašim požadavkům na rozložení.

## Požadavky

Než začnete, ujistěte se, že máte:

| Požadavek | Důvod |
|-------------|--------|
| .NET 6.0 SDK or later | Poskytuje runtime pro C# kód. |
| Visual Studio 2022 (or any IDE that supports .NET) | Umožňuje snadnější vytvoření projektu a ladění. |
| Aspose.BarCode for .NET NuGet package | Poskytuje třídu `BarcodeGenerator` používanou v příkladech. |
| Write permission to a folder for the output PNG files | Generátor zapisuje obrázky čárových kódů na disk. |

Install the Aspose.BarCode package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvořte základní DataBar Expanded Stacked čárový kód

Prvním krokem je vytvořit instanci **c# barcode generator** s formátem `EncodeTypes.DatabarExpandedStacked`. Tento formát je dvourozměrný DataBar čárový kód, který může kódovat až 74 číselných znaků.

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

* `EncodeTypes.DatabarExpandedStacked` – říká knihovně, kterou symboliku použít.
* `"Databar Expanded Stacked long"` – text, který bude zakódován.

## Krok 2: Jak nastavit sloupce

Sloupce ovlivňují horizontální hustotu DataBar čárového kódu. Zvýšení počtu sloupců rozšíří čárový kód, což může zlepšit spolehlivost skenování na tiskárnách s nízkým rozlišením.

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**Proč 4 sloupce?**  
Čtyři sloupce poskytují dobrý poměr mezi velikostí a čitelností pro většinu maloobchodních aplikací. Můžete experimentovat s hodnotami od 1 do 8; knihovna automaticky upraví šířku modulu.

## Krok 3: Uložte čárový kód nastavený na sloupce

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

Obrázek je uložen jako PNG soubor, který zachovává ostré hrany potřebné pro skenery čárových kódů.

## Krok 4: Vytvořte samostatný generátor pro nastavení řádků

Nastavení řádků funguje stejně, ale ovlivňuje vertikální hustotu. Abychom se vyhnuli míchání nastavení sloupců a řádků, vytvoříme novou instanci generátoru.

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## Krok 5: Jak nastavit řádky

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**Kdy použít více řádků?**  
Přidání řádků prodlouží čárový kód, což může být užitečné, když je tiskový prostor omezen horizontálně, ale dostatek místa vertikálně (např. na štítku produktu, který je vyšší než široký).

## Krok 6: Uložte čárový kód nastavený na řádky

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

Oba PNG soubory (`DatabarCols4.png` a `DatabarRows3.png`) se objeví ve složce `C:\Barcodes`.

## Kompletní, spustitelný příklad

Níže je samostatná konzolová aplikace, která zahrnuje všechny kroky popsané výše. Zkopírujte kód do nového .NET konzolového projektu a spusťte jej.

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

### Co kód dělá

| Sekce | Účel |
|---------|---------|
| **Namespace imports** | Načte `Aspose.BarCode` a `Aspose.BarCode.Generation`. |
| **Output directory** | Centralizuje cestu, takže pokud přesunete složku, stačí upravit jen jeden řádek. |
| **Column generator** | Ukazuje **how to set columns** na `c# barcode generator`. |
| **Row generator** | Ukazuje **how to set rows** na `c# barcode generator`. |
| **Save calls** | Zapíše PNG soubory na disk, čímž je připraví ke skenování nebo zahrnutí do reportů. |
| **Console output** | Poskytuje okamžitou zpětnou vazbu, užitečnou během vývoje. |

## Očekávaný výstup

Po spuštění programu byste měli vidět dva PNG soubory:

* **DatabarCols4.png** – širší čárový kód odrážející čtyři sloupce.
* **DatabarRows3.png** – vyšší čárový kód odrážející tři řádky.

Oba obrázky obsahují text *„Databar Expanded Stacked long“* zakódovaný v symbolice DataBar Expanded Stacked. Můžete je otevřít v libovolném prohlížeči obrázků nebo předat skeneru čárových kódů k ověření čitelnosti.

## Časté problémy a jak se jim vyhnout

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **File‑access exception** | Výstupní složka neexistuje nebo nemáte oprávnění k zápisu. | Vytvořte složku ručně nebo spusťte program s vyššími oprávněními. |
| **Incorrect column/row values** | Knihovna akceptuje pouze hodnoty 1‑8 pro sloupce a 1‑4 pro řádky. | Ověřte hodnoty před přiřazením, např. `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`. |
| **Barcode not scanning** | Vygenerovaný obrázek je příliš malý pro rozlišení skeneru. | Zvyšte `ImageHeight` nebo `ImageWidth` pomocí `generator.Parameters.Image.Height` / `...Width`. |
| **Text truncation** | Zakódovaný text překračuje maximální délku pro zvolený DataBar variant. | Použijte kratší řetězec nebo přepněte na `EncodeTypes.DatabarExpanded`, pokud potřebujete větší kapacitu. |

## Profesionální tipy

* **Cache the generator** – Pokud potřebujete vytvořit mnoho čárových kódů se stejným nastavením sloupců/řádků, znovu použijte stejnou instanci `BarcodeGenerator` a změňte pouze vlastnost `CodeText`.
* **Batch processing** – Projděte kolekci identifikátorů produktů, nastavte `generator.CodeText` uvnitř smyčky a zavolejte `Save` s unikátním názvem souboru v každé iteraci.
* **Performance** – Pro scénáře s vysokým objemem vypněte anti‑aliasing (`generator.Parameters.Image.AntiAlias = false`) pro zrychlení generování obrázků, aniž by to ovlivnilo kvalitu skenování.

## Další kroky

Nyní, když víte **how to set columns** a **how to set rows** s **c# barcode generator**, můžete chtít prozkoumat:

* **Adding human‑readable text** pod čárovým kódem (`generator.Parameters.Barcode.CodeTextLocation`).
* **Changing colors** (`generator.Parameters.Image.ForegroundColor` a `BackgroundColor`).
* **Generating other DataBar variants** jako `DatabarLimited` nebo `DatabarExpanded`.
* **Embedding barcodes in PDF reports** pomocí Aspose.PDF.

Každé z těchto témat staví na základech zde popsaných a pomáhá vám vytvořit bohatší, připravená řešení čárových kódů pro produkci.

---

*Šťastné programování! Pokud narazíte na jakékoli problémy, neváhejte zanechat komentář nebo si prohlédnout dokumentaci Aspose.BarCode pro podrobnější informace o API.*

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak nastavit sloupce a řádky čárového kódu pomocí C# BarcodeGenerator](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [Příklad generátoru čárových kódů v C# – Nastavit sloupce, řádky a exportovat obrázek](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Jak použít generátor čárových kódů C# k vytvoření DataBar čárových kódů](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}