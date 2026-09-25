---
category: general
date: 2026-08-22
description: Naučte se, jak v C# generovat čárový kód PDF417 pomocí Aspose.BarCode,
  nastavit velikost čárového kódu, upravit sloupce a povolit kompaktní režim.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: cs
lastmod: 2026-08-22
og_description: Generujte čárový kód PDF417 v C# pomocí Aspose.BarCode. Tento průvodce
  ukazuje, jak nastavit velikost čárového kódu, ovládat sloupce a povolit kompaktní
  režim pro menší obrázek.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Generování čárového kódu PDF417 v C# – nastavení velikosti, sloupců a kompaktního
  režimu
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Jak vygenerovat čárový kód PDF417 v C# a nastavit jeho velikost
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárový kód v C# a nastavit velikost čárového kódu

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento průvodce vás provede celým procesem. Uvidíte přesně **jak generovat PDF417** s Aspose.BarCode, upravit **nastavení velikosti čárového kódu** a vytvořit kompaktní PNG, který lze vložit do reportů nebo mobilních aplikací.

Vytvoření čárového kódu nevyžaduje samostatný grafický editor. Na konci tohoto tutoriálu budete mít plně funkční C# metodu, která vytváří PDF417 obrázek s přesnými rozměry, které potřebujete, připravený pro další zpracování.

## Co se naučíte

* Nainstalujte a odkažte knihovnu Aspose.BarCode.
* Vytvořte generátor PDF417 čárového kódu a zadejte kódovaný text.
* **Nastavte velikost čárového kódu** konfigurací X‑dimenze a počtu sloupců.
* Povolte kompaktní (zkrácený) režim pro zmenšení symbolu.
* Uložte výsledek jako PNG soubor.
* Řešte běžné problémy, jako jsou nečitelné kódy a příliš velké obrázky.

### Požadavky

* .NET 6.0 nebo novější (API funguje také s .NET Framework 4.6+).
* Základní znalost C# a Visual Studio (nebo jakéhokoli C# IDE).
* Platná licence Aspose.BarCode (bezplatná zkušební verze funguje pro testování).

> **Tip:** Pokud plánujete generovat mnoho čárových kódů ve smyčce, znovu použijte jedinou instanci `BarcodeGenerator` a měňte pouze vlastnost `CodeText`. Tím se sníží alokace paměti.

## Generování PDF417 čárového kódu s Aspose.BarCode

Prvním krokem je vytvořit instanci `BarcodeGenerator` pro symbologii PDF417. Tento objekt je vstupním bodem pro všechny operace s čárovými kódy.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Proč je to důležité*: `EncodeTypes.Pdf417` říká knihovně, aby použila standard PDF417, který podporuje velké objemy dat a korekci chyb. Konstruktor také přijímá data, která chcete kódovat, čímž eliminuje potřebu samostatného přiřazení `CodeText` později.

## Nastavení velikosti čárového kódu a počtu sloupců

Symboly PDF417 se skládají z řad a sloupců malých obdélníkových modulů. Ovládáním šířky modulu (X‑dimenze) a počtu sloupců můžete jemně doladit celkové rozměry.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Vysvětlení*:  
* **X‑dimenze** (`Pixels`) určuje, jak široký je každý modul. Menší hodnoty vytvářejí kompaktnější čárový kód, zatímco větší hodnoty zvyšují čitelnost na nízkorozlišovacích skenerech.  
* **Sloupce** řídí horizontální rozložení. Méně sloupců dělá čárový kód vyšší; více sloupců ho rozšiřuje. Nastavte tato dvě nastavení společně, abyste dosáhli přesné **nastavené velikosti čárového kódu**, kterou potřebujete.

## Povolení kompaktního režimu pro menší čárový kód

