---
category: general
date: 2026-07-15
description: Příklad generátoru čárových kódů v C# ukazující, jak nastavit sloupce,
  jak nastavit řádky a rychle exportovat obrázek čárového kódu. Postupujte podle tohoto
  návodu krok za krokem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to set columns
- how to set rows
- export barcode image
- create barcode image c#
language: cs
lastmod: 2026-07-15
og_description: Příklad generátoru čárových kódů v C# ukazuje, jak nastavit sloupce,
  jak nastavit řádky a exportovat obrázek čárového kódu. Naučte se celý pracovní postup
  během několika minut.
og_image_alt: Screenshot of a barcode generator example showing column and row settings
  in C#
og_title: Příklad generátoru čárových kódů v C# – sloupce, řádky a export obrázku
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  headline: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  type: TechArticle
- description: Barcode generator example in C# showing how to set columns, how to
    set rows, and export barcode image quickly. Follow this step‑by‑step guide.
  name: Barcode Generator Example in C# – Set Columns, Rows & Export Image
  steps:
  - name: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
    text: '**Add colors** – Set `generator.Parameters.Barcode.ForegroundColor` to
      `Color.Blue`.'
  - name: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
    text: '**Encode different data** – Pass a variable string instead of the hard‑coded
      `"Databar Expanded Stacked long"`.'
  - name: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
    text: '**Batch processing** – Loop over a CSV file of product codes, generating
      a PNG for each.'
  - name: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
    text: '**Integrate with a web API** – Expose an endpoint that returns the barcode
      as a base64‑encoded string.'
  type: HowTo
tags:
- barcode
- C#
- image export
title: Příklad generátoru čárových kódů v C# – Nastavení sloupců, řádků a export obrázku
url: /cs/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad generátoru čárových kódů v C# – Kompletní průvodce

Už jste se někdy zamysleli, jak vytvořit **barcode generator example** v C#, který vám umožní upravit sloupce, řádky a poté exportovat výsledek jako obrázek? Nejste sami. Mnoho vývojářů narazí na problém, když potřebují rychlý způsob, jak generovat DataBar Expanded Stacked čárové kódy s vlastními možnostmi rozložení. V tomto tutoriálu tento problém vyřešíme krok za krokem a ukážeme vám **jak nastavit sloupce**, **jak nastavit řádky** a nakonec **exportovat obrázek čárového kódu** – vše s čistým, připraveným k produkci kódem.

Na konci tohoto průvodce budete mít kompletní, spustitelný program, který vytvoří obrázek čárového kódu, upraví jeho rozložení a uloží dva PNG soubory na disk. Žádné tajemné knihovny, žádná skrytá konfigurace – jen čistý C# a spolehlivé barcode SDK.

---

## Požadavky

- **.NET 6.0** (nebo jakákoli novější verze .NET). Kód se také kompiluje s .NET Framework, ale .NET 6+ poskytuje nejnovější vylepšení runtime.
- **barcode generation library**, která podporuje DataBar Expanded Stacked. V příkladech použijeme **Aspose.BarCode for .NET**, který je zdarma v trial verzi a nabízí přímé API.
- Vývojové prostředí – Visual Studio 2022, Rider nebo VS Code budou vyhovovat.
- Oprávnění k zápisu do složky, kde budou PNG soubory uloženy.

Pokud knihovnu ještě nemáte, stáhněte ji z NuGet:

```bash
dotnet add package Aspose.BarCode
```

Tento jediný řádek načte vše, co potřebujete, včetně třídy `BarcodeGenerator` a výčtu `BarCodeImageFormat`, který se použije později.

---

## Krok 1: Nastavení kostry projektu

Vytvořte novou konzolovou aplikaci a přidejte potřebné `using` direktivy:

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum
```

Zde je **kompletní** kostra souboru `Program.cs`:

```csharp
namespace BarcodeDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

> **Tip:** Udržujte metodu `Main` přehlednou; těžkou práci delegujeme později na pomocné metody. To usnadní testování a opětovné použití kódu.

---

## Krok 2: Vytvoření příkladu generátoru čárových kódů

Nyní vytvoříme jádro **barcode generator example**, které vytvoří DataBar Expanded Stacked čárový kód. To je srdce tutoriálu.

```csharp
static BarcodeGenerator CreateGenerator()
{
    // Step 1: Instantiate the generator for DataBar Expanded Stacked.
    // The second argument is the text you want encoded.
    var generator = new BarcodeGenerator(
        EncodeTypes.DatabarExpandedStacked,
        "Databar Expanded Stacked long");

    // Optional: fine‑tune image size or resolution if needed.
    generator.Parameters.Image.Width = 300;
    generator.Parameters.Image.Height = 150;

    return generator;
}
```

Proč to oddělujeme do vlastní metody? Izoluje logiku **barcode generator example**, což ji činí znovupoužitelnou, pokud později potřebujete generovat více čárových kódů s různými daty.

---

## Krok 3: Jak nastavit sloupce

DataBar Expanded Stacked formát může být vykreslen v rozložení orientovaném na sloupce. Ve výchozím nastavení SDK zvolí rozumnou hodnotu, ale často potřebujete odpovídat konkrétní velikosti štítku. Zde je **how to set columns** na čtyři:

```csharp
static void SetColumns(BarcodeGenerator generator, int columns)
{
    // Step 2: Adjust the column count.
    generator.Parameters.Barcode.DataBar.Columns = columns;
}
```

> **Proč jsou sloupce důležité:** Každý sloupec přidává vertikální prostor, což může být klíčové při tisku na úzkých štítcích. Nastavením na `4` získáte vyvážený, čitelný čárový kód bez ztráty spolehlivosti skenování.

