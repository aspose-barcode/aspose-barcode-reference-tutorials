---
category: general
date: 2026-07-18
description: Vytvořte mikro PDF417 čárový kód pomocí Aspose.BarCode pro .NET – krok
  za krokem průvodce zahrnující sloupce, řádky a výstup PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: cs
lastmod: 2026-07-18
og_description: Okamžitě vygenerujte mikro PDF417 čárový kód pomocí Aspose.BarCode
  pro .NET. Naučte se, jak ovládat sloupce, řádky a během několika minut uložit jako
  PNG.
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: Generovat Micro PDF417 čárový kód – Kompletní C# tutoriál
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Generování mikro PDF417 čárového kódu v C# – Kompletní průvodce
url: /cs/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generování mikro PDF417 čárového kódu v C# – Kompletní průvodce

Už jste se někdy zamysleli, jak **generovat mikro pdf417 čárový kód** přímo z vaší C# aplikace? Nejste v tom sami. Ať už označujete inventář, kódujete krátké URL, nebo vytváříte vlastní skenovací řešení, zvládnutí tohoto malého, ale výkonného 2‑D kódu vám může ušetřit spoustu starostí.

V tomto tutoriálu projdeme reálným příkladem pomocí **Aspose.BarCode for .NET**, ukážeme vám, jak upravit sloupce, řádky a velikost modulu, a poté výsledek uložit do PNG souboru. Na konci budete mít připravenou konzolovou aplikaci, která vygeneruje tři různé obrázky čárových kódů – žádná záhada nezůstane nevyřešena.

## Co budete potřebovat

- .NET 6 nebo novější (kód funguje také na .NET Framework 4.7+)
- Visual Studio 2022 (nebo jakékoli C# IDE, které preferujete)
- NuGet balíček **Aspose.BarCode** (`Aspose.BarCode`)
- Zapisovatelná složka na disku pro výstupní PNG soubory

Pokud je už máte, skvělé—ponořme se do toho.

## Krok 1: Nastavení projektu a instalace Aspose.BarCode

Nejprve vytvořte nový konzolový projekt:

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **Tip:** Spusťte `dotnet restore` po přidání balíčku, aby byly vyřešeny všechny závislosti.

Nyní otevřete `Program.cs`. Začneme načtením potřebných jmenných prostorů:

```csharp
using System;
using Aspose.BarCode.Generation;
```

Tyto dva `using` příkazy nám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a výčtu formátu obrázku, který budeme později potřebovat.

## Krok 2: Inicializace generátoru MicroPdf417

Srdcem operace je objekt `BarcodeGenerator`. Naplníme jej typem kódování **MicroPdf417** a textem, který chceme zakódovat – v našem případě slovem „ASPOSE“.

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

Proč `MicroPdf417`? Ve srovnání s plno‑velikostním PDF417, mikro verze zabaluje více dat do menšího prostoru, což je ideální pro štítky s omezeným prostorem.

## Krok 3: Úprava velikosti modulu (X‑dimenze)

Velikost modulu určuje, kolik pixelů zabírá každý malý čtvereček čárového kódu. Hodnota **2 pixely** poskytuje ostrý, čitelný obrázek, aniž by zvětšovala velikost souboru.

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Poznámka:** Pokud potřebujete větší čárový kód pro dálkové skenování, zvyšte tuto hodnotu na 3 nebo 4.

## Krok 4: Generování čárových kódů s různými konfiguracemi sloupců/řádků

### 4.1 Dva sloupce, automaticky vypočítané řádky

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 Šest řádků, automaticky vypočítané sloupce

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 Čtyři sloupce × osm řádků (plně specifikováno)

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

Každé volání `Save` zapíše PNG soubor do pracovního adresáře projektu. Klidně změňte cestu (`"YOUR_DIRECTORY/..."`) na něco jako `Path.Combine(Environment.CurrentDirectory, "output")`, pokud dáváte přednost samostatné složce.

## Krok 5: Kompletní funkční příklad

Spojením všeho dohromady je zde kompletní program připravený ke zkopírování a vložení:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### Očekávaný výstup

| Název souboru | Přibližné rozměry (px) | Vizuální náznak |
|---------------|------------------------|-----------------|
| `MicroPdf417Columns2.png` | 180 × 120 | Úzký, vyšší čárový kód |
| `MicroPdf417Rows6.png` | 120 × 180 | Širší, kratší čárový kód |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | Téměř čtvercový, vyvážené rozložení |

Otevřete kterýkoli z nich v prohlížeči obrázků – uvidíte ostrý **Micro PDF417** čárový kód připravený ke skenování.

## Časté otázky a okrajové případy

- **Co když výstupní složka neexistuje?**  
  Zavolejte `Directory.CreateDirectory(path)` před prvním `Save`, aby se předešlo `DirectoryNotFoundException`.

- **Mohu změnit formát obrázku?**  
  Samozřejmě. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif` podle potřeby.

- **Existuje limit délky textu?**  
  MicroPdf417 může zakódovat až 1 KB dat, ale praktické limity závisí na zvolených řádcích/sloupcích. Pokud narazíte na chybu, zvyšte počet řádků nebo sloupců.

- **Jak vložit čárový kód do PDF?**  
  Použijte Aspose.Pdf k vložení vygenerovaného PNG, nebo přepněte na `BarCodeImageFormat.Pdf` pro přímý výstup PDF.

## Profesionální tipy pro generování čárových kódů v C#

1. **Ukládejte generátor do cache** když potřebujete mnoho čárových kódů se stejným nastavením – mění se jen text, což šetří CPU cykly.  
2. **Jemně dolaďte korekci chyb** pomocí `generator.Parameters.Barcode.Pdf417.ErrorLevel`, pokud je vaše skenovací prostředí hlučné.  
3. **Testujte s reálnými skenery** co nejdříve. Některá ruční zařízení mají problémy s velmi hustými mikro čárovými kódy; úprava `XDimension` může udělat velký rozdíl.

## Závěr

Nyní už víte, jak **generovat mikro pdf417 čárový kód** pomocí **Aspose.BarCode for .NET**, manipulovat se **sloupci MicroPdf417** a **řádky MicroPdf417** a uložit výsledek jako PNG soubory – vše z jediné přehledné C# konzolové aplikace. Experimentujte s různými velikostmi modulu, úrovněmi chyb nebo dokonce barevným výstupem, aby vyhovovaly potřebám vašeho projektu.

Dále můžete prozkoumat **generování čárových kódů v C#** pro další symboliky jako QR, Code128 nebo DataMatrix, nebo vložit obrázky přímo do PDF pomocí Aspose.Pdf. Možnosti jsou neomezené, když máte základy pod kontrolou.

Šťastné kódování a ať jsou vaše skeny vždy bez chyb!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Vytvořit obrázek DotCode čárového kódu – řádky a sloupce (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generovat DataMatrix čárový kód – Pro průvodce s Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}