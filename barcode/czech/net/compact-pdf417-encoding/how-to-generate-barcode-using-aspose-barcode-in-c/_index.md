---
category: general
date: 2026-11-20
description: Naučte se generovat čárový kód pomocí Aspose.Barcode v C#. Tento průvodce
  vás provede vytvořením čárového kódu MicroPdf417 a jeho uložením jako PNG obrázku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: cs
lastmod: 2026-11-20
og_description: Jak generovat čárový kód pomocí Aspose.Barcode v C#. Sledujte tento
  kompletní tutoriál, jak vytvořit čárový kód MicroPdf417 a exportovat jej jako PNG.
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: Jak generovat čárový kód pomocí Aspose.Barcode – krok za krokem průvodce
  v C#
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: Jak generovat čárový kód pomocí Aspose.Barcode v C#
url: /cs/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód pomocí Aspose.Barcode v C#

Pokud potřebujete **jak generovat čárový kód** pro desktopovou nebo webovou aplikaci, Aspose.Barcode poskytuje jednoduché API. Tento tutoriál vám přesně ukáže, jak vygenerovat čárový kód MicroPdf417, přizpůsobit jeho rozměry a uložit výsledek jako soubor PNG. Také uvidíte, jak **vytvořit čárový kód pomocí Aspose** pro jiné formáty, aniž byste opustili IDE.

