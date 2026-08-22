---
category: general
date: 2026-08-22
description: Návod na generátor čárových kódů v C# ukazuje, jak generovat PNG soubory
  čárových kódů, vytvářet DataBar kódy a nastavit výšku čárového kódu během několika
  kroků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- generate barcode PNG
- create DataBar barcode
- adjust barcode height
language: cs
lastmod: 2026-08-22
og_description: Průvodce generátorem čárových kódů v C# vás provede tím, jak generovat
  PNG čárových kódů, vytvářet DataBar čárové kódy a efektivně upravovat výšku čárového
  kódu.
og_image_alt: Screenshot of two DataBar Omni‑directional barcodes with different heights
  saved as PNG files
og_title: generátor čárových kódů C# – vytvořte DataBar kódy a upravte výšku
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to generate barcode PNG files,
    create DataBar barcodes, and adjust barcode height in just a few steps.
  headline: How to use a barcode generator C# to create DataBar Omni‑directional barcodes
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak použít generátor čárových kódů v C# k vytvoření DataBar omnidirekčních
  čárových kódů
url: /cs/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generátor čárových kódů C# k vytvoření DataBar Omni‑directional čárových kódů

Pokud potřebujete **barcode generator C#**, který dokáže vytvářet vysoce kvalitní PNG obrázky, tento průvodce vám pomůže. Naučíte se, jak generovat PNG soubory čárových kódů, vytvořit DataBar Omni‑directional čárový kód a upravit výšku čárového kódu, aniž byste opustili své IDE.

Programové generování čárových kódů odstraňuje ruční krok používání grafického editoru. Na konci tohoto tutoriálu budete mít dva PNG soubory — jeden s výškou čáry 30 pixelů a druhý s výškou čáry 60 pixelů — připravené k vložení do faktur, štítků nebo inventárních systémů.

**Požadavky**

- .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.7+)
- Odkaz na NuGet balíček `Aspose.BarCode` (nebo jakoukoli knihovnu, která poskytuje podobné API)
- Základní znalost C# a Visual Studio nebo vašeho preferovaného IDE

---

## Krok 1: Nastavte projekt barcode generator C#

Vytvoření instance **barcode generator C#** je první věc, kterou uděláte. Konstruktor přijímá dva argumenty: typ čárového kódu (`EncodeTypes.DatabarOmniDirectional`) a datový payload. V tomto příkladu payload následuje formát GS1 Application Identifier pro 14‑ciferný GTIN.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the barcode generator for a DataBar Omni‑directional code
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");   // GTIN‑14 example
```

**Proč je to důležité:** Výčtový typ `EncodeTypes.DatabarOmniDirectional` říká knihovně, aby vykreslila DataBar, který lze číst z libovolného směru, což je ideální pro malé maloobchodní štítky.

---

## Krok 2: Definujte rozměr modulu (X‑dimension)

X‑dimension určuje šířku jednoho modulu čárového kódu. Nastavení na 2 pixely poskytuje ostrý, čitelný obrázek a zároveň udržuje malou velikost souboru.

```csharp
        // Set the module (X) dimension to 2 pixels per module
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:** Pokud potřebujete kompaktnější čárový kód pro omezený prostor, snižte hodnotu na 1 pixel, ale otestujte čitelnost skenerem.

---

## Krok 3: Vygenerujte první PNG s výškou čáry 30 pixelů

Výška čáry určuje, jak vysoké pruhy budou. Výška 30 pixelů je běžná výchozí hodnota pro standardní štítky.

```csharp
        // Set bar height to 30 pixels
        generator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image as PNG
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png",
                       BarCodeImageFormat.Png);
```

Soubor `DatabarBarHeight30Pixels.png` nyní obsahuje **generate barcode PNG**, který lze použít přímo na webových stránkách nebo vytisknout na vyžádání.

---

## Krok 4: Upravit výšku čáry na 60 pixelů a uložit druhý PNG

