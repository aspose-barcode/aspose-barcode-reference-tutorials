---
category: general
date: 2026-07-18
description: Rychle vytvořte čárový kód PDF417 v C#. Naučte se, jak generovat čárový
  kód, nastavit parametry a uložit soubory obrázků – zahrnuje zpracování AI 10.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate barcode
- how to set parameters
- how to save image
- barcode ai 10
language: cs
lastmod: 2026-07-18
og_description: Vytvořte čárový kód PDF417 v C# s kompletním návodem. Objevte, jak
  generovat čárový kód, upravovat nastavení a ukládat obrázky při práci s AI 10.
og_image_alt: Screenshot illustrating create pdf417 barcode code in C#
og_title: Vytvořte čárový kód PDF417 v C# – rychlý, flexibilní, kompletní ukázkový
  kód
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  headline: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: Create PDF417 barcode quickly with C#. Learn how to generate barcode,
    set parameters, and save image files – includes AI 10 handling.
  name: Create PDF417 Barcode in C# – Complete Step‑by‑Step Guide
  steps:
  - name: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
    text: '**X‑dimension** – controls the width of the smallest bar (in pixels)'
  - name: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
    text: '**Column count** – influences the overall shape; fewer columns = taller
      barcode'
  - name: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
    text: '**IsLinked** – enables the optional link module that ties the barcode to
      the data string'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspnet
- barcode-generation
title: Vytvořte PDF417 čárový kód v C# – Kompletní průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu PDF417 v C# – Kompletní průvodce krok za krokem

Už jste někdy potřebovali **vytvořit pdf417 barcode**, ale nebyli jste si jisti, kterou knihovnu nebo nastavení zvolit? Nejste v tom sami – mnoho vývojářů narazí na tuto překážku, když poprvé experimentují s GS1‑Micro‑PDF417. Dobrou zprávou je, že s několika řádky C# můžete vygenerovat dokonale formátovaný čárový kód, upravit jeho vzhled a uložit obrázek přímo na disk.

V tomto tutoriálu si projdeme **jak generovat čárový kód** pomocí knihovny Aspose.BarCode, ukážeme **jak nastavit parametry** jako X‑dimension a počet sloupců a demonstrujeme **jak uložit obrázek** pro varianty AI 10 i AI 21. Na konci budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolného .NET projektu.

## Požadavky

Než se pustíme do práce, ujistěte se, že máte:

- .NET 6+ nebo .NET Framework 4.7.2 (jakékoli aktuální runtime)
- Visual Studio 2022 nebo váš oblíbený editor C#
- NuGet balíček **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)
- Zapisovatelnou složku na disku, kam budou ukládány PNG soubory

To je vše – žádné další nástroje, žádná složitá konfigurace. Připravení? Jdeme na to.

## Krok 1: Vytvoření PDF417 čárového kódu ve formátu GS1‑Micro

Prvním krokem je **vytvořit pdf417 barcode** objekt a naplnit jej počátečními daty AI. V GS1‑Micro‑PDF417 je AI 10 (číslo šarže) často výchozím bodem, takže jej zakódujeme hned na začátku.

```csharp
using Aspose.BarCode.Generation;

// Define where the PNGs will be saved
string outputDir = @"C:\Barcodes\";

// Instantiate the generator for GS1‑Micro‑PDF417
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.GS1MicroPdf417,
    "(10)ABCD12345(240)ABCD");   // AI 10 + additional data
```

> **Proč je to důležité:** `EncodeTypes.GS1MicroPdf417` říká knihovně, aby dodržela specifikaci GS1‑Micro, která automaticky přidává závorky AI. Pokud tento parametr vynecháte, získáte obecný PDF417, který nemusí být čitelný v maloobchodních prostředích.

## Krok 2: Jak nastavit parametry čárového kódu

Nyní, když máme instanci čárového kódu, musíme doladit jeho vizuální charakteristiky. Zde přichází na řadu **jak nastavit parametry**. Upravit budeme tři běžná nastavení:

1. **X‑dimension** – určuje šířku nejmenšího pruhu (v pixelech)
2. **Počet sloupců** – ovlivňuje celkový tvar; méně sloupců = vyšší čárový kód
3. **IsLinked** – aktivuje volitelný link‑modul, který spojuje čárový kód s datovým řetězcem

```csharp
// X‑dimension: 2 pixels per module (good balance of size vs readability)
barcode.Parameters.Barcode.XDimension.Pixels = 2;

// Columns: 3 columns makes the barcode compact yet readable
barcode.Parameters.Barcode.Pdf417.Columns = 3;

// Enable linking (adds a special pattern that some scanners use)
barcode.Parameters.Barcode.Pdf417.IsLinked = true;
```

