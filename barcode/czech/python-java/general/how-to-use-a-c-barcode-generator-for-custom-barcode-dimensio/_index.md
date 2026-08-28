---
category: general
date: 2026-08-22
description: Zjistěte, jak může generátor čárových kódů v C# měnit velikost čárového
  kódu, upravovat rozměry a generovat více řádků v rozšířeném vrstveném DataBar čárovém
  kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- change barcode size
- custom barcode dimensions
- generate barcode multiple rows
- adjust barcode dimensions
language: cs
lastmod: 2026-08-22
og_description: Návod na generátor čárových kódů v C#, ukazující, jak změnit velikost
  čárového kódu, upravit rozměry a generovat čárové kódy ve více řádcích s vlastními
  nastaveními.
og_image_alt: Screenshot of a c# barcode generator output displaying a custom DataBar
  Expanded Stacked barcode
og_title: Průvodce generátorem čárových kódů v C# – změna velikosti, řádků a sloupců
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how a C# barcode generator can change barcode size, adjust dimensions,
    and generate multiple rows in a DataBar Expanded Stacked barcode.
  headline: How to use a C# barcode generator for custom barcode dimensions
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Jak použít generátor čárových kódů v C# pro vlastní rozměry čárových kódů
url: /cs/python-java/general/how-to-use-a-c-barcode-generator-for-custom-barcode-dimensio/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generátor čárových kódů v C# pro vlastní rozměry čárových kódů

Pokud potřebujete **c# barcode generator**, který vám umožní **měnit velikost čárového kódu** za běhu, tento průvodce vám přesně ukáže, jak na to. Vygenerujeme čárový kód DataBar Expanded Stacked, upravíme jeho šířku a výšku nastavením vlastních sloupců a řádků a uložíme tři ukázkové obrázky.

Na konci tutoriálu budete mít kompletní spustitelný konzolový program, který demonstruje **custom barcode dimensions**, **generate barcode multiple rows** a **adjust barcode dimensions** bez opuštění IDE.

## Co budete potřebovat

| Požadavek | Proč je to důležité |
|--------------|----------------|
| .NET 6.0 SDK or later | Poskytuje runtime pro konzolovou aplikaci |
| Visual Studio 2022 (or VS Code) | Poskytuje editor s IntelliSense |
| Aspose.Barcode for .NET NuGet package | Poskytuje třídu `BarcodeGenerator` používanou v příkladech |
| Write permission to a folder on disk | Generátor ukládá PNG soubory na toto místo |

Nainstalujte knihovnu pomocí NuGet CLI:

```bash
dotnet add package Aspose.Barcode
```

Nebo použijte Visual Studio Package Manager:

```powershell
Install-Package Aspose.Barcode
```

## Krok 1: Nastavení základního C# generátoru čárových kódů

Vytvořte nový konzolový projekt a přidejte požadované `using` direktivy. Tento krok vytvoří minimální **c# barcode generator**, který dokáže vygenerovat jednoduchý DataBar Expanded Stacked čárový kód.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved.
            string outputPath = @"C:\Temp\Barcodes\";

            // Ensure the directory exists.
            System.IO.Directory.CreateDirectory(outputPath);

            // Create a basic generator for the DataBar Expanded Stacked type.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // Save the default barcode (no custom dimensions yet).
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);

            Console.WriteLine("Default barcode generated.");
        }
    }
}
```

**Proč to funguje:** `EncodeTypes.DatabarExpandedStacked` říká generátoru, kterou symbologii použít. Metoda `Save` zapíše PNG soubor na disk. V tomto okamžiku čárový kód používá výchozí velikost knihovny.

## Krok 2: Změna velikosti čárového kódu úpravou sloupců

Šířka DataBar Expanded Stacked čárového kódu je řízena vlastností **columns**. Nastavením této vlastnosti umožní **c# barcode generator** vytvořit širší nebo užší čárový kód.

```csharp
// Adjust the number of columns to 4 (wider barcode)
generator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode with custom columns.
generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 4 columns generated.");
```

**Vysvětlení:** Sloupce ovlivňují počet horizontálních modulů. Více sloupců znamená širší čárový kód, což je užitečné, když potřebujete více místa pro delší lidsky čitelný text nebo při tisku na široké štítky.

## Krok 3: Generování čárového kódu v několika řádcích pro kontrolu výšky

Výška je řízena vlastností **rows**. Zvýšením počtu řádků **generate barcode multiple rows** a vytvoříte symbol vyšší — ideální pro skeny s vysokým rozlišením.

```csharp
// Change the barcode to have 3 rows (taller barcode)
generator.Parameters.Barcode.DataBar.Rows = 3;

// Save the taller barcode.
generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);

