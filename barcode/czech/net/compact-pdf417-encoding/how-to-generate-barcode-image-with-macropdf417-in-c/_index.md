---
category: general
date: 2026-11-23
description: Naučte se, jak vygenerovat obrázek čárového kódu pomocí Aspose.BarCode
  pro .NET s metadaty MacroPdf417 v C#. Postupujte podle kompletního krok‑za‑krokem
  průvodce.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: cs
lastmod: 2026-11-23
og_description: Jak vygenerovat obrázek čárového kódu pomocí Aspose.BarCode pro .NET.
  Tento tutoriál ukazuje konfiguraci metadat MacroPdf417 a generování čárového kódu
  v C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Jak vygenerovat obrázek čárového kódu pomocí MacroPdf417 v C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Jak vygenerovat obrázek čárového kódu pomocí MacroPdf417 v C#
url: /cs/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat obrázek čárového kódu pomocí MacroPdf417 v C#

Pokud potřebujete **vygenerovat obrázek čárového kódu** v .NET aplikaci, tento průvodce vám přesně ukáže, jak to provést pomocí **Aspose.BarCode for .NET**. Provedeme vás vytvořením **čárového kódu MacroPdf417**, nastavením jeho metadat a uložením výsledku jako PNG soubor.

Tento tutoriál pokrývá vše od instalace knihovny až po psaní kompletního spustitelného konzolového programu. Na konci budete mít připravený ukázkový kód, který vytváří vysoce kvalitní obrázek čárového kódu, a pochopíte, jak **nastavit metadata čárového kódu**, vybrat **formát obrázku čárového kódu** a řešit běžné problémy. Předchozí zkušenost s Aspose není vyžadována – stačí základní znalost C#.

## Instalace Aspose.BarCode pro .NET

Než budete moci **vygenerovat obrázek čárového kódu**, potřebujete NuGet balíček Aspose.BarCode.

1. Otevřete terminál nebo konzoli Package Manager v aplikaci Visual Studio.  
2. Spusťte následující příkaz:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode.Generation`, který obsahuje třídu `BarcodeGenerator` používanou pro **generování čárových kódů v C#**.

> **Tip:** Použijte nejnovější stabilní verzi (k listopadu 2026 je aktuální verze 24.11), abyste získali nejnovější funkce a opravy chyb.

## Vytvoření instance BarcodeGenerator

První krok kódu vytvoří `BarcodeGenerator` nakonfigurovaný pro typ **čárového kódu MacroPdf417** a poskytne řetězec dat, který chcete zakódovat.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

`using` blok zajišťuje, že generátor je správně uvolněn, čímž se uvolní všechny neřízené prostředky.

## Konfigurace základního vzhledu

Čitelný čárový kód začíná rozumnými rozměry. Zde nastavíme šířku pixelu každého modulu (`XDimension`) a počet sloupců pro matici PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Proč tyto hodnoty?*  
- **XDimension** určuje, jak silná je každá čára; 2 pixely fungují dobře pro zobrazení na obrazovce i většinu tiskáren.  
- **Columns** ovlivňuje celkovou šířku; menší počet sloupců udržuje čárový kód kompaktní a zároveň zachovává kapacitu korekce chyb.

## Nastavení metadat čárového kódu (specifické pro MacroPdf417)

MacroPdf417 vám umožňuje vložit informace na úrovni souboru přímo do čárového kódu. Zde **nastavujete metadata čárového kódu**, jako je ID souboru, ID segmentu a časová razítka.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Co znamená každá vlastnost

| Vlastnost | Účel |
|----------|------|
| **MacroPdf417FileID** | Jedinečný identifikátor logického souboru, ke kterému čárový kód patří. |
| **MacroPdf417SegmentID** | Index aktuálního segmentu (počítáno od 0). |
| **MacroPdf417SegmentsCount** | Celkový počet segmentů, které tvoří celý soubor. |
| **MacroPdf417FileName** | Lidsky čitelný název zdrojového souboru. |
| **MacroPdf417Checksum** | Volitelný kontrolní součet CCITT‑16 pro ověření integrity dat. |
| **MacroPdf417FileSize** | Očekávaná velikost původního souboru v bajtech. |
| **MacroPdf417TimeStamp** | Datum a čas, kdy byl čárový kód vygenerován – užitečné pro sledování verzí. |
| **MacroPdf417Addressee / Sender** | Vlastní řetězce, které mohou obsahovat informace o směrování. |
| **MacroPdf417Terminator** | Udává, zda je tento segment poslední (`Set`) nebo ne (`Unset`). |

> **Hraniční případ:** Pokud plánujete rozdělit velký dokument na mnoho segmentů, udržujte `SegmentsCount` konzistentní ve všech vygenerovaných čárových kódech. Nesoulad počtů způsobí selhání dekódování.

## Výběr formátu obrázku čárového kódu a uložení

Aspose podporuje mnoho **formátů obrázků čárových kódů** (PNG, JPEG, BMP, TIFF atd.). PNG je bezztrátový a dobře funguje pro většinu webových a tiskových scénářů.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní složkou, kde má aplikace oprávnění k zápisu.

Když program běží, měli byste vidět zprávu v konzoli potvrzující umístění souboru. Otevřete PNG soubor v libovolném prohlížeči obrázků – uvidíte ostrý **čárový kód MacroPdf417**, který kóduje zadaný text a metadata, která jste definovali.

### Očekávaný výstup

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Velikost souboru obrázku bude přibližně 30‑40 KB, v závislosti na zvoleném `XDimension` a počtu sloupců.

## Ověření čárového kódu a řešení problémů

1. **Vizální kontrola** – Čárový kód by měl zobrazovat sérii naskládaných sloupců s tichou zónou (bílý okraj) kolem něj.  
2. **Test dekódování** – Použijte aplikaci pro skenování čárových kódů nebo třídu Aspose.BarCode `BarCodeReader` k načtení obrázku a potvrďte, že všechna metadata jsou správně vložena.  



## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vygenerovat obrázek PDF417 čárového kódu pomocí Aspose.BarCode v C# – krok za krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Jak vygenerovat čárový kód s vlastním textem pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Jak číst čárové kódy z obrázku pomocí C# s Aspose.BarCode – krok za krokem průvodce](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}