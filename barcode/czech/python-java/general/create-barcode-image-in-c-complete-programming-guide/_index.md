---
category: general
date: 2026-08-09
description: Vytvořte obrázek čárového kódu v C# podle tohoto krok za krokem návodu.
  Naučte se, jak generovat čárový kód, nastavit výšku čárového kódu v pixelech a efektivně
  vytvářet více čárových kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: cs
lastmod: 2026-08-09
og_description: Rychle vytvořte obrázek čárového kódu v C#. Sledujte tento tutoriál,
  abyste se naučili, jak generovat čárový kód, nastavit výšku čárového kódu v pixelech
  a vytvořit více čárových kódů.
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: Vytvořte obrázek čárového kódu v C# – kompletní průvodce pro vývojáře
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Vytvořte obrázek čárového kódu v C# – kompletní programovací průvodce
url: /cs/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu v C# – kompletní programovací průvodce

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento průvodce vám přesně ukáže **jak generovat čárový kód** pomocí knihovny Aspose.BarCode. Uvidíte, jak ovládat **výšku čárového kódu v pixelech**, uložit obrázek a vytvořit **více čárových kódů** bez duplicitního kódu.

Tutoriál pokrývá vše od instalace balíčku po přizpůsobení rozměrů, takže můžete zkopírovat‑vložit připravený příklad, který lze okamžitě spustit, do svého projektu ještě dnes.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* NuGet balíček `Aspose.BarCode` – nainstalujte pomocí  

```bash
dotnet add package Aspose.BarCode
```

Žádné další závislosti nejsou vyžadovány.

## Jak generovat obrázek čárového kódu pomocí BarcodeGenerator v C#

Základní třída pro vytvoření obrázku čárového kódu je `BarcodeGenerator`. Zapouzdřuje typ kódování, datový řetězec a všechny parametry vykreslování.

### Krok 1: Definujte výstupní složku

Vyberte složku, do které budou ukládány vygenerované PNG soubory. Použití absolutní cesty zabraňuje neočekávaným problémům s oprávněními.

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **Proč?** Vytvoření složky programově zajišťuje, že následné volání `Save` uspěje i na novém počítači.

### Krok 2: Vytvořte instanci generátoru čárových kódů

Pro čárový kód DataBar Omnidirectional předávejte `EncodeTypes.DatabarOmniDirectional` a datový řetězec GS1‑128.

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **Poznámka:** Objekt `BarcodeGenerator` je znovupoužitelný; můžete mezi ukládáním měnit jeho parametry a **vytvořit více čárových kódů** ze stejných dat.

### Krok 3: Nastavte společné parametry čárového kódu

Nejčastější vizuální úpravy jsou X‑dimenze (šířka modulu) a výška čárového kódu. Obě jsou vyjádřeny v pixelech.

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **Proč nastavit X‑dimenzi?** Menší X‑dimenze poskytuje vyšší rozlišení, což je důležité, když bude obrázek tištěn nebo zobrazen na obrazovkách s vysokým DPI.

### Krok 4: Uložte první obrázek čárového kódu

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

Soubor `DatabarBarHeight30Pixels.png` nyní obsahuje DataBar Omnidirectional čárový kód vysoký 30 pixelů.

### Krok 5: Upravit výšku čárového kódu v pixelech

Změna výšky nevyžaduje novou instanci `BarcodeGenerator` — stačí upravit parametr.

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### Krok 6: Uložte druhý obrázek čárového kódu

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory s různou **výškou čárového kódu v pixelech**, což ukazuje, jak snadno lze vytvořit různé **obrázky čárových kódů**.

## Dynamické nastavení výšky čárového kódu v pixelech

Často potřebujete sérii čárových kódů s výškami, které odpovídají UI prvkům nebo tištěným štítkům. Následující pomocná metoda abstrahuje změnu výšky:

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

Nyní můžete zavolat `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");` a **vytvořit obrázek čárového kódu** s výškou 45 pixelů v jediném řádku.

## Vytváření více čárových kódů ve smyčce

Když máte kolekci identifikátorů produktů, smyčka `foreach` eliminuje opakovaný kód. Tento příklad ukazuje, jak **vytvořit více čárových kódů** z pole GTIN.

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

Smyčka vytvoří tři PNG soubory, každý s odlišnou hodnotou **výšky čárového kódu v pixelech**. Protože pomocná metoda `SaveBarcodeWithHeight` zapouzdřuje změnu výšky, hlavní smyčka zůstává čistá a soustředěná na data.

### Očekávaný výstup

Po spuštění kompletního příkladu složka `Barcodes` obsahuje:

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

Otevření libovolného PNG zobrazí ostrý DataBar Omnidirectional čárový kód, který lze naskenovat standardními mobilními aplikacemi.

## Časté chyby a tipy pro profesionály

| Problém | Proč k tomu dochází | Jak tomu předejít |
|-------|----------------|-----------------|
| **Špatné EncodeTypes** | Použití 1D typu pro DataBar vytvoří nečitelné obrázky. | Vždy zvolte `EncodeTypes.DatabarOmniDirectional` (nebo jinou variantu DataBar) pro GS1‑128 payloady. |
| **Nedostatečná X‑dimenze** | Velmi nízká X‑dimenze může způsobit, že tenké čáry zmizí na monitorech s nízkým rozlišením. | Udržujte `XDimension.Pixels` ≥ 2 pro zobrazení na obrazovce; pro tisk zvýšte na 3‑4. |
| **Chyby v cestě k souboru** | Relativní cesty se mohou rozpoznat do neočekávaných adresářů. | Používejte `Path.Combine` a `Environment.CurrentDirectory` pro vytvoření absolutních cest. |
| **Přepisování obrázků** | Opakované použití stejného názvu souboru ve smyčce přepíše předchozí výsledky. | Zahrňte do názvu souboru jedinečné identifikátory (např. GTIN nebo časové razítko). |
| **Chybějící NuGet balíček** | Kód se zkompiluje, ale při běhu vyhodí `FileNotFoundException`. | Ověřte, že je nainstalován `Aspose.BarCode` a projekt na něj odkazuje. |

## Kompletní funkční příklad

Níže je kompletní program, který můžete zkopírovat do konzolové aplikace. Obsahuje všechny kroky, pomocné metody a ošetření chyb.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

Spuštěním tohoto programu

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit čárový kód s vlastní výškou – jednorozměrné čárové kódy](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Vytvořit obrázek čárového kódu C# – příklad GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Vytvořit obrázek DotCode čárového kódu – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}