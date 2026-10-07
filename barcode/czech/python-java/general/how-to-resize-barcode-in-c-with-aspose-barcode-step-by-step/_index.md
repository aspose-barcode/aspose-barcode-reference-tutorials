---
category: general
date: 2026-09-23
description: Jak změnit velikost čárového kódu v C# pomocí Aspose.BarCode. Naučte
  se generovat čárový kód v C#, přizpůsobit velikost a efektivně exportovat obrázek
  čárového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- generate barcode c#
- barcode generator example
- create databar barcode
- export barcode image
language: cs
lastmod: 2026-09-23
og_description: Jak změnit velikost čárového kódu v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto návodu k vygenerování čárového kódu v C#, úpravě rozměrů a exportu
  obrázku čárového kódu.
og_image_alt: Screenshot showing resized DataBar Omni‑directional barcode generated
  in C#
og_title: Jak změnit velikost čárového kódu v C# – kompletní tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  headline: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  type: TechArticle
- description: How to resize barcode in C# using Aspose.BarCode. Learn to generate
    barcode C# code, customize size, and export barcode image efficiently.
  name: How to resize barcode in C# with Aspose.BarCode – step‑by‑step guide
  steps:
  - name: '**Create Databar barcode** objects with custom data.'
    text: '**Create Databar barcode** objects with custom data.'
  - name: Adjust `BarHeight` (the core of resizing).
    text: Adjust `BarHeight` (the core of resizing).
  - name: Export PNG files for any required size.
    text: Export PNG files for any required size.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- image processing
title: Jak změnit velikost čárového kódu v C# pomocí Aspose.BarCode – krok za krokem
url: /cs/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit velikost čárového kódu v C# pomocí Aspose.BarCode – krok za krokem průvodce

Pokud potřebujete **jak změnit velikost čárového kódu** v .NET aplikaci, tento tutoriál ukazuje přesný kód, který můžete dnes zkopírovat‑vložit a spustit. Naučíte se, jak **generovat čárový kód v C#**, upravit výšku čáry a **exportovat obrázek čárového kódu** soubory, aniž byste opustili své IDE.

Vytváření čárových kódů je běžné v systémech inventarizace, přepravních štítcích a terminálech místa prodeje. Na konci tohoto průvodce budete schopni **vytvořit obrázky Databar čárového kódu** v libovolné výšce, kterou požadujete, a pochopíte klíčové vlastnosti, které řídí velikost, rozlišení a formát souboru.

## Požadavky

- .NET 6 nebo novější (příklad funguje také s .NET Framework 4.6+)  
- NuGet balíček Aspose.BarCode pro .NET (`Install-Package Aspose.BarCode`)  
- Základní znalost syntaxe C# a Visual Studio (nebo jakéhokoli C# IDE)  

Další knihovny nejsou potřeba; Aspose.BarCode interně zajišťuje vykreslování, škálování a export obrázků.

## Krok 1: Nastavení projektu a import Aspose.BarCode

Vytvořte nový konzolový projekt (nebo jej integrujte do existujícího) a přidejte jmenný prostor Aspose.BarCode:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;   // required for BarCodeImageFormat
```

> **Tip:** Použijte nejnovější verzi Aspose.BarCode (k září 2026), abyste získali opravy chyb a nové symbologie čárových kódů.

## Krok 2: Inicializace generátoru DataBar Omni‑directional

**Příklad generátoru čárového kódu** začíná specifikací symbologie (`EncodeTypes.DatabarOmniDirectional`) a datovým nákladem. Náklad následuje formát GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Omni‑directional barcode generator with the desired data
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Tento objekt obsahuje všechny parametry, které později upravíte, jako X‑dimenzi, výšku čáry a formát obrázku.

## Krok 3: Definice běžných parametrů velikosti

Před exportem nastavte X‑dimenzi (šířku nejúzké čáry) a počáteční výšku čáry. X‑dimenze je vyjádřena v pixelech; hodnota `2` funguje dobře pro většinu rozlišení obrazovky.

```csharp
// Step 3: Set common barcode parameters – X‑dimension and initial bar height (30 px)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
barcode.Parameters.Barcode.BarHeight.Pixels = 30; // initial height
```

> **Proč je to důležité:** Vlastnost `BarHeight` přímo ovlivňuje vizuální velikost čárového kódu. Změna této hodnoty je jádrem **jak změnit velikost čárového kódu** v Aspose.BarCode.

## Krok 4: Export první obrázku čárového kódu (30 px výška)

Nyní můžete **exportovat obrázek čárového kódu** do souboru PNG. Metoda `Save` automaticky vykreslí čárový kód s aktuálními parametry.

```csharp
// Step 4: Save the barcode image with a 30‑pixel height
barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Výsledný soubor vypadá takto:

