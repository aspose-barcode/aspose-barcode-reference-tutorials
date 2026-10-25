---
category: general
date: 2026-10-24
description: Naučte se, jak generovat čárový kód PDF417 pomocí Aspose.BarCode v C#
  s kompaktním nastavením a řízením XDimension čárového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: cs
lastmod: 2026-10-24
og_description: Generujte čárový kód PDF417 v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto kompletního průvodce a vytvořte kompaktní obrázky PDF417, ovládejte
  XDimension a nastavte sloupce.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Vytvořte čárový kód PDF417 pomocí Aspose.BarCode – krok po kroku v C#
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Jak vygenerovat čárový kód PDF417 pomocí Aspose.BarCode v C#
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód PDF417 pomocí Aspose.BarCode v C#

Pokud potřebujete **vytvořit čárový kód PDF417** v .NET aplikaci, tento návod vám ukáže kompletní, připravené řešení. Uvidíte, jak Aspose.BarCode proces zjednodušuje a zároveň vám poskytuje detailní kontrolu nad **kompaktním PDF417**, **XDimension čárového kódu** a **sloupci PDF417**.

Vytvoření čárového kódu je běžná potřeba pro systémy inventarizace, platformy pro vstupenky a workflow dokumentů. Na konci tohoto tutoriálu budete mít samostatný C# program, který vytvoří ostrý PNG obrázek čárového kódu PDF417, připravený k vložení do jakéhokoli UI nebo k tisku na štítek.

## Co budete potřebovat

- .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.6+)
- Visual Studio 2022 nebo libovolný C# editor, který preferujete
- Platná licence Aspose.BarCode pro .NET (zkušební verze funguje pro vývoj)
- Základní znalost syntaxe C#

> **Tip:** Pokud hodnotíte Aspose.BarCode, stáhněte si zkušební verzi z oficiálního webu a přidejte NuGet balíček `Aspose.BarCode` do svého projektu. Zkušební verze přidá malou vodoznak na vygenerovaný obrázek, který zmizí po aplikaci licence.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Otevřete terminál ve složce řešení a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Příkaz stáhne nejnovější stabilní verzi (k říjnu 2026, verze 23.12). Přidání balíčku obnoví jmenný prostor `Aspose.BarCode.Generation`, který použijete k **vytvoření PDF417 čárových kódů**.

## Krok 2: Vytvoření základního C# konzolového projektu

Pokud ještě nemáte projekt, vytvořte jej:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Otevřete `Program.cs`. Šablona již obsahuje metodu `Main`, kam vložíme kód pro generování čárového kódu.

## Krok 3: Inicializace generátoru čárových kódů

Nejprve importujte požadovaný jmenný prostor:

```csharp
using Aspose.BarCode.Generation;
```

Pak uvnitř `Main` vytvořte instanci `BarcodeGenerator` se symbologií PDF417 a daty, která chcete zakódovat:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Řetězec obsahuje Unicode znaky, aby se ukázalo, že Aspose.BarCode správně zpracovává ne‑ASCII vstup. Pokud potřebujete jen ASCII, nahraďte text libovolným prostým řetězcem.

## Krok 4: Úprava XDimension čárového kódu (velikost modulu)

**XDimension čárového kódu** určuje šířku nejmenšího pruhu (modulu). Nastavení v pixelech vám dává pixel‑přesnou kontrolu nad konečnou velikostí obrázku:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota `2` pixely dává kompaktní obrázek bez ztráty spolehlivosti skenování. Zvýšte hodnotu pro větší čárové kódy nebo ji snižte pro velmi husté rozvržení.

## Krok 5: Konfigurace možností kompaktního PDF417

Dvě nastavení specifická pro PDF417 výrazně ovlivňují vizuální stopu:

| Nastavení | Význam | Typická hodnota pro kompaktní výstup |
|-----------|--------|--------------------------------------|
| `Columns` | Počet datových sloupců | `3` |
| `Truncate` (kompaktní režim) | Vynechává pravý tichý pás a snižuje počet řádků | `true` |

Použijte je následovně:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Použití **sloupců PDF417** nastavených na `3` spolu s `Truncate = true` vytvoří *kompaktní PDF417* čárový kód, který se pěkně vejde na standardní štítek a přitom je čitelný většinou skenerů.

## Krok 6: Uložení obrázku čárového kódu

Nakonec zapíšete čárový kód na disk. Příklad ukládá PNG, ale Aspose.BarCode podporuje také BMP, JPEG, GIF, TIFF a SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Konstanta `BarCodeImageFormat.Png` říká knihovně, aby vytvořila bezztrátový PNG, což je ideální pro další zpracování nebo tisk.

## Kompletní, spustitelný zdrojový kód

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Po spuštění programu se v kořenové složce projektu vytvoří soubor `CompactPdf417.png`. Otevřete jej v libovolném prohlížeči obrázků; uvidíte těsně zabalený PDF417 čárový kód, který kóduje řetězec *Åspóse.Barcóde©*.

![Screenshot vygenerovaného PDF417 čárového kódu pomocí Aspose.BarCode](placeholder-image.png "Vygenerovaný PDF417 čárový kód")

*Alt text obrázku: Screenshot vygenerovaného PDF417 čárového kódu pomocí Aspose.BarCode* – tento alt text obsahuje hlavní klíčové slovo pro přístupnost a SEO.

## Ověření výsledku

1. Otevřete PNG soubor. Čárový kód by měl mít tři vertikální datové sloupce s kompaktním rozvržením (žádné extra tiché zóny vpravo).
2. Naskenujte obrázek pomocí chytrého telefonu s aplikací, která podporuje PDF417. Dekódovaný text musí odpovídat původnímu vstupnímu řetězci.
3. Pokud skener selže, zkuste zvýšit `XDimension.Pixels` na `3` nebo `4`. Větší moduly zlepšují čitelnost na zařízeních s nízkým rozlišením.

## Běžné varianty a okrajové případy

### 1. Změna formátu obrázku

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG je vektorové, takže čárový kód zůstane ostrý při libovolném přiblížení – užitečné pro webové stránky.

### 2. Kódování velkého množství dat

PDF417 může uložit až ~1,1 KB textu. Když payload přesáhne kapacitu tří sloupců, knihovna automaticky přidá řádky. Pro zachování kompaktnosti můžete:

- Zkrátit délku dat (např. použít identifikátor místo celé zprávy)
- Zvýšit počet **sloupců PDF417** (např. `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Použití licence k odstranění zkušebního vodoznaku

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Umístěte licenční soubor vedle spustitelného souboru. Po aktivaci licence vygenerovaný obrázek neobsahuje žádný vodoznak.

### 4. Ošetření výjimek

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Typické selhání zahrnují nedostatečná oprávnění k zápisu nebo nepodporovaný formát obrázku.

## Proč jsou nastavení důležitá

- **XDimension čárového kódu** – Řídí vizuální váhu každého pruhu. Příliš malý činí čárový kód nečitelným; příliš velký plýtvá prostorem.
- **Sloupce PDF417** – Méně sloupců vytváří užší čárový kód, ale zvyšuje počet řádků.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak generovat PDF417 čárový kód s Aspose – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Generovat PDF417 čárový kód s kompaktními nastaveními v C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Jak uložit čárový kód a generovat PDF417 s Aspose v C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}