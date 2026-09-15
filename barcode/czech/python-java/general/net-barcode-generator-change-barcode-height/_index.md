---
category: general
date: 2026-07-18
description: Naučte se, jak generovat obrázky čárových kódů pomocí .net generátoru
  čárových kódů a snadno měnit výšku čárového kódu pro symboly GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: cs
lastmod: 2026-07-18
og_description: .NET generátor čárových kódů vám umožní rychle vytvořit obrázky čárových
  kódů. Tento návod ukazuje, jak generovat čárový kód, nastavit výšku čáry a uložit
  soubory PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Změňte výšku čárového kódu pomocí .NET generátoru čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET generátor čárových kódů – změna výšky čárového kódu
url: /cs/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – změna výšky čárového kódu

Už jste se někdy zamýšleli **jak generovat čárový kód** obrázky bez používání desítek nástrojů třetích stran? Ve světě .NET existuje překvapivě jednoduchý způsob, jak to udělat, a klíčovým prvkem je **.net barcode generator**. Pouhými několika řádky C# můžete vytvořit symbol GS1‑Databar Omni‑Directional, upravit výšku čáry a uložit výsledek do souboru PNG.

Pokud vytváříte inventární systém, tiskárnu štítků pro dopravu nebo jakoukoli aplikaci, která potřebuje skenovatelný kód, tento tutoriál vás během několika minut provede od nuly až po fungující čárový kód. Projdeme kompletní kód, vysvětlíme, proč každé nastavení má význam, a ukážeme vám, jak **změnit výšku čárového kódu** bez porušení specifikace.

## Co budete potřebovat

- .NET 6.0 nebo novější (API funguje stejně na .NET Framework 4.7+)
- Odkaz na knihovnu čárových kódů (například Aspose.BarCode for .NET – stejné třídy používá mnoho komerčních balíčků)
- Vývojové prostředí (Visual Studio, Rider nebo VS Code s rozšířením C#)
- Složka, do které máte oprávnění zapisovat – tutoriál tam uloží soubory PNG

To je vše. Žádné další NuGet balíčky kromě samotné knihovny čárových kódů.

## Použití .net barcode generator k změně výšky čárového kódu

Níže je **kompletní, spustitelný konzolový program**. Vložte jej do nového C# projektu, upravte výstupní složku a stiskněte F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Proč je každý řádek důležitý

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Vytvoří **.net barcode generator** s požadovanou symbologií a datovým nákladem. Výčtový typ `EncodeTypes.DatabarOmniDirectional` říká knihovně, aby použila formát GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimenze je šířka nejtenčí čáry. Nastavením na *2 pixely* získáte ostrý obrázek na většině monitorů a zároveň udržíte malou velikost souboru. |
| `BarHeight.Pixels = 30;` | Toto je krok **změny výšky čárového kódu**, který určuje, jak vysoká bude každá čára. Výška 30 pixelů je dobrá výchozí hodnota pro malé štítky. |
| `generator.Save(...);` | Uloží čárový kód do souboru PNG. PNG je bezztrátový formát, což znamená, že skenery vidí přesně ten vzor, který jste vygenerovali. |
| `BarHeight.Pixels = 60;` | Zde **měníme výšku čárového kódu** znovu – tentokrát na 60 pixelů. Knihovna automaticky znovu vykreslí symbol s novým rozměrem, když zavoláte `Save` podruhé. |
| `Console.WriteLine(...);` | Poskytne vám rychlou zpětnou vazbu, že proces byl dokončen bez vyhození výjimky. |

> **Tip:** Pokud potřebujete výstup s vyšším rozlišením pro tisk, přepněte `BarCodeImageFormat.Png` na `BarCodeImageFormat.Tiff` a zvýšte vlastnost `Resolution` (např. `generator.Parameters.ImageResolution = 300;`). Výška čáry bude i nadále respektována, jen bude vykreslena s jemnějším DPI.

## Jak generovat obrázky čárových kódů s různými nastaveními

Ukázka výše pokrývá základy, ale reálné scénáře často vyžadují další úpravy:

### Úprava X‑dimenze pro větší výtisky
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Zvýšení X‑dimenze zvětší celý čárový kód, aniž by změnilo kódovaná data. To je užitečné při tisku na velké štítky.

### Přepínání výstupních formátů
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG se škáluje nekonečně, což je ideální pro webové skenery, které potřebují ostré vektory.

### Přidání lidsky čitelného textu
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Povolení `CodeTextVisible` přidá surová data pod čárový kód, což je užitečné pro ověření během testování.

## Časté úskalí při **změně výšky čárového kódu**

1. **Výška příliš malá** – Některé skenery vyžadují minimální výšku čáry (často 10 mm v reálných jednotkách). Pokud nastavíte `BarHeight.Pixels` příliš nízko, může být vygenerovaný obrázek nečitelné pro skutečný scanner. Vždy testujte s vaším cílovým hardwarem.
2. **Nesoulad X‑dimenze a výšky** – Velká výška čáry spojená s malou X‑dimenzí může vypadat nataženě a může způsobit chyby při dekódování. Usilujte o vyvážený poměr (přibližně 3:1 až 5:1), pokud specifikace neuvádí jinak.
3. **Zapomenutí resetovat parametry** – Generátor si uchovává stav mezi ukládáními. Pokud změníte `BarHeight` pro jeden obrázek a poté znovu použijete stejnou instanci pro jiný čárový kód, předchozí výška zůstane. Buď resetujte vlastnost, nebo vytvořte novou `BarcodeGenerator` pro každý odlišný čárový kód.

## Kompletní end‑to‑end příklad (včetně instalace NuGet)

Pokud začínáte od nuly, postupujte podle těchto kroků, abyste projekt spustili:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Nahraďte automaticky vygenerovaný `Program.cs` kódem uvedeným výše, **nezapomeňte nahradit `YOUR_DIRECTORY`** něčím jako `Path.Combine(Environment.CurrentDirectory, "output")`. Poté:

```bash
dotnet run
```

V adresáři `output` byste měli vidět dva soubory PNG:

- `DatabarBarHeight30Pixels.png` – kompaktní čárový kód vysoký 30 pixelů.
- `DatabarBarHeight60Pixels.png` – vyšší verze s výškou 60 pixelů.

Oba obrázky budou vypadat podobně, ale druhý bude mít výrazně delší čáry, což usnadní čtení skenerům s nízkým rozlišením.

![Příklad výšky čárového kódu](/images/barcode-height.png){alt=".net barcode generator výstup zobrazující různé výšky čar"}

## Shrnutí a další kroky

Probrali jsme, jak **generovat čárový kód** obrázky pomocí **.net barcode generator**, doladili vlastnost **změny výšky čárového kódu** a uložili výsledky ve formátu PNG. Hlavní body jsou:

- Vytvořte generátor s správným `EncodeTypes`.
- Ovládejte vizuální velikost pomocí `XDimension` a `BarHeight`.
- Po každé změně zavolejte `Save`, aby se uložil nový obrázek.
- Upravte rozlišení, formát,

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak vytvořit rozšířený kódový text pro dotcode pomocí Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) pomocí Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}