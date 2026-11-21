---
category: general
date: 2026-11-20
description: Vytvořte obrázek čárového kódu v C# pomocí Aspose.BarCode. Naučte se,
  jak vygenerovat čárový kód PDF417 s vlastním rozvržením a uložit jej jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: cs
lastmod: 2026-11-20
og_description: Vytvořte obrázek čárového kódu v C# pomocí Aspose.BarCode. Tento návod
  ukazuje, jak generovat čárový kód PDF417, přizpůsobit rozvržení a exportovat do
  PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Vytvořte obrázek čárového kódu PDF417 v C# – kompletní návod
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Jak vytvořit obrázek čárového kódu PDF417 v C# – průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek čárového kódu s PDF417 v C# – krok za krokem průvodce

Pokud potřebujete **vytvořit obrázek čárového kódu** v .NET aplikaci, tento průvodce vám přesně ukáže **jak vygenerovat PDF417 čárový kód** s vlastním rozložením a uložit jej jako soubor PNG. Uvidíte kompletní, spustitelný kód, pochopíte, proč každé nastavení má význam, a naučíte se běžné úskalí, aby váš čárový kód fungoval spolehlivě v produkci.

V tomto tutoriálu se naučíte:

* Inicializovat generátor Aspose.BarCode pro PDF417.
* Nakonfigurovat počet sloupců a řádků pro ovládání tvaru čárového kódu.
* Exportovat výsledek jako vysoce kvalitní PNG obrázek.
* Prozkoumat volitelná nastavení pro korekci chyb a délku dat.

Jedinou podmínkou je aktuální .NET SDK (.NET 6 nebo novější) a licence nebo bezplatná zkušební verze **Aspose.BarCode for .NET**.

---

## Požadavky a nastavení

Než začnete, ujistěte se, že máte:

| Požadavek | Proč je důležitý |
|-------------|----------------|
| .NET 6 SDK nebo novější | Poskytuje runtime pro konzolovou aplikaci v C#. |
| Visual Studio 2022 (nebo VS Code) | Poskytuje IDE s IntelliSense pro Aspose API. |
| Aspose.BarCode for .NET NuGet balíček | Dodává `BarcodeGenerator`, `EncodeTypes` a pomocníky pro export obrázků. |
| Oprávnění zápisu do výstupní složky | Generátor zapisuje PNG soubor na disk. |

NuGet balíček můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

---

## Krok 1: Vytvořte nový konzolový projekt

Nejprve vytvořte jednoduchou konzolovou aplikaci, která bude hostovat logiku generování čárového kódu.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Proč tento kód funguje

* **`BarcodeGenerator`** je vstupní bod pro všechny typy čárových kódů. Předáním `EncodeTypes.Pdf417` říkáte knihovně, aby vytvořila symbol PDF417.
* **Sloupce a řádky** jsou hlavními pákami pro rozložení. Méně sloupců vytvoří vyšší čárový kód; více sloupců jej rozšíří do šířky. Přizpůsobte tyto hodnoty tak, aby odpovídaly prostoru, kde bude obrázek zobrazen (např. tiskárna štítků vs. webová stránka).
* **Korekce chyb** zvyšuje spolehlivost skenování, když může být čárový kód rozmazaný nebo tištěný na nízkokvalitním médiu. Výchozí úroveň je 0; mírné zvýšení (2–4) představuje dobrý kompromis mezi velikostí a robustností.
* **`Save`** zapíše obrázek na disk ve formátu PNG, který zachovává ostré hrany a funguje napříč prohlížeči i mobilními zařízeními.

Po spuštění programu (`dotnet run`) se v kořenové složce projektu vytvoří soubor `CustomPdf417.png`. PNG vypadá takto:

