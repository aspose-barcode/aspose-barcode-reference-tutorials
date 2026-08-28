---
category: general
date: 2026-08-22
description: Naučte se nastavit rozměry pro čárové kódy Mailmark v C# a uložit je
  jako PNG obrázky. Obsahuje kompletní kód, vysvětlení a tipy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: cs
lastmod: 2026-08-22
og_description: Jak nastavit rozměry pro čárové kódy Mailmark v C# a exportovat je
  jako PNG soubory. Sledujte kompletní příklad a vyhněte se běžným úskalím.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Jak nastavit rozměry čárových kódů Mailmark v C# – průvodce krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Jak nastavit rozměry pro čárové kódy Mailmark v C#
url: /cs/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit rozměry pro Mailmark čárové kódy v C#

Pokud potřebujete **nastavit rozměry** pro Mailmark čárový kód v C#, tento průvodce ukazuje přesné kroky. Uvidíte, jak nakonfigurovat X‑dimenzi a výšku čáry a poté uložit čárový kód jako PNG obrázek bez dalšího nástroje.

Generování poštovních čárových kódů je rutinní úkol při tvorbě softwaru pro štítky, ale výchozí velikost často neodpovídá požadavkům tiskárny nebo rozvržení. Na konci tohoto tutoriálu budete schopni přesně ovládat velikost čárového kódu a vytvořit dva platné typy Mailmark (C‑type a L‑type) připravené k tisku.

**Co se naučíte**

* Jak nastavit X‑dimenzi (šířku modulu) a výšku čáry pro `BarcodeGenerator`.
* Jak uložit vygenerovaný čárový kód jako PNG soubor pomocí `BarCodeImageFormat`.
* Běžné úskalí, jako jsou neplatné cesty ke složkám nebo nepodporované hodnoty rozměrů.
* Tipy pro opakované použití stejné konfigurace napříč více čárovými kódy.

## Požadavky

* .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.6+).
* NuGet balíček **Aspose.BarCode for .NET** (nebo jakákoli kompatibilní knihovna poskytující `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`).
* Základní znalost syntaxe C# a práce se soubory.

> **Tip:** Nainstalujte balíček pomocí příkazu CLI  
> `dotnet add package Aspose.BarCode` aby byl váš projekt přehledný.

## Krok 1: Definujte výstupní složku

Než vytvoříte jakýkoli čárový kód, musíte se rozhodnout, kam budou PNG soubory uloženy. Použití absolutní cesty zabraňuje překvapením na různých počítačích.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Proč je to důležité*: Pokud složka neexistuje, `Save` vyhodí `IOException`. Volání `Directory.CreateDirectory` je idempotentní – nedělá nic, pokud složka již existuje.

## Krok 2: Vytvořte Mailmark C‑type čárový kód a **nastavte rozměry**

Mailmark C‑type kóduje 20‑znakový alfanumerický řetězec. Po inicializaci generátoru můžete **nastavit rozměry** pomocí objektu `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Proč zvolit tyto hodnoty?

* **X‑dimension** určuje šířku nejmenší čáry (tzv. „modulu“). Hodnota `4` pixely dává čárový kód, který je snadno čitelný většinou laserových tiskáren a zároveň udržuje velikost souboru přiměřenou.
* **BarHeight** určuje vertikální velikost čar. `50` pixelů je běžná výška pro standardní poštovní štítky, ale můžete ji zvýšit pro větší formáty.

> **Hraniční případ:** Některé tiskárny vyžadují minimální výšku čáry 30 px. Nastavení výšky pod tuto hodnotu může vést k nečitelnosti čárových kódů.

## Krok 3: Vytvořte Mailmark L‑type čárový kód a **nastavte rozměry**

L‑type používá delší datový řetězec (až 30 znaků). Stejný postup nastavení rozměrů platí i zde.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Opakované použití konfigurace

Pokud generujete mnoho čárových kódů se stejnými rozměry, zvažte extrahování konfigurace do pomocné metody:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Volání `ApplyStandardDimensions(mailmarkC)` a `ApplyStandardDimensions(mailmarkL)` snižuje duplicitní kód a umožňuje budoucí změny (např. přechod na 5‑pixelové moduly) provést jedním řádkem.

## Krok 4: Ověřte vygenerované PNG soubory

Po spuštění programu otevřete oba PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět dva odlišné Mailmark čárové kódy, každý s 4 px na modul a výškou 50 px.

*Očekávaný výstup*

| Název souboru                 | Přibližné rozměry (px) |
|-------------------------------|--------------------------|
| `PostalMailmarkCType.png`     | 4 px × modul × N modulů |
| `PostalMailmarkLType.png`     | 4 px × modul × N modulů |

Přesná šířka závisí na délce kódovaných dat, ale výška bude vždy **50 px**, protože jsme nastavili `BarHeight.Pixels`.

## Běžná úskalí a jak je řešit

| Problém                           | Symptom                                      | Řešení |
|-----------------------------------|----------------------------------------------|--------|
| Neplatná cesta ke složce          | `IOException: Could not find a part of the path` | Použijte `Path.Combine` s `Environment.SpecialFolder` nebo ověřte řetězec cesty. |
| X‑dimension nastavena na 0 nebo zápornou hodnotu | Čárový kód se zobrazuje jako jednolitý blok | Zajistěte, aby `XDimension.Pixels` byla kladná celá hodnota (minimum 1). |
| Nepodporovaný `EncodeTypes.Mailmark` | `ArgumentException` při konstrukci generátoru | Ověřte, že máte aktuální verzi knihovny Aspose.BarCode, která zahrnuje podporu Mailmark. |
| Ukládání ve špatném formátu obrázku | Poškozený PNG soubor                         | Použijte `BarCodeImageFormat.Png` (nebo `Jpeg`, pokud potřebujete jiný formát). |

## Rozšíření příkladu

* **Různé velikosti** – změňte `XDimension.Pixels` na 3 pro kompaktnější čárový kód, nebo zvýšte `BarHeight.Pixels` na 70 pro větší štítky.
* **Dávkové generování** – projděte kolekci datových řetězců a pro každou iteraci aplikujte stejná nastavení rozměrů.
* **Jiné formáty obrázků** – nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg` nebo `BarCodeImageFormat.Bmp`, pokud to váš workflow vyžaduje.

## Závěr

Nyní víte, **jak nastavit rozměry** pro Mailmark čárové kódy v C# a exportovat je jako PNG soubory. Konfigurací `XDimension.Pixels` a `BarHeight.Pixels` řídíte vizuální velikost jak C‑type, tak L‑type kódů, což zajišťuje soulad s požadavky tiskáren a rozvržením.

---

*Další kroky*: prozkoumejte **rozměry BarcodeGenerator** pro QR kódy, nebo si přečtěte dokumentaci Aspose.BarCode o **nastavení DPI** pro vysoce rozlišený tisk. Pokud potřebujete vložit čárový kód do PDF, zkombinujte tento přístup s knihovnou **Aspose.PDF** pro kompletní end‑to‑end řešení.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Jak nastavit okraj pro přizpůsobení ITF-14 čárového kódu](/barcode/english/net/itf-14-barcode-customization/)
- [Jak konfigurovat Patch Code čárové kódy s Aspose.BarCode pro .NET](/barcode/english/net/patch-code-configuration/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}