![Jak změnit velikost čárového kódu – příklad](https://example.com/images/databar-30px.png){: .align-center alt="Jak změnit velikost čárového kódu – 30 pixelová výška"}

## Krok 5: Změna výšky čáry pro vytvoření většího čárového kódu

Abychom demonstrovali **jak změnit velikost čárového kódu** dynamicky, upravte vlastnost `BarHeight` a znovu uložte. Není nutné vytvářet novou instanci `BarcodeGenerator`; stačí upravit existující objekt.

```csharp
// Step 5: Change the bar height to 60 pixels for a larger barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Krok 6: Export zvětšeného obrázku čárového kódu (60 px výška)

```csharp
// Step 6: Save the barcode image with the new 60‑pixel height
barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory — jeden s 30 px a druhý s 60 px — ukazující, jak lze stejná data vykreslit v různých velikostech.

### Očekávaný výstup

| Název souboru                     | Výška čáry (px) | Vizuální výsledek |
|-----------------------------------|----------------|-------------------|
| `DatabarBarHeight30Pixels.png`    | 30             | ![30 px čárový kód](https://example.com/images/databar-30px.png){: alt="30 pixelový DataBar Omni‑directional čárový kód"} |
| `DatabarBarHeight60Pixels.png`    | 60             | ![60 px čárový kód](https://example.com/images/databar-60px.png){: alt="60 pixelový DataBar Omni‑directional čárový kód"} |

Oba obrázky jsou platné GS1‑128 DataBar čárové kódy připravené ke skenování.

## Krok 7: Volitelné – úprava dalších vizuálních nastavení

Zatímco hlavním cílem je **jak změnit velikost čárového kódu**, můžete také doladit:

| Vlastnost | Popis | Typické hodnoty |
|-----------|-------|-----------------|
| `XDimension.Pixels` | Šířka nejúzké čáry | 1–4 |
| `BarHeight.Pixels`  | Výška celého čárového kódu | 20–200 |
| `Resolution` | DPI pro rastrový výstup | 72, 150, 300 |
| `ForeColor` / `BackColor` | Barva popředí a pozadí | `Color.Black`, `Color.White` |

Příklad:

```csharp
barcode.Parameters.Barcode.XDimension.Pixels = 3;
barcode.Parameters.Barcode.ForeColor = Color.DarkBlue;
barcode.Parameters.Barcode.BackColor = Color.White;
barcode.Parameters.ImageResolution.DpiX = 300;
barcode.Parameters.ImageResolution.DpiY = 300;
```

Tyto úpravy neovlivňují logiku **změny velikosti**, ale poskytují plnou kontrolu nad konečnou kvalitou obrázku.

## Časté úskalí a jak se jim vyhnout

| Problém | Symptom | Řešení |
|---------|---------|--------|
| Výška čáry se nemění | Uložené obrázky vypadají identicky | Ujistěte se, že upravujete `barcode.Parameters.Barcode.BarHeight.Pixels` *před* každým voláním `Save`. |
| Čárový kód se stane nečitelným | Skener hlásí “nelze přečíst” | Zachovejte `XDimension` ≥ 2 px pro DataBar Omni‑directional; příliš tenké čáry mohou skenování zlomit. |
| Soubor PNG je rozmazaný | Exportováno při nízkém DPI | Nastavte `barcode.Parameters.ImageResolution.DpiX/Y` alespoň na 150 pro tiskové kvality. |
| Soubor byl neúmyslně přepsán | Nový obrázek nahradí starý | Používejte jedinečné názvy souborů nebo zahrňte hodnotu výšky do názvu souboru, jak je uvedeno výše. |

## Kompletní, spustitelný příklad

Zkopírujte celý blok níže do nové konzolové aplikace (`Program.cs`). Kód se kompiluje a spouští tak, jak je, a vytvoří dva PNG soubory ve výstupní složce projektu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing.Imaging;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑directional barcode generator
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set common parameters
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first height

        // 3️⃣ Export first image (30 px height)
        barcode.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // 4️⃣ Change height to 60 px
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Export second image (60 px height)
        barcode.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Optional: tweak additional settings (uncomment if needed)
        // barcode.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;
        // barcode.Parameters.ImageResolution.DpiX = 300;
        // barcode.Parameters.ImageResolution.DpiY = 300;
    }
}
```

Spuštění programu produkuje:

```
Saved 30‑pixel barcode.
Saved 60‑pixel barcode.
```

Zkontrolujte výstupní složku pro dva PNG soubory. Oba jsou připravené k tisku, vložení do PDF nebo odeslání na vzdálené zařízení.

## Závěr

V tomto průvodci jsme probrali **jak změnit velikost čárového kódu** v C# pomocí Aspose.BarCode, ukázali kompletní **příklad generátoru čárového kódu** a demonstrovali **export obrázku čárového kódu** v různých výškách. Nyní umíte:

1. **Vytvořit Databar čárový kód** s vlastním datovým nákladem.  
2. Upravit `BarHeight` (jádro změny velikosti).  
3. Exportovat PNG soubory v libovolné požadované velikosti.  

Odtud můžete dále zkoumat přizpůsobení — různé symbologie, barevná schémata nebo vektorové formáty jako SVG. Stejný vzor (`barcode.Parameters.Barcode.BarHeight.Pixels = <value>`) funguje pro jakýkoli typ čárového kódu podporovaný Aspose.BarCode, takže můžete sebejistě aplikovat znalosti **jak změnit velikost čárového kódu** v celé své aplikaci.

---

**Další kroky**

- Vyzkoušejte změnu velikosti u jiných symbologií (QR, Code128) a podívejte se, jak výška a šířka spolupracují.  
- Použijte `BarCodeImageFormat.Svg` k vytvoření škálovatelných vektorových grafik pro webové stránky.  
- Integrovejte vygenerované obrázky do PDF zpráv pomocí Aspose.PDF nebo iTextSharp.  

Šťastné programování a užijte si flexibilitu, kterou přináší programové generování čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak generovat čárový kód – konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}