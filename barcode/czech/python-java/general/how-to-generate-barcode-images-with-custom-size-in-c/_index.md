---
category: general
date: 2026-08-22
description: Jak rychle vygenerovat čárový kód a naučit se, jak změnit velikost čárového
  kódu při exportu obrázku čárového kódu jako PNG pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: cs
lastmod: 2026-08-22
og_description: Jak generovat čárový kód v C# a snadno změnit velikost čárového kódu
  před exportem obrázku čárového kódu jako PNG. Postupujte podle tohoto kompletního
  návodu.
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: Jak generovat obrázky čárových kódů s vlastní velikostí v C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak generovat obrázky čárových kódů s vlastní velikostí v C#
url: /cs/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat obrázky čárových kódů s vlastní velikostí v C#

Pokud potřebujete **jak generovat čárový kód** pro poštovní automatizaci, sledování zásob nebo vstupenky na akce, tento průvodce vám představí kompletní, připravené řešení v C#. Také se naučíte **jak změnit velikost čárového kódu** a **exportovat obrázek čárového kódu** ve formátu PNG, aniž byste opustili své IDE.

Použijeme knihovnu Aspose.BarCode, protože podporuje symbologii OneCode, umožňuje řídit rozměry pixel po pixelu a zpracovává export obrázku jedním voláním metody. Na konci tutoriálu budete mít čtyři soubory PNG – každý představuje OneCode čárový kód s jiným počtem číslic.

## Požadavky

- .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.6+)
- Visual Studio 2022 (nebo jakýkoli jiný C# editor)
- NuGet reference na **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- Základní znalost syntaxe C#

> **Tip:** Pokud knihovnu hodnotíte, Aspose nabízí bezplatnou 30‑denní zkušební verzi, která zahrnuje všechny funkce čárových kódů.

## Krok 1: Nastavte minimální konzolový projekt

Vytvořte novou konzolovou aplikaci a přidejte balíček Aspose.BarCode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Vygenerovaný soubor `Program.cs` bude obsahovat kompletní logiku generování čárových kódů.

## Krok 2: Jak generovat čárový kód – vytvořte znovupoužitelnou metodu

Níže je samostatná metoda, která přijímá řetězec dat, požadovaný název souboru a volitelné parametry velikosti. Tato metoda ukazuje **jak generovat čárový kód** jako základní vzor.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### Proč je tato metoda důležitá

- **Zapouzdření:** Všechna nastavení související s velikostí jsou na jednom místě, což usnadňuje volání metody s různými rozměry.
- **Znovupoužitelnost:** Stejnou metodu můžete použít pro libovolnou délku řetězce OneCode, což je podstatné, protože OneCode akceptuje pouze 20‑31 číslic.
- **Přehlednost:** Komentáře označené emotikony provádějí čtenáře třemi logickými fázemi – inicializace, změna velikosti a export.

## Krok 3: Změna velikosti čárového kódu pro různé požadavky

Někdy skener očekává vyšší čárový kód nebo rozvržení tisku vyžaduje užší modul. Vlastnost `XDimension.Pixels` řídí šířku jednoho modulu čárového kódu, zatímco `BarHeight.Pixels` nastavuje celkovou výšku.

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**Klíčové body při změně velikosti:**

- **Minimální X‑rozměr:** 1 pixel je technicky povolen, ale většina scannerů potřebuje alespoň 2 pixely pro spolehlivé čtení.
- **Maximální výška:** Neexistuje pevný limit, ale velmi vysoké čárové kódy mohou přesáhnout tiskovou oblast na standardních štítcích.
- **Poměr stran:** Udržujte poměr výšky k šířce modulu vyvážený (≈12‑15 × šířka modulu), aby nedošlo k deformaci.

## Krok 4: Export obrázku čárového kódu do jiných formátů (volitelné)

Metoda `Save` přijímá několik hodnot `BarCodeImageFormat`: `Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`. Pokud potřebujete bezztrátový vektorový formát, můžete exportovat do `Svg`.

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

Export do PNG je nejčastější volba, protože zachovává ostré hrany a je široce podporován webovými prohlížeči i tiskovými řetězci.

## Očekávaný výstup

Po spuštění programu se ve složce projektu vytvoří čtyři soubory PNG:

- `PostalOneCodeBarcode20Digits.png` – 20‑ciferný OneCode čárový kód
- `PostalOneCodeBarcode25Digits.png` – 25‑ciferný OneCode čárový kód
- `PostalOneCodeBarcode29Digits.png` – 29‑ciferný OneCode čárový kód
- `PostalOneCodeBarcode31Digits.png` – 31‑ciferný OneCode čárový kód

Každý obrázek bude vypadat podobně jako zástupný obrázek níže (skutečná grafika závisí na zadaných číselných datech).

![Příklad generování čárového kódu](https://example.com/placeholder.png "Příklad generování čárového kódu")

*Alt text obrázku obsahuje hlavní klíčové slovo pro přístupnost a SEO.*

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Co když je řetězec dat kratší než 20 číslic?** | OneCode vyžaduje minimálně 20 číslic. Doplněte řetězec úvodními nulami nebo použijte jinou symbologii (např. Code128). |
| **Mohu generovat čárové kódy v multithreaded prostředí?** | Ano. `BarcodeGenerator` není thread‑safe, takže vytvořte samostatný generátor pro každý vlákno. |
| **Jak nastavit barvu pozadí?** | Použijte `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` před voláním `Save`. |
| **Existuje způsob, jak vložit obrázek přímo do HTML stránky?** | Uložte obrázek do `MemoryStream`, převedete ho na Base64 a vložte pomocí `<img src="data:image/png;base64,..." />`. |

## Závěr

Nyní víte **jak generovat obrázky čárových kódů** v C# pomocí Aspose.BarCode, **jak změnit velikost čárového kódu** úpravou X‑rozměru a výšky čáry a **jak exportovat obrázek čárového kódu** ve formátu PNG (nebo jiném). Znovupoužitelná metoda `GenerateOneCode` vám umožní vytvořit libovolný OneCode čárový kód mezi 20 a 31 číslicemi jedním řádkem kódu.

Odtud můžete:

- Experimentovat s dalšími symbologiemi (`EncodeTypes.Code128`, `EncodeTypes.QR`).
- Integrovat generátor do webového API, které vrací obrázky čárových kódů na požádání.
- Kombinovat výstup PNG s knihovnou PDF a vkládat čárové kódy do přepravních štítků.

Šťastné programování a klidně se podělte o své vlastní variace v komentářích!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem](/barcode/english/net/datamatrix-barcode-configuration/)
- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}