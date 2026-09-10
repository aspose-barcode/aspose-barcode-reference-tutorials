---
category: general
date: 2026-07-21
description: Jak rychle generovat čárový kód pomocí Aspose.BarCode pro C#. Naučte
  se vytvářet čárové kódy s Aspose, upravovat poměry stran a během několika minut
  ukládat PNG soubory.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: cs
lastmod: 2026-07-21
og_description: Jak generovat čárový kód pomocí Aspose.BarCode pro C#. Tento krok‑za‑krokem
  průvodce vám ukáže, jak vytvořit čárový kód s Aspose, upravit nastavení a exportovat
  obrázky.
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: Jak generovat čárový kód v C# – Rychlý tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: Jak generovat čárový kód v C# – Kompletní průvodce Aspose.BarCode
url: /cs/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód v C# – Kompletní průvodce Aspose.BarCode

Už jste se někdy zamýšleli **jak generovat čárový kód** v .NET aplikaci, aniž byste se museli potýkat s nízkoúrovňovým kódem obrázků? Nejste v tom sami. V mnoha podnikových projektech potřebujeme **vytvořit čárový kód pomocí Aspose** pro faktury, přepravní štítky nebo sledování zásob a knihovna to dělá překvapivě snadné.

V tomto tutoriálu projdeme reálným příkladem, který vytvoří DataBar Stacked Omnidirectional čárový kód, upraví jeho poměr stran a uloží dva PNG soubory. Na konci budete mít připravený spustitelný konzolový program a jasné pochopení klíčových vlastností, které můžete ovládat.

## Co se naučíte

- Nastavit Aspose.BarCode v C# projektu (NuGet, základy licencování)
- Inicializovat **DataBar stacked omnidirectional** generátor
- Upravit X‑dimenzi (velikost pixelu) a poměr stran
- Uložit čárový kód jako PNG obrázky
- Rozšířit příklad na jiné typy čárových kódů nebo výstupní formáty

Předchozí zkušenost s Aspose není vyžadována – stačí fungující .NET 6 (nebo novější) SDK a oblíbené IDE.

## Požadavky

| Požadavek | Důvod |
|-------------|--------|
| .NET 6 SDK nebo novější | Moderní jazykové funkce a snadné vytvoření projektu |
| Visual Studio 2022 (nebo VS Code) | IDE pro vývoj a ladění |
| Aspose.BarCode for .NET NuGet balíček | Hlavní knihovna, která provádí těžkou práci |
| Platná Aspose licence (nebo zkušební) | Odstraňuje vodoznak hodnocení a odemyká všechny funkce |

Pokud jste ještě nenainstalovali NuGet balíček, spusťte:

```bash
dotnet add package Aspose.BarCode
```

Nyní, když je vše připraveno, ponořme se do kódu.

## Krok 1: Vytvořte nový konzolový projekt

Nejprve vytvořte novou konzolovou aplikaci. Otevřete terminál a zadejte:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Tím se vytvoří `Program.cs` a soubor `.csproj`. Otevřete projekt ve svém editoru a přidejte odkaz na Aspose, jak je ukázáno výše.

## Krok 2: Inicializujte BarcodeGenerator

Srdcem procesu je třída `BarcodeGenerator`. Požádáme o **DataBar stacked omnidirectional** symbologii a předáme jí ukázkový řetězec GS1‑128.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**Proč je to důležité:** `EncodeTypes.DatabarStackedOmniDirectional` vytváří kompaktní, vysoce hustý čárový kód ideální pro malé štítky. Datový řetězec používá GS1 identifikátor aplikace `(01)` pro hodnotu GTIN‑14, kterou očekává mnoho systémů dodavatelského řetězce.

## Krok 3: Upravit poměr stran a uložit obrázky

Aspose.BarCode vám umožňuje upravit **poměr stran** symbolů DataBar pomocí `Parameters.Barcode.DataBar.AspectRatio`. Změna této hodnoty mění vizuální poměr šířky k výšce, což může být klíčové pro umístění čárového kódu na štítek pevné velikosti.

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**Vysvětlení každého řádku**

