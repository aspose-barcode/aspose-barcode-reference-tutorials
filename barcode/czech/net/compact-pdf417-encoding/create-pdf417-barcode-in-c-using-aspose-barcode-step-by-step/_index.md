---
category: general
date: 2026-10-18
description: Naučte se, jak vytvořit čárový kód PDF417 v C# pomocí Aspose.BarCode.
  Tento tutoriál pokrývá základní, kompaktní, makro a mikro generování PDF417 s kompletním
  kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: cs
lastmod: 2026-10-18
og_description: Vytvořte čárový kód PDF417 v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto návodu a krok za krokem generujte základní, kompaktní, makro a mikro
  čárové kódy PDF417.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Vytvoření PDF417 čárového kódu v C# – kompletní tutoriál Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Vytvoření čárového kódu PDF417 v C# pomocí Aspose.BarCode – krok za krokem
url: /cs/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření čárového kódu PDF417 v C# pomocí Aspose.BarCode – krok za krokem

Pokud potřebujete **vytvořit čárový kód PDF417** v .NET aplikaci, tento tutoriál vás provede celým procesem. Uvidíte, jak vygenerovat základní čárový kód, povolit kompaktní režim, přidat makro metadata a vytvořit mikro variantu – vše s jasnými vysvětleními a spustitelným kódem.

Generování čárových kódů PDF417 je běžné v logistice, ticketingu a správě dokumentů. Na konci tohoto průvodce budete schopni integrovat tvorbu čárových kódů do libovolného C# projektu bez externích nástrojů.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.7+)
* Visual Studio 2022 nebo libovolné C# IDE
* **Aspose.BarCode for .NET** NuGet balíček  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Oprávnění zápisu do složky, kam budou ukládány vygenerované PNG soubory

Žádná další konfigurace není potřeba; knihovna se postará o všechny nízkoúrovňové detaily kódování.

## Krok 1: Vytvoření základního čárového kódu PDF417

Prvním krokem je vytvořit běžný čárový kód PDF417 s vlastní velikostí a počtem sloupců.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Proč jsou tato nastavení důležitá**

* `XDimension.Pixels` řídí fyzickou velikost každého elementu čárového kódu. Hodnota 2 produkuje čistý obraz na většině obrazovek a tiskáren.
* `Pdf417.Columns` určuje, kolik datových sloupců čárový kód obsahuje. Méně sloupců snižuje šířku; více sloupců zvyšuje kapacitu dat.

Spuštěním kódu vznikne soubor `Pdf417Basic.png`, který vypadá jako typický symbol PDF417 se třemi datovými sloupci a plným sloupcem metadat vpravo.

## Krok 2: Povolení kompaktního (zkráceného) režimu

Kompaktní režim odstraní pravý sloupec metadat, čímž čárový kód zúží. To je užitečné, když je prostor omezený, ale data lze rekonstruovat ze zbývajících řádků.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Proč zkracovat?**  
Když je `Truncate` nastaveno na `true`, generátor vynechá volitelný pravý sloupec, který ukládá korekci chyb a metadata na úrovni souboru. Výsledný čárový kód zabírá méně sloupců a přesto je čitelný většinou čteček PDF417.

## Krok 3: Vytvoření makro čárového kódu PDF417 s metadata na úrovni souboru

Makro PDF417 rozšiřuje standardní formát o identifikátory segmentů, což umožňuje rozdělit velký dokument do více čárových kódů. To je praktické pro kódování dlouhých řetězců nebo vícestránkových souborů.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Vysvětlení makro polí**

| Property | Účel |
|----------|------|
| `MacroPdf417FileID` | Jedinečný identifikátor celého souboru; všechny segmenty sdílejí tuto hodnotu. |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná na 1). |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů, které tvoří kompletní datovou sadu. |

Čtečka, která rozumí makro PDF417, může znovu složit původní data přečtením všech segmentů a použitím těchto identifikátorů.

## Krok 4: Vytvoření mikro čárového kódu PDF417 pro krátká data

Micro PDF417 je kompaktní verze určená pro malé objemy dat (až 90 znaků). Omezuje rozsah sloupců na 1‑4, což činí čárový kód vhodným pro drobné štítky nebo zařízení s omezeným zobrazovacím prostorem.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Kdy použít Micro PDF417**  
Použijte tuto variantu, když je datová zátěž krátká a potřebujete co nejmenší možný čárový kód. Je ideální pro inventární štítky, přístupové karty nebo jakýkoli scénář, kde je obrazová plocha omezená.

## Kompletní funkční příklad

Níže je samostatná konzolová aplikace, která v jednom běhu vygeneruje všechny čtyři typy čárových kódů. Zkopírujte kód do nového C# projektu, nahraďte `YOUR_DIRECTORY` existující cestou ke složce a spusťte jej.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Očekávaný výstup**

Po spuštění programu se v určené složce vytvoří čtyři PNG soubory:

* `Pdf417Basic.png` – standardní čárový kód se třemi sloupci
* `CompactPdf417.png` – stejná data, zkrácený pravý sloupec
* `MacroPdf417.png` – makro čárový kód obsahující metadata segmentů
* `MicroPdf417.png` – kompaktní mikro čárový kód pro krátké řetězce

Otevřete libovolný obrázek v prohlížeči; uvidíte charakteristické vzory PDF417. Po naskenování mobilní čtečkou čárových kódů (např. ZXing, Scandit) získáte původní textové řetězce.

## Časté otázky a tipy

* **Co když čárový kód vypadá rozmazaně?**  
  Zvyšte `XDimension.Pixels` na 3 nebo 4. Větší velikost modulů poskytuje vyšší rozlišení, za cenu většího souboru.

* **Mohu místo PNG vygenerovat SVG?**  
  Ano. V metodách `Save` nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Svg`.

* **Musím ručně nastavit úroveň korekce chyb?**  
  Aspose.BarCode volí optimální úroveň automaticky. Pro speciální případy můžete upravit `Pdf417.ErrorCorrectionLevel`.

* **Jak vložit čárový kód do PDF dokumentu?**  
  Použijte `Aspose.Pdf` a přidejte vygenerovaný PNG nebo SVG jako obrázek na stránku PDF.

* **Je knihovna thread‑safe?**  
  Každá instance `BarcodeGenerator` je nezávislá; můžete vytvářet generátory na více vláknech bez sdíleného stavu.

## Závěr

Nyní víte, jak **vytvořit čárový kód PDF417** v C# pomocí Aspose.BarCode, včetně základní, kompaktní, makro a mikro variant.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to create pdf417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}