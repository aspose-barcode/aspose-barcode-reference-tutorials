---
category: general
date: 2026-09-19
description: Jak generovat čárový kód v C# s podrobným návodem krok za krokem. Naučte
  se přizpůsobit nastavení čárového kódu PDF417 a vytvořit obrázek čárového kódu,
  který mohou vývojáři C# okamžitě použít.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: cs
lastmod: 2026-09-19
og_description: Jak generovat čárový kód v C# s podrobnými instrukcemi. Přizpůsobte
  parametry čárového kódu PDF417 a vytvořte obrázek čárového kódu, který mohou projekty
  v C# použít ještě dnes.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Jak generovat čárový kód a přizpůsobit čárový kód PDF417 v C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Jak generovat čárový kód a přizpůsobit PDF417 čárový kód v C#
url: /cs/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat čárový kód a přizpůsobit PDF417 čárový kód v C#

Pokud potřebujete **how to generate barcode** v .NET aplikaci, tento tutoriál vám ukáže kompletní, připravené řešení. Naučíte se, jak přizpůsobit rozměry PDF417 čárového kódu, vybrat počet sloupců a nakonec **create barcode image C#** projekty mohou vložit přímo.

Generování čárového kódu nevyžaduje složitý build pipeline. Na konci tohoto průvodce budete mít PNG soubor obsahující MicroPDF417 čárový kód, který odpovídá přesné velikosti a rozlišení, které potřebujete.

## Požadavky

Měli byste mít před zahájením instalováno:

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.6+)
* Visual Studio 2022 (nebo jakýkoli C# editor, který preferujete)
* NuGet balíček Aspose.BarCode pro .NET – nainstalujte pomocí  
  `dotnet add package Aspose.BarCode`

Není vyžadován žádný další externí nástroj.

## Krok 1: Nastavte projekt a importujte jmenné prostory

Vytvořte nový konzolový projekt a přidejte referenci na Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Otevřete `Program.cs` a přidejte požadované `using` direktivy:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Tyto jmenné prostory poskytují třídy, které vám umožní **how to generate barcode** a ovládat specifické možnosti PDF417.

## Krok 2: Inicializujte generátor MicroPDF417 s požadovaným textem

První řádek vytvoří instanci `BarcodeGenerator` nakonfigurovanou pro symbologii MicroPDF417. Konstruktor přijímá typ kódování a řetězec dat, který chcete zakódovat.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Proč je to důležité:** MicroPDF417 je kompaktní varianta plného standardu PDF417, ideální pro malé štítky nebo mobilní obrazovky. Inicializace generátoru se správným `EncodeTypes` zajišťuje, že knihovna použije správný algoritmus kódování.

## Krok 3: Přizpůsobte X‑dimenzi (šířku modulu) pro vyšší rozlišení

X‑dimenze řídí šířku jednoho modulu čárového kódu (nejmenší černý nebo bílý pruh). Nastavením na nízkou hodnotu v pixelech získáte obrázek s vyšším rozlišením.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** Větší X‑dimenze usnadňuje čtení čárového kódu skenery s nízkým rozlišením, zatímco menší hodnota umožňuje zabalit více dat do omezeného prostoru. Upravit tuto hodnotu podle prostředí skenování.

## Krok 4: Definujte počet sloupců pro řízení velikosti čárového kódu

MicroPDF417 umožňuje 1‑4 sloupce. Více sloupců vytváří kratší, širší čárový kód; méně sloupců vytváří vyšší, užší.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Proč je to důležité:** Výběrem správného počtu sloupců můžete čárový kód umístit do konkrétního UI prvku nebo tištěného štítku bez ručního škálování.

## Krok 5: Uložte čárový kód jako PNG obrázek

Nakonec zapište vygenerovaný čárový kód na disk. PNG zachovává bezztrátovou kvalitu, což je důležité pro ostré skenování.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Pokud cílový adresář neexistuje, metoda `Save` vyhodí `ArgumentException`. Můžete se proti tomu chránit jednoduchou kontrolou:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Kompletní zdrojový kód

Složení všech částí dohromady, zde je kompletní, spustitelný program:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Spuštěním tohoto programu se vytvoří soubor s názvem **MicroPdf417.png**, který vypadá jako snímek obrazovky níže (obrázek vynechán pro stručnost). Čárový kód kóduje text *Sample* a respektuje nastavení X‑dimenze a sloupců, které jste definovali.

## Přizpůsobení dalších možností PDF417

Zatímco tento průvodce se zaměřuje na parametry **customize pdf417 barcode**, které ovlivňují velikost, Aspose.BarCode nabízí mnoho dalších nastavení, která můžete potřebovat:

| Vlastnost | Účel | Typické hodnoty |
|----------|------|-----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Řídí počet řádků (výška) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Nastavuje úroveň korekce chyb (vyšší = tolerantnější) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Generuje zkrácený čárový kód (bez stop pattern) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Volí numerickou, textovou nebo bajtovou kompakci | `CompactionModes.Numeric`, etc. |

**Tip:** Když potřebujete čárový kód, který se vejde do pevné šířky, začněte zvyšováním `Columns` a snižováním `XDimension`. Pokud skener hlásí chybějící symboly, zvyšte `ErrorLevel` pro zlepšení redundance.

## Řešení okrajových případů

* **Text příliš dlouhý pro MicroPDF417:** Varianta Micro podporuje až 1 KB dat. Pokud váš řetězec překročí tento limit, přepněte na plnou symbologii `Pdf417` změnou `EncodeTypes.MicroPdf417` na `EncodeTypes.Pdf417`.
* **Nepodporovaný formát obrázku:** `BarCodeImageFormat` také podporuje `Jpeg`, `Bmp` a `Gif`. Vyberte formát, který odpovídá vašemu následnému zpracovatelskému řetězci.
* **Cesty napříč platformami:** Použijte `Path.Combine` místo pevně zadaných zpětných lomítek, když cílíte na Linux nebo macOS.

## Ověření čárového kódu

Můžete ověřit vygenerovaný obrázek pomocí jakékoli standardní aplikace pro skenování čárových kódů (mobilní nebo desktopové). Skener by měl vrátit původní text **Sample**. Pokud selže:

1. Zkontrolujte, že X‑dimenze není nastavena pod 1 pixel (některé skenery nedokážou rozlišit subpixelové moduly).
2. Ujistěte se, že výstupní soubor není poškozený — spusťte program znovu a porovnejte velikosti souborů.
3. Zvyšte `ErrorLevel` pro zlepšení tolerance.

## Závěr

Nyní víte, **how to generate barcode** v C# pomocí Aspose.BarCode, jak **customize pdf417 barcode** rozměry a počet sloupců, a jak **create barcode image C#** projekty mohou vložit přímo. Kompletní příklad demonstruje praktický workflow od nastavení projektu až po finální PNG výstup.

Dále prozkoumejte další symbologie jako QR, Code128 nebo DataMatrix výměnou hodnoty výčtu `EncodeTypes`. Úprava dalších parametrů jako `Resolution` nebo `Margin` vám umožní jemně doladit každý čárový kód pro vaši konkrétní aplikaci.

Šťastné kódování a ať vaše čárové kódy posílí váš další automatizační projekt!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód jako obrázek v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak vytvořit PDF417 čárový kód s Aspose – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Jak uložit čárový kód v C# – Generovat PDF417 čárové kódy](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}