Generování čárového kódu je běžnou požadavkem pro inventární systémy, platformy pro prodej vstupenek a zabezpečené pracovní postupy s dokumenty. Na konci tohoto průvodce budete mít spustitelný program, který vytváří vysoce kvalitní obrázek čárového kódu připravený k tisku nebo vložení.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+)
* Visual Studio 2022 (nebo jakýkoli editor C#)
* Platná licence pro Aspose.Barcode pro .NET – bezplatná zkušební verze funguje pro vývoj a testování
* Základní znalost syntaxe C#

Žádné další NuGet balíčky nejsou vyžadovány kromě `Aspose.Barcode`.

## Jak generovat čárový kód pomocí Aspose.Barcode

Následující sekce rozdělují proces na jednotlivé kroky. Každý krok vysvětluje **proč** je kód potřebný, nejen **co** dělá.

### Krok 1: Instalace NuGet balíčku Aspose.Barcode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.Barcode
```

Tento příkaz přidá nejnovější stabilní verzi Aspose.Barcode do souboru projektu, čímž zajistí, že třída `BarcodeGenerator` bude k dispozici při kompilaci.

**Proč je to důležité:** Balíček obsahuje jádro renderovacího enginu a sadu předdefinovaných `EncodeTypes`. Bez něj kompilátor nemůže rozpoznat `BarcodeGenerator` ani `EncodeTypes`.

### Krok 2: Vytvoření instance `BarcodeGenerator` pro MicroPdf417

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**Proč je to důležité:** Konstruktor spojuje symbologii (`EncodeTypes.MicroPdf417`) s surovými daty, která chcete kódovat. MicroPdf417 je ideální, když potřebujete menší rozměr než plný PDF417 a přitom podporuje alfanumerická data.

### Krok 3: Úprava X‑dimenze (šířka modulu)

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** X‑dimenze určuje velikost každé buňky čárového kódu. Hodnota, která je příliš nízká, vede k rozmazanému obrazu; příliš vysoká hodnota způsobí, že čárový kód bude zbytečně velký. Dva pixely jsou vyvážený výchozí parametr pro většinu scénářů na obrazovce i tisku.

### Krok 4: Výběr počtu sloupců pro komponentu PDF417

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Proč je to důležité:** MicroPdf417 interně používá komponentu PDF417. Úprava počtu sloupců ovlivňuje poměr stran čárového kódu a kapacitu dat. Čtyři sloupce poskytují kompaktní tvar při zachování čitelnosti.

### Krok 5: Uložení obrázku čárového kódu

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**Proč je to důležité:** `Save` zapíše vykreslený čárový kód na disk. PNG je bezztrátový, což zachovává ostré hrany důležité pro skenery. Pokud váš pracovní postup vyžaduje jiný formát, můžete nahradit `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`.

### Kompletní zdrojový kód

Spojením všech kroků získáte kompletní, samostatnou konzolovou aplikaci:

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

Spusťte program (`dotnet run`) a na ploše najdete soubor `MicroPdf417.png`. Otevřením souboru uvidíte ostrý čárový kód MicroPdf417, který kóduje text `"Åspóse.Barcóde©"`.

## Ověření čárového kódu

Pro potvrzení, že čárový kód byl vygenerován správně:

1. Otevřete PNG v libovolném prohlížeči obrázků.
2. Použijte mobilní aplikaci pro skenování čárových kódů, která podporuje PDF417 nebo MicroPdf417.
3. Naskenujte obrázek; aplikace by měla zobrazit původní text, včetně speciálních znaků.

Pokud skener selže, zkontrolujte následující:

* **X‑dimenze:** Hodnoty pod 1 px mohou způsobit artefakty při vykreslování.
* **Počet sloupců:** Hodnoty mimo 1‑4 vyvolají výjimku.
* **Znaková sada:** Aspose.Barcode podporuje UTF‑8; ujistěte se, že zdrojový soubor je uložen s kódováním UTF‑8.

## Běžné varianty a okrajové případy

### Generování jiných symbologií

Pokud chcete **vytvořit čárový kód pomocí Aspose** pro QR kódy, Code128 nebo UPC, nahraďte `EncodeTypes.MicroPdf417` odpovídající hodnotou enumu, např.:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

### Změna formátu obrázku

Aspose.Barcode podporuje více rastrových formátů. Pro export jako JPEG s 90 % kvalitou:

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### Zpracování velkých datových nákladů

MicroPdf417 může uložit až 1 KB dat. Pro větší náklady přepněte na plný `EncodeTypes.Pdf417` a podle toho upravte `Rows` a `Columns`.

### Unicode a speciální znaky

Knihovna automaticky kóduje Unicode řetězce. Některé starší skenery však rozpoznávají pouze ASCII. Pokud cílíte na taková zařízení, omezte vstup na rozsah ASCII nebo použijte jinou symbologii, která zaručuje kompatibilitu.

## Profesionální tipy pro produkční použití

* **Ukládejte generátor** při generování mnoha čárových kódů se stejným nastavením – snižuje to režii vytváření objektů.
* **Nastavte `Resolution`** (`generator.Parameters.ImageResolution`) na 300 dpi pro výstup s vysokou kvalitou tisku.
* **Povolte korekci chyb** pro 2‑D čárové kódy (`generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`) pro zlepšení spolehlivosti skenování poškozených médií.
* **Zabalte logiku ukládání** do bloku `try / catch` pro ošetření I/O výjimek, zejména při zápisu na síťové sdílené disky.

## Závěr

Nyní víte **jak generovat čárový kód** pomocí Aspose.Barcode v C#. Tutoriál pokryl instalaci NuGet balíčku, vytvoření `BarcodeGenerator`, nastavení rozměrů a sloupců a uložení výsledku jako PNG obrázek. S tímto základem můžete **vytvořit čárový kód pomocí Aspose** pro jakoukoli podporovanou symbologii, upravit vizuální parametry a integrovat generování čárových kódů do větších .NET řešení.

Připraveni na další průzkum? Vyzkoušejte generování QR kódů pro zkracování URL, vložte čárové kódy do PDF reportů pomocí Aspose.PDF nebo automatizujte hromadné vytváření čárových kódů pro správu inventáře. Každý nový scénář staví na stejných základních konceptech předvedených zde. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód s Aspose – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – Krok za krokem průvodce](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generovat obrázek čárového kódu s Aspose.BarCode v C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}