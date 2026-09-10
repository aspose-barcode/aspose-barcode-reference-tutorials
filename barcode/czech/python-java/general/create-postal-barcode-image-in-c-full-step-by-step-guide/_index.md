---
category: general
date: 2026-07-27
description: Rychle vytvořte obrázek poštovního čárového kódu v C# — naučte se, jak
  generovat poštovní čárový kód, generovat planetový čárový kód a jak nastavit výšku
  čárového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: cs
lastmod: 2026-07-27
og_description: Vytvořte obrázek poštovního čárového kódu v C# a osvojte si, jak generovat
  poštovní čárový kód, generovat planetární čárový kód a jak nastavit výšku čárového
  kódu pro dokonalé výsledky.
og_image_alt: Sample PNG showing Planet and RM4SCC postal barcodes generated with
  Aspose.BarCode
og_title: Vytvořte obrázek poštovního čárového kódu v C# – Kompletní průvodce programováním
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  headline: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create postal barcode image in C# quickly—learn how to generate postal
    barcode, generate planet barcode, and how to set barcode height.
  name: Create Postal Barcode Image in C# – Full Step‑by‑Step Guide
  steps:
  - name: Why set `XDimension`?
    text: '`XDimension` is the pixel width of the smallest bar. If you leave it at
      the library’s default (usually 1 px), the barcode can look cramped on high‑resolution
      screens. Setting it to **4 px** gives a nicely spaced image that prints cleanly
      on most printers.'
  - name: What does `BarHeight.Pixels` actually do?
    text: When you **set barcode height**, you override the library’s automatic calculation.
      By default Aspose.BarCode chooses a height that keeps the barcode square‑ish,
      which is fine for many use‑cases. However, postal standards sometimes demand
      a minimum bar height (e.g., 100 px for high‑resolution printin
  - name: Edge Cases & Common Pitfalls
    text: '- **Zero or negative height** – the library throws `ArgumentException`.
      Always validate user input. - **Non‑integer pixel values** – the property is
      an `int`, so fractions are rounded down automatically. - **Changing DPI after
      setting height** – the visual size changes, but the pixel count stays the'
  - name: Expected Output
    text: 'When you open the generated PNG files you’ll see:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- postal
title: Vytvořte obrázek poštovního čárového kódu v C# – Kompletní průvodce krok za
  krokem
url: /cs/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku poštovního čárového kódu v C# – Kompletní průvodce krok za krokem

Už jste někdy potřebovali **vytvořit obrázek poštovního čárového kódu** v C#, ale nebyli jste si jisti, které vlastnosti nastavit? Nejste v tom sami. Ať už budujete systém štítků pro poštu nebo jen experimentujete s poštovními symbologiemi, ovládnutí správných volání API udělá celý proces hračkou.

V tomto tutoriálu si projdeme **generování obrázků poštovních čárových kódů** pro formáty Planet i RM4SCC a ukážeme vám **jak nastavit výšku čárového kódu**, aby pruhy vypadaly přesně tak, jak očekáváte. Na konci budete mít připravenou konzolovou aplikaci, která vytvoří čtyři PNG soubory – dva s výškou výchozí a dva s explicitní výškou 100 px.

## Co budete potřebovat

- **.NET 6.0** nebo novější (kód také kompiluje na .NET Framework 4.6+)  
- **Aspose.BarCode for .NET** – NuGet balíček, který poskytuje `BarcodeGenerator`  
- Složku na disku, kam lze uložit PNG soubory (nahraďte `YOUR_DIRECTORY` ve vzorku)  

Pokud jste s Aspose.BarCode ještě nepracovali, stáhněte jej z NuGet:

```bash
dotnet add package Aspose.BarCode
```

To je vše – žádné další DLL, žádné nativní závislosti. Pojďme na to.

## Vytvoření poštovního čárového kódu – inicializace generátoru

První, co uděláte, je vytvořit instanci `BarcodeGenerator`. Tento objekt je vstupním bodem pro *každý* čárový kód, který chcete vykreslit. Do konstruktoru předáte dva argumenty:

1. **Typ kódování** (`EncodeTypes.Planet` nebo `EncodeTypes.RM4SCC`)  
2. **Datový řetězec** (číslicový poštovní kód, např. `"123456"`)

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Folder where PNG files will be saved
        const string outputFolder = @"C:\Temp\Barcodes";

        // Ensure the folder exists
        System.IO.Directory.CreateDirectory(outputFolder);

        // ---------- Planet barcode with default height ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        // X‑dimension controls the width of the narrowest bar (in pixels)
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetDefaultPath = System.IO.Path.Combine(outputFolder, "PlanetDefault.png");
        planetDefaultPath = System.IO.Path.ChangeExtension(planetDefaultPath, "png");
        planetGenerator.Save(planetDefaultPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with default height ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccDefaultPath = System.IO.Path.Combine(outputFolder, "RM4SCCDefault.png");
        rm4sccGenerator.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
```

### Proč nastavit `XDimension`?

`XDimension` určuje šířku nejmenšího pruhu v pixelech. Pokud ji necháte na výchozí hodnotě knihovny (obvykle 1 px), čárový kód může na obrazovkách s vysokým rozlišením vypadat stísněně. Nastavením na **4 px** získáte hezky rozestoupený obrázek, který se čistě vytiskne na většině tiskáren.

## Jak generovat poštovní čárový kód – typy Planet a RM4SCC

Nyní, když máme generátor, podívejme se na *dvě* nejčastější poštovní symbologie: **Planet** (používá se ve Velké Británii) a **RM4SCC** (používá se v USA). Jediný rozdíl v kódu je hodnota výčtu `EncodeTypes`. Všechno ostatní – ukládání, DPI nebo formát PNG – zůstává stejné.

```csharp
        // ---------- Planet barcode with explicit 100 px height ----------
        var planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        // Here we answer the “how to set barcode height” question.
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string planetHeightPath = System.IO.Path.Combine(outputFolder, "PlanetHeight100.png");
        planetHeightGenerator.Save(planetHeightPath, BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode with explicit 100 px height ----------
        var rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        string rm4sccHeightPath = System.IO.Path.Combine(outputFolder, "RM4SCCHeight100.png");
        rm4sccHeightGenerator.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
    }
}
```

### Co vlastně dělá `BarHeight.Pixels`?

Když **nastavíte výšku čárového kódu**, přepíšete automatický výpočet knihovny. Ve výchozím nastavení Aspose.BarCode volí výšku, která udržuje čárový kód zhruba čtvercový, což stačí pro mnoho případů. Poštovní standardy však někdy vyžadují minimální výšku pruhu (např. 100 px pro tisk ve vysokém rozlišení). Vlastnost `BarHeight.Pixels` vám umožní tyto požadavky splnit přesně.

## Jak nastavit výšku čárového kódu – řízení výšky pruhů podle poštovních standardů

Jestli se ptáte **jak nastavit výšku čárového kódu** pro konkrétní DPI tiskárny, můžete kombinovat `BarHeight.Pixels` s nastavením `Resolution`:

```csharp
        // Example: 300 DPI, 1 inch tall => 300 px
        planetHeightGenerator.Parameters.ImageResolution = 300;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 300; // 1‑inch bar at 300 DPI
```

> **Tip:** Vždy otestujte několik různých výšek na cílové tiskárně. Příliš vysoká výška může přesáhnout tisknutelnou oblast štítku; příliš nízká může způsobit, že skenery nezachytí klidovou zónu.

### Hraniční případy a běžné úskalí

- **Nula nebo záporná výška** – knihovna vyhodí `ArgumentException`. Vždy validujte vstup od uživatele.  
- **Není‑celé hodnoty pixelů** – vlastnost je typu `int`, takže zlomky se automaticky zaokrouhlují dolů.  
- **Změna DPI po nastavení výšky** – vizuální velikost se změní, ale počet pixelů zůstane stejný. Pokud potřebujete fyzickou velikost (např. 1 cm), vypočítejte `pixels = DPI * cm / 2.54`.

## Kompletní funkční příklad – všechny kroky dohromady

Níže je kompletní program připravený ke zkopírování a vložení. Obsahuje ošetření chyb, vytvoření složky a komentáře, které vysvětlují každý řádek. Spusťte jej v konzolovém projektu a získáte čtyři PNG soubory v `C:\Temp\Barcodes`.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            const string outputFolder = @"C:\Temp\Barcodes";
            Directory.CreateDirectory(outputFolder);

            try
            {
                // 1️⃣ Planet barcode – default (automatic) height
                var planetDefault = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string planetDefaultPath = Path.Combine(outputFolder, "PlanetDefault.png");
                planetDefault.Save(planetDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetDefaultPath}");

                // 2️⃣ RM4SCC barcode – default (automatic) height
                var rm4sccDefault = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccDefault.Parameters.Barcode.XDimension.Pixels = 4;
                string rm4sccDefaultPath = Path.Combine(outputFolder, "RM4SCCDefault.png");
                rm4sccDefault.Save(rm4sccDefaultPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccDefaultPath}");

                // 3️⃣ Planet barcode – explicit 100 px height
                var planetHeight = new BarcodeGenerator(EncodeTypes.Planet, "123456");
                planetHeight.Parameters.Barcode.XDimension.Pixels = 4;
                planetHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string planetHeightPath = Path.Combine(outputFolder, "PlanetHeight100.png");
                planetHeight.Save(planetHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {planetHeightPath}");

                // 4️⃣ RM4SCC barcode – explicit 100 px height
                var rm4sccHeight = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
                rm4sccHeight.Parameters.Barcode.XDimension.Pixels = 4;
                rm4sccHeight.Parameters.Barcode.BarHeight.Pixels = 100;
                string rm4sccHeightPath = Path.Combine(outputFolder, "RM4SCCHeight100.png");
                rm4sccHeight.Save(rm4sccHeightPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Saved: {rm4sccHeightPath}");
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Something went wrong: {ex.Message}");
            }
        }
    }
}
```

### Očekávaný výstup

Po otevření vygenerovaných PNG souborů uvidíte:

| Soubor | Symbologie | Výška | Poznámky k vizuálu |
|--------|------------|-------|--------------------|
| `PlanetDefault.png` | Planet | Automatická (≈ 50 px) | Tenká |

## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak generovat čárový kód – Jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)
- [Jak generovat čárový kód – Konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}