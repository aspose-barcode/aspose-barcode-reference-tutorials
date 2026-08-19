---
category: general
date: 2026-08-19
description: Vygenerujte čárový kód v C# pomocí Aspose.BarCode k vytvoření Macro PDF417
  s vlastním textem a uložte jej jako soubor obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: cs
lastmod: 2026-08-19
og_description: Generujte čárový kód v C# pomocí Aspose.BarCode, naučte se vytvářet
  PDF417, přidejte vlastní text a uložte soubor s obrázkem čárového kódu.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Generování čárového kódu v C# – Průvodce Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generovat čárový kód C# s Macro PDF417 – kompletní příklad
url: /cs/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování čárového kódu C# s Macro PDF417 – kompletní příklad

Pokud potřebujete **generovat čárový kód C#** ve formátu Macro PDF417, tento návod vám ukáže připravené řešení připravené k okamžitému spuštění. Uvidíte, jak **generovat pdf417**, vložit vlastní text a **vytvořit soubor s obrázkem čárového kódu** v jednom samostatném programu.

Tutoriál pokrývá vše od instalace knihovny Aspose.BarCode po konfiguraci metadat Macro PDF417, takže můžete kód zkopírovat přímo do svého projektu a okamžitě vidět výsledek.

## Požadavky

- .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
- Visual Studio 2022 (nebo jakékoli IDE podporující C#)
- Licence Aspose.BarCode pro .NET (bezplatná zkušební verze funguje pro hodnocení)
- Základní znalost syntaxe C#

> **Tip:** Nainstalujte NuGet balíček pomocí CLI, abyste se vyhnuli nesouladu verzí:  
> `dotnet add package Aspose.BarCode`

## Krok 1: Nastavení projektu a import knihovny

Vytvořte novou konzolovou aplikaci a přidejte požadované direktivy `using`.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Proč je tento krok důležitý:**  
`Aspose.BarCode.Generation` jmenný prostor poskytuje třídu `BarcodeGenerator`, která je vstupním bodem pro vytváření libovolného typu čárového kódu, včetně Macro PDF417. Import `System` vám umožní přístup k `DateTime` pro metadata časových razítek.

## Krok 2: Vytvoření generátoru Macro PDF417 s vlastním textem

Nahraďte zástupný komentář inicializací generátoru. Tím se ukáže **vytvoření vlastního textu čárového kódu**, přičemž se také vybere správný typ kódování.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Vysvětlení:**  
- `EncodeTypes.MacroPdf417` říká Aspose, aby vytvořil PDF417 čárový kód, který podporuje makro funkce (segmentace souboru, kontrolní součet atd.).  
- Text `"Åspóse.Barcóde©"` ukazuje, že Unicode znaky jsou plně podporovány, což je často vyžadováno pro mezinárodní aplikace.

## Krok 3: Konfigurace vzhledu a metadat Macro PDF417

Doladěte rozměry čárového kódu a nastavte makro‑specifická pole vyžadovaná pro zpracování segmentovaných souborů.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Proč jsou tato nastavení důležitá:**

| Setting | Purpose |
|---------|---------|
| `XDimension.Pixels` | Řídí vizuální hustotu; 2 px poskytuje čistý, čitelný obrázek. |
| `Columns` | Určuje, kolik datových sloupců se zobrazí v řádku, což ovlivňuje velikost čárového kódu. |
| `MacroPdf417FileID` | Jedinečně identifikuje logický soubor napříč všemi segmenty. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Umožňuje rekonstrukci původního souboru z více čárových kódů. |
| `MacroPdf417FileName` | Lidsky čitelný název uložený v čárovém kódu pro následné zpracování. |
| `MacroPdf417Checksum` | Poskytuje detekci chyb pomocí algoritmu CCITT‑16 CRC. |
| `MacroPdf417FileSize` | Pomáhá dekodéru vědět, kdy byl celý soubor přijat. |
| `MacroPdf417TimeStamp` | Zaznamenává, kdy byl čárový kód vygenerován, užitečné pro auditní záznamy. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Volitelná pole, která mohou být použita v obchodních pracovních postupech. |
| `MacroPdf417Terminator` | Indikuje, že tento segment je poslední (`Set`). |

## Krok 4: Uložení čárového kódu jako obrázkový soubor

Nakonec zapíšete čárový kód do PNG souboru, abyste jej mohli zobrazit nebo vložit jinde.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Co uvidíte:**  
PNG obrázek pojmenovaný `ExtPDF417Meta.png` obsahující Macro PDF417 čárový kód, který kóduje vlastní text a všechna metadata, která jste výše nastavili. Obrázek lze otevřít v libovolném standardním prohlížeči nebo vložit do PDF, reportů či webových stránek.

## Kompletní zdrojový kód (připravený ke kopírování)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Očekávaný výstup

Spuštěním programu se vypíše:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Otevřením `ExtPDF417Meta.png` se zobrazí čistý Macro PDF417 čárový kód, který se správně načte v libovolném PDF417 čtečce a zachová vlastní text `"Åspóse.Barcóde©"` a makro metadata, která jste definovali.

## Časté otázky a okrajové případy

- **Mohu generovat jiný formát obrázku?**  
  Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif` podle potřeby.

- **Co když moje data přesáhnou jeden čárový kód?**  
  Macro PDF417 je navržen pro segmentaci. Upravit `MacroPdf417SegmentsCount` a `MacroPdf417SegmentID` pro každou část a poté spojit naskenované výsledky.

- **Je podpora Unicode zaručena?**  
  Aspose.BarCode plně podporuje Unicode. Ujistěte se, že váš zdrojový soubor je uložen v kódování UTF‑8, aby nedošlo k poškození znaků.

- **Potřebuji licenci pro produkci?**  
  Licencovaná verze odstraňuje vodotisk pro hodnocení a poskytuje plnou funkčnost. Zkušební verze funguje pro testování a učení.

## Závěr

Nyní víte, jak **generovat čárový kód C#** pro Macro PDF417, **generovat pdf417** s bohatými metadaty, **vytvořit vlastní text čárového kódu** a **vytvořit soubor s obrázkem čárového kódu** pomocí Aspose.BarCode. Kompletní, spustitelný příklad demonstruje každý potřebný krok – od nastavení projektu po uložení finálního PNG obrázku.

### Další kroky

- Experimentujte s dalšími nastaveními PDF417, jako jsou `ErrorCorrectionLevel` a `CompactPdf417`, pro menší symboly.  
- Integrujte vygenerovaný čárový kód do PDF reportu pomocí Aspose.PDF.  
- Prozkoumejte hromadné generování: projděte kolekci souborů a vytvořte sérii segmentovaných Macro PDF417 čárových kódů.

Neváhejte upravit kód podle svého pracovního postupu a nechte generování čárových kódů stát se plynulou součástí vašich C# aplikací. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Vytvořit obrázek čárového kódu – Code 93 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Jak generovat a upravit výšku čárového kódu pro One-Dimensional Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}