Změna výšky čáry je tak jednoduchá jako přiřazení nové hodnoty ke stejné vlastnosti. Tím se demonstruje schopnost **adjust barcode height** generátoru.

```csharp
        // Change bar height to 60 pixels for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image
        generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png",
                       BarCodeImageFormat.Png);
    }
}
```

Nyní máte `DatabarBarHeight60Pixels.png`, který je ideální pro větší balení, kde musí být čárový kód skenován z větší vzdálenosti.

**Očekávaný výstup**

- `DatabarBarHeight30Pixels.png` — kompaktní DataBar Omni‑directional čárový kód, výška 30 px.
- `DatabarBarHeight60Pixels.png` — stejný čárový kód, dvojnásobná výška pro lepší viditelnost.

Obě obrázky jsou ve formátu PNG, zachovávají bezztrátovou kvalitu a podporují průhlednost, pokud je potřeba.

---

## Jak generovat PNG soubory čárových kódů v různých formátech

I když se tento tutoriál zaměřuje na PNG, metoda `Save` přijímá i jiné formáty, jako `Jpeg`, `Bmp` a `Svg`. Pro **how to generate barcode** soubory v jiném formátu stačí nahradit `BarCodeImageFormat.Png` požadovanou hodnotou výčtu:

```csharp
generator.Save(@"path\barcode.svg", BarCodeImageFormat.Svg);
```

Volba SVG je užitečná, když potřebujete vektorový obrázek, který se škáluje bez pixelace.

---

## Časté úskalí při **create DataBar barcode** obrázcích

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Čárový kód je rozmazaný | X‑dimension příliš nízká pro cílové rozlišení | Zvyšte `XDimension.Pixels` na 3 nebo 4 |
| Skener kód nečte | Výška čáry příliš krátká pro optiku skeneru | Použijte minimálně 30 pixelů nebo se řiďte specifikacemi skeneru |
| Datový řetězec je odmítnut | Nesprávné formátování GS1 | Ujistěte se, že řetězec začíná správným Application Identifier, např. `(01)` pro GTIN‑14 |

Řešení těchto bodů včas šetří čas při integraci čárových kódů do produkčních pipeline.

---

## Pokročilý tip: Opětovné použití stejného generátoru pro více čárových kódů

Pokud potřebujete **generate barcode PNG** soubory pro dávku produktů, znovu použijte stejnou instanci `BarcodeGenerator` a pouze aktualizujte vlastnost `CodeText`:

```csharp
string[] gtins = { "(01)12345678901231", "(01)98765432109876" };
int[] heights = { 30, 60 };

foreach (var gtin in gtins)
{
    generator.CodeText = gtin;          // Change data payload
    foreach (var h in heights)
    {
        generator.Parameters.Barcode.BarHeight.Pixels = h;
        string fileName = $"Databar_{gtin.Substring(4)}_{h}Px.png";
        generator.Save($@"YOUR_DIRECTORY\{fileName}", BarCodeImageFormat.Png);
    }
}
```

Tento vzor minimalizuje režii vytváření objektů a udržuje kód stručný.

---

## Závěr

Nyní máte kompletní **barcode generator C#** workflow, který **creates DataBar barcodes**, **generates barcode PNG** soubory a umožňuje **adjust barcode height** jedinou změnou vlastnosti. Příklad pokrývá vše od nastavení projektu až po řešení okrajových případů, takže můžete s jistotou integrovat tvorbu čárových kódů do jakékoli .NET aplikace.

**Další kroky**

- Prozkoumejte další symbologie čárových kódů (`EncodeTypes.QR`, `EncodeTypes.Code128`) a rozšiřte své řešení.
- Kombinujte generátor s ASP.NET Core pro dynamické poskytování čárových kódů přes API endpoint.
- Experimentujte s možnostmi barev (`generator.Parameters.Barcode.ForeColor`) pro branding.

Šťastné kódování a ať jsou vaše skeny vždy rychlé!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate One-Dimensional Databar 2D Barcodes Using Aspose.BarCode .NET API](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}