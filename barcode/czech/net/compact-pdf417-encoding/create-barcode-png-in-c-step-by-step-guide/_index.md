---
category: general
date: 2026-07-18
description: Rychle vytvořte PNG čárového kódu v C#. Naučte se, jak upravit sloupce,
  povolit propojení a generovat PDF417 pomocí generátoru čárových kódů v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to adjust columns
- c# barcode generator
- how to generate pdf417
- how to enable linking
language: cs
lastmod: 2026-07-18
og_description: Vytvořte PNG čárového kódu v C# a osvojte si, jak upravit sloupce,
  povolit propojení a generovat PDF417 pomocí generátoru čárových kódů v C#. Postupujte
  podle tohoto stručného návodu.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Vytvořte čárový kód PNG v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create barcode PNG in C# quickly. Learn how to adjust columns, enable
    linking, and generate PDF417 with a C# barcode generator.
  headline: Create barcode PNG in C# – Step‑by‑Step Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Vytvořte PNG čárový kód v C# – krok za krokem
url: /cs/net/compact-pdf417-encoding/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření barcode PNG v C# – Kompletní programovací průvodce

Už jste se někdy zamysleli, jak **create barcode PNG** soubory z C# vytvořit, aniž byste si trhali vlasy? Nejste v tom sami. Ať už potřebujete GS1‑Micro‑PDF417 pro přepravní štítek nebo jednoduchý QR kód pro marketingový leták, zvládnutí **c# barcode generator** usnadní celý proces.

V tomto tutoriálu projdeme vše, co potřebujete k **create barcode PNG** obrázkům, od instalace správného NuGet balíčku po ladění počtu sloupců a zapnutí propojení. Na konci budete vědět **how to adjust columns**, **how to enable linking** a **how to generate PDF417** během několika úhledných řádků kódu.

## Co se naučíte

- Nastavte C# projekt s knihovnou pro generování čárových kódů.  
- Použijte **c# barcode generator** k vytvoření GS1‑Micro‑PDF417 čárového kódu.  
- Použijte **how to adjust columns** pro kontrolu hustoty čárového kódu.  
- Povolte speciální funkci propojení (**how to enable linking**).  
- Uložte výsledek jako vysoce kvalitní soubor **create barcode PNG**.  

## Předpoklady

- .NET 6.0 SDK nebo novější (kód funguje na .NET Core i .NET Framework).  
- Základní znalost syntaxe C# – pokud umíte napsat `foreach`, jste v pohodě.  
- Visual Studio 2022, VS Code nebo jakékoli IDE, které preferujete.  
- Přístup k internetu pro stažení knihovny čárových kódů z NuGet (v příkladu použijeme *Aspose.BarCode*).

Externí konfigurační soubory nejsou potřeba; vše žije v kódu, který napíšeme společně.

## Krok 1: Přidání knihovny pro čárové kódy (c# barcode generator)

Otevřete terminál (nebo Package Manager Console) a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Tento jediný příkaz přidá robustní **c# barcode generator**, který zvládne PDF417, QR, Code128 a mnoho dalšího. Knihovna je aktivně udržována (v24.9 k červenci 2026) a funguje napříč platformami, takže nebudete vázáni na Windows.

## Krok 2: Definování výstupní složky

Než něco vygenerujeme, potřebujeme místo, kam uložit obrázek. Hard‑coding cesty funguje pro ukázku, ale později ji můžete nahradit konfigurační hodnotou.

```csharp
// Step 2: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

Všimněte si, že používáme `Path.Combine` pro bezpečnost – žádné magické řetězce, které selžou na Linuxu. Tento krok je nezbytný, protože pokus o **create barcode PNG** bez platné složky vyvolá výjimku za běhu.

## Krok 3: Inicializace generátoru GS1‑Micro‑PDF417 (how to generate pdf417)

Nyní zábavná část. Vytvoříme instanci **c# barcode generator** a předáme jí řetězec s daty.

```csharp
// Step 3: Initialise the GS1‑Micro‑PDF417 generator
var generator = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(01)12345678901231(240)ABCD123456789012345");
```

`EncodeTypes.GS1MicroPdf417` flag říká knihovně, že chceme variantu PDF417, která splňuje standardy GS1. Řetězec dat používá formát Application Identifier: `(01)` pro GTIN a `(240)` pro interní kód společnosti. Pokud potřebujete obyčejný PDF417, stačí vyměnit enum na `EncodeTypes.Pdf417` – to je **how to generate pdf417** v jiné podobě.

## Krok 4: Úprava rozvržení čárového kódu (how to adjust columns & how to enable linking)

Dvě nastavení často způsobují zmatek: počet sloupců a příznak propojení. Pojďme je objasnit.

```csharp
// Step 4a: Adjust the number of columns – this is how to adjust columns
generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns gives a compact barcode

