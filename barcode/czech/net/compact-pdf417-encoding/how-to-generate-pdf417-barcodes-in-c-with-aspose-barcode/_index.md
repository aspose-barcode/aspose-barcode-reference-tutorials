---
category: general
date: 2026-09-10
description: Jak generovat čárové kódy PDF417 v C# pomocí Aspose.BarCode. Postupujte
  podle krok‑za‑krokem průvodce, jak vytvořit Macro PDF417, upravit parametry a exportovat
  jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: cs
lastmod: 2026-09-10
og_description: Jak generovat čárové kódy PDF417 v C# s Aspose.BarCode. Naučte se
  celý pracovní postup od nastavení až po uložení makro PDF417 PNG obrázku.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Jak generovat čárové kódy PDF417 v C# – kompletní průvodce Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Jak generovat čárové kódy PDF417 v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárové kódy v C# pomocí Aspose.BarCode

Pokud potřebujete **jak generovat pdf417** v projektu .NET, tento tutoriál ukazuje kompletní pracovní postup. Uvidíte, jak vytvořit Macro PDF417 čárový kód, jemně doladit jeho nastavení a exportovat výsledek jako PNG obrázek – vše s Aspose.BarCode pro .NET.

Generování PDF417 čárových kódů je běžné v logistice, prodeji vstupenek a zabezpečených pracovních postupech s dokumenty. Na konci tohoto průvodce budete mít připravený generátor čárových kódů v C#, který můžete vložit do jakékoli aplikace.

## Co budete potřebovat

