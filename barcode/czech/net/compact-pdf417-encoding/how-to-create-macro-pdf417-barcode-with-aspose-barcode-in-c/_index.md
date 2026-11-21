---
category: general
date: 2026-11-20
description: Naučte se, jak vytvořit makro PDF417 čárový kód v C# pomocí Aspose.BarCode.
  Tento průvodce pokrývá metadata, parametry a ukládání obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: cs
lastmod: 2026-11-20
og_description: Vytvořte makro PDF417 čárový kód v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto kompletního tutoriálu, nastavte metadata, nakonfigurujte parametry
  a exportujte PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Vytvořte makro PDF417 čárový kód v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak vytvořit makro PDF417 čárový kód s Aspose.BarCode v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit makro PDF417 čárový kód pomocí Aspose.BarCode v C#

Pokud potřebujete **vytvořit makro PDF417 čárový kód** v .NET aplikaci, tento tutoriál ukazuje přesné kroky. Uvidíte, jak nakonfigurovat makro‑specifické metadata, upravit vizuální nastavení a uložit výsledek jako PNG soubor.

Generování makro PDF417 čárového kódu je užitečné, když chcete rozdělit velký datový soubor na několik symbolů a přitom zachovat identifikátor platný pro celý soubor. V níže uvedeném příkladu používáme knihovnu Aspose.BarCode, která poskytuje plynulé API pro všechny funkce PDF417.

Na konci tohoto průvodce budete mít připravený spustitelný konzolový program, který vytvoří obrázek čárového kódu obsahující kompletní makro informace.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalované.
* Visual Studio 2022 (nebo jakékoli IDE podporující C#).
* NuGet balíček **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Balíček můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Inicializace generátoru čárových kódů pro makro PDF417

Prvním krokem je vytvořit instanci `BarcodeGenerator` s hodnotou výčtu `EncodeTypes.MacroPdf417`. Tím se knihovně řekne, aby považovala čárový kód za makro PDF417 symbol.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Proč je to důležité*: Výběrem `MacroPdf417` se aktivují všechny makro‑související vlastnosti na objektu parametru `Pdf417`.

## Krok 2: Nastavení základního vizuálního vzhledu

Čitelný čárový kód začíná vhodnou velikostí modulu a počtem sloupců. Vlastnost `XDimension.Pixels` určuje šířku jednoho modulu, zatímco `Pdf417.Columns` definuje, kolik datových sloupců má každý řádek.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Úprava těchto hodnot ovlivňuje jak spolehlivost skeneru, tak velikost obrázku.

## Krok 3: Definice detailů identifikace souboru makra

Makro PDF417 vyžaduje identifikátor souboru, identifikátor segmentu a celkový počet segmentů. Tyto tři pole umožňují skeneru znovu složit původní datový soubor.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Tyto **parametry makro PDF417** jsou jádrem makro funkčnosti. Bez nich nemůže skener propojit symboly dohromady.

## Krok 4: Přidání volitelných makro metadat

Kromě povinných identifikátorů formát makra podporuje další pole, jako je kontrolní součet, velikost souboru, časové razítko, adresát, odesílatel a příznak terminátoru. Poskytnutí těchto dat zlepšuje detekci chyb a poskytuje kontext pro následné systémy.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Tip*: Pokud váš pracovní postup nevyžaduje konkrétní pole, můžete jej nechat na výchozí hodnotě. Knihovna vynechá odpovídající datový prvek z čárového kódu.

## Krok 5: Uložení obrázku čárového kódu

Po nastavení všech parametrů zavolejte `Save` a exportujte čárový kód. Příklad ukládá PNG soubor do uživatelem zadaného adresáře.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Po dokončení programu soubor `ExtPDF417Meta.png` obsahuje makro PDF417 čárový kód, který kóduje text `"Åspóse.Barcóde©"` spolu se všemi makro metadaty.

## Kompletní zdrojový kód

Níže je kompletní, samostatný program. Zkopírujte jej do nového konzolového projektu a spusťte po instalaci NuGet balíčku Aspose.BarCode.

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
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Očekávaný výstup

Spuštění programu vypíše potvrzovací řádek podobný tomuto:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Otevření PNG souboru zobrazí hustý, vysokokontrastní čárový kód. Skenování jej pomocí PDF417‑kompatibilního skeneru vrátí původní text plus všechna makro pole.

## Časté otázky a okrajové případy

### Co když potřebuji více než 20 segmentů?

Vlastnost `MacroPdf417SegmentsCount` lze nastavit až na `255`. Ujistěte se, že přijímací systém dokáže zpracovat vyšší počet segmentů, a zvažte rozdělení dat na zvládnutelný počet symbolů.

### Jaký vliv má kontrolní součet na skenování?

Kontrolní součet CCITT‑16 (`MacroPdf417Checksum`) poskytuje další vrstvu kontroly chyb. Pokud skener zjistí nesoulad, čárový kód odmítne. Kontrolní součet můžete vynechat, pokud váš pracovní postup nevyžaduje jeho použití.

### Můžu generovat PDF417 makro čárový kód bez Aspose?

Ano, jiné knihovny (např. ZXing.Net, Dynamsoft) podporují PDF417, ale makro‑specifická pole často chybí. Aspose.BarCode nabízí nejkompletnější implementaci makro metadat.

### Jaké formáty obrázků jsou podporovány pro ukládání?

Metoda `Save` akceptuje libovolný formát definovaný v `BarCodeImageFormat`, jako jsou `Png`, `Jpeg`, `Gif`, `Bmp` a `Tiff`. Vyberte formát, který odpovídá vašemu následnému zpracovatelskému řetězci.

## Závěr

Nyní víte, jak **vytvořit makro PDF417 čárový kód** v C# pomocí Aspose.BarCode. Tutoriál pokryl inicializaci generátoru, vizuální nastavení, identifikátory souboru makra, volitelná metadata a export obrázku. S tímto základem můžete integrovat makro PDF do inventárních systémů, sledování dokumentů nebo jakéhokoli scénáře, který vyžaduje segmentovaný přenos dat.

Další kroky zahrnují experimentování s různými hodnotami `XDimension` pro vyšší rozlišení, úpravu úrovně opravy chyb nebo integraci čárového kódu do webového API, které přímo vrací PNG stream. Pro související témata se podívejte na tutoriály o **příkladu generátoru čárových kódů**, **parametrech PDF417 makra** a **zpracování makro PDF417 metadat**.

Šťastné programování!

## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}