Console.WriteLine("Barcode with 3 rows generated.");
```

**Proč jsou řádky důležité:** Řádky přidávají vertikální moduly. Vyšší čárový kód může zlepšit čitelnost na nízkokontrastních pozadích nebo když se mění vzdálenost zaostření skeneru.

## Krok 4: Kombinace vlastních sloupců a řádků pro plnou kontrolu

Nyní, když víte, jak **adjust barcode dimensions**, můžete nastavit obě vlastnosti najednou. Tento krok vytvoří čárový kód se šesti sloupci a deseti řádky, což demonstruje plnou flexibilitu **c# barcode generator**.

```csharp
// Set both columns and rows for a custom size.
generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller

// Save the custom-sized barcode.
generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);

Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");
```

**Výsledek:** Soubor `DatabarCols6Rows10.png` obsahuje čárový kód, který je jak širší, tak vyšší než výchozí, což dokazuje, že můžete **adjust barcode dimensions** tak, aby vyhovovaly jakémukoli požadavku na rozvržení.

## Kompletní spustitelný příklad

Níže je celý program, který zahrnuje všechny čtyři kroky. Zkopírujte jej do `Program.cs`, spusťte `dotnet run` a podívejte se do složky `C:\Temp\Barcodes\`, kde najdete čtyři PNG soubory.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -------------------------------------------------
            // 1️⃣  Prepare output folder
            // -------------------------------------------------
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // -------------------------------------------------
            // 2️⃣  Create a basic C# barcode generator
            // -------------------------------------------------
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked demo");

            // -------------------------------------------------
            // 3️⃣  Default barcode (no size changes)
            // -------------------------------------------------
            generator.Save($"{outputPath}DefaultDatabar.png", BarCodeImageFormat.Png);
            Console.WriteLine("Default barcode generated.");

            // -------------------------------------------------
            // 4️⃣  Change barcode size – custom columns
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 4;
            generator.Save($"{outputPath}DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 4 columns generated.");

            // -------------------------------------------------
            // 5️⃣  Generate barcode multiple rows – custom rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Rows = 3;
            generator.Save($"{outputPath}DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode with 3 rows generated.");

            // -------------------------------------------------
            // 6️⃣  Adjust barcode dimensions – both columns & rows
            // -------------------------------------------------
            generator.Parameters.Barcode.DataBar.Columns = 6; // Wider
            generator.Parameters.Barcode.DataBar.Rows = 10;   // Taller
            generator.Save($"{outputPath}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
            Console.WriteLine("Custom barcode with 6 columns and 10 rows generated.");

            Console.WriteLine("All barcodes saved to: " + outputPath);
        }
    }
}
```

### Očekávaný výstup

Spuštěním programu se vytvoří čtyři PNG soubory:

| File name                | Visual description |
|--------------------------|--------------------|
| `DefaultDatabar.png`     | Standardní šířka a výška |
| `DatabarCols4.png`       | Širší čárový kód (4 sloupce) |
| `DatabarRows3.png`       | Vyšší čárový kód (3 řádky) |
| `DatabarCols6Rows10.png` | Jak širší, tak vyšší (6 sloupců, 10 řádků) |

Otevřete libovolný PNG v prohlížeči obrázků; uvidíte, že vzor DataBar Expanded Stacked je upraven přesně podle specifikace.

## Časté úskalí a profesionální tipy

- **Invalid column/row values** – Knihovna vyhodí `ArgumentException`, pokud nastavíte hodnotu mimo podporovaný rozsah (1‑12 pro sloupce, 1‑10 pro řádky). Ověřte vstupy před přiřazením.
- **Directory permissions** – Pokud je výstupní složka chráněná, `Save` selže. Použijte `System.IO.Directory.CreateDirectory` jak je ukázáno, aby cesta existovala.
- **Performance** – Vytváření mnoha čárových kódů ve smyčce může být náročné na CPU. Znovu použijte stejnou instanci `BarcodeGenerator` a mezi ukládáními měňte pouze `Columns`/`Rows`, aby se snížilo zatížení alokací objektů.
- **Scanning considerations** – Extrémně vysoké nebo široké čárové kódy mohou přesáhnout zorné pole skeneru. Otestujte s vaším cílovým hardwarem po úpravě rozměrů.

## Závěr

Nyní máte solidní příklad **c# barcode generator**, který dokáže **change barcode size**, **custom barcode dimensions**, **generate barcode multiple rows** a **adjust barcode dimensions** tak, aby vyhovoval jakékoli aplikaci. Úpravou vlastností `Columns` a `Rows` získáte přesnou kontrolu nad vizuální stopou DataBar Expanded Stacked čárového kódu.

Neváhejte experimentovat s dalšími symbologiemi (`EncodeTypes.QR`, `EncodeTypes.Code128`) nebo výstupními formáty (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`). Stejný vzor — vytvořit `BarcodeGenerator`, nastavit vlastnosti rozměrů a poté zavolat `Save` — platí napříč Aspose.Barcode API.

**Next steps**

- Prozkoumejte **error correction levels** pro QR kódy.
- Kombinujte **custom colors** a **background images** pro branding vašich čárových kódů.
- Integrajte generátor do ASP.NET Core webové služby pro tvorbu čárových kódů na požádání.

Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak upravit velikost čárového kódu – poměr stran Codablock F s Aspose.BarCode pro .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}