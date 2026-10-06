---
category: general
date: 2026-09-07
description: Naučte se, jak vytvořit obrázek čárového kódu v C# a upravit jeho výšku,
  šířku a formát pro rychlé generování PNG souborů s čárovým kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: cs
lastmod: 2026-09-07
og_description: Vytvořte obrázek čárového kódu v C# a naučte se, jak nastavit rozměry
  čárového kódu, změnit jeho výšku a generovat PNG soubory čárových kódů pro jakoukoli
  aplikaci.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Vytvořte obrázek čárového kódu v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Jak vytvořit obrázek čárového kódu v C# s nastavitelnou výškou
url: /cs/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu v C# s nastavitelnou výškou

Pokud potřebujete v C# vytvořit obrázek čárového kódu pro pokladní systém nebo sledování zásob, tento průvodce vám ukáže kompletní postup. Uvidíte, jak nastavit parametry čárového kódu, změnit výšku kódu a vygenerovat PNG soubory čárových kódů, které splňují vizuální požadavky.

Generování obrázku čárového kódu je běžná úloha při integraci skenovacího hardwaru, tisku štítků nebo tvorbě přehledových dashboardů. Na konci tohoto tutoriálu budete mít znovupoužitelný úryvek kódu, který vám umožní upravit X‑dimenzi, výšku a výstupní formát čárového kódu přímo v IDE.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 (nebo novější) nainstalovaný – kód se kompiluje s jakýmkoli aktuálním .NET SDK.
* Odkaz na knihovnu **Aspose.BarCode** (k dispozici přes NuGet `Aspose.BarCode`).
* Základní znalosti C# konzolových aplikací.

Tyto požadavky zajišťují, že příklad poběží ihned na Windows, Linuxu i macOS.

## Krok 1: Nastavení projektu a import knihovny

Vytvořte nový konzolový projekt a přidejte balíček s čárovým kódem:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Nyní otevřete *Program.cs* a přidejte potřebné `using` direktivy:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Tyto importy vám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a výčtům formátů obrázků potřebných k **vytvoření obrázku čárového kódu**.

## Krok 2: Inicializace generátoru s požadovanou symbologií

První řádek kódu vytvoří `BarcodeGenerator`, který ví, jaký typ čárového kódu má kódovat. V tomto příkladu používáme symbologii DataBar Omni‑Directional, ale můžete nahradit `EncodeTypes.DatabarOmniDirectional` libovolným jiným typem podporovaným Aspose.BarCode.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Řetězec `"(01)12345678901231"` odpovídá formátu GS1 Application Identifier, který vyžaduje mnoho prodejců. Inicializace generátoru je základem pro každou **operaci nastavení čárového kódu**, která následuje.

## Krok 3: Jak nastavit rozměry čárového kódu – X‑dimenze a výška

### 3.1 Úprava šířky úzkého pruhu (X‑dimenze)

X‑dimenze řídí tloušťku nejtenčího pruhu. Hodnota **2 pixely** dává jemnější vzhled, užitečný při potřebě kompaktního štítku.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Změna výšky čárového kódu pro vizuální rovnováhu

Výška pruhu určuje, jak vysoký čárový kód vypadá. Níže ukazujeme dvě běžné výšky – 30 pixelů pro malý štítek a 60 pixelů pro větší vizuál. Toto demonstruje **jak programově upravit výšku čárového kódu**.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Krok 4: Generování PNG souborů čárových kódů s různými výškami

### 4.1 Uložení prvního obrázku (výška 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Zvýšení výšky a uložení druhého obrázku

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Tyto dva volání `Save` ukazují **generování PNG souborů čárových kódů** s odlišnými rozměry při opětovném použití stejné instance generátoru. Formát obrázku je explicitně nastaven na PNG, který zachovává bezztrátovou kvalitu – ideální pro tisk nebo zobrazení na obrazovce.

## Krok 5: Kompletní, spustitelný příklad

Sestavením všeho dohromady získáte jedinou metodu `Main`, kterou můžete zkopírovat do libovolného C# konzolového projektu:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Spuštěním tohoto programu vzniknou dva PNG soubory ve výstupní složce projektu:

* `DatabarBarHeight30Pixels.png` – kompaktní 30 px čárový kód.
* `DatabarBarHeight60Pixels.png` – větší 60 px čárový kód.

Oba soubory obsahují **vytvořený obrázek čárového kódu**, který lze vložit do HTML, vytisknout na štítky nebo odeslat mobilní aplikaci ke skenování.

## Často kladené otázky a řešení okrajových případů

| Otázka | Odpověď |
|----------|--------|
| **Co když potřebuji jiný formát obrázku?** | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`, `Bmp` nebo `Gif`. Knihovna automaticky provede konverzi. |
| **Mohu změnit barvy popředí/pozadí?** | Ano. Použijte `generator.Parameters.Barcode.ForeColor` a `BackColor` k nastavení hodnot `System.Drawing.Color` před voláním `Save`. |
| **Jak vygenerovat čárový kód bez souboru na disku?** | Zavolejte `generator.GenerateBarCodeImage()` a získáte objekt `System.Drawing.Image`, který můžete přímo streamovat do odpovědi nebo databáze. |
| **Co když řetězec dat překročí limit symbologie?** | Generátor vyhodí `ArgumentException`. Ověřte délku vstupu nebo ořízněte podle specifikace symbologie. |
| **Existuje způsob, jak hromadně zpracovat více čárových kódů?** | Zabalte kroky do `foreach` smyčky, která aktualizuje `generator.CodeText` a `BarHeight` pro každou položku, a poté zavolejte `Save` s unikátním názvem souboru. |

Řešení těchto scénářů činí logiku **nastavení výšky čárového kódu** robustní pro reálné projekty.

## Profesionální tipy pro spolehlivé generování čárových kódů

* **Cacheujte generátor**, pokud vytváříte mnoho čárových kódů stejného typu; opětovné použití objektu snižuje režii alokace.
* **Nastavte `Resolution`** (`generator.Parameters.ImageResolution.Dpi`), pokud potřebujete vysoce rozlišené PNG pro tisk.
* **Validujte GS1 data** před přiřazením k `CodeText`, abyste předešli chybám kódování, které by mohly způsobit selhání skenování.
* **Testujte na skutečných skenerech** po změně výšky nebo X‑dimenze – některá starší zařízení mají minimální požadavky na velikost.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C#, **jak nastavit rozměry čárového kódu**, **jak upravit výšku čárového kódu** a **generovat PNG soubory čárových kódů** pro jakýkoli vizuální požadavek. Úpravou `XDimension` a `BarHeight` můžete vytvářet kompaktní i velké čárové kódy, aniž byste měnili samotná data.

Dále prozkoumejte související témata, jako je **dynamické měnění výšky čárového kódu** na základě vstupu uživatele, vkládání čárových kódů do PDF reportů pomocí Aspose.PDF, nebo přechod na generování QR‑kódů s `EncodeTypes.QR`. Experimentujte s různými symbologiemi a výstupními formáty, abyste plně ovládli tvorbu čárových kódů v C#.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}