![Vygenerovaný obrázek čárového kódu PDF417](https://example.com/images/pdf417-sample.png "Snímek obrazovky vygenerovaného obrázku čárového kódu vytvořeného pomocí PDF417 v C#")

*Alt text:* **vytvořit obrázek čárového kódu** – PDF417 čárový kód vygenerovaný v C# a uložený jako PNG.

---

## Krok 2: Doladění čárového kódu pro reálné scénáře

### Úprava délky dat

PDF417 může kódovat až 1 850 znaků. Pokud potřebujete kódovat delší řetězce, zvažte rozdělení dat do více čárových kódů nebo použití **kompaktního režimu**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Kompaktní režim snižuje počet řádků, ale může zvýšit vizuální hustotu, proto jej otestujte se svým skenerem.

### Ovládání velikosti obrázku

Výchozí velikost obrázku se vypočítává z velikosti modulu (nejmenšího čtverce v čárovém kódu). Můžete explicitně nastavit DPI nebo po vygenerování obrázek škálovat:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Nebo po uložení změnit velikost pomocí `System.Drawing`, pokud potřebujete miniaturu.

### Zpracování speciálních znaků

PDF417 podporuje celý ASCII soubor. Pokud vaše data obsahují Unicode znaky, ujistěte se, že řetězec kódujete jako UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Krok 3: Běžná úskalí a jak se jim vyhnout

| Úskalí | Příznak | Řešení |
|---------|---------|-----|
| Příliš mnoho sloupců pro daná data | Čárový kód se zkrátí nebo vyvolá výjimku. | Snižte `Columns` nebo nechte knihovnu automaticky nastavit velikost vynecháním tohoto nastavení. |
| Nízká korekce chyb na hlučné tiskárně | Skener občas nedokáže čárový kód přečíst. | Zvyšte `ErrorCorrectionLevel` alespoň na 2. |
| Ukládání do složky jen pro čtení | `UnauthorizedAccessException` během běhu. | Použijte zapisovatelnou složku, např. `Environment.CurrentDirectory` nebo `Path.GetTempPath()`. |
| Použití zastaralé verze Aspose.BarCode | Chybí vlastnosti jako `CompactMode`. | Aktualizujte NuGet balíček na nejnovější stabilní verzi. |

---

## Krok 4: Ověření výsledku

Pro potvrzení, že čárový kód byl vygenerován správně, můžete:

1. Otevřít `CustomPdf417.png` v libovolném prohlížeči obrázků – čárový kód by měl být ostrý, s jasně černými moduly na bílém pozadí.  
2. Použít bezplatnou aplikaci pro skenování PDF417 (dostupnou na iOS i Android) a naskenovat obrázek. Aplikace by měla zobrazit **„Sample data for PDF417 barcode“**.  
3. (Volitelné) Načíst obrázek v unit testu pomocí `System.Drawing.Bitmap` a ověřit, že pixel na souřadnici `(0,0)` je černý, což potvrzuje, že obrázek není prázdný.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Pokud test projde, úspěšně jste **vytvořili obrázek čárového kódu** a **generovali PDF417 čárový kód** programově.

---

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí **generování PDF417 čárového kódu** s vlastním rozložením, úpravou korekce chyb a exportem do PNG. Kompletní příklad ukazuje každý potřebný krok – od inicializace `BarcodeGenerator` po uložení finálního obrázku – takže jej můžete zkopírovat, vložit a spustit ve svém projektu.

Dále můžete zkusit:

* **Vložit PNG do webového API**, aby klienti mohli požadovat čárové kódy na vyžádání (`generate pdf417` jako službu).  
* **Dávkové generování** pro velké datové sady – projít seznam řetězců a uložit každý PNG do databáze.  
* **Alternativní výstupní formáty** (SVG, JPEG) změnou `BarCodeImageFormat`.

Neváhejte experimentovat s poměrem sloupců/řádků, úrovněmi korekce chyb a rozlišením obrázku, aby vyhovovaly přesným požadavkům vašeho skeneru nebo UI designu. Šťastné programování!

## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}