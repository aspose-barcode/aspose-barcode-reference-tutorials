---
category: general
date: 2026-09-19
description: Jak generovat čárový kód pomocí Aspose v C# – krok za krokem průvodce,
  jak rychle a spolehlivě vytvořit čárový kód s Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: cs
lastmod: 2026-09-19
og_description: Jak generovat čárový kód pomocí Aspose v C#. Postupujte podle tohoto
  návodu, vytvořte čárový kód s Aspose, nakonfigurujte MacroPdf417 a uložte jej jako
  PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Jak generovat čárový kód pomocí Aspose – kompletní průvodce C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Jak generovat čárový kód pomocí Aspose v C#
url: /cs/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód pomocí Aspose v C#

Generování čárového kódu v C# je jednoduché, když použijete knihovnu Aspose.BarCode. Tento tutoriál vám ukáže, jak **vytvořit čárový kód pomocí Aspose** krok za krokem, zahrnující formát MacroPdf417, běžná nastavení vzhledu a jak uložit výsledek jako PNG obrázek.

Dozvíte se, jak:

* Nainstalovat a odkazovat na Aspose.BarCode pro .NET  
* Nakonfigurovat specifické vlastnosti MacroPdf417, jako je ID souboru, ID segmentu a kontrolní součet  
* Upravit vizuální možnosti jako X‑dimenzi a počet sloupců  
* Exportovat čárový kód do souboru s obrázkem  

Předchozí zkušenost s Aspose není vyžadována – stačí základní znalost C# a Visual Studio.

## Požadavky

| Požadavek | Podrobnosti |
|-----------|-------------|
| .NET runtime | .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider nebo jakýkoli editor podporující C# |
| Aspose.BarCode | NuGet balíček `Aspose.BarCode` (bezplatná zkušební verze nebo licencovaná verze) |
| Základní znalost C# | Znalost `using` příkazů a inicializace objektů |

Můžete přidat Aspose.BarCode do svého projektu pomocí správce balíčků NuGet:

```bash
dotnet add package Aspose.BarCode
```

## Jak vygenerovat čárový kód v C# – celkový pracovní postup

Proces se skládá ze čtyř logických kroků:

1. **Vytvořte instanci `BarcodeGenerator`** s požadovaným typem kódování (MacroPdf417) a textem, který chcete zakódovat.  
2. **Nastavte běžné možnosti vzhledu** jako X‑dimenzi a počet sloupců.  
3. **Nakonfigurujte specifické vlastnosti MacroPdf417** jako ID souboru, ID segmentu a časové razítko.  
4. **Uložte čárový kód** do formátu souboru dle vašeho výběru (v tomto příkladu PNG).

Každý krok je podrobně vysvětlen níže.

## Krok 1: Vytvořte generátor čárových kódů pro MacroPdf417

Třída `BarcodeGenerator` je vstupním bodem pro všechny úlohy tvorby čárových kódů. Při její instanciaci předáte dva argumenty:

* `EncodeTypes.MacroPdf417` – říká Aspose, aby použil symbologii MacroPdf417.  
* Řetězec dat – text, který bude zakódován uvnitř čárového kódu.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Proč je to důležité:** MacroPdf417 je dvourozměrný čárový kód, který může nést velké množství dat a podporuje makro‑funkce jako segmentaci souboru, což je užitečné při přenosu velkých souborů po částech.

## Krok 2: Nastavte běžné možnosti vzhledu čárového kódu

I když MacroPdf417 má mnoho specializovaných nastavení, stále chcete ovládat vizuální hustotu a rozvržení. Nejčastější parametry jsou:

* **X‑dimension** – šířka nejmenšího modulu (pixel). Menší hodnoty vytvářejí hustší obrázek.  
* **Columns** – počet datových sloupců na řádek; vyšší čísla snižují výšku čárového kódu.

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Tip:** Udržujte `XDimension` mezi 2 a 4 pixely pro většinu scénářů zobrazení na obrazovce. Větší hodnoty zlepšují čitelnost na nízkorozlišovacích tiskárnách, ale zvětšují celkovou velikost obrázku.

## Krok 3: Nakonfigurujte specifické vlastnosti MacroPdf417

