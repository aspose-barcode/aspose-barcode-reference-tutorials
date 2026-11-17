---
category: general
date: 2026-11-17
description: Jak vytvořit PDF417 čárové kódy pomocí Aspose.BarCode – krok za krokem
  průvodce, který také ukazuje, jak vytvořit čárový kód pomocí Aspose v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create pdf417
- create barcode aspose
language: cs
lastmod: 2026-11-17
og_description: Jak vytvořit čárové kódy PDF417 pomocí Aspose.BarCode. Tento tutoriál
  vás provede přesnými kroky k vytvoření čárového kódu Aspose, konfiguraci metadat
  Macro PDF417 a uložení obrázku.
og_image_alt: Screenshot of a PDF417 barcode generated with Aspose.BarCode in C#
og_title: Jak vytvořit čárové kódy PDF417 pomocí Aspose.BarCode – kompletní průvodce
  v C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  headline: How to create PDF417 barcodes with Aspose.BarCode in C#
  type: TechArticle
- description: How to create PDF417 barcodes using Aspose.BarCode – step‑by‑step guide
    that also shows how to create barcode aspose in C#.
  name: How to create PDF417 barcodes with Aspose.BarCode in C#
  steps:
  - name: Set up the project and import Aspose.BarCode
    text: 'Create a new console project and add the Aspose.BarCode NuGet package:'
  - name: Initialise the `BarcodeGenerator` for Macro PDF417
    text: The `BarcodeGenerator` constructor takes the barcode type and the text you
      want to encode. For Macro PDF417 you use `EncodeTypes.MacroPdf417`.
  - name: Configure appearance and Macro PDF417 metadata
    text: Configure appearance and Macro PDF417 metadata
  - name: Save the barcode image
    text: '```csharp // Choose the output folder (ensure it exists) and save as PNG.
      string outputPath = "MacroPdf417.png"; generator.Save(outputPath, BarCodeImageFormat.Png);
      Console.WriteLine($"PDF417 barcode saved to {outputPath}"); } ```'
  - name: Full, runnable example
    text: 'Putting everything together, here’s the complete program you can compile
      and run immediately:'
  type: HowTo
tags:
- barcode
- pdf417
- aspose
- csharp
title: Jak vytvořit PDF417 čárové kódy pomocí Aspose.BarCode v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-pdf417-barcodes-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PDF417 čárové kódy pomocí Aspose.BarCode v C#

Pokud potřebujete **jak vytvořit PDF417** čárové kódy pro inventarizaci, dopravu nebo sledování dokumentů, tento návod vám ukáže přesné kroky s Aspose.BarCode. Uvidíte, jak vytvořit čárový kód aspose, nakonfigurovat pole Macro PDF417 a exportovat výsledek jako PNG obrázek — vše v jediném spustitelném C# programu.

Vytvoření PDF417 čárového kódu je běžné, když musíte zakódovat velké množství dat v kompaktním, strojově čitelném formátu. Aspose.BarCode proces zjednodušuje a umožňuje jemně doladit rozměry, sloupce i kompletní sadu metadat Macro PDF417. Na konci tohoto tutoriálu budete mít kompletní, samostatný příklad, který můžete vložit do libovolného .NET projektu.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.7+).
* Platnou licenci Aspose.BarCode pro .NET (bezplatná zkušební licence funguje pro testování).
* Visual Studio 2022, VS Code nebo jakékoli IDE podporující C#.
* Základní znalosti syntaxe C# a příkazu `using`.

> **Tip:** Pokud spustíte příklad bez licence, Aspose přidá malou vodoznak na vygenerovaný obrázek.

## Jak vytvořit PDF417 čárový kód s Aspose.BarCode

Následující sekce rozdělují implementaci do čtyř jasných kroků. Každý krok obsahuje úryvek kódu, vysvětlení **proč** je kód potřeba, a praktické tipy, které můžete použít ve svých projektech.

### Krok 1: Nastavení projektu a import Aspose.BarCode

Vytvořte nový konzolový projekt a přidejte NuGet balíček Aspose.BarCode:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Poté otevřete `Program.cs` a přidejte požadované jmenné prostory:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

*Proč je to důležité:* Import `Aspose.BarCode.Generation` vám poskytuje přístup k `BarcodeGenerator` a výčtu `EncodeTypes`, což jsou základní třídy pro tvorbu čárových kódů.

### Krok 2: Inicializace `BarcodeGenerator` pro Macro PDF417

Konstruktor `BarcodeGenerator` přijímá typ čárového kódu a text, který chcete zakódovat. Pro Macro PDF417 použijete `EncodeTypes.MacroPdf417`.

```csharp
// Initialise a Macro PDF417 generator with the data you want to encode.
using (BarcodeGenerator generator = 
       new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
{
    // The generator instance will be disposed automatically at the end of the block.
```

*Proč je to důležité:* Příkaz `using` zajišťuje, že neřízené prostředky (např. GDI+ handle) jsou uvolněny okamžitě, což zabraňuje únikům paměti v dlouho běžících službách.

### Krok 3: Konfigurace vzhledu a metadat Macro PDF417

#### 3.1 Úprava vizuálních parametrů

```csharp
    // Set the module (X) dimension – 2 pixels gives a reasonably dense barcode.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Define the number of columns; fewer columns make the barcode taller.
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

#### 3.2 Vyplnění polí Macro PDF417

Macro PDF417 vám umožňuje rozdělit velký dokument do více segmentů čárového kódu. Níže uvedená pole jsou volitelná, ale často vyžadovaná v logistických nebo dokumentačních systémech.

```csharp
    // Unique identifier for the whole file (must be the same across all segments).
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Segment index (starting at 1). Here we generate the 12th segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that will be produced.
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Human‑readable file name, useful for audits.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // CCITT‑16 checksum – helps receivers verify data integrity.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes; some scanners use this for validation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of the original file creation.
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2024, 5, 1);

    // Optional address fields that can be read by advanced scanners.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator tells the scanner that this is the last segment.
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;
```

*Proč jsou tato pole užitečná:*  
* **FileID** propojuje všechny segmenty dohromady a umožňuje jejich rekonstrukci.  
* **SegmentID** a **SegmentsCount** informují skener o pořadí a o tom, kdy je série kompletní.  
* **Checksum** a **FileSize** poskytují rychlé kontroly integrity bez nutnosti dekódovat celý payload.

> **Pozor:** `MacroPdf417FileID` musí být jedinečné pro každý logický dokument. Opakované použití stejného ID pro nesouvisející soubory může způsobit chyby při rekonstrukci.

### Krok 4: Uložení obrázku čárového kódu

```csharp
    // Choose the output folder (ensure it exists) and save as PNG.
    string outputPath = "MacroPdf417.png";
    generator.Save(outputPath, BarCodeImageFormat.Png);
    Console.WriteLine($"PDF417 barcode saved to {outputPath}");
}
```

*Proč PNG?* PNG zachovává přesná pixelová data bez kompresních artefaktů, což je ideální pro čtečky čárových kódů, které spoléhají na ostré hrany.

### Kompletní, spustitelný příklad

Spojením všech částí získáte kompletní program, který můžete okamžitě zkompilovat a spustit:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1‑4: generate a Macro PDF417 barcode and save it as PNG
            using (BarcodeGenerator generator = 
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text for PDF417"))
            {
                // Appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Macro PDF417 metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
                    new DateTime(2024, 5, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
                    Pdf417MacroTerminator.Set;

                // Save
                string outputPath = "MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

**Očekávaný výstup:** Po spuštění programu najdete v kořenovém adresáři projektu soubor `MacroPdf417.png`. Otevřením obrázku uvidíte hustý, vysokokontrastní PDF417 čárový kód, který kóduje „Sample text for PDF417“ spolu s makro metadaty, jež jste zadali.

## Často kladené otázky a řešení okrajových případů

| Otázka | Odpověď |
|----------|--------|
| *Mohu generovat více segmentů v cyklu?* | Ano. Zvyšte `MacroPdf417SegmentID` pro každou iteraci, ponechte `MacroPdf417FileID` konstantní a aktualizujte `MacroPdf417SegmentsCount` až po zjištění celkového počtu segmentů. |
| *Co když data přesáhnou jeden PDF417 symbol?* | Macro |

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to create a micro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}