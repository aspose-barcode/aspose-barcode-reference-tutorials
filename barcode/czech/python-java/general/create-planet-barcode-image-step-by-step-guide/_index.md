---
category: general
date: 2026-07-27
description: Rychle vytvořte obrázek planetárního čárového kódu. Naučte se, jak generovat
  planetární čárový kód v C# a přizpůsobit vyplněné nebo prázdné pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode image
- how to generate planet barcode
- planet barcode C#
- barcode X‑dimension
- filled vs empty bars
language: cs
lastmod: 2026-07-27
og_description: Vytvořte obrázek planetárního čárového kódu během několika sekund.
  Postupujte podle tohoto návodu, abyste se naučili, jak generovat planetární čárový
  kód, upravit X‑rozměr a přepínat mezi vyplněnými a prázdnými pruhy.
og_image_alt: Screenshot showing a create planet barcode image with filled bars
og_title: Vytvořte obrázek planetárního čárového kódu – kompletní C# tutoriál
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  headline: create planet barcode image – Step‑by‑Step Guide
  type: TechArticle
- description: create planet barcode image quickly. Learn how to generate planet barcode
    with C# and customize filled or empty bars.
  name: create planet barcode image – Step‑by‑Step Guide
  steps:
  - name: Why the X‑dimension matters
    text: The X‑dimension controls how wide each tiny bar (or “module”) is. A value
      of **4 pixels** yields a barcode that’s clear on screen and prints nicely on
      standard label printers. If you need a denser image for a high‑resolution print,
      bump the value up to 6 or 8.
  - name: Expected output
    text: Open the resulting `PostalPlanetFilledBars.png` and you should see a classic
      Planet barcode—solid vertical bars with a quiet zone on each side. It looks
      just like the example you’d find on a postal envelope.
  - name: What “FilledBars = false” does
    text: Setting `FilledBars` to `false` tells the rendering engine to draw only
      the bar outlines. This is useful when you need a lighter‑weight image for on‑screen
      display or when a printing guideline explicitly requires the empty style.
  - name: Expected output
    text: The `PostalPlanetEmptyBars.png` file shows the same pattern as before, but
      each bar is a thin line instead of a solid block. It’s perfect for low‑contrast
      printing on colored paper.
  - name: When to use RM4SCC
    text: RM4SCC is the Dutch “Postcode” barcode. If you’re building a multi‑country
      logistics platform, having both Planet and RM4SCC generators at hand saves you
      a lot of boilerplate code.
  - name: What if I need a different image format?
    text: Just swap `BarCodeImageFormat.Png` for `Jpeg`, `Bmp`, or `Gif`. The library
      handles the conversion automatically.
  - name: How do I change the barcode height?
    text: Use `planetFilled.Parameters.Barcode.BarHeight = 50; // height in points`
      (or pixels, depending on the library version). Higher values give you a taller
      barcode, which can improve scan reliability on low‑resolution scanners.
  - name: Can I embed the barcode directly into a PDF?
    text: Absolutely. The `Save` method returns a `byte[]` if you call the overload
      that writes to a stream. Feed that stream into a PDF generation library (e.g.,
      iTextSharp) and you’ve got a fully‑automated mailing label.
  - name: What if the data string contains non‑numeric characters?
    text: 'Planet and RM4SCC expect **numeric only** payloads. Passing letters will
      throw an `ArgumentException`. Validate your input first:'
  - name: Does the X‑dimension affect scanning speed?
    text: A larger X‑dimension creates a more robust barcode, which generally improves
      scanning speed, especially on low‑quality scanners. However, it also increases
      the physical size of the label, so balance readability with space constraints.
  type: HowTo
tags:
- barcode
- C#
- imaging
title: Vytvořte obrázek planetárního čárového kódu – průvodce krok za krokem
url: /cs/python-java/general/create-planet-barcode-image-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# vytvořte planet barcode image – Kompletní C# tutoriál

Už jste se někdy zamysleli **jak generovat planet barcode** pro poštovní systém nebo logistickou aplikaci? Nejste první, kdo se nad tím trápí. V tomto tutoriálu projdeme vše, co potřebujete k **vytvořit planet barcode image** souborům, od základů třídy `BarcodeGenerator` po ladění X‑dimenze a výměnu plných pruhů za prázdné.

