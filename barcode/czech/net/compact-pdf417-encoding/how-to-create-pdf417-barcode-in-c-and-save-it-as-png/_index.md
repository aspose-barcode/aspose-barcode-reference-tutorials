---
category: general
date: 2026-08-22
description: Naučte se, jak vytvořit čárový kód PDF417 v C# pomocí generátoru čárových
  kódů, nastavit rozvržení a uložit PNG. Obsahuje kompletní kód a tipy pro projekty
  generátoru čárových kódů v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- barcode generator C#
- how to save PNG
- how to generate PDF417
language: cs
lastmod: 2026-08-22
og_description: Vytvořte čárový kód PDF417 v C# pomocí generátoru čárových kódů, přizpůsobte
  rozvržení a naučte se, jak uložit PNG. Postupujte podle tohoto krok‑za‑krokem tutoriálu.
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG file
og_title: Vytvořte čárový kód PDF417 v C# – kompletní průvodce generováním a ukládáním
  PNG
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create PDF417 barcode in C# with a barcode generator,
    set layout, and save PNG. Includes full code and tips for barcode generator C#
    projects.
  headline: How to create PDF417 barcode in C# and save it as PNG
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak vytvořit čárový kód PDF417 v C# a uložit jej jako PNG
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-and-save-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód v C# a uložit jej jako PNG

Pokud potřebujete **vytvořit PDF417 čárový kód** v aplikaci C#, tento tutoriál vám ukáže přesné kroky. Uvidíte, jak knihovna pro generování čárových kódů v C# může převést libovolný řetězec na skenovatelný PDF417 obrázek a jak uložit PNG soubory bez dalších nástrojů.

Generování čárových kódů je běžné v logistice, prodeji vstupenek a správě dokumentů. Na konci tohoto průvodce budete mít spustitelný konzolový program, který vytvoří PNG soubor pojmenovaný `Pdf417Layout.png` ve vámi zvoleném adresáři.

## Požadavky

