---
category: general
date: 2026-07-15
description: Rychle vytvořte poštovní čárový kód v C#. Tento příklad generátoru čárových
  kódů ukazuje, jak exportovat čárový kód ve formátu PNG pro čárové kódy Planet a
  RM4SCC.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode
- barcode generator example
- barcode png format
- how to generate planet barcode
- export barcode image
language: cs
lastmod: 2026-07-15
og_description: Vytvořte poštovní čárový kód v C# pomocí tohoto krok‑za‑krokem průvodce.
  Naučte se příklad generátoru čárových kódů, který vám umožní exportovat obrázek
  čárového kódu ve formátu PNG.
og_image_alt: Screenshot of a generated postal barcode saved as a PNG file
og_title: Vytvořte poštovní čárový kód v C# – Kompletní průvodce generátorem
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  headline: Create Postal Barcode in C# – Full Generator Example
  type: TechArticle
- description: Create postal barcode in C# quickly. This barcode generator example
    shows how to export barcode PNG format for Planet and RM4SCC barcodes.
  name: Create Postal Barcode in C# – Full Generator Example
  steps:
  - name: Prepare the Output Directory
    text: First things first, we need a folder where the generated PNG files will
      live. Hard‑coding a path works for a demo, but in production you’d probably
      read it from config.
  - name: Generate a Planet Barcode with Automatic Height
    text: Now we get to the heart of the **how to generate planet barcode** part.
      We create a `BarcodeGenerator` instance, set the module width (X‑dimension),
      and let the library decide the bar height.
  - name: Generate an RM4SCC Barcode with Automatic Height
    text: RM4SCC is the Canadian postal barcode format. The code mirrors the Planet
      example, which illustrates the **barcode generator example** pattern you can
      reuse for any supported symbology.
  - name: Generate a Planet Barcode with Fixed Height (100 px)
    text: Sometimes the mailing system demands a strict bar height—maybe the printer
      expects 100 px exactly. Here’s how you **export barcode image** with a forced
      height.
  - name: Generate an RM4SCC Barcode with Fixed Height (100 px)
    text: 'We repeat the fixed‑height approach for RM4SCC. This demonstrates the flexibility
      of the **barcode generator example**: you can mix and match automatic and manual
      settings per symbology.'
  - name: Full Source Listing
    text: Putting it all together, here’s the complete, runnable program. Copy the
      block below into a new console project and hit **Run**.
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: Vytvoření poštovního čárového kódu v C# – Kompletní příklad generátoru
url: /cs/python-java/general/create-postal-barcode-in-c-full-generator-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření poštovního čárového kódu v C# – Kompletní příklad generátoru

Už jste se někdy zamýšleli, jak **vytvořit poštovní čárový kód** v projektu .NET, aniž byste prohledávali nekonečné dokumentace? Nejste v tom sami. Ať už budujete systém štítků pro poštu nebo automatizujete hromadné poštovné, generování čistého PNG souboru s čárovým kódem je nezbytná dovednost. V tomto tutoriálu projdeme kompletním **příkladem generátoru čárových kódů**, který ukazuje přesně, jak **exportovat soubory s obrázkem čárového kódu** ve **formátu PNG**.

Probereme vše od nastavení výstupní složky po úpravu šířky modulu a výšky čáry pro standardy Planet i RM4SCC. Na konci budete mít připravenou konzolovou aplikaci, která vygeneruje čtyři PNG soubory – dva s automatickou výškou a dva s pevnou výškou 100 px. Žádné zbytečnosti, jen praktické řešení, které můžete zkopírovat a vložit.

## Požadavky

Než se pustíme dál, ujistěte se, že máte:

- .NET 6 SDK nebo novější (kód funguje s .NET Core i .NET Framework)
- IDE nebo editor, ve kterém se cítíte dobře (Visual Studio, VS Code, Rider…)
- NuGet balíček Aspose.BarCode for .NET (nainstalujte pomocí `dotnet add package Aspose.BarCode`)

To je vše – žádné další služby, žádné webové API. Pouze lokální projekt v C#.

## Vytvoření poštovního čárového kódu – krok za krokem

Níže rozdělujeme proces do pěti jasných kroků. Každý krok má popisný **H2** nadpis, který obsahuje buď primární, nebo sekundární klíčové slovo, takže rychlým přehlédnutím najdete přesně to, co potřebujete.

### Krok 1: Připravte výstupní adresář

Nejprve potřebujeme složku, kde budou uložené vygenerované PNG soubory. Hard‑kódování cesty funguje pro ukázku, ale v produkci byste pravděpodobně četli hodnotu z konfigurace.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the folder where the barcode images will be saved
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");

        // Ensure the directory exists
        Directory.CreateDirectory(outputDir);
```

> **Tip:** Použití `Path.Combine` dělá kód OS‑agnostickým a `Directory.CreateDirectory` je bezpečné volat i v případě, že složka již existuje.

### Krok 2: Vygenerujte Planet čárový kód s automatickou výškou

Nyní přichází jádro části **jak vygenerovat planet čárový kód**. Vytvoříme instanci `BarcodeGenerator`, nastavíme šířku modulu (X‑dimenzi) a necháme knihovnu rozhodnout o výšce čáry.

```csharp
        // Planet barcode – automatic height
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // module width
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Výčtový typ `EncodeTypes.Planet` říká Aspose, že chceme symbologii Planet, která je běžná pro poštovní služby v mnoha zemích. Protože jsme se nedotkli `BarHeight`, generátor vybere rozumnou výchozí hodnotu, která zachová čitelnost čárového kódu.

