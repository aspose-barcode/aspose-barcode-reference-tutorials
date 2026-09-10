---
category: general
date: 2026-09-10
description: Jak nastavit čárový kód v C# pomocí generátoru čárových kódů. Nastavte
  šířku modulu čárového kódu, generujte obrázky čárových kódů a naučte se, jak uložit
  soubory čárových kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: cs
lastmod: 2026-09-10
og_description: Jak nastavit čárový kód v C# pomocí generátoru čárových kódů. Naučte
  se upravit šířku modulu, vygenerovat čárový kód a efektivně uložit obrázek čárového
  kódu.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Jak nastavit vlastnosti čárového kódu pomocí generátoru čárových kódů v
  C#
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Jak nastavit vlastnosti čárového kódu pomocí generátoru čárových kódů v C#
url: /cs/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit vlastnosti čárového kódu pomocí C# Barcode Generator

Nastavení vlastností čárového kódu je nezbytné, když potřebujete přesnou kontrolu nad vizuálním stylem čárového kódu. Tento průvodce vám ukáže, jak vygenerovat Planet čárový kód, upravit šířku modulu čárového kódu a uložit obrázek čárového kódu pomocí C# Barcode Generator.

Uvidíte kompletní, spustitelný příklad, který pokrývá každý krok od vytvoření objektu čárového kódu až po zápis PNG souborů na disk. Není potřeba žádná externí dokumentace – stačí kód níže a knihovna Aspose.BarCode (nebo jakékoli kompatibilní SDK pro čárové kódy). Na konci tutoriálu budete schopni odpovědět na otázky jako „jak vygenerovat čárový kód s vlastními rozměry?“ a „jak uložit čárový kód v různých formátech?“.

## Požadavky

* .NET 6.0 nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* NuGet balíček **Aspose.BarCode** (nebo jiná knihovna, která poskytuje `BarcodeGenerator`)  

Balíček můžete přidat pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

## Jak nastavit šířku modulu čárového kódu

*Šířka modulu* (také nazývaná X‑dimenze) určuje velikost v pixelech každého úzkého pruhu v čárovém kódu. Nastavením této hodnoty můžete ovládat celkovou velikost a čitelnost obrázku.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Proč je to důležité*: Větší X‑dimenze vytváří větší čárový kód, který je snáze čitelný skenery z větší vzdálenosti, zatímco menší hodnota snižuje velikost souboru při vykreslování na obrazovce.

## Generování čárového kódu s vyplněnými pruhy

Výchozí styl pro Planet čárový kód používá **vyplněné pruhy** (plné černé pruhy). Následující kód vytvoří obrázek a uloží jej jako PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Výsledek**: `PostalPlanetFilledBars.png` obsahuje standardní Planet čárový kód, kde je každý pruh vyplněný.

## Vytvoření čárového kódu s prázdnými pruhy

Někdy potřebujete čárový kód, který zobrazuje pouze obrysy pruhů (prázdné pruhy). K tomu duplikujete generátor, zachováte stejnou šířku modulu a vypnete příznak `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Výsledek**: `PostalPlanetEmptyBars.png` zobrazuje stejná data, ale s nevyplněnými pruhy, což je užitečné pro dokumenty s bohatým designem, kde chcete, aby se čárový kód sloučil s pozadím.

## Jak uložit čárový kód v různých formátech

Metoda `Save` přijímá libovolný formát podporovaný SDK, například **Jpeg**, **Bmp**, **Gif** nebo **Svg**. Změna formátu vyžaduje pouze výměnu hodnoty výčtu `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Tip*: Použijte SVG, když potřebujete vektorovou grafiku, která se škáluje bez pixelace, zejména pro PDF připravené k tisku.

## Kompletní, spustitelný příklad

Sestavením všech částí dohromady získáte samostatný program, který můžete vložit do konzolové aplikace.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Očekávaný výstup**

| File name                     | Description                              |
|-------------------------------|------------------------------------------|
| `PostalPlanetFilledBars.png`  | Planet čárový kód s plnými černými pruhy |
| `PostalPlanetEmptyBars.png`   | Stejná data, pruhy vykreslené jako obrysy |
| `PostalPlanet.svg`            | Vektorová verze pro škálování bez ztráty  |

Spusťte program, otevřete vygenerované soubory a ověřte, že čárové kódy odpovídají číselnému řetězci „123456“.

## Běžné varianty a okrajové případy

| Situace                               | Úprava                                                                 |
|---------------------------------------|------------------------------------------------------------------------|
| Potřeba silnějšího čárového kódu      | Zvyšte `XDimension.Pixels` (např. `8`)                                 |
| Potřeba menší velikosti souboru       | Použijte `BarCodeImageFormat.Jpeg` nebo snižte X‑dimenzi               |
| Generování jiných symbolů             | Nahraďte `EncodeTypes.Planet` za `EncodeTypes.Code128`, `QR` atd.      |
| Tisk na vysoce rozlišených tiskárnách | Uložte jako `BarCodeImageFormat.Tiff` pro bezztrátový rastrový výstup   |
| Spouštění na serveru bez grafického rozhraní | Kód UI není vyžadován; generátor funguje v kontextu konzole nebo služby |

**Pro tip**: Vždy ověřte vygenerovaný čárový kód pomocí skeneru nebo ověřovacího nástroje před nasazením do produkce. Nesprávná šířka modulu nebo formát může způsobit selhání skenování.

## Závěr

Nyní víte, jak nastavit vlastnosti čárového kódu pomocí C# Barcode Generator, jak ovládat šířku modulu čárového kódu, jak generovat jak vyplněné, tak prázdné styly pruhů a jak uložit čárový kód ve formátech PNG nebo SVG. Tyto kroky vám poskytují pevný základ pro přidání tvorby čárových kódů do jakékoli .NET aplikace.

Dále prozkoumejte související témata, jako je **c# barcode generator performance tuning**, **embedding barcodes in PDF documents** a **creating QR codes with custom colors**. Experimentujte s různými `EncodeTypes` a formáty obrázků, abyste našli nejlepší řešení pro váš projekt.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak uložit čárový kód v C# – Generovat PDF417 čárové kódy](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tutorial generátoru čárových kódů: Jak vygenerovat PDF417 čárový kód v C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Jak nastavit úroveň chyby v PDF417 čárovém kódu – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}