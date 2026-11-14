---
category: general
date: 2026-11-14
description: Naučte se rychle vytvářet čárový kód PDF417 v C#. Tento průvodce také
  ukazuje, jak generovat PDF417 a jak přizpůsobit nastavení PDF417 pro přesnou kontrolu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: cs
lastmod: 2026-11-14
og_description: Vytvořte čárový kód PDF417 v C# s podrobným návodem krok za krokem.
  Naučte se, jak generovat PDF417 a jak přizpůsobit parametry PDF417 pro přesné výsledky.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Vytvořte čárový kód PDF417 v C# – kompletní průvodce s vlastním rozvržením
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Jak vytvořit PDF417 čárový kód s vlastním rozložením v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód s vlastním rozvržením v C#

Pokud potřebujete **vytvořit pdf417 čárový kód** pro systém vstupenek, inventární štítek nebo skenování v mobilní aplikaci, tento tutoriál ukazuje kompletní proces. Uvidíte, jak rychle vygenerovat PDF417 a jak přizpůsobit nastavení PDF417, jako jsou sloupce a řádky, aby čárový kód vyhovoval vašim návrhovým omezením.

Generování čárového kódu nevyžaduje složitou grafickou knihovnu – stačí Aspose.BarCode pro .NET (nebo jakékoli kompatibilní API). Na konci tohoto průvodce budete mít připravený PNG soubor, který můžete vložit do PDF, webových stránek nebo přímo vytisknout z vaší aplikace.

## Požadavky

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+)
- Aspose.BarCode pro .NET (NuGet balíček `Aspose.BarCode`)
- Základní znalost C# a Visual Studio (nebo jakéhokoli IDE)

> **Tip:** Pokud používáte CI/CD pipeline, přidejte odkaz na NuGet balíček ve vašem souboru projektu, aby byly sestavení reprodukovatelné.

## Krok 1: Instalace knihovny pro čárový kód

Otevřete složku projektu v terminálu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček obsahuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu. Žádné další nativní závislosti nejsou vyžadovány.

## Krok 2: Vytvoření základního PDF417 čárového kódu

Prvním cílem je **vytvořit pdf417 čárový kód** s výchozími nastaveními. Následující program nastaví generátor, zakóduje ukázkový řetězec a uloží výsledek jako PNG obrázek.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Proč to funguje:**  
`EncodeTypes.Pdf417` říká knihovně, aby použila symbologii PDF417. Konstruktor automaticky vytvoří objekt `Barcode` s výchozími hodnotami sloupců/řádků, které zajišťují čitelnost pro většinu případů použití.

Spusťte program (`dotnet run`). V složce projektu najdete `Pdf417Default.png`. Otevřením obrázku uvidíte standardní PDF417 čárový kód připravený ke skenování.