### Krok 3: Vygenerujte RM4SCC čárový kód s automatickou výškou

RM4SCC je kanadský formát poštovního čárového kódu. Kód odráží příklad pro Planet, což ilustruje **příklad generátoru čárových kódů**, který můžete znovu použít pro jakoukoli podporovanou symbologii.

```csharp
        // RM4SCC barcode – automatic height
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // keep module width consistent
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);
```

Opět spoleháme na automatickou výšku, což je ideální pro rychlé prototypy nebo když necháte tiskárnu provést škálování.

### Krok 4: Vygenerujte Planet čárový kód s pevnou výškou (100 px)

Někdy poštovní systém vyžaduje přísnou výšku čáry – třeba tiskárna očekává přesně 100 px. Zde je návod, jak **exportovat obrázek čárového kódu** s vynucenou výškou.

```csharp
        // Planet barcode – fixed height of 100 px
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);
```

Nastavení `BarHeight.Pixels` přepíše automatický výpočet. Ostatní nastavení zůstávají stejná, což zajišťuje vizuální konzistenci mezi automatickými i pevně nastavenými obrázky.

### Krok 5: Vygenerujte RM4SCC čárový kód s pevnou výškou (100 px)

Opakujeme přístup s pevnou výškou i pro RM4SCC. To demonstruje flexibilitu **příkladu generátoru čárových kódů**: můžete kombinovat automatické a manuální nastavení podle symbologie.

```csharp
        // RM4SCC barcode – fixed height of 100 px
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // force bar height
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);
    }
}
```

### Kompletní výpis zdrojového kódu

Sestavíme vše dohromady – zde je kompletní, spustitelný program. Zkopírujte blok níže do nového konzolového projektu a spusťte **Run**.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // -----------------------------
        // 1️⃣ Prepare output folder
        // -----------------------------
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // 2️⃣ Planet barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
        planetAuto.Save(Path.Combine(outputDir, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 3️⃣ RM4SCC barcode – automatic height (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccAuto.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 4️⃣ Planet barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
        planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        planetFixed.Save(Path.Combine(outputDir, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // 5️⃣ RM4SCC barcode – fixed height 100 px (PNG export)
        // -------------------------------------------------
        BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccFixed.Save(Path.Combine(outputDir, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in: " + outputDir);
    }
}
```

Po spuštění tohoto programu se vytvoří následující soubory (vše ve **formátu PNG**):

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Každý obrázek je ostrý, černobílý a připravený k tisku nebo dalšímu zpracování.

## Proč tento přístup funguje

- **Konzistence:** Nastavením `XDimension.Pixels` na 4 u všech čárových kódů zaručíte stejnou šířku modulu, což je zásadní pro skenery očekávající konkrétní velikost bodu.
- **Flexibilita:** Stejný kód vám umožní přepínat mezi automatickou a pevnou výškou bez přepisování logiky generátoru – ideální pro řešení s více dopravci.
- **Výkon:** Generování PNG je lehká operace; knihovna Aspose přímo streamuje obrázek na disk, čímž se vyhnete zbytečnému zatížení paměti.
- **Přenositelnost:** Volání `Path.Combine` a `Directory.CreateDirectory` udržují kód napříč platformami, takže stejný zdroj funguje na Windows, Linuxu i macOS.

## Časté problémy a jak se jim vyhnout

| Problém | Proč se vyskytuje | Řešení |
|------|----------------|-----|
| Čárový kód vypadá rozmazaně | Použití příliš nízké X‑dimenze (např. 1 px) | Zvyšte `XDimension.Pixels` na alespoň 3‑4 pro poštovní čárové kódy |
| Skener odmítá obrázek | Výška čáry je příliš malá nebo příliš velká pro tiskárnu | Použijte `BarHeight.Pixels` tak, aby odpovídala specifikacím tiskárny |
| PNG soubor je poškozený | Zapomenutí uzavřít stream (vzácné u Aspose) | Nechte metodu `Save` spravovat uvolnění; vyhněte se ručnímu zacházení se streamem, pokud to není nutné |
| Výstupní složka nebyla nalezena | Hard‑kódovaná cesta ukazuje na neexistující adresář | Vždy před uložením zavolejte `Directory.CreateDirectory` |

## Rozšíření příkladu

Nyní, když ovládáte základy **vytvoření poštovního čárového kódu**, můžete zkusit:

- **Přidání lidsky čitelného textu** pod čárový kód (vlastnost `DisplayText`)
- **Změnu barev** (`ForeColor`, `BackColor`) pro branding
- **Dávkové zpracování** seznamu poštovních kódů z CSV (smyčka přes generátor)
- **Export do jiných formátů** jako SVG nebo PDF (`BarCodeImageFormat.Svg`, `BarCodeImageFormat.Pdf`)

Každé z těchto rozšíření následuje stejný vzor, který byl předveden v tomto **příkladu generátoru čárových kódů**, takže můžete experimentovat bez nutnosti začínat od nuly.

## Závěr

You


## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}