---
category: general
date: 2026-09-26
description: Naučte se, jak vytvořit obrázek poštovního čárového kódu v C#. Tento
  průvodce vám ukáže, jak generovat planetární čárový kód a nastavit výšku čárového
  kódu pro vlastní výstup.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- barcode generator custom height
- how to set barcode height
language: cs
lastmod: 2026-09-26
og_description: Vytvořte rychle obrázek poštovního čárového kódu v C#. Postupujte
  podle tohoto tutoriálu, abyste vygenerovali planetární čárový kód, nastavili výšku
  čárového kódu a vytvořili vysoce kvalitní PNG soubory.
og_image_alt: Screenshot of a generated postal barcode image with custom bar height
og_title: Vytvořte obrázek poštovního čárového kódu s vlastními výškami v C# – krok
  za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create postal barcode image in C#. This guide shows you
    how to generate planet barcode and set barcode height for custom output.
  headline: How to create postal barcode image with custom heights in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Jak vytvořit obrázek poštovního čárového kódu s vlastními výškami v C#
url: /cs/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit obrázek poštovního čárového kódu s vlastní výškou v C#

Pokud potřebujete **vytvořit obrázek poštovního čárového kódu** pro poštovní štítky, tento tutoriál vám ukáže přesné kroky. Naučíte se, jak vygenerovat Planet čárový kód, upravit výšku čáry a uložit výsledek jako PNG soubor – vše pomocí knihovny Aspose.BarCode pro .NET.

Vytvoření obrázku čárového kódu nevyžaduje externí nástroj pro návrh. Na konci tohoto průvodce budete schopni vytvořit jak čárové kódy s výchozí výškou, tak s vlastní výškou pro standardy Planet a RM4SCC, připravené k integraci do jakéhokoli odesílacího workflow.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný  
* Visual Studio 2022 (nebo libovolné C# IDE)  
* Aspose.BarCode pro .NET přidaný přes NuGet (`Install-Package Aspose.BarCode`)  

Žádná další konfigurace není potřeba; knihovna interně zajišťuje vykreslování obrázku.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte novou konzolovou aplikaci a přidejte požadované `using` direktivy.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Tyto jmenné prostory zpřístupňují třídu `BarcodeGenerator` a výčtový typ `EncodeTypes`, které použijete k **generování Planet čárového kódu** a dalších poštovních formátů.

## Krok 2: Vytvoření Planet čárového kódu s výchozí výškou čáry

První příklad vytváří Planet čárový kód s výchozí výškou čáry knihovny. Tento příklad ukazuje základní výstup před aplikací jakýchkoli vlastních rozměrů.

```csharp
// Initialize the generator for a Planet barcode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels for better readability
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode image; the default bar height is applied automatically
planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);
```

**Proč je to důležité:** Výchozí výška je vhodná pro většinu tiskáren štítků, ale některé workflow vyžadují vyšší čáry pro zvýšenou spolehlivost skenování. Kód výše vám poskytne referenční obrázek, se kterým můžete porovnat verzi s vlastní výškou.

## Krok 3: Nastavení vlastní výšky čáry pro Planet čárový kód

Pro **ruční nastavení výšky čárového kódu** přiřaďte pixelovou hodnotu k `BarHeight.Pixels`. Následující úryvek vytvoří Planet čárový kód vysoký 100 pixelů.

```csharp
// Initialize a second generator for the same data
BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define X‑dimension and a custom bar height of 100 pixels
planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**Tip:** Zvolte výšku čáry, která odpovídá DPI vaší tiskárny. Pro 300 dpi tiskárnu představuje 100 pixelů přibližně 0,33 palce, což je často doporučováno pro poštovní skenery.

## Krok 4: Vytvoření RM4SCC čárového kódu s výchozí výškou

RM4SCC je další běžná poštovní symbologie. Proces je obdobný jako u Planet příkladu, ale používá `EncodeTypes.RM4SCC`.

```csharp
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set X‑dimension; the library applies the default bar height automatically
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);
```

Tento krok potvrzuje, že stejná logika **generátoru čárových kódů s vlastní výškou** funguje napříč různými poštovními formáty.

## Krok 5: Nastavení vlastní výšky pro RM4SCC čárový kód

Nakonec upravte výšku čáry pro RM4SCC čárový kód stejným způsobem, jako jste to udělali pro Planet čárový kód.

```csharp
BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Define both X‑dimension and a 100‑pixel bar height
rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the custom‑height image
rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

