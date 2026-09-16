---
category: general
date: 2026-08-03
description: Vytvořte PNG čárový kód v C# a naučte se, jak změnit poměr stran pro
  obrázky DataBar. Sledujte tento kompletní příklad s kódem a tipy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- how to change aspect ratio
- Aspose.BarCode C#
- DataBar stacked omnidirectional
- barcode image format PNG
language: cs
lastmod: 2026-08-03
og_description: Vytvořte PNG čárový kód v C# a zjistěte, jak změnit poměr stran pro
  DataBar čárové kódy. Tento průvodce vám poskytuje připravený kód k okamžitému spuštění
  a praktické tipy.
og_image_alt: Sample barcode PNG generated with aspect ratio 15
og_title: Vytvořte PNG čárový kód v C# – kompletní příklad s řízením poměru stran
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  headline: Create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# and learn how to change aspect ratio for DataBar
    images. Follow this complete example with code and tips.
  name: Create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: How to change other visual properties?
    text: 'You can adjust foreground color, background color, or add human‑readable
      text through the `generator.Parameters.Barcode` object. For example:'
  - name: What if I need a different image format?
    text: Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as needed.
      PNG remains the best choice for lossless barcode images.
  - name: Does the aspect ratio affect scanning speed?
    text: Higher aspect ratios increase the barcode’s height, which can improve scan
      reliability on devices that struggle with short stacked symbols. However, extremely
      tall barcodes may not fit on small labels, so test with your target hardware.
  - name: Can I generate multiple barcodes in a loop?
    text: Yes. Create a new `BarcodeGenerator` instance for each data string or reuse
      the same instance while updating `CodeText` and `DataBar.AspectRatio`. This
      approach reduces object allocation overhead.
  type: HowTo
tags:
- barcode
- C#
- PNG
- Aspose
title: Vytvořte PNG čárový kód v C# – krok za krokem
url: /cs/python-java/general/create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PNG čárového kódu v C# – krok za krokem

Pokud potřebujete **create barcode PNG** v C#, tento tutoriál vám ukáže přesně jak. Vygenerujete vrstvený omnidirekcionální DataBar čárový kód, uložíte jej jako PNG soubor a naučíte se **jak změnit poměr stran** tak, aby vyhovoval různým skenovacím prostředím.

Průvodce pokrývá vše, co potřebujete: požadované balíčky, kompletní spustitelný program a vysvětlení, proč má každé nastavení význam. Na konci budete mít dva PNG soubory — jeden s poměrem stran 15 a druhý s 30 — připravené k testování nebo produkčnímu použití.

## Požadavky

Než začnete, ujistěte se, že máte:

- .NET 6.0 SDK nebo novější nainstalovaný
- Visual Studio 2022 (nebo jakékoli C# IDE)
- NuGet odkaz na **Aspose.BarCode** (knihovna, která poskytuje `BarcodeGenerator`)
- Oprávnění k zápisu do adresáře, kam budou PNG soubory uloženy

Balíček Aspose.BarCode můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte novou konzolovou aplikaci a importujte jmenné prostory potřebné pro generování čárových kódů a práci se soubory.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // All subsequent steps are inside Main
```

**Proč je to důležité:** Import `Aspose.BarCode.Generation` vám poskytuje přístup k `BarcodeGenerator`. Umístění kódu uvnitř `Main` dělá příklad samostatným a snadno spustitelným.

## Krok 2: Vytvoření generátoru čárového kódu pro vrstvený omnidirekcionální DataBar

Instancujte `BarcodeGenerator` s typem `EncodeTypes.DatabarStackedOmniDirectional` a ukázkovým řetězcem dat GS1‑128.

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");
```

**Proč je to důležité:** Vybraný typ kódování vytváří vysoce hustý DataBar, který lze přečíst většinou moderních skenerů. Řetězec dat odpovídá formátu GS1 Application Identifier (01), který je běžný pro identifikátory produktů.

## Krok 3: Definování X‑dimenze (šířky modulu) v pixelech

Nastavte šířku modulu, aby se řídila celková velikost čárového kódu, aniž by to ovlivnilo jeho čitelnost.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** X‑dimenze 2 pixely dává čárový kód, který není ani příliš malý pro skenery, ani příliš velký pro typické štítky.

## Krok 4: Uložení prvního PNG s poměrem stran 15

Upravte poměr stran DataBar a poté uložte obrázek jako PNG soubor.

```csharp
            // Step 4: Set the DataBar aspect ratio to 15 and save the image
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;
            string outputPath15 = @"YOUR_DIRECTORY\DatabarAspectRatio15.png";
            generator.Save(outputPath15, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath15} (aspect ratio 15).");
```

**Proč je to důležité:** Poměr stran řídí vztah výšky k šířce vrstveného DataBar. Hodnota 15 je běžná výchozí hodnota, která vyvažuje čitelnost a výšku štítku.

## Krok 5: Změna poměru stran na 30 a uložení druhého PNG

Upravte stejnou instanci generátoru tak, aby používala větší poměr stran, a poté uložte druhý obrázek.

```csharp
            // Step 5: Change the aspect ratio to 30 and save another image
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string outputPath30 = @"YOUR_DIRECTORY\DatabarAspectRatio30.png";
            generator.Save(outputPath30, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath30} (aspect ratio 30).");
        }
    }
}
```

**Proč je to důležité:** Zvýšení poměru stran prodlouží čárový kód vertikálně, což může zlepšit spolehlivost skenování na zařízeních s nízkým rozlišením nebo když je štítek tištěn na úzkém médiu.

## Očekávaný výstup

Po spuštění programu vzniknou dva PNG soubory:

| File                               | Aspect Ratio | Approximate dimensions (pixels) |
|------------------------------------|--------------|---------------------------------|
| `DatabarAspectRatio15.png`         | 15           | 200 × 300 (width × height)      |
| `DatabarAspectRatio30.png`         | 30           | 200 × 600 (width × height)      |

Oba obrázky obsahují jasný, skenovatelný DataBar čárový kód, který kóduje GS1 identifikátor `(01)12345678901231`.

## Časté otázky a okrajové případy

### Jak změnit další vizuální vlastnosti?

Můžete upravit barvu popředí, barvu pozadí nebo přidat lidsky čitelný text pomocí objektu `generator.Parameters.Barcode`. Například:

```csharp
generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
generator.Parameters.Barcode.CodeTextParameters.ShowCodeText = true;
```

### Co když potřebuji jiný formát obrázku?

Nahraďte `BarCodeImageFormat.Png` hodnotou `Jpeg`, `Bmp` nebo `Gif` podle potřeby. PNG zůstává nejvhodnější volbou pro bezztrátové obrázky čárových kódů.

### Ovlivňuje poměr stran rychlost skenování?

Vyšší poměr stran zvyšuje výšku čárového kódu, což může zlepšit spolehlivost skenování na zařízeních, která mají problémy se čtením krátkých vrstvených symbolů. Nicméně extrémně vysoké čárové kódy se nemusí vejít na malé štítky, proto testujte s vaším cílovým hardwarem.

### Můžu generovat více čárových kódů ve smyčce?

Ano. Vytvořte novou instanci `BarcodeGenerator` pro každý řetězec dat nebo znovu použijte stejnou instanci a aktualizujte `CodeText` a `DataBar.AspectRatio`. Tento přístup snižuje režii alokace objektů.

## Profesionální tipy

- **Znovupoužití generátoru**: Změna pouze `CodeText` nebo `AspectRatio` eliminuje nutnost znovu vytvářet objekt, což urychluje dávkové zpracování.
- **Validace výstupu**: Použijte ruční skener nebo mobilní aplikaci k potvrzení, že vygenerované PNG se načítá správně, před nasazením do produkce.
- **Pojmenování souborů**: Vložte poměr stran do názvu souboru (jak je ukázáno), abyste během testování snadno sledovali různé varianty.

## Závěr

Nyní víte, jak **create barcode PNG** soubory v C# a přesně **jak změnit poměr stran** pro vrstvené omnidirekcionální DataBar symboly. Kompletní příklad ukazuje inicializaci, nastavení X‑dimenze, manipulaci s poměrem stran a ukládání obrázku — vše v jednom spustitelném programu.

Odtud můžete zkoumat další typy čárových kódů, experimentovat s barvami nebo integrovat generátor do většího reportovacího či inventárního systému. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Customize Barcode - Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}