// Step 4b: Enable linking between macro and micro PDF417 – this is how to enable linking
generator.Parameters.Barcode.Pdf417.IsLinked = true;
```

- **How to adjust columns**: Vlastnost `Columns` řídí horizontální hustotu. Méně sloupců dělá čárový kód vyšší, ale širší; více sloupců jej stlačuje vertikálně. Zvolili jsme `4`, protože to vyvažuje čitelnost na 2‑palcovém štítku s přijatelnou velikostí souboru.  
- **How to enable linking**: Nastavení `IsLinked = true` spojí makro (plno‑velikost) a mikro (malou) verzi dohromady, což některé skenery vyžadují pro hierarchické získávání dat.

Pokud tyto dva řádky vynecháte, stále získáte čárový kód, ale nemusí splňovat vaše specifikace. Věřte mi, strávil jsem hodiny laděním nesouladu počtu sloupců.

## Krok 5: Jemné doladění šířky modulu (X‑Dimension)

Ačkoliv to není hlavní klíčové slovo, úprava šířky modulu se často kombinuje s úpravami sloupců.

```csharp
// Step 5: Set X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Modul o šířce `2` pixelů poskytuje ostrý obrázek, který se dobře škáluje, když jej později vložíte do PDF nebo vytisknete na termální tiskárně.

## Krok 6: Uložení obrázku – Nakonec **create barcode PNG**

Veškeré nastavení vyvrcholí jedním řádkem, který skutečně zapíše soubor na disk.

```csharp
// Step 6: Save the generated barcode as a PNG – the core of create barcode png
string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
generator.Save(filePath, BarCodeImageFormat.Png);
Console.WriteLine($"✅ Barcode PNG saved to: {filePath}");
```

`BarCodeImageFormat.Png` enum zajišťuje bezztrátovou kompresi, ideální pro následné zpracování (např. vložení PNG do PDF nebo HTML `<img>` tagu). Tento řádek je jádrem **create barcode PNG** – bez něj byste výsledek neviděli.

## Kompletní funkční příklad

Spojením všeho dohromady získáte samostatnou konzolovou aplikaci, kterou můžete zkopírovat a spustit:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Define the output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // 2️⃣ Create a GS1‑Micro‑PDF417 barcode generator (how to generate pdf417)
        var generator = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(01)12345678901231(240)ABCD123456789012345");

        // 3️⃣ Adjust X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 4️⃣ How to adjust columns – set column count
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 5️⃣ How to enable linking – link macro and micro versions
        generator.Parameters.Barcode.Pdf417.IsLinked = true;

        // 6️⃣ Save as PNG – the moment we finally create barcode png
        string filePath = Path.Combine(outputFolder, "GS1MicroPdf417_906_907.png");
        generator.Save(filePath, BarCodeImageFormat.Png);

        Console.WriteLine($"✅ Successfully created barcode PNG at: {filePath}");
    }
}
```

### Očekávaný výstup

Když spustíte program, konzole vypíše něco jako:

```
✅ Successfully created barcode PNG at: C:\YourProject\Barcodes\GS1MicroPdf417_906_907.png
```

Otevřete soubor a uvidíte čistý, čitelný obrázek GS1‑Micro‑PDF417 – přesně to, co jste potřebovali pro **create barcode PNG** ve vašem logistickém workflow.

## Časté úskalí a tipy

- **Pitfall:** Zapomenutí `Directory.CreateDirectory`. Aplikace spadne s `DirectoryNotFoundException`.  
  **Tip:** Vždy se ujistěte, že výstupní složka existuje před uložením.

- **Pitfall:** Použití špatného `EncodeTypes`. `EncodeTypes.Pdf417` vám dá běžný PDF417, *ne* mikro verzi.  
  **Tip:** Dvakrát zkontrolujte enum, když potřebujete GS1‑Micro čárový kód.

- **Pitfall:** Nastavení `Columns` na hodnotu mimo povolený rozsah (1‑30).  
  **Tip:** Držte se 2‑10 pro většinu velikostí štítků; jinak knihovna vyhodí `ArgumentOutOfRangeException`.

- **Pro tip:** Pokud potřebujete průhledné pozadí, přidejte  
  ```csharp
  generator.Parameters.Barcode.BackgroundColor = Color.Transparent;
  ```  
  před uložením. To umožní PNG hladce splynout s UI prvky.

- **Pro tip:** Pro dávkové zpracování zabalte logiku generování do `foreach` smyčky a měňte řetězec dat v každé iteraci. To je jednoduchý způsob, jak **create barcode PNG** soubory hromadně vytvořit.

## Rozšíření příkladu

Nyní, když ovládáte základy, zvažte prozkoumání těchto souvisejících témat:

- **How to generate QR codes** pomocí stejného `BarcodeGenerator` (stačí změnit `EncodeTypes.QR`).  
- **Adding human‑readable text** pod čárový kód pomocí `generator.Parameters.Barcode.BarHeight`.  
- **Exporting to SVG** (`BarCodeImageFormat.Svg`) pro vektorovou webovou grafiku.  
- **Integrating with ASP.NET Core** pro dynamické poskytování obrázků čárových kódů (`FileStreamResult`).  

Všechny tyto scénáře znovu používají základní vzor, který jsme probrali: inicializujte generátor, upravte parametry a **create barcode PNG** (nebo jiný formát) pomocí jediného volání `Save`.

## Závěr

Prošli jsme kompletním, připraveným pro produkci způsobem, jak v C# **create barcode PNG** soubory. Po absolvování kroků nyní znáte **how to adjust columns**, **how to enable linking** a **how to generate PDF**

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}