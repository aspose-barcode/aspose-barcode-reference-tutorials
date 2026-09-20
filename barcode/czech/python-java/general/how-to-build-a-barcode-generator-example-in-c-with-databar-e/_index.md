---
category: general
date: 2026-09-19
description: příklad generátoru čárových kódů v C# ukazující, jak generovat čárový
  kód v C# pomocí Aspose.BarCode pro sloupcové a řádkové rozložení
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate barcode c#
language: cs
lastmod: 2026-09-19
og_description: Příklad generátoru čárových kódů demonstruje, jak v C# generovat čárový
  kód s rozvržením do sloupců a řádků pomocí Aspose.BarCode.
og_image_alt: C# barcode generator example output showing a DataBar Expanded Stacked
  barcode with 4 columns
og_title: příklad generátoru čárových kódů – vytvořte DataBar Expanded Stacked čárové
  kódy v C#
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
title: Jak vytvořit příklad generátoru čárových kódů v C# s DataBar Expanded Stacked
url: /cs/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Příklad generátoru čárových kódů – vytvoření DataBar Expanded Stacked čárových kódů v C#

Pokud potřebujete **příklad generátoru čárových kódů**, který funguje v .NET projektu, tento průvodce vám přesně ukáže, jak generovat čárový kód v C# pomocí knihovny Aspose.BarCode. Uvidíte, jak nakonfigurovat DataBar Expanded Stacked čárový kód pro rozložení založené na sloupcích i na řádcích, a získáte připravený kód, který vytváří PNG obrázky.

Tutoriál pokrývá vše od instalace NuGet balíčku až po uložení finálních obrázků, takže můžete kód zkopírovat do svého řešení bez dalšího výzkumu.

## Co se naučíte

* Jak nainstalovat a odkazovat na Aspose.BarCode v C# projektu.  
* Jak vytvořit **příklad generátoru čárových kódů**, který kóduje dlouhý datový řetězec.  
* Jak nastavit rozložení se 4 sloupci a 3 řádky pro stejný typ čárového kódu.  
* Jak uložit vygenerované obrázky jako PNG soubory.  

Na konci tohoto článku budete mít dva připravené PNG soubory: `ExpandedStackedCols4.png` (čtyři sloupce) a `ExpandedStackedRows3.png` (tři řádky).

## Požadavky

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7.2).  
* Visual Studio 2022, VS Code nebo jakékoli C# IDE, které preferujete.  
* Přístup k internetu pro stažení **Aspose.BarCode** NuGet balíčku.  

Žádné další externí služby nejsou vyžadovány.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz přidá nejnovější stabilní verzi Aspose.BarCode do souboru projektu. Po obnovení balíčku můžete v C# zdrojových souborech odkazovat na jeho jmenné prostory.

## Krok 2: Přidání požadovaných using direktiv

Vytvořte novou C# konzolovou aplikaci (nebo přidejte kód do existujícího projektu) a na začátek souboru vložte následující `using` příkazy:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Tyto direktivy vám umožní přístup ke třídě `BarcodeGenerator` a výčtu `EncodeTypes` používaným v **příkladu generátoru čárových kódů**.

## Krok 3: Vytvoření příkladu generátoru čárových kódů se 4‑sloupcovým rozložením

První část příkladu vytváří DataBar Expanded Stacked čárový kód, který používá čtyřsloupcové uspořádání. Níže uvedený kód následuje přesně kroky z původního úryvku, ale přidává komentáře vysvětlující, proč je každý řádek potřebný.

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

**Proč to funguje**

* `EncodeTypes.DatabarExpandedStacked` říká Aspose.BarCode, aby vygeneroval symbol DataBar Expanded Stacked, který je vhodný pro maloobchodní aplikace.  
* Nastavením `DataBar.Columns` na `4` vynutíte, aby generátor rozdělil symbol do čtyř vertikálních sekcí, což zlepšuje čitelnost na úzkých štítcích.  
* `Save` zapíše čárový kód na disk; argument `BarCodeImageFormat.Png` zajišťuje bezztrátovou kvalitu obrázku.

Spuštěním tohoto bloku se v pracovním adresáři aplikace vytvoří soubor `ExpandedStackedCols4.png`. Soubor obsahuje vysoce rozlišený čárový kód, který lze načíst libovolným standardním DataBar čtečkou.