![Create PDF417 barcode example](https://example.com/images/pdf417-default.png){:alt="Příklad vytvoření PDF417 čárového kódu ukazující výchozí rozvržení"}

## Krok 3: Jak vygenerovat PDF417 s vlastními rozměry

Někdy štítek s pevnou velikostí nebo UI komponenta vyžaduje specifickou stopu čárového kódu. V takovém případě je **jak vygenerovat pdf417** s vlastními sloupci a řádky nezbytné.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Proč byste to mohli chtít:**  
- **Omezená šířka:** Snížení počtu sloupců a zvýšení řádků vytvoří širší, ale kratší čárový kód, ideální pro úzké štítky.  
- **Omezená výška:** Zvýšení počtu sloupců a snížení řádků vytvoří vyšší, užší čárový kód, užitečný, když máte vertikální prostor.

Jak `Columns`, tak `Rows` přijímají pouze hodnoty v dokumentovaných rozsazích (2‑30 pro sloupce, 1‑90 pro řádky). Zadání hodnoty mimo rozsah vyvolá `ArgumentOutOfRangeException`, takže vždy validujte vstup uživatele, pokud tato nastavení zpřístupníte v UI.

## Krok 4: Jak dále přizpůsobit PDF417

Kromě sloupců a řádků symbologie PDF417 nabízí mnoho volitelných parametrů:

| Vlastnost | Účel | Typické hodnoty |
|----------|------|----------------|
| `ErrorLevel` | Řídí schopnost korekce chyb | 0‑8 (vyšší = robustnější) |
| `MacroPdf417` | Aktivuje macro PDF417 pro více‑segmentová data | `true`/`false` |
| `CompactPdf417` | Vytváří kompaktnější čárový kód na úkor snížené korekce chyb | `true`/`false` |
| `SecurityLevel` | Přidává kontrolní číslici zabezpečení | 0‑2 |

Zde je rychlý příklad, který také nastavuje úroveň chyb na maximum (8) pro hlučné prostředí:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Proč je to důležité:**  
Vyšší korekce chyb umožňuje skenerům obnovit data i když je část čárového kódu poškozena. Nicméně také zvětšuje velikost čárového kódu, takže nastavení vyvažte s vašimi omezeními rozvržení.

## Krok 5: Ověření funkčnosti čárového kódu

Po vygenerování PNG jej otestujte libovolnou aplikací pro čtení čárových kódů (většina chytrých telefonů má zdarma čtečky PDF417). Pokud skener vrátí původní text (`Custom layout text`), je čárový kód platný.

Pokud narazíte na problémy se skenováním:

1. **Zkontrolujte rozměry:** Ujistěte se, že sloupce/řádky jsou v povoleném rozsahu.  
2. **Upravte úroveň chyb:** Zvyšte `ErrorLevel` pro poškozená média.  
3. **Zkontrolujte kvalitu obrazu:** Uložte s vyšším DPI (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) pokud plánujete tisk.

## Kompletní zdrojový kód pro znovupoužitelný pomocník

Níže je kompaktní, znovupoužitelná třída, kterou můžete vložit do libovolného .NET projektu. Zahrnuje **jak vygenerovat pdf417** a **jak přizpůsobit pdf417** v jedné metodě.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Tento pomocník můžete volat takto:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Metoda abstrahuje opakující se boiler‑plate, což vám umožní soustředit se na obchodní logiku.

## Časté úskalí a jak se jim vyhnout

- **Hodnoty mimo rozsah:** Vždy validujte `columns` a `rows` před jejich přiřazením.  
- **Nesprávný formát obrázku:** Některé starší skenery akceptují jen BMP nebo JPEG. Použijte `BarCodeImageFormat.Bmp`, pokud je potřeba.  
- **Nízké DPI pro tisk:** Výchozí DPI je 96. Pro vysoce kvalitní tisk explicitně nastavte vyšší DPI (např. 300) při volání `Save`.  
- **Chybějící podpora fontů:** PDF417 kóduje binární data, takže obvykle nemusíte specifikovat font. Pokud však překrýváte text na obrázku, ujistěte se, že je font nainstalován na cílovém počítači.

## Závěr

Nyní víte, jak **vytvořit pdf417 čárový kód** od začátku až do konce, jak **vygenerovat pdf417** s vlastními nastaveními sloupců/řádků a jak **přizpůsobit pdf417** pro korekci chyb a kompaktnost. Dodržením vzoru znovupoužitelného pomocníka můžete generovat čárové kódy na vyžádání, přizpůsobit je jakémukoli omezení rozvržení a zajistit spolehlivé skenování v produkčních prostředích.

**Další kroky**

- Prozkoumejte další symbologie jako QR nebo Code128 pomocí stejné třídy `BarcodeGenerator`.  
- Spojte výstup PNG s knihovnou pro generování PDF (např. iText7) a vložte čárové kódy do faktur.  
- Experimentujte s `MacroPdf417` pro přenos více‑segmentových dat, funkce užitečná v logistice a dopravních aplikacích.

Šťastné programování a ať se vaše čárové kódy vždy načtou na první pokus!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vygenerovat PDF417 čárový kód v C# – krok za krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak vygenerovat čárový kód a přizpůsobit PDF417 čárový kód v C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [Jak vytvořit PDF417 čárový kód a exportovat PNG v C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}