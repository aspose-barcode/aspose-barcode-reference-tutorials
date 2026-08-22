---
category: general
date: 2026-08-22
description: Návod na generátor čárových kódů v C# ukazuje, jak vytvořit makro PDF417
  čárový kód s metadaty a uložit jej jako PNG pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: cs
lastmod: 2026-08-22
og_description: Generátor čárových kódů C# vám umožní vytvořit makro PDF417 čárový
  kód s kompletními metadaty na úrovni souboru a exportovat jej jako PNG. Postupujte
  podle tohoto návodu k implementaci řešení.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: generátor čárových kódů C# – vytvářejte makro PDF417 čárové kódy krok po
  kroku
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak použít generátor čárových kódů v C# pro Macro PDF417
url: /cs/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generátor čárových kódů C# pro Macro PDF417

Pokud potřebujete **barcode generator C#**, který dokáže vytvořit symbol Macro PDF417 s metadaty na úrovni souboru, tento průvodce poskytuje kompletní, připravené řešení. Uvidíte, jak nastavit vzhled čárového kódu, vložit makro informace jako ID souboru a počet segmentů a nakonec výsledek uložit jako PNG obrázek.

Příklad používá knihovnu Aspose.BarCode, široce používanou **C# barcode library**, která podporuje kompletní sadu funkcí PDF417. Nevyžaduje žádné externí služby a kód funguje s .NET 6 nebo novějším.

## Požadavky

* .NET 6 SDK (nebo jakákoli novější verze) nainstalována.
* Visual Studio 2022, VS Code nebo jiné C# IDE.
* Odkaz na NuGet balíček **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Znalost základní syntaxe C# a konceptu čárových kódů PDF417 vám pomůže sledovat kroky, ale tutoriál podrobně vysvětluje každou konfigurační možnost.

## Co tutoriál pokrývá

* Inicializace instance **barcode generator C#** pro formát Macro PDF417.  
* Úprava vizuálních parametrů, jako je X‑dimenze a počet sloupců.  
* Poskytnutí polí na úrovni souboru Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender a terminator.  
* Uložení vygenerovaného symbolu jako PNG soubor.  
* Tipy pro řešení okrajových případů, jako jsou velké velikosti souborů nebo vlastní časové značky.

Na konci tohoto článku budete mít samostatný program, který vytváří plně kompatibilní Macro PDF417 čárový kód.

## Krok 1: Vytvořte instanci barcode generator C# 

Prvním krokem je vytvořit instanci `BarcodeGenerator` s hodnotou výčtu `EncodeTypes.MacroPdf417` a textem, který chcete zakódovat. Konstruktor také přijímá řetězec payload, který se stane datovou částí makro čárového kódu.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Proč je to důležité** – Příznak `EncodeTypes.MacroPdf417` říká Aspose.BarCode, aby symbol považoval za makro čárový kód, což umožňuje následná extra pole. Bez tohoto příznaku by knihovna generovala běžný PDF417 čárový kód bez metadat na úrovni souboru.

## Krok 2: Upravit základní vzhled čárového kódu (vizuální nastavení PDF417)

Vizální jasnost je klíčová pro spolehlivé skenování. Dva běžné parametry jsou šířka modulu (`XDimension`) a počet sloupců. Nastavením těchto hodnot se vyvažuje velikost a čitelnost.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` řídí šířku každého černého/bílého pruhu. Hodnota **2** funguje dobře pro většinu tiskáren štítků.
* `Pdf417.Columns` určuje, kolik sloupců čárový kód použije. Pět sloupců vytváří kompaktní symbol bez ztráty kapacity dat.

## Krok 3: Definujte informace na úrovni souboru Macro PDF417

Macro PDF417 rozšiřuje standardní formát PDF417 o pole, která popisují, jak je velký soubor rozdělen do více segmentů čárových kódů. Poskytnutí těchto polí zajišťuje, že následné skenery dokážou rekonstruovat původní soubor.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` musí být stejný pro každý segment patřící ke stejnému logickému souboru.
* `MacroPdf417SegmentID` se zvyšuje od **0** do `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` informuje dekodér, kolik částí má očekávat.
* `MacroPdf417FileName` je volitelný, ale užitečný pro lidsky čitelnou identifikaci.

