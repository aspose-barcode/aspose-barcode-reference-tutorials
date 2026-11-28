---
category: general
date: 2026-11-27
description: Vytvořte obrázek čárového kódu v C# a uložte jej ve formátu PNG pomocí
  Aspose.BarCode – krok za krokem průvodce.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: cs
lastmod: 2026-11-27
og_description: Vytvořte obrázek čárového kódu v C# a uložte jej ve formátu PNG pomocí
  Aspose.BarCode. Postupujte podle tohoto tutoriálu a krok po kroku vygenerujte makro
  PDF417 čárový kód.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Vytvořte obrázek čárového kódu a uložte jej ve formátu PNG v C# – kompletní
  průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Vytvořit obrázek čárového kódu a uložit ve formátu PNG v C#
url: /cs/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu a uložení ve formátu PNG v C#

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento průvodce vám ukáže, jak vygenerovat Macro PDF417 čárový kód a **uložit obrázek ve formátu PNG** pomocí Aspose.BarCode. Získáte kompletní, spustitelný příklad a vysvětlení každého nastavení, abyste mohli kód přizpůsobit svým požadavkům.

Generování čárového kódu není jen volání jediné metody; musíte nakonfigurovat velikost modulu, makro parametry a výstupní formát. Na konci tohoto tutoriálu pochopíte, proč je každá vlastnost důležitá, jak řešit běžné okrajové případy a jak ověřit, že soubor PNG byl správně zapsán.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)
- Aspose.BarCode pro .NET (k dispozici přes NuGet: `Install-Package Aspose.BarCode`)
- IDE, například Visual Studio 2022 nebo Visual Studio Code
- Oprávnění k zápisu do složky, kde bude soubor PNG uložen

## Krok 1: Inicializace generátoru čárových kódů

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která specifikuje symbologii `EncodeTypes.MacroPdf417` a text, který chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Proč je to důležité:**  
`EncodeTypes.MacroPdf417` říká knihovně, aby použila variantu PDF417 macro, která podporuje segmentaci souboru a další metadata. Konstruktor také přijímá lidsky čitelný text, který bude zakódován do čárového kódu.

## Krok 2: Definice velikosti modulu (X‑dimenze)

X‑dimenze řídí šířku jednoho modulu čárového kódu (nejmenšího černobílého prvku). Hodnota `2` pixely dobře funguje pro PNG zobrazované na obrazovce.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Praktický tip:**  
Pokud plánujete tisk čárového kódu, zvýšte hodnotu pixelů (např. `4` nebo `5`), abyste se vyhnuli rozmazanému výstupu na tiskárnách s nízkým rozlišením.

## Krok 3: Konfigurace PDF417 macro parametrů

Macro PDF417 přidává několik volitelných polí, která pomáhají identifikovat zdrojový soubor, pořadí segmentů a kontrolní kontroly. Níže je kompletní sada typických parametrů; můžete vynechat jakékoli, které nepotřebujete.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Proč jsou tato pole užitečná:**  

| Parameter | Purpose |
|-----------|---------|
| `Columns` | Řídí šířku čárového kódu; méně sloupců vytváří vyšší čárový kód. |
| `MacroPdf417FileID` | Jedinečný identifikátor, který spojuje všechny segmenty dohromady. |
| `MacroPdf417SegmentID` | Pozice tohoto segmentu v celém souboru. |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů; vyžadováno pro rekonstrukci. |
| `MacroPdf417FileName` | Lidsky čitelný název, který může zobrazovat skenovací aplikace. |
| `MacroPdf417Checksum` | Pomáhá příjemcům ověřit integritu dat (CCITT‑16). |
| `MacroPdf417FileSize` | Volitelná nápověda o velikosti původního souboru. |
| `MacroPdf417TimeStamp` | Časové razítko vytvoření původního souboru. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Metadata pro směrování nebo vlastnictví. |
| `MacroPdf417Terminator` | Udává, zda se jedná o poslední segment (`Set`) nebo mezičlánek (`Unset`). |

**Okrajový případ:** Pokud generujete jednosegmentový čárový kód, nastavte `MacroPdf417SegmentsCount` na `1` a `MacroPdf417Terminator` na `Unset`. Knihovna automaticky vynechá pole související se segmenty, která nejsou aplikovatelná.

## Krok 4: Uložení vygenerovaného čárového kódu jako PNG obrázek

Nakonec zavolejte `Save` s cestou k souboru a hodnotou výčtu `BarCodeImageFormat.Png`. Metoda zapíše obrázek na disk ve ztrátově bezztrátovém formátu PNG.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Proč PNG?**  
PNG zachovává přesné hodnoty pixelů, což je nezbytné pro skenery čárových kódů, které spoléhají na ostrý kontrast. JPEG komprese může zavést artefakty, které naruší vzor čárového kódu.

### Ověření výstupu

Po spuštění programu byste měli ve složce spuštění vidět soubor pojmenovaný `ExtPDF417Meta.png`. Otevřením v libovolném prohlížeči obrázků se zobrazí hustý, obdélníkový čárový kód. Správnost můžete ověřit nasnímáním obrázku mobilním čtečkou čárových kódů, která podporuje PDF417 macro; aplikace obvykle zobrazí vložená metadata (ID souboru, číslo segmentu atd.).

## Časté úskalí a jak se jim vyhnout

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Čárový kód je rozmazaný | X‑dimenze je příliš nízká pro zvolené DPI | Zvyšte `XDimension.Pixels` nebo renderujte při vyšším DPI (`generator.Parameters.ImageResolution`). |
| Skener hlásí „chybu kontrolního součtu“ | Nesprávná hodnota `MacroPdf417Checksum` | Nechte Aspose vypočítat kontrolní součet automaticky vynecháním vlastnosti, nebo zajistěte, aby hodnota odpovídala algoritmu CCITT‑16. |
| Soubor PNG je prázdný nebo nebyl vytvořen | Neplatná výstupní cesta nebo chybějící oprávnění k zápisu | Použijte `Path.Combine` s známou zapisovatelnou složkou (např. `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Makro pole jsou ignorována | `EncodeTypes` nastaven na běžný `Pdf417` místo `MacroPdf417` | Ověřte, že v konstruktoru je použito `EncodeTypes.MacroPdf417`. |

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat do konzolové aplikace. Kompiluje se s .NET 6.0 a vytváří PNG soubor popsaný výše.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Očekávaný výstup (konzole):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Otevření `ExtPDF417Meta.png` zobrazí čistý Macro PDF417 čárový kód připravený ke skenování.

## Další kroky

- **Změna formátu obrázku** – nahraďte `BarCodeImageFormat.Png` hodnotou `Jpeg` nebo `Bmp`, pokud potřebujete jiný typ souboru. Pamatujte, že JPEG zavádí kompresní artefakty, které mohou ovlivnit spolehlivost skenování.
- **Upravit rozlišení** – use

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit obrázek čárového kódu s Aspose.Barcode v C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Jak vytvořit PDF417 obrázek čárového kódu v C# s možnostmi Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Jak číst čárové kódy z obrázku pomocí C# s Aspose.BarCode – krok za krokem](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}