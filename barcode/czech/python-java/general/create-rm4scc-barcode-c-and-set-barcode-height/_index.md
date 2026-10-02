---
category: general
date: 2026-08-25
description: Vytvořte RM4SCC čárový kód v C# s krok‑za‑krokem kódem a naučte se, jak
  nastavit výšku čárového kódu pro přesné rozměry.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: cs
lastmod: 2026-08-25
og_description: Vytvořte čárový kód RM4SCC v C# pomocí Aspose.BarCode a zjistěte,
  jak nastavit výšku čárového kódu pro přesnou kontrolu ve vašich .NET aplikacích.
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: Vytvoření čárového kódu RM4SCC v C# – průvodce nastavením výšky čárového
  kódu
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: Vytvořit RM4SCC čárový kód v C# a nastavit výšku čárového kódu
url: /cs/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte RM4SCC čárový kód C# a nastavte výšku čárového kódu

Rychle vytvořte RM4SCC čárový kód C# pomocí knihovny Aspose.BarCode. Tento tutoriál ukazuje **jak nastavit výšku čárového kódu** a přizpůsobit další vizuální vlastnosti, aby čárový kód přesně zapadl do vašeho rozvržení.

Uvidíte kompletní, připravený ke spuštění konzolový program, který vygeneruje tři PNG soubory:

* výchozí výšky Planet čárový kód (pro srovnání)  
* RM4SCC čárový kód s ručně nastavenou výškou 100 px  
* Planet čárový kód s prázdnými (nevyplněnými) pruhy  

Příklad předpokládá, že máte Visual Studio 2022 (nebo jakékoli IDE pro .NET 6+) a platnou licenci Aspose.BarCode pro .NET nebo evaluační kopii.

## Požadavky

| Požadavek | Důvod |
|-------------|--------|
| .NET 6 SDK (nebo novější) | Poskytuje runtime pro konzolovou aplikaci |
| Aspose.BarCode for .NET NuGet balíček | Poskytuje `BarcodeGenerator`, `EncodeTypes` a API pro export obrázků |
| Základní znalost C# | Potřebná pro pochopení průběhu kódu |

Install the NuGet package with:

```bash
dotnet add package Aspose.BarCode
```

> **Tip:** Pokud spustíte kód bez licence, vygenerované obrázky budou obsahovat malý vodoznak Aspose.

## Krok 1: Nastavte strukturu projektu

Vytvořte nový konzolový projekt a přidejte potřebné `using` direktivy:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

Příkazy `using` vám poskytují přístup ke třídám generátoru čárových kódů a výčtu formátu PNG.

## Krok 2: Definujte výstupní složku

Vyberte složku, kam budou uloženy PNG soubory. Složka musí existovat před voláním `Save`.

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

Vytvoření adresáře programově zabraňuje výjimce *FileNotFoundException*, když se kód spouští na novém počítači.

## Krok 3: Vygenerujte Planet čárový kód s výchozí výškou (základní linie)

Planet čárový kód není hlavním tématem tohoto návodu, ale poskytuje vizuální základ pro srovnání s ručně nastaveným RM4SCC čárovým kódem.

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Proč je to důležité:*  
`XDimension` určuje šířku jednoho pruhu. Udržení konstantní hodnoty při změně `BarHeight` izoluje vliv výšky.

## Krok 4: **Vytvořte RM4SCC čárový kód C#** – nastavte ruční výšku

Nyní se zaměříme na hlavní úkol: **vytvořit RM4SCC čárový kód C#** a explicitně ovládat jeho výšku.

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### Jak nastavit výšku čárového kódu

Vlastnost `BarHeight` se nachází pod `Parameters.Barcode`. Přijímá hodnotu typu `float` vyjádřenou v **pixelech**, **bodech** nebo **milimetrech** v závislosti na zvolené jednotce `Unit` (`Pixels`, `Points`, `Millimeters`). V příkladu používáme `Pixels`, protože výstupní formát je PNG.

Pokud potřebujete výšku v milimetrech, nejprve změňte jednotku:

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## Krok 5: Vygenerujte Planet čárový kód s prázdnými (nevyplněnými) pruhy

Tento krok ukazuje další užitečnou vlastnost — `FilledBars`. Nastavením na `false` vytvoříte „prázdný“ čárový kód, což může být užitečné pro designové účely.

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## Kompletní, spustitelný program

Zkopírujte následující kód do `Program.cs`. Sestavte a spusťte projekt; ve složce `GeneratedBarcodes` se objeví tři PNG soubory.



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit code128 čárový kód v Java a nastavit výšku pruhu](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [Jak vytvořit tichou zónu čárového kódu .NET pro Code 16K pomocí Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Jak vytvořit Aztec čárový kód s Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}