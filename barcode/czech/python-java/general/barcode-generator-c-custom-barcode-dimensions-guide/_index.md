---
category: general
date: 2026-07-21
description: Návod na generátor čárových kódů v C# ukazující, jak nastavit vlastní
  rozměry čárového kódu, upravit výšku pixelů čárového kódu a rychle změnit výšku
  obrázku čárového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- custom barcode dimensions
- barcode pixel height
- barcode image height
- change barcode height
language: cs
lastmod: 2026-07-21
og_description: Generátor čárových kódů v C# vám umožní ovládat každý pixel. Naučte
  se nastavit vlastní rozměry čárového kódu, upravit výšku pixelu čárového kódu a
  snadno změnit výšku čárového kódu.
og_image_alt: Screenshot of barcode generator c# output with custom dimensions
og_title: Generátor čárových kódů v C# – Ovládněte vlastní rozměry během několika
  minut
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  headline: Barcode generator c# – Custom barcode dimensions guide
  type: TechArticle
- description: Barcode generator c# tutorial showing how to set custom barcode dimensions,
    adjust barcode pixel height, and change barcode image height quickly.
  name: Barcode generator c# – Custom barcode dimensions guide
  steps:
  - name: What if I need a different **barcode image height** than the default?
    text: 'You can control the overall canvas size via `GeneratorParameters.ImageHeight.Pixels`.
      For example:'
  - name: How does `XDimension` affect scanning reliability?
    text: A smaller `XDimension` creates thinner bars, which can look sharper but
      may be harder for low‑resolution scanners. As a rule of thumb, keep `XDimension`
      ≥ 2 px for 300 dpi printing and ≥ 3 px for 200 dpi.
  - name: Can I switch from PNG to another format without changing code?
    text: 'Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Gif`,
      `Bmp`, etc. Just replace the enum value:'
  - name: What if I need to generate dozens of barcodes with varying heights?
    text: 'Wrap the height‑changing logic in a loop:'
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Generátor čárových kódů v C# – Průvodce vlastními rozměry čárových kódů
url: /cs/python-java/general/barcode-generator-c-custom-barcode-dimensions-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator c# – Průvodce vlastním rozměrem čárových kódů

Už jste se někdy zamysleli, jak nechat **barcode generator c#** vytvořit přesně požadovanou velikost? Nejste v tom sami. Ať už tisknete štítky produktů na výrobní ploše nebo generujete QR‑stylové značky pro inventurní systém, získání správných rozměrů je zásadní.

V tomto tutoriálu vás provedeme kompletním, připraveným příkladem, který ukazuje, jak nastavit **custom barcode dimensions**, upravit **barcode pixel height** a nakonec **change barcode height** za běhu. Žádné vágní odkazy – jen kód, který můžete dnes zkopírovat, vložit a spustit.

## Co se naučíte

- Jak vytvořit instanci **barcode generator c#** pro symbologii DataBar Omnidirectional.  
- Rozdíl mezi **barcode pixel height** a celkovou **barcode image height**.  
- Dva praktické způsoby, jak **change barcode height** bez opětovného vytvoření generátoru.  
- Tipy, jak uložit obrázek s přesnými rozměry, které potřebujete.

Potřebujete pouze aktuální .NET runtime (4.7+ nebo .NET 6) a knihovnu Aspose.BarCode pro .NET (nebo jakékoli kompatibilní API). Pokud je už máte, pojďme na to.

## Krok 1: Nastavení projektu a import knihovny

Nejprve vytvořte novou konzolovou aplikaci (nebo přidejte kód do existující). Poté přidejte NuGet balíček:

```bash
dotnet add package Aspose.BarCode
```

Nyní přidejte jmenné prostory, které budete potřebovat:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.Drawing;   // only if you manipulate the bitmap later
```

> **Tip:** Pokud používáte Visual Studio, NuGet manager za vás nastaví referenci – není potřeba ručně hledat DLL.

## Krok 2: Vytvoření instance barcode generator c# s kódem DataBar Omnidirectional

Třída **barcode generator c#** je vaším vstupním bodem. Zakódujeme jednoduchou hodnotu GTIN‑14:

```csharp
// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

V tomto okamžiku generátor ví, *co* má zakódovat, ale ne *jak* velké by měly být pruhy. Zde vstupují do hry **custom barcode dimensions**.

## Krok 3: Definování vlastních rozměrů čárového kódu – zaměření na výšku pixelů čárového kódu

Dvě vlastnosti řídí vertikální velikost:

| Property | Co dělá | Typický rozsah |
|----------|---------|----------------|
| `XDimension.Pixels` | Šířka jednoho pruhu (modulu) | 1‑5 px je běžné |
| `BarHeight.Pixels` | Výška samotných pruhů | 30‑100 px v závislosti na DPI tisku |

Nastavme skromnou šířku 2 pixely a **barcode pixel height** na 30 px:

```csharp
// Step 3: Apply custom barcode dimensions
generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel tall bars
```

Proč 30 px? Na 300 dpi tiskárně 30 px odpovídá přibližně 0,1 palce – ideální pro většinu maloobchodních štítků. Zvyšte hodnotu, pokud potřebujete větší vizuální dopad.

## Krok 4: Uložení obrázku čárového kódu s požadovanou výškou obrázku čárového kódu

