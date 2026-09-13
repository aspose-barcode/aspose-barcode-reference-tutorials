---
category: general
date: 2026-09-13
description: Naučte se, jak v C# generovat čárový kód, přizpůsobit jeho velikost a
  uložit obrázek čárového kódu jako PNG pomocí Aspose.BarCode. Kompletní krok‑za‑krokem
  průvodce.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: cs
lastmod: 2026-09-13
og_description: Jak v C# generovat čárový kód s vlastní velikostí a uložit obrázek
  čárového kódu jako PNG. Postupujte podle tohoto kompletního průvodce pro Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Jak generovat čárový kód, nastavit vlastní velikost a uložit obrázek v C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Jak vygenerovat sadu čárových kódů s vlastní velikostí a uložit obrázek v C#
url: /cs/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat čárový kód s vlastní velikostí a uložit obrázek v C#

Pokud potřebujete **jak vygenerovat čárový kód** v .NET aplikaci, tento tutoriál vám ukáže kompletní řešení. Uvidíte, jak upravit **vlastní velikost čárového kódu** a **uložit obrázek čárového kódu** pomocí několika řádků C# kódu.

Generování čárových kódů je běžná potřeba pro inventární systémy, přepravní štítky a pokladní aplikace. Na konci tohoto průvodce budete mít spustitelný program, který vytvoří dva DataBar‑Stacked‑Omnidirectional čárové kódy, každý s jiným poměrem stran, a zapíše je jako PNG soubory na disk.

**Prerequisites**

- .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakékoli C# IDE
- Aspose.BarCode for .NET (bezplatná zkušební verze nebo licencovaný NuGet balíček)

---

## Jak vygenerovat čárový kód pomocí Aspose.BarCode

Knihovna Aspose.BarCode abstrahuje nízkoúrovňové detaily standardů čárových kódů, což vám umožní soustředit se na data, která chcete zakódovat, a na vizuální vzhled, který potřebujete.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Proč je každý řádek důležitý

| Krok | Vysvětlení |
|------|------------|
| **1️⃣ Create a generator** | Výčtový typ `EncodeTypes.DatabarStackedOmniDirectional` říká Aspose, kterou symbologii čárového kódu použít. Řetězec `"(01)12345678901231"` následuje formát dat GS1‑128, kde `(01)` je identifikátor aplikace pro GTIN. |
| **2️⃣ Set X‑dimension** | `XDimension.Pixels` určuje šířku jednoho modulu čárového kódu (nejmenšího pruhu). Změna této hodnoty je hlavní způsob, jak dosáhnout **vlastní velikosti čárového kódu** bez úpravy zakódovaných dat. |
| **3️⃣ Set aspect ratio & save** | `DataBar.AspectRatio` řídí poměr výšky k šířce symbolů DataBar. Poměr 15 vytváří relativně krátký, široký čárový kód, zatímco 30 jej prodlužuje. `Save` zapíše vizuální reprezentaci do PNG souboru, čímž splňuje požadavek **save barcode image**. |
| **4️⃣ Change aspect ratio & save again** | Opětovné použití stejné instance generátoru vám umožní vytvořit více obrázků s různými vizuálními charakteristikami při zachování stejných dat. |

---

## Úprava vlastní velikosti čárového kódu mimo X‑dimension

Zatímco `XDimension.Pixels` nastavuje šířku modulu, můžete také jemně doladit celkové rozměry čárového kódu kombinací dvou vlastností:

1. **`BarHeight`** – explicitní výška v pixelech.  
2. **`BarWidth`** – explicitní šířka v pixelech (přepíše X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Pro tip:** Při tisku čárových kódů vždy otestujte vygenerovaný obrázek ve finální tiskové velikosti. Šířka modulu 2 px funguje pro zobrazení na obrazovce, ale tištěné štítky často vyžadují alespoň 4 px, aby zůstaly čitelné.

---

## Výběr správného formátu obrázku pro uložení čárového kódu

Aspose.BarCode podporuje PNG, JPEG, BMP, GIF a TIFF. PNG je bezztrátový a zachovává ostré hrany, což z něj činí nejbezpečnější volbu pro většinu aplikací. Pokud potřebujete menší soubor pro web, JPEG s nastavením kvality 90 funguje dobře, ale mějte na vědomí, že kompresní artefakty mohou ovlivnit spolehlivost skenování.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Kompletní, spustitelný příklad

Níže je samostatná konzolová aplikace, kterou můžete zkopírovat, vložit a spustit. Ukazuje **jak vygenerovat čárový kód**, upravit **vlastní velikost čárového kódu** a **uložit obrázek čárového kódu** ve dvou různých formátech.

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
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Očekávaný výstup v konzoli**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Čtyři souborové obrázky se objeví v programu

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich vlastních projektech.

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generovat PDF417 čárový kód s Aspose – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}