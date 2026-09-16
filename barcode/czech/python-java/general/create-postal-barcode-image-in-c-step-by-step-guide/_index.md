---
category: general
date: 2026-08-03
description: Rychle vytvořte obrázek poštovního čárového kódu v C#. Naučte se, jak
  generovat poštovní čárový kód, nastavit rozměry čárového kódu a vytvořit Planet
  čárový kód.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- how to generate postal barcode
- generate planet barcode
- how to set barcode dimensions
language: cs
lastmod: 2026-08-03
og_description: Vytvořte obrázek poštovního čárového kódu v C# s tímto kompletním
  tutoriálem; naučte se, jak nastavit rozměry čárového kódu, vygenerovat Planet čárový
  kód a vytvořit čárové kódy RM4SCC.
og_image_alt: Generated postal barcode image saved as PNG using C# BarcodeGenerator
og_title: Vytvořte obrázek poštovního čárového kódu v C# – kompletní programovací
  průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create postal barcode image in C# quickly. Learn how to generate postal
    barcode, set barcode dimensions, and generate a Planet barcode.
  headline: Create postal barcode image in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- postal barcode
title: Vytvořte obrázek poštovního čárového kódu v C# – průvodce krok po kroku
url: /cs/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku poštovního čárového kódu v C# – krok za krokem

Pokud potřebujete **vytvořit obrázek poštovního čárového kódu** v C#, tento návod vám přesně ukáže jak. Pokryjeme **jak generovat poštovní čárový kód**, **jak nastavit rozměry čárového kódu** a jak **vytvořit planet čárový kód** pro běžné poštovní standardy.

Na konci budete mít dva připravené PNG soubory – jeden s Planet čárovým kódem a jeden s RM4SCC čárovým kódem – každý vysoký 100 px. Kromě knihovny Aspose.BarCode pro .NET nejsou potřeba žádné další nástroje.

## Požadavky

* .NET 6 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
* Visual Studio 2022 nebo jakékoli C# IDE
* NuGet balíček **Aspose.BarCode** (knihovna, která poskytuje `BarcodeGenerator`)

## Krok 1: Instalace knihovny čárových kódů

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode`, který obsahuje `BarcodeGenerator` a výčtový typ `EncodeTypes` potřebný pro poštovní čárové kódy.

## Krok 2: Definování výstupní složky

Vytvoření spolehlivé výstupní cesty zabraňuje chybám za běhu, pokud složka neexistuje.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure the directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);
```

*Proč je to důležité*: `Directory.CreateDirectory` je idempotentní – vytvoří složku jen pokud ještě neexistuje, čímž se vyhneme výjimkám při dalších spuštěních.

## Krok 3: Nastavení běžných rozměrů čárového kódu

Nastavení X‑dimenze (šířka jedné čáry) a celkové výšky čáry vám umožní řídit vizuální velikost generovaného obrázku.

```csharp
        // Common dimension settings
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Desired barcode height
```

**Jak nastavit rozměry čárového kódu**: Vlastnost `Parameters.Barcode.XDimension.Pixels` určuje šířku úzké čáry, zatímco `Parameters.Barcode.BarHeight.Pixels` určuje celkovou výšku. Přizpůsobte tyto hodnoty podle specifikací vaší poštovní služby.

## Krok 4: Vytvoření Planet čárového kódu

Planet je široce používaný poštovní čárový kód ve Spojeném království. Následující kód vytvoří Planet čárový kód vysoký 100 px a uloží jej jako PNG.

```csharp
        // Step 4: Generate Planet barcode
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
```

**Proč to funguje**: `EncodeTypes.Planet` říká generátoru, aby použil symbologii Planet. Metoda `Save` zapíše PNG soubor na zadanou cestu a zachová rozměry, které jsme nastavili dříve.

## Krok 5: Vytvoření RM4SCC čárového kódu

RM4SCC je nizozemský standard poštovních čárových kódů. Níže uvedený kód odráží příklad s Planet, demonstrující **jak generovat poštovní čárový kód** jiného typu se stejnými rozměry.

```csharp
        // Step 5: Generate RM4SCC barcode
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;

        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
```

Oba PNG soubory se nyní nacházejí ve složce `Barcodes`. Po jejich otevření uvidíte čisté, 100 px vysoké čárové kódy připravené k tisku nebo vložení do dokumentů.

## Kompletní zdrojový kód

Níže je kompletní spustitelný program, který **vytváří soubory s obrázkem poštovního čárového kódu** pro standardy Planet i RM4SCC.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class PostalBarcodeDemo
{
    static void Main()
    {
        // Ensure output directory exists
        string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Dimension settings – reusable for all barcodes
        const int xDimensionPixels = 4;   // Width of a single bar
        const int barHeightPixels = 100; // Height of the barcode

        // ---- Generate Planet barcode ----
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        planetGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string planetPath = Path.Combine(outputFolder, "PostalPlanetBarHeight100Pixels.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);

        // ---- Generate RM4SCC barcode ----
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = xDimensionPixels;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = barHeightPixels;
        string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCBarHeight100Pixels.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated:");
        Console.WriteLine($"• {planetPath}");
        Console.WriteLine($"• {rm4sccPath}");
    }
}
```

### Očekávaný výstup

Spuštěním programu se vypíšou cesty k souborům a vytvoří se dva PNG soubory:

```
Barcodes/
 ├─ PostalPlanetBarHeight100Pixels.png
 └─ PostalRM4SCCBarHeight100Pixels.png
```

Každý obrázek má výšku 100 px, s úzkou čárou širokou 4 pixely, což odpovídá nastaveným rozměrům.

## Praktické tipy a běžné úskalí

* **Oprávnění ke složce** – Pokud program běží pod omezeným účtem, ujistěte se, že cílová složka je zapisovatelná.
* **Různé rozměry** – Pro vytvoření vyššího čárového kódu zvyšte `barHeightPixels`. Pro jemnější rozlišení snižte `xDimensionPixels`, ale ponechte hodnotu ≥ 2, aby nedocházelo k artefaktům při vykreslování.
* **Další poštovní symbologie** – Aspose.BarCode také podporuje `EncodeTypes.Postnet` a `EncodeTypes.AustralianPost`. Vyměňte hodnotu `EncodeTypes` a zachovejte stejnou logiku rozměrů.
* **Formát obrázku** – Použijte `BarCodeImageFormat.Jpeg` pro menší velikost souboru, pokud není vyžadována bezztrátová kvalita.

## Závěr

Nyní víte, jak **vytvořit soubory s obrázkem poštovního čárového kódu** v C# nastavením rozměrů, výběrem správné symbologie a uložením výsledku jako PNG. Návod pokryl **jak generovat poštovní čárový kód**, předvedl **vytvoření Planet čárového kódu** a vysvětlil **jak nastavit rozměry čárového kódu** pro konzistentní výstup.

Dále můžete prozkoumat **přizpůsobení barev čárových kódů**, přidání **čitelného textu** nebo integraci obrázků do PDF faktur. Stejný vzor platí pro jakýkoli jiný typ čárového kódu podporovaný knihovnou Aspose.BarCode, což vám umožní rozšířit toto řešení na kompletní workflow poštovní automatizace.

## Co byste se měli naučit dál?

Následující návody pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat čárový kód – jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat čárový kód v Java – Australia Post Barcode s Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}