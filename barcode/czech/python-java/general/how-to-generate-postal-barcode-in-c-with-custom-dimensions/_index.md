---
category: general
date: 2026-08-22
description: Naučte se, jak v C# generovat poštovní čárový kód a ovládat výšku čáry,
  X‑rozměr a formát obrázku pomocí knihovny generátoru čárových kódů pro C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: cs
lastmod: 2026-08-22
og_description: Vytvořte poštovní čárový kód v C# s plnou kontrolou nad výškou čáry,
  X rozměrem a formátem obrázku. Postupujte podle tohoto krok‑za‑krokem tutoriálu
  a vytvořte dokonalé poštovní symboly.
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: Generujte poštovní čárový kód v C# – kompletní průvodce s vlastní velikostí
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: Jak vygenerovat poštovní čárový kód v C# s vlastními rozměry
url: /cs/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat poštovní čárový kód v C# s vlastními rozměry

Pokud potřebujete v C# generovat poštovní čárový kód, tento průvodce vám ukáže kompletní workflow. Uvidíte, jak ovládat výšku čáry, upravit X‑rozměr čárového kódu a vybrat vhodný formát obrázku čárového kódu.

Poštovní čárové kódy používají poštovní služby po celém světě a spolehlivá implementace musí poskytovat konzistentní rozměry napříč různými symbologiemi. V tomto tutoriálu se naučíte používat třídu **BarcodeGenerator**, měnit šířku čárového kódu a ukládat výsledek jako PNG, JPEG nebo jiný podporovaný formát.

## Předpoklady

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný  
* Odkaz na NuGet balíček **Aspose.BarCode** (nebo jakoukoli kompatibilní knihovnu pro generování čárových kódů v C#)  
* Základní znalosti syntaxe C# a Visual Studio nebo vašeho preferovaného IDE  

Nemusíte používat žádné externí služby; kód běží výhradně na klientském počítači.

## Krok 1: Nastavte projekt a importujte jmenné prostory

Vytvořte novou konzolovou aplikaci a přidejte knihovnu pro čárové kódy. Následující `using` direktivy vám umožní přístup k generátoru a výčtům formátů obrázků.

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

Třída `BarcodeGenerator` je jádrem API generátoru čárových kódů v C#. Vytváří objekt, který obsahuje všechna nastavení vykreslování.

## Krok 2: Vygenerujte základní poštovní čárový kód s výchozími rozměry

První příklad vytváří Planet čárový kód s výchozí výškou čáry. Ukazuje minimální konfiguraci potřebnou k vygenerování poštovního čárového kódu.

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*Proč to funguje*: Když vynecháte vlastnost `BarHeight`, knihovna použije standardní výšku definovanou pro vybranou symbologii. `XDimension` řídí **barcode X dimension**, což přímo ovlivňuje celkovou šířku symbolu.

## Krok 3: Změňte šířku čárového kódu a zvyšte výšku čáry

Často je potřeba vyšší čára, aby vyhověla specifickým poštovním směrnicím. Následující kód nastaví vlastní výšku čáry na 100 pixelů při zachování stejného X‑rozměru.

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*Proč upravovat výšku*: Vlastnost `BarHeight` řídí vertikální velikost každé čáry. Pro poštovní služby, které vyžadují minimální výšku, nastavení této hodnoty zajišťuje soulad bez ovlivnění kódování.

## Krok 4: Vygenerujte RM4SCC čárový kód s výchozím nastavením

RM4SCC je další běžná poštovní symbologie. Kód níže odráží příklad s Planet, ale přepíná výčet `EncodeTypes`.

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

Protože knihovna automaticky vybere vhodnou výchozí výšku pro RM4SCC, získáte obrázek splňující standardy jediným řádkem kódu.

## Krok 5: Změňte výšku čáry pro RM4SCC čárový kód

Pokud poštovní systém vyžaduje vyšší čáru, můžete výšku upravit stejným způsobem jako u Planet.

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*Tip*: Výčet **barcode image format** zahrnuje `Jpeg`, `Bmp`, `Tiff` a `Gif`. Vyberte formát, který odpovídá vašemu následnému zpracování.

## Krok 6: Prozkoumejte další formáty obrázků a dolaďte rozměry

Níže je kompaktní úryvek, který ukazuje, jak přepnout výstupní formát a experimentovat s různými X‑rozměry.

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*Proč iterovat*: Tento cyklus vytvoří matici obrázků, které ilustrují, jak **change barcode width** (pomocí X‑rozměru) ovlivňuje celkový vzhled. Také ukazuje, že stejný generátor může produkovat více typů **barcode image format** bez dalších úprav kódu.

## Časté problémy a jak se jim vyhnout

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Čáry jsou příliš tenké | X rozměr nastaven na 1 pixel nebo méně | Nastavte `XDimension.Pixels` alespoň na 2 pro čitelnost |
| Obrázek je rozmazaný | Ukládání jako JPEG s vysokou kompresí | Použijte `BarCodeImageFormat.Png` pro bezztrátový výstup |
| Neočekávaná velikost při tisku | Není zohledněno DPI | Nastavte `barcodeGenerator.Parameters.ImageResolution.Dpi`, pokud tiskárna vyžaduje konkrétní DPI |
| Špatná symbologie | Použití `EncodeTypes.Planet` pro data RM4SCC | Zvolte správnou hodnotu `EncodeTypes`, která odpovídá specifikaci poštovní služby |

## Ověřte výstup

Po spuštění kódu otevřete některý z vygenerovaných PNG souborů. Měli byste vidět čistý, obdélníkový čárový kód s rovnoměrnými vertikálními čarami. Výška čáry bude odpovídat nastavené hodnotě (např. 100 pixelů) a celková šířka bude odrážet **barcode X dimension**, kterou jste nakonfigurovali.

Pokud potřebujete obrázek vložit do webové stránky, formát PNG funguje nativně v prohlížečích. Pro PDF zprávy můžete PNG převést na pole bajtů a vložit jej pomocí PDF knihovny.

## Kompletní příklad – všechny kroky v jednom programu

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

Po spuštění tohoto programu vzniknou čtyři PNG soubory v `C:\Barcodes\`. Každý soubor demonstruje jinou kombinaci **generate postal barcode**, **barcode X dimension** a **barcode image format**.

## Závěr

Nyní víte, jak v C# generovat poštovní čárový kód a plně ovládat výšku čáry, šířku modulu i výstupní formát. Úpravou **barcode X dimension** a použitím vhodného **barcode image format** můžete splnit jakékoli poštovní specifikace a integrovat symboly do desktopových, webových nebo mobilních aplikací.

Dále prozkoumejte pokročilé funkce, jako je přidání lidsky čitelného textu, použití barevných palet nebo vložení čárového kódu do PDF dokumentů. Tyto témata zahrnují stejné koncepty **barcode generator C#**, které jste právě zvládli, takže můžete tuto základnu rozšířit s jistotou.

## Co byste se měli naučit dál?

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}