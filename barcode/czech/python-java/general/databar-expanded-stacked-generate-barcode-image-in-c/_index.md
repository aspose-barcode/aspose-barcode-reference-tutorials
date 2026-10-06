---
category: general
date: 2026-08-15
description: Databar rozšířil generování vrstvených čárových kódů v C#. Naučte se,
  jak vytvořit obrázek čárového kódu a nastavit sloupce a řádky pro rozvržení DataBar.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: cs
lastmod: 2026-08-15
og_description: Databar rozšířil generování vrstvených čárových kódů v C#. Postupujte
  podle tohoto krok‑za‑krokem průvodce a efektivně generujte obrázky čárových kódů,
  nastavujte sloupce a řádky.
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar expanded stacked – vytvořte obrázek čárového kódu v C#
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 'Databar expanded stacked: vytvořit obrázek čárového kódu v C#'
url: /cs/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked: generování obrázku čárového kódu v C#

Pokud potřebujete v C# vygenerovat obrázek čárového kódu **databar expanded stacked**, tento návod vám přesně ukáže **jak generovat čárové kódy** s vlastními rozvrženími sloupců a řádků. Uvidíte, jak nastavit sloupce, jak nastavit řádky a jak uložit vzniklé obrázky, aniž byste opustili IDE.

Návod pokrývá:

* Vytvoření generátoru čárových kódů pro symbologii **databar expanded stacked**.  
* Nastavení rozvržení s 4 sloupci a 3 řádky.  
* Uložení každé konfigurace jako soubor PNG.  
* Tipy pro zpracování okrajových případů, jako jsou neplatné počty sloupců.

Externí dokumentace není vyžadována; kompletní spustitelný příklad je zahrnut.

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="databar expanded stacked čárový kód vygenerovaný v C#" }

## Kroky generování čárového kódu Databar expanded stacked

### 1. Instalace knihovny Aspose.BarCode

Kód používá knihovnu **Aspose.BarCode for .NET**, která poskytuje třídu `BarcodeGenerator`. Nainstalujte NuGet balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

Po instalaci balíčku přidejte požadovaný jmenný prostor na začátek souboru:

```csharp
using Aspose.BarCode.Generation;
```

### 2. Vytvoření generátoru čárových kódů pro **databar expanded stacked**

Generátor je vstupním bodem pro všechny operace s čárovými kódy. Musíte zadat symbologii (`EncodeTypes.DatabarExpandedStacked`) a text, který se má kódovat.

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*Proč je to důležité:* Výčtový typ `EncodeTypes` říká knihovně, který formát čárového kódu má vytvořit. Použití **databar expanded stacked** zajišťuje, že výsledný obrázek odpovídá specifikaci GS1 DataBar pro vrstvená rozvržení.

### 3. Jak nastavit sloupce pro DataBar

Vlastnost `Columns` určuje, kolik vertikálních modulů se objeví ve vrstveném čárovém kódu. Platné hodnoty jsou 2, 3 nebo 4. Nastavení sloupců ovlivňuje šířku čárového kódu a množství dat, která může uložit.

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**Tip:** Pokud se pokusíte přiřadit hodnotu mimo povolený rozsah, knihovna vyhodí `ArgumentException`. Vždy validujte vstup, když uživatelům umožňujete výběr sloupců.

### 4. Uložení obrázku čárového kódu se 4 sloupci

Uložení obrázku vytvoří soubor, který můžete vložit do reportů, faktur nebo mobilních aplikací. Metoda `Save` přijímá cestu k souboru a formát obrázku.

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

Po zápisu souboru jej můžete otevřít v libovolném prohlížeči obrázků a ověřit, že vzor **databar expanded stacked** je zobrazen správně.

### 5. Jak nastavit řádky pro DataBar

Řádky přidávají druhý rozměr k vrstvenému rozvržení, což umožňuje kódovat více dat bez rozšiřování šířky čárového kódu. Výchozí hodnota vlastnosti `Rows` je 1; můžete ji zvýšit až na 3 pro variantu expanded stacked.

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**Proč jsou řádky důležité:** Zvýšení počtu řádků snižuje celkovou šířku při zachování kapacity dat, což je užitečné pro úzké štítky nebo prostor na mobilních obrazovkách.

### 6. Uložení obrázku čárového kódu se 3 řádky

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

Nyní máte dva soubory PNG – jeden s rozvržením 4 sloupců a druhý s rozvržením 3 řádků – oba používají symbologii **databar expanded stacked**.

### 7. Kompletní příklad v C# pro generování obrázku čárového kódu

Spojením všech kroků získáte samostatný program, který můžete zkopírovat do konzolové aplikace:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**Očekávaný výstup**

Spuštěním programu se vypíše:

```
4‑column barcode saved.
3‑row barcode saved.
```

a vytvoří dva soubory PNG v `YOUR_DIRECTORY`. Otevřete soubory a ověřte, že každý obrázek zobrazuje platný čárový kód **databar expanded stacked**.

## Časté úskalí a praktické tipy

* **Existence adresáře** – `Save` nevytváří chybějící složky. Ujistěte se, že `YOUR_DIRECTORY` existuje, nebo před uložením použijte `Directory.CreateDirectory`.
* **Limity sloupců** – Hodnoty jiné než 2, 3 nebo 4 vyvolají výjimku. Chraňte se před chybami uživatelského vstupu jednoduchou kontrolou rozsahu:

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **Limity řádků** – Varianta expanded stacked podporuje až 3 řádky. Nastavení `Rows` na 0 nebo na hodnotu větší než 3 také vyvolá výjimku.
* **Formát obrázku** – `BarCodeImageFormat.Png` poskytuje bezztrátovou kvalitu, což je ideální pro tisk. `Jpeg` použijte jen tehdy, když je velikost souboru hlavní prioritou.

## Další kroky

Nyní, když víte **jak generovat čárové kódy** s vlastními konfiguracemi sloupců a řádků, můžete:

* Integrovat generátor do webového API, které bude na vyžádání poskytovat obrázky čárových kódů.  
* Kombinovat čárový kód s knihovnami pro generování PDF a vložit jej do faktur.  
* Experimentovat s dalšími variantami DataBar (`DatabarExpanded`, `DatabarLimited`) pomocí stejného objektu `Parameters.Barcode.DataBar`.

Pro podrobnější přizpůsobení – například změnu barvy čáry, přidání lidsky čitelného textu nebo aplikaci překryvů QR‑kódu – se podívejte do dokumentace Aspose.BarCode k vlastnostem `BarcodeGenerator`.

---

Podle tohoto návodu jste zvládli workflow **databar expanded stacked**, naučili se **jak nastavit sloupce**, **jak nastavit řádky** a vytvořili dva odlišné obrázky čárových kódů připravené k produkčnímu použití. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vygenerovat obrázek čárového kódu – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Vytvořit obrázek DotCode čárového kódu – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Jak generovat čárový kód – jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}