- `outputPath` ukazuje na složku, kam budou uloženy PNG soubory. `Directory.CreateDirectory` zajišťuje, že složka existuje i na novém počítači.
- `AspectRatio = 15` dává relativně vysoký čárový kód; `AspectRatio = 30` jej roztahuje vodorovně.
- `generator.Save(...)` zapíše obrázek na disk. Výčet `BarCodeImageFormat.Png` zajišťuje bezztrátovou kvalitu.
- `Console.WriteLine` vám poskytne okamžitou zpětnou vazbu při spuštění programu.

### Očekávaný výstup

Když spustíte `dotnet run`, měli byste vidět něco jako:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

Otevřete oba PNG soubory vedle sebe; všimnete si, že druhý obrázek je výrazně širší při zachování stejné výšky. Oba obrázky jsou čitelné standardními čtečkami čárových kódů.

## Krok 4: Spusťte kompletní příklad

Zde je **úplný, spustitelný zdroj** v jednom bloku pro pohodlné zkopírování:

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Zkompilujte a spusťte:

```bash
dotnet run
```

Voilà—dvě perfektně vykreslené PNG čárové kódy se objeví v `GeneratedBarcodes/`.

## Krok 5: Rozšíření příkladu (volitelné)

Nyní, když **víte, jak generovat čárový kód** pomocí Aspose, můžete se ptát: *Co ještě mohu upravit?* Zde je několik rychlých nápadů:

| Vlastnost | Co dělá | Typické použití |
|----------|--------------|------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | Mění velikost lidsky čitelného textu | Větší písmo pro ruční skenery |
| `generator.Parameters.Barcode.ImageFormat` | Globální výstupní formát (PNG, JPEG, BMP, atd.) | JPEG pro web‑přátelskou velikost |
| `generator.Parameters.Barcode.Color` | Nastavuje barvu popředí | Kategorie kódované barvou |
| `generator.Save(..., BarCodeImageFormat.Svg)` | Vektorový výstup pro nekonečné škálování | PDF připravené k tisku |

Pro experimentování stačí přidat odpovídající řádky před každé volání `Save`.

## Časté úskalí a profesionální tipy

- **Umístění licence:** Pokud používáte placenou licenci, zavolejte `License license = new License(); license.SetLicense("Aspose.BarCode.lic");` před vytvořením generátoru. Zapomenutí této akce zanechá na obrázku vodoznak.
- **Neplatný datový řetězec:** Symbologie DataBar očekávají číselná GS1 data. Poskytnutí alfabetických znaků vyvolá `ArgumentException`.
- **Bezpečnost vláken:** Instance `BarcodeGenerator` **nejsou** bezpečné pro více vláken. Vytvořte novou instanci pro každé vlákno, pokud generujete čárové kódy paralelně.
- **Velikost obrázku vs. schopnost skeneru:** Velmi vysoká hodnota `XDimension.Pixels` může vytvořit obrovský obrázek, který některé skenery obtížně čtou. Otestujte s vaším cílovým hardwarem.

## Závěr

Právě jsme prošli **jak generovat čárový kód** v C# pomocí Aspose.BarCode, od nastavení projektu po uložení dvou obrázků s různými poměry stran. Klíčové kroky – inicializace generátoru, nastavení X‑dimenze a poměru stran a volání `Save` – tvoří opakovatelný vzor, který můžete použít pro jakýkoli typ čárového kódu, který Aspose podporuje.

Nyní můžete **vytvářet čárové kódy pomocí Aspose** pro faktury, přepravní štítky nebo inventární značky a máte pevný základ pro zkoumání pokročilejších funkcí, jako jsou barvy, vlastní písma nebo výstup SVG. Klidně upravujte kód, experimentujte s dalšími `EncodeTypes` a integrujte generátor do vašich stávajících služeb.

Máte otázky nebo chcete vidět konkrétní styl čárového kódu? Zanechte komentář níže a šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak přizpůsobit čárový kód – poměr stran Codablock F pomocí Aspose.BarCode pro .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [Jak generovat DataMatrix čárové kódy (ECC 200) pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}