## Krok 4: Nastavte další makro metadata

Kromě základních informací o souboru specifikace umožňuje extra pole jako checksum, file size, timestamp, addressee, sender a terminátor. Vyplnění těchto polí zvyšuje integritu dat a sledovatelnost.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` poskytuje 16‑bitový CCITT checksum pro celý soubor; dekodér může po rekonstrukci ověřit integritu.
* `MacroPdf417FileSize` by měl odrážet přesný počet bajtů původního souboru; hodnoty větší než `2^31‑1` vyžadují 64‑bitové pole, které Aspose zpracuje automaticky.
* `MacroPdf417TimeStamp` zaznamenává, kdy byl čárový kód vygenerován. Použijte UTC, aby nedošlo k nejasnostem časových pásem.
* `MacroPdf417Addressee` a `MacroPdf417Sender` jsou volně formátované řetězce, které mohou uchovávat informace o směrování.
* `MacroPdf417Terminator` signalizuje, že se jedná o poslední segment; nastavte na `Set` pro poslední část, jinak ponechte výchozí (`NotSet`).

**Tip pro okrajové případy** – Pokud velikost souboru překročí 4 GB, rozdělte obsah do více makro segmentů a upravte `SegmentsCount` podle toho. Knihovna zvládne pole velké velikosti bez přetečení.

## Krok 5: Uložte čárový kód jako PNG obrázek

Poslední krok zapíše vygenerovaný symbol na disk. PNG zachovává přesné rozměry pixelů a je široce podporován skenovacím hardwarem.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, do které může běžící proces zapisovat. Výčet `BarCodeImageFormat.Png` zajišťuje bezztrátový výstup.

**Proč PNG?** – Rasterové formáty jako PNG udržují hrany modulů ostré, což je nezbytné pro skenery, které spoléhají na vysoký kontrast hran. Pokud potřebujete vektorový formát, Aspose také podporuje `Pdf` a `Svg`.

## Kompletní spustitelný příklad

Níže je kompletní program, který můžete zkopírovat do konzolové aplikace. Obsahuje potřebné `using` direktivy a metodu `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Očekávaný výstup

Spuštěním programu se vytvoří soubor s názvem **MacroPdf417.png** v pracovním adresáři projektu. Otevření obrázku zobrazí kompaktní PDF417 čárový kód s vloženými makro poli. Skenováním obrázku čtečkou kompatibilní s PDF417 (např. ZXing, Aspose.BarCode decoder) se vrátí původní payload `"Sample text"` spolu s makro metadaty.

## Časté otázky a řešení problémů

| Otázka | Odpověď |
|----------|--------|
| *Co když je čárový kód příliš velký pro cílový štítek?* | Snižte `XDimension.Pixels` nebo zvyšte `Pdf417.Columns`. Oba parametry ovlivňují celkovou velikost. |
| *Mohu generovat vektorový obrázek místo PNG?* | Ano. Zavolejte `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` pro škálovatelný výstup. |
| *Jak ověřím kontrolní součet po skenování?* | Dekodér Aspose.BarCode automaticky ověřuje `MacroPdf417Checksum` a hlásí nesrovnalosti v objektu `MacroPdf417Result`. |
| *Je knihovna kompatibilní s .NET Core?* | NuGet balíček podporuje .NET Standard 2.0+, což zahrnuje .NET Core, .NET 5, .NET 6 a novější. |
| *Co když potřebuji vložit binární data místo textu?* | Převěďte binární payload na Base64 nebo použijte přetížení `EncodeTypes.MacroPdf417`, které přijímá pole bajtů. |

## Profesionální tipy pro produkční použití

* **Cache generátoru** – 

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}