MacroPdf417 přidává sadu metadatových polí, která vám umožní rozdělit velký soubor na několik segmentů čárových kódů. Následující vlastnosti jsou běžně vyžadovány:

| Vlastnost | Účel |
|-----------|------|
| `MacroPdf417FileID` | Jedinečný identifikátor celého souboru (max 8 ciferných). |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná od 0). |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů v souboru. |
| `MacroPdf417FileName` | Lidsky čitelný název původního souboru. |
| `MacroPdf417Checksum` | Volitelný CCITT‑16 kontrolní součet pro detekci chyb. |
| `MacroPdf417FileSize` | Velikost původního souboru v bajtech. |
| `MacroPdf417TimeStamp` | Časové razítko, kdy byl soubor vygenerován. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Volitelné řetězce pro identifikaci příjemce/odesílatele. |
| `MacroPdf417Terminator` | Určuje, zda je čárový kód posledním segmentem (`Set`) nebo prostředním (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Proč jsou tato pole užitečná:**  
> *Když potřebujete odeslat velký dokument přes kanál s nízkou šířkou pásma, můžete dokument rozdělit do více čárových kódů MacroPdf417. Příjemce rekonstruuje původní soubor načtením metadat každého segmentu.*

## Krok 4: Uložte vygenerovaný čárový kód jako obrázek

Aspose podporuje mnoho výstupních formátů: PNG, JPEG, BMP, TIFF, SVG a PDF. PNG je bezztrátový formát ideální pro web nebo UI zobrazení.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Po spuštění programu najdete PNG soubor, který vypadá podobně jako ilustrace níže.

![MacroPdf417 čárový kód vygenerovaný pomocí Aspose v C#](placeholder-image.png){.img-fluid alt="jak vygenerovat čárový kód pomocí Aspose v C#"}

> **Očekávaný výstup:** PNG o rozměrech 300 × 150 pixelů zobrazující čárový kód MacroPdf417, který kóduje text „Sample“ spolu s makro‑metadaty, jež jste zadali.

## Kompletní spustitelný příklad

Spojením všech částí získáte kompletní program, který můžete zkopírovat, vložit a spustit:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Program spusťte pomocí `dotnet run` (nebo stiskněte **F5** ve Visual Studiu). Po dokončení ověřte, že PNG soubor existuje a otevře se bez chyb.

## Časté otázky a řešení okrajových případů

### Co když potřebuji jiný formát obrázku?

Aspose podporuje `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` a `Pdf`. Stačí nahradit `BarCodeImageFormat.Png` požadovanou hodnotou výčtu.

### Jak automaticky vygenerovat více segmentů?

Můžete umístit výše uvedený kód do smyčky, při každé iteraci zvýšit `MacroPdf417SegmentID` a aktualizovat řetězec dat. Nezapomeňte, že `MacroPdf417SegmentsCount` musí zůstat konstantní napříč všemi segmenty.

### Co když data překročí kapacitu jednoho symbolu MacroPdf417?

MacroPdf417 je navržen pro velké objemy dat, ale každý čárový kód má teoretické maximum (≈ 1,1 KB na segment). Rozdělte zdrojový soubor na bloky, které se vejdou do tohoto limitu, a každý blok zakódujte jako samostatný segment.

### Je potřeba kontrolní součet vypočítat ručně?

Aspose může automaticky vygenerovat CCITT‑16 kontrolní součet, pokud nastavíte `MacroPdf417Checksum` na `0`. V příkladu jsme pro ilustraci použili pevně zadanou hodnotu; v produkčním kódu byste obvykle nechali knihovnu vypočítat součet.

### Jak mohu změnit barvy popředí/pozadí čárového kódu?

Použijte vlastnosti `BarColor` a `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Závěr

Nyní víte, **jak vygenerovat čárový kód** v C# pomocí Aspose.BarCode a konkrétně, **jak vytvořit čárový kód pomocí Aspose** pro symbologii MacroPdf417. Tutoriál pokryl instalaci, konfiguraci vzhledu a makro‑specifických polí.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak vygenerovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak vygenerovat PDF417 čárový kód jako obrázek v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak vygenerovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}