PDF417 obsahuje „kompaktní“ (nebo zkrácený) režim, který odstraňuje zbytečné odsazení a snižuje celkovou velikost. To je zvláště užitečné, když máte omezený prostor na obrazovce.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Proč povolit zkrácení?*  
Když je `Truncate` nastaven na `true`, generátor vynechá stop pattern a některá kódová slova pro korekci chyb, která nejsou vyžadována ve většině skenovacích scénářů. Výsledný obrázek je přibližně o 15‑20 % menší, aniž by to ohrozilo integritu dat pro typické případy použití.

## Uložení čárového kódu jako PNG obrázku

Po nastavení velikosti a režimu zapište čárový kód na disk. PNG je bezztrátový formát, který zajišťuje, že hrany modulů zůstanou ostré.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Soubor `CompactPdf417.png` bude obsahovat ostrý PDF417 symbol, který odpovídá rozměrům nastaveným v předchozích krocích.

### Očekávaný výstup

Otevření uloženého PNG by mělo zobrazit svisle orientovaný PDF417 čárový kód sestávající ze tří sloupců, každý modul široký 2 px, a celkovou velikost přibližně **120 × 240 px** (šířka × výška). Skenování obrázku jakýmkoli standardním PDF417 čtečkou vrátí původní text „Sample text for PDF417“.

## Běžné úskalí a jak se jim vyhnout

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Čárový kód je nečitelný | X‑dimenze je příliš malá pro skener | Zvyšte `XDimension.Pixels` na 3 nebo 4 |
| Obrázek je příliš široký pro UI | Nastaveno příliš mnoho sloupců | Snižte `Pdf417.Columns` nebo povolte `Truncate` |
| Výjimka `ArgumentOutOfRangeException` | Negativní nebo nulový počet sloupců | Ujistěte se, že `Columns` je kladné celé číslo (minimum 1) |
| PNG soubor je prázdný | Cesta k výstupu neexistuje nebo chybí oprávnění k zápisu | Ověřte, že adresář existuje a aplikace má práva k zápisu |

> **Tip:** Použijte `barcodeGenerator.ValidateParameters()` před voláním `Save()`, abyste včas zachytili chyby konfigurace.

## Kompletní, spustitelný příklad

Níže je samostatný konzolový program, který zahrnuje všechny výše uvedené kroky. Zkopírujte jej do nového C# projektu, obnovte NuGet balíček Aspose.BarCode a spusťte jej, abyste viděli výsledek.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Spuštění programu** vytvoří `CompactPdf417.png` v pracovním adresáři spustitelného souboru. Naskenujte obrázek mobilní aplikací (např. „Barcode Scanner“), abyste ověřili, že kódovaný text odpovídá zdrojovému řetězci.

## Další kroky a související témata

* **Zvyšte úroveň korekce chyb** – upravte `Pdf417.ErrorLevel` pro prostředí s šumivým skenováním.  
* **Změňte orientaci** – nastavte `Pdf417.Rotate` na `RotationAngle.Rotate90`, pokud potřebujete horizontální rozložení.  
* **Vložte čárový kód do PDF** – kombinujte Aspose.PDF s Aspose.BarCode, abyste obrázek umístili přímo do dokumentu.  
* **Generujte jiné 2‑D čárové kódy** – třída `BarcodeGenerator` podporuje DataMatrix, QR a Aztec kódy; stačí vyměnit `EncodeTypes.Pdf417` za požadovanou symbologii.

Ovládnutím technik **generování PDF417 čárového kódu** můžete automatizovat vydávání vstupenek, označování zásob a bezpečný přenos dat napříč širokou škálou .NET aplikací.

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód** v C#, přesně **nastavit velikost čárového kódu**, konfigurovat sloupce, povolit kompaktní režim a uložit výsledek jako PNG. Použijte tato nastavení k přizpůsobení jakémukoli omezení UI nebo požadavku na skenování a rozšiřte přístup i na další formáty čárových kódů podle potřeby. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód – Kompaktní kódování PDF417](/barcode/english/net/compact-pdf417-encoding/)
- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – Průvodce krok za krokem](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}