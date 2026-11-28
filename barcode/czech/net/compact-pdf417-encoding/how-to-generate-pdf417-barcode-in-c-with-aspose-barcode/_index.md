---
category: general
date: 2026-11-27
description: Naučte se generovat čárový kód PDF417 v C# pomocí Aspose.BarCode. Nastavte
  rozměry, počet sloupců a uložte jako PNG během několika řádků kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: cs
lastmod: 2026-11-27
og_description: Generujte PDF417 čárový kód v C# okamžitě. Tento tutoriál ukazuje,
  jak nastavit rozměry, počet sloupců a uložit výsledek jako PNG obrázek.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Generování čárového kódu PDF417 v C# – rychlý průvodce s Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Jak vygenerovat čárový kód PDF417 v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód PDF417 v C# s Aspose.BarCode

Pokud potřebujete **generovat čárový kód PDF417** v aplikaci .NET, tento průvodce vám ukáže stručné, kompletní řešení. Uvidíte, jak vytvořit čárový kód, doladit jeho velikost a zapsat výsledek do souboru PNG – vše pomocí knihovny Aspose.BarCode.

Generování čárového kódu PDF417 je běžné, když potřebujete zakódovat velké množství dat pro skenování na mobilních zařízeních, palubních vstupenkách nebo inventárních štítcích. Na konci tohoto tutoriálu budete mít připravený spustitelný konzolový program, který vytváří vysoce kvalitní PNG obrázek.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno  
* Aktuální verze **Aspose.BarCode pro .NET** (NuGet balíček `Aspose.BarCode`)  
* IDE nebo editor (Visual Studio, VS Code, Rider atd.)  

Kód funguje na Windows, Linuxu i macOS, protože Aspose.BarCode je multiplatformní.

## Krok 1: Vytvořte nový konzolový projekt

Otevřete terminál a spusťte:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Tím se vytvoří minimální C# projekt s názvem **Pdf417Demo** a přidá se závislost `Aspose.BarCode`.

## Krok 2: Napište kód pro generování čárového kódu

Otevřete **Program.cs** a nahraďte jeho obsah následujícím:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Proč je každý řádek důležitý

* **BarcodeGenerator** – základní třída, která vytváří obrázek čárového kódu. Předáním `EncodeTypes.Pdf417` se vybere symbologie PDF417.  
* **XDimension.Pixels** – určuje nejmenší šířku čáry. Menší hodnoty zmenší obrázek; větší hodnoty zlepší čitelnost na skenerech s nízkým rozlišením.  
* **Pdf417.Columns** – řídí počet datových sloupců. Více sloupců vytvoří kratší, ale vyšší čárový kód; méně sloupců jej rozšíří.  
* **ErrorCorrectionLevel** – vyšší úrovně přidávají redundantní data, což činí čárový kód odolnější vůči poškození, ale zvětšuje jeho velikost.  
* **Save(..., BarCodeImageFormat.Png)** – zapíše obrázek na disk ve formátu PNG, bezztrátovém formátu ideálním pro další zpracování nebo vložení do dokumentů.

## Krok 3: Sestavte a spusťte program

V terminálu spusťte:

```bash
dotnet run
```

Měli byste vidět:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Soubor s názvem **Pdf417Basic.png** se objeví ve složce projektu. Po otevření zobrazí čistý PDF417 čárový kód, který kóduje text *„Sample text for PDF417 barcode“*.

![Vygenerovaný PDF417 čárový kód uložený jako PNG soubor](pdf417-barcode-example.png "Vygenerovaný PDF417 čárový kód ve formátu PNG")

*Popisek obrázku: snímek vygenerovaného PDF417 čárového kódu uloženého jako PNG soubor, ukazující výsledek tutoriálu pro generování PDF417 čárového kódu.*

## Krok 4: Běžné varianty a okrajové případy

### Změna kódovaných dat

Nahraďte druhý argument `BarcodeGenerator` libovolným UTF‑8 řetězcem, např.:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

Generátor automaticky rozdělí data do řádků a sloupců.

### Úprava velikosti obrázku bez ztráty kvality

Pokud potřebujete větší obrázek pro tisk, zvyšte `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Zpracování velmi dlouhých vstupů

PDF417 může kódovat až 1 850 znaků. Pro extrémně dlouhé řetězce můžete chtít zvýšit počet sloupců:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Pokud obsah překročí maximální kapacitu, Aspose.BarCode vyhodí `ArgumentException`. Zabalte kód generování do bloku try‑catch, aby se zobrazila přátelská chybová zpráva.

### Ukládání v jiných formátech

Aspose.BarCode podporuje BMP, JPEG, TIFF a SVG. Formát můžete změnit takto:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Krok 5: Ověřte čárový kód

Můžete potvrdit, že čárový kód je platný, jeho naskenováním libovolnou aplikací pro čtení PDF417 (např. aplikacemi fotoaparátu na chytrém telefonu, které podporují skenování čárových kódů). Dekódovaný text by měl odpovídat řetězci, který jste předali generátoru.

Pokud skenování selže:

* Ujistěte se, že obrázek není komprimován (použijte PNG nebo bezztrátové SVG).  
* Ověřte, že `ErrorCorrectionLevel` je dostatečně vysoká pro zamýšlené prostředí.  
* Zkontrolujte, že rozměry čárového kódu jsou vhodné pro rozlišení skeneru.

## Závěr

Nyní víte, jak **generovat čárový kód PDF417** v C# pomocí Aspose.BarCode, přizpůsobit jeho rozměry, nastavit počet sloupců a exportovat výsledek jako PNG obrázek. Tento přístup funguje v široké škále scénářů, od mobilního prodeje vstupenek po správu zásob.

Dále můžete zkoumat:

* **Čtení** PDF417 čárového kódu pomocí `BarCodeReader`.  
* Generování dalších symbologií, jako je QR Code nebo DataMatrix.  
* Vkládání PNG do PDF, reportů nebo webových stránek.  

Neváhejte experimentovat s různými úrovněmi korekce chyb, formáty obrázků a datovými náklady, aby vyhovovaly potřebám vašeho projektu. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak generovat PDF417 čárový kód v C# s Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Jak generovat PDF417 čárový kód a vykreslit jej jako PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Jak generovat PDF417 čárový kód v C# a nastavit velikost čárového kódu](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}