Po zavolání `Save` knihovna automaticky přidá odsazení, aby vyhověla **barcode image height** (celkové výšce bitmapy). Výsledný obrázek bude vyšší než 30 px kvůli klidovým zónám a případnému popisku, který můžete povolit. Zde je, jak zapsat první PNG:

```csharp
// Step 4: Export the first image (30‑pixel bar height)
string output30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
generator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 30‑pixel barcode to {output30}");
```

Otevřete výsledný soubor a uvidíte ostrý DataBar s **barcode image height** mírně větší než 30 px – přesně to, co většina skenerů očekává.

## Krok 5: Změna výšky čárového kódu bez přestavby generátoru

Změna výšky pruhu je tak jednoduchá jako úprava jediné vlastnosti. Není potřeba znovu vytvářet instanci `BarcodeGenerator`:

```csharp
// Step 5: Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
generator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved 60‑pixel barcode to {output60}");
```

Všimněte si, že jsme změnili pouze `BarHeight.Pixels`. To ukazuje schopnost **change barcode height** – rychlé, šetrné k paměti a ideální pro dávkové zpracování, kde každý štítek může vyžadovat jinou velikost.

## Očekávaný výstup

Spuštěním celého programu vzniknou dva PNG soubory:

- `DatabarBarHeight30Pixels.png` – pruhy jsou vysoké 30 px, celkový obrázek má přibližně 40 px výšky (včetně klidových zón).  
- `DatabarBarHeight60Pixels.png` – pruhy jsou vysoké 60 px, celkový obrázek má přibližně 70 px výšky.

Oba obrázky obsahují stejná zakódovaná data, takže jakýkoli skener, který přečte první, přečte i druhý bez změny nastavení.

## Kompletní zdrojový kód – zkopírujte, vložte a spusťte

```csharp
// ------------------------------------------------------------
// Barcode generator c# – Custom dimensions demo
// ------------------------------------------------------------
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize generator for DataBar Omnidirectional
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set custom barcode dimensions (X‑dimension & bar height)
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bars
        generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30‑pixel bars

        // 3️⃣ Save first image – demonstrates barcode pixel height = 30
        string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(path30, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 30‑pixel barcode to {path30}");

        // 4️⃣ Change barcode height – now 60 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // 5️⃣ Save second image – demonstrates change barcode height
        string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(path60, BarCodeImageFormat.Png);
        System.Console.WriteLine($"Saved 60‑pixel barcode to {path60}");
    }
}
```

> **Poznámka:** Nahraďte `YOUR_DIRECTORY` skutečnou cestou ke složce, do které může vaše aplikace zapisovat. Ve Windows například `@"C:\Temp"` funguje dobře.

## Časté otázky a řešení okrajových případů

### Co když potřebuji jinou **barcode image height** než výchozí?

Můžete řídit celkovou velikost plátna pomocí `GeneratorParameters.ImageHeight.Pixels`. Například:

```csharp
generator.Parameters.ImageHeight.Pixels = 120; // forces total image height
```

To je užitečné, když musíte čárový kód umístit do předem navržené šablony štítku.

### Jak `XDimension` ovlivňuje spolehlivost skenování?

Menší `XDimension` vytváří tenčí pruhy, které mohou vypadat ostřeji, ale mohou být obtížnější pro skenery s nízkým rozlišením. Obecně platí, že `XDimension` by měla být ≥ 2 px pro tisk na 300 dpi a ≥ 3 px pro 200 dpi.

### Můžu přejít z PNG na jiný formát bez změny kódu?

Určitě. Metoda `Save` přijímá `BarCodeImageFormat.Jpeg`, `Gif`, `Bmp` atd. Stačí nahradit hodnotu výčtu:

```csharp
generator.Save(@"path\barcode.jpg", BarCodeImageFormat.Jpeg);
```

### Co když potřebuji vygenerovat desítky čárových kódů s různými výškami?

Zabalte logiku změny výšky do smyčky:

```csharp
int[] heights = {30, 45, 60, 75};
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($@"YOUR_DIRECTORY\BarHeight{h}.png", BarCodeImageFormat.Png);
}
```

Tímto způsobem můžete **change barcode height** programově pro každou iteraci bez opětovného vytváření generátoru.

## Shrnutí

Nyní jsme si ukázali, jak lze **barcode generator c#** nastavit tak, aby vytvářel **custom barcode dimensions**, manipuloval s **barcode pixel height** a **change barcode height** za běhu. Kompletní příklad ukazuje inicializaci, úpravy vlastností a dva uložení, která ilustrují vizuální rozdíl.

Připraveni na další krok? Zkuste kombinovat tato nastavení s textovými popisky, barvami pozadí nebo dokonce vložením čárového kódu do PDF pomocí Aspose.PDF. Stejné principy platí – stačí upravit příslušné parametry.

Pokud se vám tento průvodce líbil, dejte mu hvězdičku na GitHubu, sdílejte ho s kolegy nebo zanechte komentář níže s vašimi vlastními experimenty. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvoření čárového kódu s vlastní výškou – Jednorozměrné čárové kódy](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Jednorozměrná úprava výšky Databar čárového kódu](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [barcode generator tutorial c# – Přizpůsobení poměru stran kódu 16K s Aspose.BarCode pro .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}