---
category: general
date: 2026-09-22
description: Naučte se, jak v C# vytvořit čárový kód PDF417, nastavit jeho velikost
  a generovat soubory s obrázky čárových kódů pomocí jasných krok‑za‑krokem příkladů
  kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: cs
lastmod: 2026-09-22
og_description: Vytvořte PDF417 čárový kód v C# rychle. Tento tutoriál ukazuje, jak
  nastavit velikost čárového kódu, povolit kompaktní režim a generovat PNG obrázky
  pro jakýkoli .NET projekt.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Vytvořte PDF417 čárový kód v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Jak vytvořit čárový kód PDF417 a nastavit jeho velikost v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárový kód a nastavit jeho velikost v C#

Pokud potřebujete **vytvořit PDF417 čárový kód** v C#, tento návod vám ukáže, jak generovat čárový kód, ovládat jeho rozměry a uložit výsledek jako obrázkový soubor. Ať už budujete systém vstupenek, logistický štítek nebo zabezpečený průkaz, zvládnutí formátu PDF417 vám umožní zakódovat velké množství dat v kompaktní vizuální podobě.

V tomto tutoriálu se naučíte:

* **Vytvořit PDF417 čárový kód** pomocí knihovny Aspose.BarCode (nebo jakékoli kompatibilní).  
* **Nastavit velikost čárového kódu** úpravou X‑dimenze a počtu sloupců.  
* Generovat **obrázek čárového kódu v C#** pro výstup PNG, JPEG nebo BMP.  

Příklad používá bezplatnou komunitní edici Aspose.BarCode pro .NET, ale stejné koncepty platí i pro jiné knihovny, které poskytují podobné vlastnosti.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný.  
* C# IDE (Visual Studio, Visual Studio Code, Rider atd.).  
* NuGet balíček `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Další konfigurace není potřeba; knihovna funguje na Windows, Linuxu i macOS.

## Krok 1: Vytvořte základní PDF417 čárový kód a nastavte jeho velikost

Prvním krokem je vytvořit instanci `BarcodeGenerator` s výčtem `EncodeTypes.Pdf417` a zadat text, který chcete zakódovat. Pak upravte **X‑dimenzi** (šířku modulu) a počet **sloupců**, abyste ovládali celkovou velikost.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Proč jsou tato nastavení důležitá**

* `XDimension.Pixels` určuje nejúžší šířku čáry. Menší hodnoty vytvoří kompaktnější čárový kód, větší hodnoty zvyšují čitelnost na nízkokvalitních skenerech.  
* `Pdf417.Columns` ovlivňuje poměr stran čárového kódu. Méně sloupců činí kód vyšším; více sloupců jej zploští. Úprava sloupců je hlavní způsob, jak **nastavit velikost čárového kódu** bez změny zakódovaných dat.

Po spuštění kódu najdete soubor `Pdf417Basic.png` ve zvoleném adresáři. Obrázek vypadá podobně jako snímek níže:

<img src="images/pdf417-basic.png" alt="příklad vytvoření PDF417 čárového kódu ukazující základní rozložení čárového kódu">

## Krok 2: Vytvořte kompaktní PDF417 čárový kód (režim truncate) se stejnou velikostí

Někdy potřebujete kratší čárový kód kvůli omezenému prostoru. PDF417 nabízí *truncate* (kompaktní) režim, který odstraňuje stop pattern a snižuje celkovou výšku. Vlastnost `Truncate` tento režim zapíná.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Co se změní při `Truncate = true`?**

* Čárový kód je přibližně o 15‑20 % nižší vertikálně, což je užitečné pro malé štítky nebo mobilní obrazovky.  
* Data zůstávají plně obnovitelná; většina moderních skenerů rozumí truncate režimu automaticky.

Výsledný soubor `CompactPdf417.png` vypadá jako štíhlejší verze základního čárového kódu.

## Krok 3: Vytvořte Micro PDF417 čárový kód, upravte sloupce a uložte jej

Micro PDF417 je novější, vysoce hustá varianta určená pro velmi malé prostory (např. ID karty). Podporuje pouze 1‑4 sloupce a knihovna poskytuje stejnou vlastnost `XDimension` pro řízení velikosti.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Klíčové body pro Micro PDF417**

* Výčet `EncodeTypes.MicroPdf417` automaticky vybírá mikro variantu.  
* Protože je symbol hustší, může být potřeba tiskárna s vyšším DPI (300 dpi nebo více), aby byl čárový kód čitelný.  
* Úprava počtu sloupců je jediným dostupným „knoflíkem“ pro velikost; knihovna i nadále respektuje `XDimension`.

## Jak nastavit velikost čárového kódu pro různé výstupní formáty

Příklady výše používají PNG, ale stejná metoda `Save` funguje i pro JPEG, BMP nebo TIFF. Pokud potřebujete konkrétní rozměry obrázku (např. 300 × 150 px), zkombinujte `XDimension` s `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Zvýšení `ImageResolution` při škálování `XDimension` zachovává vizuální kvalitu při tisku ve vysokém rozlišení.

## Časté problémy a profesionální tipy

| Problém | Proč se vyskytuje | Řešení |
|---------|-------------------|--------|
| Čárový kód je na obrazovce rozmazaný | Nízké DPI v kombinaci s malou `XDimension` | Zvyšte `ImageResolution` a/nebo `XDimension.Pixels` |
| Skener nedokáže přečíst truncate režim | Starší firmware skeneru nepodporuje | Použijte plný (ne‑truncate) režim pro starší hardware |
| Micro PDF417 není čitelný | Tisk pod < 300 dpi nebo s nedostatečným kontrastem | Tiskněte na matný papír při 300 dpi nebo vyšším, zajistěte tmavý popředí |
| Výstupní soubor je poškozený | Chybí oprávnění k zápisu do cílové složky | Ověřte, že `YOUR_DIRECTORY` existuje a je zapisovatelná |

**Profesionální tip:** Vždy generujte čárový kód jako PNG, pokud potřebujete bezztrátovou kvalitu pro další zpracování (např. vložení do PDF). PNG zachovává přesné hodnoty pixelů, zatímco JPEG zavádí kompresní artefakty, které mohou ovlivnit čitelnost čárového kódu.

## Kompletní, spustitelný příklad

Níže je kompletní konzolová aplikace, která demonstruje všechny tři typy čárových kódů v jednom běhu. Zkopírujte kód do nového .NET konzolového projektu a spusťte jej.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Očekávaný výstup**

Po spuštění programu se vytvoří tři PNG soubory ve složce `Barcodes`:

* `Pdf417Basic.png` – standardní PDF417 čárový kód se třemi sloupci.  
* `CompactPdf417.png` – stejná data v truncate (kompaktním) režimu, mírně kratší.  
* `MicroPdf417.png` – vysoce hustá varianta Micro PDF417 se čtyřmi sloupci.

Otevřete libovolný obrázek v prohlížeči; měli byste vidět charakteristické vrstvené uspořádání.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Create PDF417 Barcode Metadata in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}