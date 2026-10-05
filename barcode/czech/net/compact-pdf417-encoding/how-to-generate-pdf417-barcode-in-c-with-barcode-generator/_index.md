---
category: general
date: 2026-08-25
description: Naučte se, jak v C# generovat čárový kód PDF417 pomocí knihovny C# PDF417
  – krok za krokem s ukázkami kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: cs
lastmod: 2026-08-25
og_description: Vytvořte čárový kód PDF417 v C# pomocí generátoru čárových kódů C#
  PDF417 knihovny. Sledujte tento stručný tutoriál pro kompletní kód a osvědčené postupy.
og_image_alt: Generated PDF417 barcode example
og_title: Generování čárového kódu PDF417 v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak generovat PDF417 čárový kód v C# s generátorem čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárový kód v C# pomocí Barcode Generator

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento návod vám ukáže připravené řešení. Pomocí knihovny **barcode generator C# PDF417** můžete ovládat rozměry, sloupce, řádky a formát obrázku pomocí několika řádků kódu.

Naučíte se, jak vytvořit vysoce rozlišené čárové kódy, přizpůsobit rozvržení a uložit výsledek jako PNG soubory — vše bez opuštění IDE.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)
- Balíček Aspose.BarCode pro .NET (instalace přes NuGet: `Install-Package Aspose.BarCode`)
- Složka, do které budou ukládány vygenerované PNG obrázky
- Základní znalost syntaxe C#

## Krok 1: Nastavte projekt a importujte jmenné prostory

Vytvořte novou konzolovou aplikaci (nebo přidejte kód do existujícího projektu) a přidejte potřebné using direktivy:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Namespace` `Aspose.BarCode.Generation` poskytuje `BarcodeGenerator`, zatímco `Aspose.BarCode` obsahuje výčtový typ `BarCodeImageFormat`.

## Krok 2: Inicializujte generátor PDF417 čárového kódu

Vytvořte instanci `BarcodeGenerator` s typem kódování PDF417 a textem, který chcete zakódovat. Příklad používá řetězec s ne‑ASCII znaky pro demonstraci podpory Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Proč je to důležité:** `EncodeTypes.Pdf417` říká knihovně, aby vytvořila PDF417 čárový kód, což je vrstvený lineární čárový kód ideální pro ukládání velkého množství dat. Poskytnutí textu při konstrukci zajišťuje, že generátor je připraven okamžitě vykreslit.

## Krok 3: Zlepšete rozlišení pomocí X‑dimenze

X‑dimenze (šířka modulu) určuje, kolik pixelů zabírá každý malý pruh. Větší hodnota poskytuje ostřejší obrázek, zejména při tisku.

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nastavení `Pixels = 2` poskytuje dobrý kompromis mezi velikostí a čitelností. Můžete tuto hodnotu zvýšit pro výstupy s vysokým DPI, ale dejte pozor na větší velikost souboru.

## Krok 4: Vygenerujte čárový kód s pevně daným počtem sloupců

PDF417 čárový kód může být uspořádán v konkrétním počtu sloupců. Zde požadujeme **2 sloupce** a necháme knihovnu automaticky určit počet řádků.

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**Výsledek:** `Pdf417Columns2.png` obsahuje kompaktní čárový kód se dvěma svislými sloupci.

## Krok 5: Nechte generátor rozhodnout o sloupcích a nastavte pevný počet řádků

Když potřebujete konkrétní počet řádků — např. pro přizpůsobení výšky štítku — můžete nastavit řádky a nechat sloupce na *auto*.

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

Knihovna vypočítá optimální počet sloupců, aby data vešla do šesti řádků.

## Krok 6: Zadejte jak sloupce, tak řádky pro vlastní rozvržení

Někdy máte přísná omezení rozvržení (např. předtištěný formulář). Můžete explicitně nastavit oba rozměry:

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

Tím vznikne čárový kód, který přesně odpovídá mřížce 4 × 9, což je užitečné pro zarovnání s fyzickými šablonami.

## Kompletní spustitelný příklad

Níže je kompletní program, který provádí všech pět kroků postupně. Zkopírujte jej do `Program.cs` a spusťte projekt.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**Očekávaný výstup**

Spuštěním programu se vytvoří tři PNG soubory ve výstupní složce projektu:

- `Pdf417Columns2.png` – čárový kód se dvěma svislými sloupci.
- `Pdf417Rows6.png` – čárový kód roztažený na šest řádků.
- `Pdf417Rows9Columns4.png` – čárový kód uspořádaný v mřížce 4 × 9.

Můžete otevřít kterýkoli z obrázků v běžném prohlížeči a ověřit, že čárový kód se správně načte pomocí aplikace pro skenování PDF417.

## Profesionální tipy a časté úskalí

- **Zpracování Unicode**: Generátor automaticky kóduje Unicode znaky, ale ujistěte se, že cílový skener podporuje použité znakové sady.
- **Formát obrázku**: PNG zachovává bezztrátovou kvalitu. Pokud potřebujete vektorový formát (např. SVG) pro škálování, nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg`.
- **Výkon**: Opakované používání stejné instance `BarcodeGenerator` (jak je ukázáno) je efektivnější než vytváření nové instance pro každé rozvržení.
- **Zpracování chyb**: Zabalte volání `Save` do `try/catch`, abyste zachytili I/O chyby, zejména při zápisu do chráněných adresářů.
- **Úvahy o tisku**: Pro tištěné štítky zvyšte `XDimension.Pixels` na 3 nebo 4, aby nedošlo k pixelaci při typickém DPI (300 dpi).

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód** v C# pomocí knihovny **barcode generator C# PDF417**. Tutoriál pokryl nastavení rozlišení, řízení

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód – Kompaktní PDF417 kódování](/barcode/english/net/compact-pdf417-encoding/)
- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java knihovna čárových kódů – Přidat čárový kód do PDF pomocí Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}