Také se podíváme na související symbologii — RM4SCC — abyste viděli, jak stejný vzor funguje pro jiné poštovní čárové kódy. Na konci budete mít tři připravené úryvky kódu, které vygenerují PNG soubory, jež můžete rovnou vložit do svého projektu.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód funguje také na .NET Framework 4.7+)
- Odkaz na **Aspose.BarCode** (nebo libovolnou knihovnu, která poskytuje `BarcodeGenerator`, `EncodeTypes`, `BarCodeImageFormat`)
- IDE, ve které se cítíte pohodlně — Visual Studio, Rider nebo VS Code bude stačit
- Složka, do které můžete zapisovat obrázky (nahraďte `YOUR_DIRECTORY` ve vzorcích)

To je vše. Žádné další NuGet balíčky kromě samotné knihovny pro čárové kódy.

---

## Krok 1: Nastavení projektu a importů

Nejprve si vytvořme malou konzolovou aplikaci, abychom mohli kód okamžitě spustit.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll call helper methods here (see later)
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();
        }
```

> **Tip:** Udržujte metodu `Main` přehlednou; delegujte každý scénář do vlastní metody. Zjednoduší to čtení kódu a odráží tři příklady v původním úryvku.

---

## Krok 2: **create planet barcode image** s výchozími plnými pruhy

Symbologie Planet používá mnoho poštovních služeb pro sledovací čísla. Pro **create planet barcode image** s obvyklými plnými pruhy postupujte podle těchto tří řádků:

```csharp
        static void GeneratePlanetFilledBars()
        {
            // 1️⃣ Create a generator for the Planet symbology with data "123456"
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the X‑dimension (module width) to 4 pixels for better visibility
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode as a PNG image
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }
```

### Proč je X‑dimenze důležitá
X‑dimenze určuje, jak široký je každý drobný pruh (nebo „modul“). Hodnota **4 pixely** vytváří čárový kód, který je na obrazovce jasný a dobře se tiskne na standardních tiskárnách štítků. Pokud potřebujete hustší obrázek pro vysoce rozlišený tisk, zvyšte hodnotu na 6 nebo 8.

### Očekávaný výstup
Otevřete výsledný soubor `PostalPlanetFilledBars.png` a měli byste vidět klasický Planet čárový kód — plné svislé pruhy s tichou zónou na každé straně. Vypadá přesně jako příklad, který najdete na poštovní obálce.

---

## Krok 3: **create planet barcode image** s prázdnými pruhy

Někdy poštovní specifikace vyžaduje styl *prázdného pruhu*, kde jsou pruhy obrysy místo plných výplní. Přepnutí do tohoto režimu vyžaduje jedinou změnu vlastnosti.

```csharp
        static void GeneratePlanetEmptyBars()
        {
            // 1️⃣ Create the generator (same data as before)
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Keep the X‑dimension consistent
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Disable filled bars → we get an empty‑bar representation
            planetEmpty.Parameters.Barcode.FilledBars = false;

            // 4️⃣ Save the PNG
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }
```

### Co dělá „FilledBars = false“
Nastavení `FilledBars` na `false` říká vykreslovacímu enginu, aby kreslil jen obrysy pruhů. To je užitečné, když potřebujete lehčí obrázek pro zobrazení na obrazovce nebo když tisková směrnice explicitně vyžaduje prázdný styl.

### Očekávaný výstup
Soubor `PostalPlanetEmptyBars.png` zobrazuje stejný vzor jako předtím, ale každý pruh je tenká čára místo plného bloku. Je ideální pro tisk s nízkým kontrastem na barevném papíru.

---

## Krok 4: Generování RM4SCC čárového kódu (Bonus)

I když je naším hlavním zaměřením symbologie Planet, stejné API vám umožní získat výsledky podobné **create planet barcode image** i pro jiné poštovní kódy. Zde je návod, jak **jak generovat planet barcode**‑stylový výstup pro RM4SCC:

```csharp
        static void GenerateRM4SCCFilledBars()
        {
            // 1️⃣ Create a generator for the RM4SCC symbology
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

            // 2️⃣ Align X‑dimension with the other examples
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the image
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

### Kdy použít RM4SCC
RM4SCC je nizozemský čárový kód „Postcode“. Pokud budujete logistickou platformu pro více zemí, mít k dispozici generátory pro Planet i RM4SCC vám ušetří spoustu boilerplate kódu.

---

## Časté otázky a okrajové případy

### Co když potřebuji jiný formát obrázku?
Stačí vyměnit `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`. Knihovna provede konverzi automaticky.

### Jak změním výšku čárového kódu?
Použijte `planetFilled.Parameters.Barcode.BarHeight = 50; // výška v bodech` (nebo pixelech, v závislosti na verzi knihovny). Vyšší hodnoty vám dají vyšší čárový kód, což může zlepšit spolehlivost skenování na nízkokvalitních skenerech.

### Můžu čárový kód vložit přímo do PDF?
Ano. Metoda `Save` vrací `byte[]`, pokud zavoláte přetížení, které zapisuje do proudu. Tento proud předáte knihovně pro generování PDF (např. iTextSharp) a získáte plně automatizovaný poštovní štítek.

### Co když řetězec dat obsahuje ne‑číselné znaky?
Planet a RM4SCC očekávají **pouze číselné** payloady. Předání písmen vyvolá `ArgumentException`. Nejprve validujte vstup:

```csharp
if (!Regex.IsMatch(data, @"^\d+$"))
    throw new ArgumentException("Planet barcode data must be numeric.");
```

### Ovlivňuje X‑dimenze rychlost skenování?
Větší X‑dimenze vytváří robustnější čárový kód, což obecně zvyšuje rychlost skenování, zejména na nízkokvalitních skenerech. Na druhou stranu zvětšuje fyzickou velikost štítku, takže je třeba vyvážit čitelnost s omezením prostoru.

---

## Kompletní funkční příklad (všechny tři metody)

Níže je kompletní program, který můžete zkopírovat a vložit do nového konzolového projektu. Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, do které může vaše aplikace zapisovat.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            GeneratePlanetFilledBars();
            GeneratePlanetEmptyBars();
            GenerateRM4SCCFilledBars();

            Console.WriteLine("All barcode images have been saved.");
        }

        static void GeneratePlanetFilledBars()
        {
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
        }

        static void GeneratePlanetEmptyBars()
        {
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCFilledBars()
        {
            BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFilled.Save("YOUR_DIRECTORY/PostalRM4SCCFilledBars.png", BarCodeImageFormat.Png);
        }
    }
}
```

Spusťte program, otevřete tři PNG soubory a uvidíte přesně obrázky popsané výše. Žádná další konfigurace není potřeba.

---

## Shrnutí a další kroky

Probrali jsme **jak generovat planet barcode** obrázky od nuly, přepínání mezi plnými a obrysovými styly a rozšíření stejného přístupu na RM4SCC. Hlavní body:

1. Vytvořte instanci `BarcodeGenerator` s správným `EncodeTypes` a daty.  
2. Upravte `XDimension.Pixels` pro kontrolu šířky pruhů.  
3. Použijte `FilledBars = false` pro variantu s prázdnými pruhy.  
4. Uložte výsledek v preferovaném formátu obrázku.

Nyní, když můžete **create planet barcode image** soubory, zvažte následující nápady:

- **Dávkové generování**: Procházejte CSV sledovacích čísel a pro každé vytvořte PNG.  
- **Dynamické dimenzování**: Zveřejněte X‑dimenzi a výšku pruhu jako konfigurační parametry ve webovém API.  
- **Integrace s tiskárnami štítků**: Odesílejte PNG bajty přímo do ZPL‑kompatibilní tiskárny pro tvorbu štítků za běhu.

Nebojte se experimentovat — vyměňte řetězec dat, vyzkoušejte různé dimenze nebo kombinujte čárový kód s QR kódem na stejném štítku. Knihovna čárových kódů je dostatečně flexibilní, aby to vše zvládla.

Máte složitý scénář, o kterém si nejste jisti? Zanechte komentář níže a společně ho vyřešíme. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit DotCode čárový kód – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Vytvořit čárový kód C# – příklad GS1 DataMatrix](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Vytvořit čárový kód c# – konfigurace řádků a sloupců Codablock F](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}