- **Visual Studio 2022** (nebo jakékoli C# IDE)  
- **.NET 6.0** nebo novější  
- **Aspose.BarCode for .NET** NuGet balíček (`Install-Package Aspose.BarCode`)  
- Základní znalost syntaxe C#  

> **Pro tip:** Použijte nejnovější verzi Aspose.BarCode, abyste získali nejnovější funkce Macro PDF417 a opravy chyb.

---

## Jak generovat PDF417 čárové kódy v C#

Níže je plně spustitelný příklad, který vytváří **Macro PDF417** čárový kód, konfiguruje jeho makro‑specifické pole a uloží obrázek.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Proč je každý krok důležitý

1. **Vytvořit generátor Macro PDF417** – `EncodeTypes.MacroPdf417` říká Aspose.BarCode, aby použil makro verzi PDF417, která podporuje rozdělení velkého payloadu do více symbolů.  
2. **Upravit základní vzhled** – `XDimension` řídí šířku modulu (tečky); `Columns` určuje, kolik sloupců bude každý symbol obsahovat, což ovlivňuje jak velikost, tak čitelnost.  
3. **Nastavit makro‑specifická pole** – Tyto vlastnosti (`MacroPdf417FileID`, `MacroPdf417SegmentID`, atd.) jsou vyžadovány specifikací PDF417 macro pro znovu‑sestavení původních dat na straně skeneru.  
4. **Exportovat obrázek** – `BarCodeImageFormat.Png` poskytuje bezztrátový obrázek, který dobře funguje pro web, tisk a mobilní scénáře.

## Nastavení Aspose.BarCode pro .NET (generátor čárových kódů v C#)

Než budete moci spustit výše uvedený kód, musíte do svého projektu přidat knihovnu Aspose.BarCode:

```bash
dotnet add package Aspose.BarCode
```

*NuGet balíček obsahuje všechny závislosti, takže nejsou potřeba žádné další DLL soubory.*

Pokud cílíte na .NET Framework, stejný příkaz `Install-Package Aspose.BarCode` funguje z konzole Package Manager Console.

### Časté úskalí

- **Chybějící licence** – Ve výchozím nastavení Aspose běží v evaluačním režimu, který přidává vodoznak do čárového kódu. Zaregistrujte licenční soubor (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`), aby byl odstraněn.  
- **Nesprávné `EncodeTypes`** – Použití `EncodeTypes.Pdf417` místo `EncodeTypes.MacroPdf417` bude ignorovat všechna makro pole, což rozbije rekonstrukci více segmentů.

## Konfigurace parametrů Macro PDF417 čárového kódu

Makro pole vám umožní rozdělit velký dokument do několika PDF417 symbolů. Zde je rychlý přehled:

| Vlastnost | Účel | Typický rozsah |
|----------|------|----------------|
| `MacroPdf417FileID` | Jedinečný identifikátor pro celý soubor | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná od 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů v souboru | 1‑255 |
| `MacroPdf417FileName` | Volitelný čitelný název | 0‑255 characters |
| `MacroPdf417Checksum` | CCITT‑16 kontrolní součet pro detekci chyb | 0‑65535 |
| `MacroPdf417FileSize` | Původní velikost souboru v bajtech | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Časové razítko vytvoření (volitelné) | `DateTime` value |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Volitelná metadata pro směrování | Any string |
| `MacroPdf417Terminator` | Indikuje poslední segment (`Set` nebo `Unset`) | `Pdf417MacroTerminator` enum |

Upravte tyto hodnoty tak, aby odpovídaly datům, která kódujete. Například pokud rozdělíte 2 MB soubor na 20 segmentů, nastavte `MacroPdf417FileSize` na `2_000_000` a `MacroPdf417SegmentsCount` na `20`.

## Export čárového kódu jako PNG obrázek (export obrázku čárového kódu)

Ukládání čárového kódu jako PNG je nejčastější exportní formát, protože zachovává ostré hrany a podporuje průhlednost. Aspose.BarCode také podporuje JPEG, BMP, GIF a TIFF – vyberte ten, který vyhovuje vašemu následnému procesu.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Tipy pro vysokou kvalitu výstupu**

- Zvyšte `XDimension.Pixels` pro větší moduly při tisku na vysoce rozlišených médiích.  
- Použijte `BarCodeImageFormat.Tiff` s kompresí CCITT Group 4 pro fax‑kompatibilní PDF.  
- Nastavte `generator.Parameters.ImageOptions.Resolution`, pokud potřebujete konkrétní DPI (např. 300 dpi pro tisk).

## Testování a řešení problémů s vaším PDF417 čárovým kódem

1. **Vizuální ověření** – Otevřete `MacroPdf417.png` v libovolném prohlížeči obrázků. Měli byste vidět sadu svislých pruhů s malým textovým popiskem (kódovaná data).  
2. **Test skeneru** – Použijte mobilní aplikaci pro skenování čárových kódů, která podporuje PDF417. Naskenujte obrázek; aplikace by měla vrátit původní „Sample text“ plus makro metadata (ID souboru, ID segmentu, atd.).  
3. **Zpracování chyb** – Pokud skener hlásí „checksum error“, dvojitě zkontrolujte `MacroPdf417Checksum` a ujistěte se, že `MacroPdf417Terminator` je nastaven správně na posledním segmentu.  
4. **Výkon** – Generování mnoha segmentů ve smyčce může být náročné na CPU. Znovu použijte jedinou instanci `BarcodeGenerator` a mezi ukládáními pouze aktualizujte makro pole, aby se zvýšila propustnost.

## Závěr

Nyní víte **jak generovat PDF417** čárové kódy v C# pomocí Aspose.BarCode, od instalace knihovny po konfiguraci Macro PDF417 polí a export čistého PNG obrázku. Kompletní řešení ukazuje:

- Nastavení **generátoru čárových kódů v C#** s typem Macro PDF417  
- Přizpůsobení **parametrů PDF417 čárového kódu** pro data rozdělená do více segmentů  
- Provádění **exportu obrázku čárového kódu** pro následné použití  

Odtud můžete zkoumat pokročilá témata, jako je vložení čárového kódu do PDF dokumentů, generování QR‑kódových doprovodných prvků nebo automatizace hromadného zpracování velkých souborů.

**Další kroky**

- Vyzkoušejte různé hodnoty `BarCodeImageFormat` (např. `Tiff` pro vysoce rozlišený tisk).  
- Kombinujte Macro PDF417 s dalšími symbologiemi ve stejném dokumentu pomocí `generator.Parameters.Barcode.Symbology`.  
- Prohlédněte si [Aspose.BarCode dokumentaci](https://docs.aspose.com/barcode/net/) pro podrobnější možnosti přizpůsobení, jako je úroveň opravy chyb a režimy kódování.

Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Generovat čárový kód s textem – Kompletní průvodce PDF417 Macro](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [upravit velikost čárového kódu – C# průvodce generováním PDF417 čárových kódů](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Jak generovat PDF417 čárový kód – Kompletní programovací průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}