- .NET 6.0 SDK nebo novější nainstalovaný (kód také funguje s .NET Framework 4.7+).
- Visual Studio 2022 nebo jakýkoli editor, který umí sestavit projekty C#.
- Balíček NuGet **Aspose.BarCode for .NET** (nebo jakákoli kompatibilní knihovna pro generování čárových kódů v C#).  
  Nainstalujte jej pomocí:

```bash
dotnet add package Aspose.BarCode
```

Žádné další knihovny pro zpracování obrázků nejsou potřeba, protože generátor dokáže přímo zapisovat PNG.

## Krok 1: Vytvořte nový konzolový projekt

Vytvořte nový konzolový projekt, aby byl příklad samostatný.

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Složka `Pdf417Demo` nyní obsahuje soubor `Program.cs`, do kterého napíšeme kód čárového kódu.

## Krok 2: Naimportujte jmenný prostor čárového kódu

Otevřete `Program.cs` a přidejte požadovanou direktivu `using` na začátek:

```csharp
using Aspose.BarCode.Generation;
```

Tento jmenný prostor vám poskytuje přístup k `BarcodeGenerator`, `EncodeTypes` a výčtu formátu obrázku potřebnému pro **jak uložit PNG**.

## Krok 3: Vytvořte generátor PDF417 čárového kódu

Jádrem **jak generovat PDF417** je třída `BarcodeGenerator`. Předáte typ kódování `EncodeTypes.Pdf417` a text, který chcete zakódovat.

```csharp
// Step 3: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

`generator` nyní obsahuje všechna nastavení čárového kódu. Výchozí rozvržení funguje, ale v dalším kroku jej upravíme.

## Krok 4: Definujte rozvržení čárového kódu (sloupce a řádky)

PDF417 vám umožňuje řídit počet sloupců (2‑30) a řádků (1‑90). Úprava těchto hodnot může zlepšit čitelnost pro konkrétní skenery.

```csharp
// Step 4a: Set the number of columns (2‑30 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Step 4b: Set the number of rows (1‑90 allowed)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

> **Tip:** Pokud tyto nastavení vynecháte, knihovna automaticky zvolí optimální hodnoty. Nicméně pevné nastavení sloupců a řádků vám poskytne předvídatelné rozměry obrázku, což je užitečné, když vkládáte PNG do PDF nebo UI rozvržení.

## Krok 5: Uložte vygenerovaný čárový kód jako PNG obrázek

Nyní odpovězte na **jak uložit PNG** voláním `Save`. Metoda přijímá cílovou cestu a výčet formátu obrázku.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = Path.Combine(Environment.CurrentDirectory, "Pdf417Layout.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
```

Soubor `Pdf417Layout.png` se objeví ve složce projektu `bin/Debug/net6.0` po spuštění programu.

## Kompletní spustitelný příklad

Níže je kompletní soubor `Program.cs`. Zkopírujte jej do projektu vytvořeného v **Kroku 1** a spusťte `dotnet run`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

            // 2️⃣ Define the barcode layout – set columns (2‑30) and rows (1‑90)
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // 9 rows

            // 3️⃣ Choose the output path and save as PNG
            string outputPath = Path.Combine(
                Environment.CurrentDirectory,
                "Pdf417Layout.png");

            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode created and saved as PNG at:");
            Console.WriteLine(outputPath);
        }
    }
}
```

### Očekávaný výstup

Když spustíte program, konzole vypíše absolutní cestu k PNG souboru a soubor bude obsahovat čistý PDF417 čárový kód, který vypadá podobně jako obrázek níže.

![create PDF417 barcode example](image-placeholder.png "PDF417 barcode saved as PNG")

PNG můžete naskenovat libovolným PDF417‑kompatibilním skenerem (mobilní aplikace, hardwarové čtečky), abyste ověřili, že zakódovaný text je `"Sample"`.

## Řešení okrajových případů a běžných úskalí

| Situace | Na co si dát pozor | Doporučené řešení |
|-----------|-------------------|-----------------|
| **Neplatné hodnoty sloupců/řádků** | Hodnoty mimo rozsah 2‑30 (sloupce) nebo 1‑90 (řádky) způsobí `ArgumentException`. | Ověřte vstup uživatele před přiřazením, nebo nechte knihovnu zvolit výchozí hodnoty. |
| **Dlouhé vstupní řetězce** | PDF417 může kódovat až 1 850 znaků, ale velmi dlouhé řetězce dramaticky zvyšují požadovaný počet řádků. | Rozdělte data do více čárových kódů nebo použijte vyšší úroveň korekce chyb, pokud je to potřeba. |
| **Oprávnění souborového systému** | Ukládání do složky jen pro čtení vyvolá `UnauthorizedAccessException`. | Zapisujte do `Environment.CurrentDirectory` nebo do cesty, do které má uživatel právo zápisu, a ošetřete výjimky pomocí try/catch. |
| **Chybějící NuGet balíček** | Kompilace selže s chybou “type or namespace name could not be found”. | Ujistěte se, že je nainstalován `Aspose.BarCode` (`dotnet add package Aspose.BarCode`). |

## Rozšíření příkladu

Nyní, když víte **jak vytvořit PDF417 čárový kód** a **jak uložit PNG**, můžete prozkoumat následující související témata:

- **Barcode generator C#**: Změňte `EncodeTypes` na `Code128`, `QR` nebo jiné symbologie.
- **Vlastní barvy**: Použijte `generator.Parameters.Barcode.ForegroundColor` a `BackgroundColor` pro sladění s brandingem.
- **Vkládání do PDF**: Kombinujte PNG s PDF knihovnou (např. iText7) pro vytvoření tisknutelných dokumentů.
- **Dynamická data**: Načtěte text z databáze nebo vstupu uživatele pro generování čárových kódů za běhu.

## Závěr

Nyní máte kompletní, připravené řešení pro **vytvoření PDF417 čárového kódu** v C# a uložení výsledku jako PNG soubor. Tutoriál pokryl každý krok od nastavení projektu po úpravu rozvržení a zdůraznil, jak se vyhnout běžným chybám při používání knihovny pro generování čárových kódů v C#.

Neváhejte experimentovat s různými nastaveními sloupců/řádků, barvami nebo i s jinými formáty čárových kódů. Pokud narazíte na problémy, vraťte se k sekci **jak generovat PDF417** nebo prozkoumejte dokumentaci knihovny pro pokročilé funkce. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat PDF417 čárový kód – Kompaktní PDF417 kódování](/barcode/english/net/compact-pdf417-encoding/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}