> **Tip:** Pokud cílíte na skenování mobilními zařízeními, zvýšte X‑dimension na 3‑4 pixely; větší moduly lépe přežijí kamery s nízkým rozlišením.

## Krok 3: Jak uložit obrázek – první verze (AI 10)

Po nastavení generátoru můžeme konečně **jak uložit obrázek**. Metoda `Save` zapíše čárový kód do souboru ve formátu, který určíte. Zde používáme PNG, protože zachovává ostré hrany bez kompresních artefaktů.

```csharp
// Save the barcode that encodes AI 10
barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
```

V tomto okamžiku by se ve složce `outputDir` měl objevit soubor `GS1MicroPdf417_AI10.png`. Otevřete jej v libovolném prohlížeči obrázků – uvidíte čistý, vysokokontrastní PDF417 připravený k tisku.

## Krok 4: Přepnutí na jiný AI (AI 21) a opětovné uložení

Často je potřeba zakódovat jiný identifikátor aplikace, například AI 21 (sériové číslo). Změna vlastnosti `CodeText` je vše, co je potřeba. Tím demonstrujeme **barcode ai 10** versus **barcode ai 21** v jednom kroku.

```csharp
// Change the encoded data – now using AI 21
barcode.CodeText = "(21)ABCD12345(240)ABCD";

// Save the new variant
barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
```

> **Co když potřebujete více AI?** Stačí je spojit ve stejném řetězci, např. `"(10)ABCD(21)12345(240)XYZ"`. Knihovna automaticky rozpozná závorky.

## Kompletní funkční příklad

Sestavte vše dohromady a získáte samostatný program, který můžete zkopírovat a vložit do konzolové aplikace:

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Output folder – change to suit your environment
        string outputDir = @"C:\Barcodes\";

        // 2️⃣ Create generator with initial AI 10 data
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.GS1MicroPdf417,
            "(10)ABCD12345(240)ABCD");

        // 3️⃣ Set visual parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // how to set parameters
        barcode.Parameters.Barcode.Pdf417.Columns = 3;
        barcode.Parameters.Barcode.Pdf417.IsLinked = true;

        // 4️⃣ Save first image (AI 10)
        barcode.Save($"{outputDir}GS1MicroPdf417_AI10.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 10 barcode.");

        // 5️⃣ Switch to AI 21 and save second image
        barcode.CodeText = "(21)ABCD12345(240)ABCD";
        barcode.Save($"{outputDir}GS1MicroPdf417_AI21.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved AI 21 barcode.");
    }
}
```

**Očekávaný výstup:** V `C:\Barcodes\` se objeví dva PNG soubory – `GS1MicroPdf417_AI10.png` a `GS1MicroPdf417_AI21.png`. Oba obsahují skenovatelný PDF417; první kóduje AI 10, druhý AI 21.

## Časté problémy a jak se jim vyhnout

- **Chybějící oprávnění ke složce:** Pokud `Save` vyhodí `UnauthorizedAccessException`, ověřte, že cesta existuje a aplikace má právo zapisovat.
- **Nesprávné formátování AI:** Zapomenutí závorek (`(10)`) způsobí, že čárový kód bude považován za běžná data, čímž selže validace GS1.
- **Příliš malá X‑dimension:** Pruhy tenčí než 1 pixel mohou při změně velikosti obrázku zmizet. Pro zobrazení na obrazovce používejte alespoň 2 pixely.

## Další kroky a související témata

Nyní, když víte **jak generovat čárový kód**, **jak nastavit parametry** a **jak uložit obrázek**, můžete zkusit:

- Přidání **čitelného textu** pod čárový kód (`barcode.Parameters.Barcode.CodeTextLocation = CodeLocation.BelowBarcode`)
- Export do **PDF** místo PNG (`BarCodeImageFormat.Pdf`)
- Integraci generování čárových kódů do **ASP.NET Core API** pro tvorbu obrázků za běhu

Každé z těchto témat staví přímo na základech, které jsme v tomto průvodci vytvořili.

---

### Rychlé shrnutí

- **Vytvořit pdf417 barcode** pomocí `BarcodeGenerator` s `EncodeTypes.GS1MicroPdf417`
- **Jak nastavit parametry** jako X‑dimension, počet sloupců a propojení
- **Jak uložit obrázek** jako PNG pro varianty AI 10 i AI 21
- Zpracováno **barcode ai 10** a přepnuto na **barcode ai 21** pouhou změnou vlastnosti

Vyzkoušejte to, dolaďte nastavení a budete mít robustní motor čárových kódů připravený do produkce. Máte otázky nebo potřebujete podrobnější informace? Zanechte komentář níže – šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}