## Očekávaný výstup

Spuštěním kompletního programu vzniknou čtyři PNG soubory ve výstupním adresáři projektu:

| Název souboru                              | Výška čáry | Symbolika |
|--------------------------------------------|------------|-----------|
| `PostalPlanetBarHeightDefault.png`        | default    | Planet    |
| `PostalPlanetBarHeight100Pixels.png`      | 100 px     | Planet    |
| `PostalRM4SCCBarHeightDefault.png`        | default    | RM4SCC    |
| `PostalRM4SCCBarHeight100Pixels.png`      | 100 px     | RM4SCC    |

Každý obrázek zobrazuje jasný, vysokokontrastní čárový kód připravený k tisku na poštovních štítcích. PNG soubory můžete otevřít v libovolném prohlížeči obrázků a ověřit tak rozměry čar.

## Časté otázky a okrajové případy

**Co když potřebuji výšku čáry v milimetrech místo pixelů?**  
Knihovna pracuje v pixelech, protože přímo mapuje na rozlišení bitmapy. Převod milimetrů na pixely provedete pomocí DPI tiskárny:  
`pixels = (mm / 25.4) * DPI`. Nastavte `BarHeight.Pixels` na vypočtenou hodnotu.

**Mohu změnit výšku čáry po volání `Save`?**  
Ne. Obrázek čárového kódu je vykreslen v okamžiku, kdy je voláno `Save`. Všechny parametry upravte před tímto voláním.

**Je potřeba větší X‑dimension pro vyšší čáry?**  
Zvýšení `XDimension` rozšíří každý modul, což může zlepšit čitelnost na tiskárnách s nízkým rozlišením. Na druhou stranu se tím zvětší celková šířka čárového kódu. Otestujte obě hodnoty a najděte optimální poměr pro velikost vašeho štítku.

**Bude stejný kód fungovat na .NET Framework 4.8?**  
Ano. Aspose.BarCode podporuje .NET Framework 4.6.2 a novější, takže můžete cílit na starší runtime bez úprav.

## Kompletní zdrojový kód pro rychlé zkopírování

Níže je kompletní, spustitelný program, který zahrnuje všechny výše popsané kroky.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ---------- Planet barcode (default height) ----------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- Planet barcode (custom 100‑pixel height) ----------
        BarcodeGenerator planetHeightGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        planetHeightGenerator.Save("PostalPlanetBarHeight100Pixels.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (default height) ----------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Save("PostalRM4SCCBarHeightDefault.png", BarCodeImageFormat.Png);

        // ---------- RM4SCC barcode (custom 100‑pixel height) ----------
        BarcodeGenerator rm4sccHeightGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccHeightGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccHeightGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccHeightGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("All barcode images have been generated successfully.");
    }
}
```

Spusťte program a konzole potvrdí, že každý obrázek byl uložen. Nyní můžete tyto PNG soubory vložit do šablon poštovních štítků, vytisknout je nebo odeslat třetí straně prostřednictvím logistického API.

## Závěr

Nyní víte, jak **vytvořit obrázek poštovního čárového kódu** v C# pomocí Aspose.BarCode. Průvodce pokrýval generování Planet čárového kódu, úpravu výšky čáry a aplikaci stejné techniky na RM4SCC čárové kódy. Ovládáním `XDimension` a `BarHeight.Pixels` dosáhnete přesných vizuálních výsledků, které splňují požadavky poštovních služeb.

Dále můžete zkoumat související témata, jako je **generování QR kódů pro sledování**, **vkládání čárových kódů do PDF faktur** nebo **hromadné zpracování více obrázků čárových kódů**. Úprava výšky čáry je jen jedním z nástrojů; můžete také měnit barvy, přidávat lidsky čitelný text nebo exportovat do SVG pro webové použití.

Šťastné kódování a ať vaše poštovní zásilky skenují bezchybně!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Vytvořit obrázek poštovního čárového kódu v C# – krok za krokem](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)
- [Vytvořit obrázky poštovních čárových kódů – snadno změnit výšku čárového kódu](/barcode/english/python-java/general/create-postal-barcode-images-change-barcode-height-easily/)
- [Jak vygenerovat poštovní čárový kód v C# s vlastními rozměry](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}