## Krok 4: Znovu‑inicializace generátoru pro jiné rozložení

Pro demonstraci rozložení založeného na řádcích potřebujete novou instanci `BarcodeGenerator`. Znovu‑inicializace zaručuje, že předchozí nastavení sloupců neovlivní novou konfiguraci.

```csharp
// Step 4.1: Create a new generator with the same data string
generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Long data string");
```

## Krok 5: Nastavení čárového kódu pro použití 3‑řádkového rozložení

API DataBar také podporuje uspořádání po řádcích. Nastavením vlastnosti `Rows` určíte, kolik horizontálních částí bude symbol obsahovat.

```csharp
// Step 5.1: Apply a 3‑row layout
generator.Parameters.Barcode.DataBar.Rows = 3;

// Step 5.2: Save the row‑oriented barcode
generator.Save("ExpandedStackedRows3.png", BarCodeImageFormat.Png);
```

**Proč můžete zvolit řádky místo sloupců**

Řádky jsou užitečné, když je výška štítku omezená, ale šířka dostatečná. Třířádkové rozložení komprimuje čárový kód vertikálně a přitom zachovává požadované množství dat.

## Kompletní zdrojový soubor

Níže je kompletní, samostatný `Program.cs`, který můžete přímo zkompilovat a spustit. Obsahuje jak příklad se sloupci, tak s řádky, takže jedním spuštěním získáte dva PNG soubory.

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

### Očekávaný výstup

Po spuštění programu uvidíte dvě zprávy v konzoli potvrzující vytvoření souborů:

```
Saved ExpandedStackedCols4.png (4‑column layout)
Saved ExpandedStackedRows3.png (3‑row layout)
```

Oba PNG soubory zobrazí DataBar Expanded Stacked čárový kód, který kóduje řetězec `"Long data string"`. Načtením libovolného obrázku standardním čtečkou čárových kódů získáte původní data.

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Mohu změnit formát obrázku?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Tiff` podle vašich požadavků. |
| **Co když je datový řetězec kratší?** | Formát DataBar automaticky upraví velikost symbolu; není nutné měnit nastavení rozložení. |
| **Jak nastavit velikost čárového kódu (šířka/výška)?** | Použijte `generator.Parameters.Image.Width` a `generator.Parameters.Image.Height` před voláním `Save`. |
| **Je možné přidat lidsky čitelný popisek?** | Nastavte `generator.Parameters.Barcode.CodeText` a povolte `generator.Parameters.Barcode.CodeLocation = CodeLocation.Above`. |
| **Jaké verze .NET jsou podporovány?** | Aspose.BarCode podporuje .NET Standard 2.0, .NET 5/6 a .NET Framework 4.6.1+. |

## Profesionální tipy

* **Znovu používejte objekt generátoru pouze když rozložení zůstává stejné.** Vytvoření nové instance pro každé rozložení, jak je ukázáno v krocích 4‑5, zabraňuje neúmyslnému přenosu vlastností.  
* **Ověřte vygenerovaný čárový kód** pomocí `generator.Validate()`, pokud potřebujete zajistit soulad s normami ISO/GS1.  
* **Dávkové zpracování:** Zabalte logiku sloupců a řádků do smyčky, která iteruje přes seznam konfigurací rozložení. Tím se sníží duplikace kódu, když potřebujete mnoho variant.

## Závěr

Tento **příklad generátoru čárových kódů** demonstruje, jak **generovat čárový kód v C#** tak, aby vytvořil jak 4‑sloupcový, tak 3‑řádkový DataBar Expanded Stacked čárový kód. Nyní máte kompletní spustitelný program, pochopení klíčových vlastností (`Columns`, `Rows`) a praktické tipy pro rozšíření řešení.

Dále prozkoumejte související témata, jako je **úprava barev čárových kódů**, **vkládání čárových kódů do PDF dokumentů** nebo **generování QR kódů pomocí Aspose.BarCode**. Každé z těchto témat staví na stejných principech API, které jsou zde popsány.

Neváhejte experimentovat s různými datovými řetězci, formáty obrázků a kombinacemi rozložení. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Příklad generátoru čárových kódů v C# – Nastavení sloupců, řádků a export obrázku](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Generování Aspose.BarCode Databar čárového kódu pomocí .NET API – Konfigurace řádků a sloupců](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [Příklad generátoru čárových kódů v C# – nastavení šířky a výšky](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}