V hlavním toku zavoláme tuto metodu:

```csharp
var generator = CreateGenerator();
SetColumns(generator, 4);
```

---

## Krok 4: Jak nastavit řádky

Někdy potřebujete kompaktnější rozložení, zejména pokud tisknete na krátký, široký štítek. Zde přichází na řadu **how to set rows**. Přepnutí z rozložení zaměřeného na sloupce na řádky může zmenšit rozměry čárového kódu.

```csharp
static void SetRows(BarcodeGenerator generator, int rows)
{
    // Step 4: Change the layout to use rows instead of columns.
    generator.Parameters.Barcode.DataBar.Rows = rows;
}
```

Volání vypadá takto:

```csharp
SetRows(generator, 3);
```

> **Poznámka k okrajovému případu:** Nemůžete nastavit současně sloupce *i* řádky – SDK upřednostní řádky, pokud přiřadíte nenulovou hodnotu `Rows`. Proto při přepínání rozložení vymažte druhou vlastnost:

```csharp
generator.Parameters.Barcode.DataBar.Columns = 0; // Disable columns when using rows
```

---

## Krok 5: Export obrázku čárového kódu

Po nastavení rozložení je posledním krokem **exportovat soubory barcode image**. SDK podporuje PNG, JPEG, BMP a další. PNG je bezztrátový a dobře funguje pro většinu tiskáren štítků.

```csharp
static void SaveBarcode(BarcodeGenerator generator, string filePath)
{
    // Step 5: Save the image using the PNG format.
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

Sestavíme vše dohromady v metodě `Main`:

```csharp
static void Main(string[] args)
{
    // 1️⃣ Create the generator (barcode generator example)
    var generator = CreateGenerator();

    // 2️⃣ Set columns and save the first image
    SetColumns(generator, 4);
    string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
    SaveBarcode(generator, colsPath);
    Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");

    // 3️⃣ Switch to rows and save the second image
    SetRows(generator, 3);
    // Clear columns to avoid conflict
    generator.Parameters.Barcode.DataBar.Columns = 0;
    string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
    SaveBarcode(generator, rowsPath);
    Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
}
```

### Očekávaný výstup

Po spuštění programu byste měli v `YOUR_DIRECTORY` vidět dva PNG soubory:

- **DatabarCols4.png** – čárový kód vykreslený se čtyřmi vertikálními sloupci.
- **DatabarRows3.png** – stejná data, ale uspořádaná ve třech horizontálních řádcích.

Oba obrázky budou mít rozměry 300 × 150 px (jak je nastaveno v `CreateGenerator`) a budou připravené k tisku nebo vložení do PDF.

---

## Časté problémy a tipy

| Problém | Proč se to děje | Oprava |
|-------|----------------|-----|
| **Chyby cesty k souboru** | Použití relativní cesty bez správného adresáře může vyvolat `DirectoryNotFoundException`. | Použijte `Path.Combine(Environment.CurrentDirectory, "output", "file.png")` nebo zajistěte, aby složka existovala pomocí `Directory.CreateDirectory`. |
| **Konflikt řádků vs. sloupců** | Nastavení obou vlastností vede SDK k ignorování sloupců. | Explicitně nastavte opačnou vlastnost na `0` při přepínání rozložení. |
| **Není podporován typ čárového kódu** | Ne všechny knihovny čárových kódů podporují DataBar Expanded Stacked. | Ověřte, že vaše verze knihovny obsahuje `EncodeTypes.DatabarExpandedStacked`. |
| **Nízká kvalita obrazu** | Výchozí DPI může být nedostatečné pro vysoce rozlišené tiskárny. | Upravte `generator.Parameters.Image.ResolutionX/Y` na `300` nebo vyšší. |

---

## Rozšíření příkladu generátoru čárových kódů

Nyní, když máte solidní **barcode generator example**, můžete se ptát, co dalšího můžete udělat.

1. **Přidat barvy** – Nastavte `generator.Parameters.Barcode.ForegroundColor` na `Color.Blue`.
2. **Kódovat jiná data** – Předávejte proměnný řetězec místo pevně zakódovaného `"Databar Expanded Stacked long"`.
3. **Dávkové zpracování** – Procházejte CSV soubor s kódy produktů a generujte PNG pro každý.
4. **Integrace s webovým API** – Zveřejněte endpoint, který vrací čárový kód jako base64‑kódovaný řetězec.

Každé z těchto rozšíření následuje stejný vzor: nakonfigurujte instanci `BarcodeGenerator` a poté zavolejte `Save` nebo `Export` podle potřeby.

---

## Závěr

Prošli jsme kompletním **barcode generator example** v C#, který ukazuje **jak nastavit sloupce**, **jak nastavit řádky** a jak **exportovat obrázek čárového kódu**. Kód je samostatný, funguje ihned s Aspose.BarCode a demonstruje osvědčené postupy pro čitelnost a udržovatelnost.

Neváhejte experimentovat – vyměňte řetězec dat, upravte rozměry obrázku nebo přepněte na jinou symbologii čárového kódu. Koncepty, které jste se zde naučili – inicializace generátoru, konfigurace parametrů rozložení a export – platí prakticky pro jakýkoli typ čárového kódu podporovaný SDK.

Máte otázky ohledně vytváření programů pro obrázek čárového kódu v C#, nebo potřebujete pomoc s konkrétní tiskárnou štítků? Zanechte komentář níže a šťastné kódování!

---

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit obrázek čárového kódu DotCode – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Vytvořit obrázek čárového kódu c# – Konfigurace řádků a sloupců Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Vytvořit obrázek čárového kódu C# – Příklad GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}