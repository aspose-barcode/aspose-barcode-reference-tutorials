---
category: general
date: 2026-09-07
description: Vytvářejte obrázky poštovních čárových kódů v C# a naučte se, jak změnit
  výšku čárového kódu pomocí stručného příkladu generátoru čárových kódů v C# tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode images
- barcode generator example c#
- change barcode height
language: cs
lastmod: 2026-09-07
og_description: Vytvářejte obrázky poštovních čárových kódů v C# a objevte nejjednodušší
  způsob, jak změnit výšku čárového kódu pomocí přehledného příkladu generátoru čárových
  kódů v C#.
og_image_alt: Screenshot showing created postal barcode images with custom height
og_title: Vytvořte obrázky poštovních čárových kódů – nastavte výšku čárového kódu
  v C#
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create postal barcode images in C# and learn how to change barcode
    height with a concise barcode generator example C# tutorial.
  headline: Create postal barcode images and set barcode height in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Vytvořte obrázky poštovních čárových kódů a nastavte výšku čárového kódu v
  C#
url: /cs/python-java/general/create-postal-barcode-images-and-set-barcode-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte obrázky poštovních čárových kódů a nastavte výšku čárového kódu v C#

Pokud potřebujete **vytvořit obrázky poštovních čárových kódů** pro poštovní aplikace, tento průvodce vám ukáže kompletní, připravené řešení k okamžitému spuštění. Uvidíte **příklad generátoru čárových kódů v C#**, který vytváří jak kódy Planet, tak RM4SCC, a naučíte se **změnit výšku čárového kódu** přímo v kódu.

Tutoriál pokrývá vše, co potřebujete k okamžitému generování poštovních čárových kódů: požadované NuGet balíčky, přípravu složky, generování s výchozí výškou, úpravu pevné výšky a běžné úskalí, kterým se vyhnout.

## Požadavky

- .NET 6.0 SDK nebo novější nainstalováno  
- Visual Studio 2022 (nebo jakékoli C# IDE)  
- NuGet balíček **Aspose.BarCode** (`Install-Package Aspose.BarCode`)  

Tyto komponenty vám poskytují přístup ke třídě `BarcodeGenerator`, která je používána ve všech příkladech.

## Krok 1: Připravte výstupní složku

Generátor zapisuje soubory PNG na disk, takže složka musí existovat a být zapisovatelná.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define where the barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
Console.WriteLine($"Images will be saved to: {outputFolder}");
```

*Proč je to důležité*: Pokus o uložení do neexistující cesty vyvolá `DirectoryNotFoundException`. `Directory.CreateDirectory` je bezpečné, protože nic neudělá, pokud složka již existuje.

## Krok 2: Vygenerujte výchozí výšku Planet a RM4SCC čárových kódů

Když vynecháte vlastnost `BarHeight`, knihovna automaticky zvolí optimální výšku (režim auto). To je užitečné pro rychlé prototypy.

```csharp
// Planet barcode – auto height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // Set module width (X dimension) to 4 pixels for readability
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode – auto height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                BarCodeImageFormat.Png);
```

**Výsledek**: V `Barcodes/` se objeví dva soubory PNG s výškou čáry zvolené knihovnou.

## Krok 3: Nastavte explicitní výšku čáry (100 pixelů)

Někdy poštovní specifikace vyžadují pevnou výšku čáry. Můžete ji nastavit pomocí vlastnosti `BarHeight.Pixels`.

```csharp
// Planet barcode – fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },   // module width
            BarHeight = { Pixels = 100 }   // explicit height
        }
    }
};
planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode – fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 }
        }
    }
};
rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Proč to můžete potřebovat**: Poštovní služby často definují minimální výšku čáry pro spolehlivé skenování. Nastavení pevné výšky zajišťuje soulad se všemi vygenerovanými obrázky.

## Krok 4: Ověřte vygenerované obrázky

Můžete otevřít soubory PNG v libovolném prohlížeči obrázků. Vizuelní rozdíl je v délce čáry:

- **Soubory s automatickou výškou**: výška čáry se přizpůsobuje délce dat.  
- **Soubory s pevnou výškou**: čáry mají přesně 100 pixelů, bez ohledu na obsah.

Pokud potřebujete programově potvrdit výšku, můžete načíst obrázek pomocí `System.Drawing` a zkontrolovat `Bitmap.Height`.

```csharp
using System.Drawing;

void PrintBarHeight(string filePath)
{
    using var bmp = new Bitmap(filePath);
    Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
}

PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
```

## Profesionální tip: Úprava DPI pro vysoce rozlišený tisk

Když bude čárový kód tisknut na štítkový tiskárně, můžete chtít vyšší nastavení DPI. Vlastnost `Resolution` vám umožní to ovládat, aniž byste měnili rozměry v pixelech.

```csharp
planetFixed.Parameters.Resolution = 300; // 300 dpi for crisp prints
planetFixed.Save(Path.Combine(outputFolder, "Planet_300dpi.png"),
                 BarCodeImageFormat.Png);
```

## Běžná úskalí a jak se jim vyhnout

| Problém | Příčina | Řešení |
|-------|-------|-----|
| **Obrázek nebyl vytvořen** | Chybějící výstupní složka nebo nedostatečná oprávnění k zápisu | Zavolejte `Directory.CreateDirectory` a spusťte aplikaci s dostatečnými oprávněními |
| **Čárový kód nečitelný** | X‑dimenze je příliš malá (např. 1 pixel) | Použijte alespoň 2 pixely; 4 pixely fungují dobře pro většinu skenerů |
| **Nesprávný typ čárového kódu** | Špatná hodnota `EncodeTypes` | Ověřte poštovní specifikaci (Planet vs. RM4SCC) a použijte odpovídající výčet |

## Kompletní zdrojový kód (připravený ke kopírování)

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // Step 1 – Prepare output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);
        Console.WriteLine($"Saving images to: {outputFolder}");

        // -------------------------------------------------
        // Step 2 – Auto‑height barcodes
        // -------------------------------------------------
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 3 – Fixed 100‑pixel height barcodes
        // -------------------------------------------------
        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 4 – Verify heights (optional)
        // -------------------------------------------------
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
    }

    static void PrintBarHeight(string filePath)
    {
        using var bmp = new Bitmap(filePath);
        Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
    }
}
```

Spuštěním programu se vytvoří čtyři soubory PNG:

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Každý

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořte poštovní čárový kód v C# – kompletní příklad generátoru](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [.net generátor čárových kódů – změna výšky čárového kódu](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)
- [Vytvořte čárový kód s vlastní výškou – jednorozměrné čárové kódy](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}