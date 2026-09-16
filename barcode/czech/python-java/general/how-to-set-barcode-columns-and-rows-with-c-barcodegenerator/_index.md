---
category: general
date: 2026-09-16
description: Naučte se, jak nastavit sloupce čárových kódů v C# pomocí BarcodeGenerator
  a také nastavit řádky čárových kódů pro DataBar Expanded Stacked.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: cs
lastmod: 2026-09-16
og_description: Rychle nastavte sloupce čárových kódů v C#. Tento průvodce vám ukáže,
  jak pomocí BarcodeGeneratoru konfigurovat sloupce, řádky a formát obrázku.
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: Nastavte sloupce a řádky čárových kódů v C# – kompletní průvodce BarcodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak nastavit sloupce a řádky čárového kódu pomocí C# BarcodeGenerator
url: /cs/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit sloupce a řádky čárových kódů pomocí C# BarcodeGenerator

Pokud potřebujete nastavit sloupce čárových kódů v aplikaci C#, tento tutoriál ukazuje přesné kroky, které jsou potřeba. Uvidíte, jak nakonfigurovat jak sloupce, tak řádky pro čárový kód DataBar Expanded Stacked, a poté výsledek uložit jako PNG obrázek.

Generování čárových kódů programově vám ušetří ruční návrh a zaručuje konzistenci napříč zprávami, fakturami a produktovými štítky. Níže uvedený příklad pokrývá celý pracovní postup, od instalace knihovny až po vytvoření dvou obrázků — jednoho s vlastním počtem sloupců a druhého s vlastním počtem řádků.

## Prerequisites

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný.  
* Odkaz na NuGet balíček **Aspose.BarCode for .NET**. Nainstalujte jej pomocí:

```bash
dotnet add package Aspose.BarCode
```

* Zápisová práva do složky, kam budou ukládány vygenerované PNG soubory.

Tyto požadavky zajišťují, že kód se úspěšně zkompiluje a spustí bez další konfigurace.

## How to set barcode columns in C#

Prvním hlavním krokem je vytvořit instanci `BarcodeGenerator` pro symbologii **DataBar Expanded Stacked** a přiřadit požadovaný počet sloupců.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
`EncodeTypes.DatabarExpandedStacked` říká knihovně, kterou symbologii má vykreslit. Nastavením `Parameters.Barcode.DataBar.Columns` měníte vnitřní rozložení modulů, což přímo ovlivňuje vizuální šířku čárového kódu. Metoda `Save` zapíše obrázek na disk ve zvoleném formátu `BarCodeImageFormat`.

### Expected result
Otevřete `C:\Barcodes\DatabarCols4.png` v libovolném prohlížeči obrázků. Měli byste vidět DataBar Expanded Stacked čárový kód, který je širší než výchozí, protože používá čtyři sloupce.

## How to set barcode rows in C#

Po uložení obrázku založeného na sloupcích můžete chtít čárový kód, který se liší výškou úpravou řádků. Proces je obdobný jako u sloupců, ale používá vlastnost `Rows`.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**Why this works:**  
Znovu‑inicializace generátoru zajišťuje, že předchozí nastavení sloupců neovlivní konfiguraci řádků. Změna `Parameters.Barcode.DataBar.Rows` upravuje výšku čárového kódu a vytváří vyšší obrázek, pokud počet řádků překročí výchozí hodnotu.

### Expected result
Otevřete `C:\Barcodes\DatabarRows3.png`. Čárový kód bude vyšší, což odráží konfiguraci se třemi řádky.

## Full end‑to‑end example

Níže je jeden program, který vytvoří oba obrázky během jedné exekuce. Udržení kódu v jednom souboru ukazuje, jak můžete přepínat mezi konfiguracemi sloupců a řádků bez restartování aplikace.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

Spuštěním programu vzniknou dva PNG soubory:

* **DatabarCols4.png** – čárový kód se čtyřmi sloupci.  
* **DatabarRows3.png** – čárový kód se třemi řádky.

Oba soubory používají **barcode image format** PNG, který zachovává ostré hrany a podporuje bezztrátovou kompresi — ideální pro tisk i digitální zobrazení.

## Common questions and tips

| Question | Answer |
|----------|--------|
| *Can I use JPEG instead of PNG?* | Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. JPEG is smaller but introduces compression artifacts, which may affect scanner reliability. |
| *What is the maximum number of columns or rows?* | The library validates the values against the DataBar specification. Values outside the allowed range throw an `ArgumentException`. Check the Aspose.BarCode documentation for the exact limits. |
| *Do I need to dispose the `BarcodeGenerator`?* | The class implements `IDisposable`. Wrap the generator in a `using` block if you create many instances in a loop to free unmanaged resources promptly. |
| *How do I change the barcode size without altering columns/rows?* | Use `barcodeGenerator.Parameters.Image.Width` and `Height` to scale the output image while keeping the module layout unchanged. |

**Pro tip:** Když generujete čárové kódy pro tisk ve vysokém rozlišení, zvyšte rozměry výstupního obrázku (`Width`/`Height`) místo počtu sloupců nebo řádků. Tento přístup zachovává standardní velikost modulu definovanou symbologií a zároveň vám poskytne ostřejší obrázek.

## Conclusion

Nyní víte, jak nastavit sloupce a řádky čárových kódů v C# pomocí třídy **BarcodeGenerator**. Průvodce pokrýval inicializaci generátoru, konfiguraci počtu sloupců a řádků, uložení čárového kódu ve formátu PNG a řešení běžných variant, jako jsou změny formátu obrázku a uvolnění prostředků.

Dále prozkoumejte související témata, jako je **přizpůsobení barev čárových kódů**, **přidání lidsky čitelného textu** a **vkládání čárových kódů do PDF dokumentů**. Všechny tyto rozšíření staví na stejném konfiguračním vzoru předvedeném zde, což vám umožní vytvořit plnohodnotná řešení čárových kódů pro jakoukoli .NET aplikaci.

## What Should You Learn Next?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Příklad generátoru čárových kódů v C# – nastavení sloupců, řádků a export obrázku](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [Průvodce čárovým kódem DataBar Expanded Stacked – jak jej generovat a nastavit velikost v C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [Příklad generátoru čárových kódů v C# – nastavení šířky a výšky](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}