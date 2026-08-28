---
category: general
date: 2026-08-06
description: Vygenerujte obrázek čárového kódu v C# pomocí Aspose.BarCode. Naučte
  se, jak generovat Databar, upravit vlastní velikost čárového kódu a změnit výšku
  čárového kódu pomocí jednoduchého kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: cs
lastmod: 2026-08-06
og_description: Vytvořte obrázek čárového kódu v C# pomocí Aspose.BarCode. Tento tutoriál
  vám ukáže, jak vytvořit čárový kód Databar Omnidirectional, přizpůsobit jeho velikost
  a efektivně změnit výšku čárového kódu.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Vytvořte obrázek čárového kódu v C# – kompletní průvodce Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Vytvořte obrázek čárového kódu v C# pomocí Aspose.BarCode
url: /cs/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu v C# s Aspose.BarCode

Pokud potřebujete **vytvořit obrázek čárového kódu** programově, tento průvodce vám přesně ukáže, jak na to. Ať už budujete systém inventarizace v maloobchodě nebo portál pro sledování logistiky, uvidíte kompletní workflow pro vytvoření Databar Omnidirectional čárového kódu, úpravu jeho rozměrů a uložení výsledku jako PNG soubor.

Vytváření obrázku čárového kódu je běžná potřeba, ale vývojáři se často ptají **jak vytvořit Databar** s přesnou velikostí, kterou potřebují. V tomto tutoriálu se naučíte vytvořit Databar čárový kód, přizpůsobit jeho šířku a výšku a změnit výšku čárového kódu bez přepisování celého generátoru.

## Požadavky

* .NET 6.0 SDK nebo novější (kód funguje s .NET Core a .NET Framework)
* Visual Studio 2022 (nebo jakékoli IDE podporující C#)
* Platná licence Aspose.BarCode pro .NET (bezplatná evaluační verze funguje pro testování)
* Základní znalost syntaxe C#

## Krok 1: Instalace Aspose.BarCode

Přidejte NuGet balíček Aspose.BarCode do svého projektu:

```bash
dotnet add package Aspose.BarCode
```

Balíček obsahuje třídu `BarcodeGenerator`, která je používána v celém tomto tutoriálu. Po instalaci obnovte projekt, aby se stáhly závislosti.

## Krok 2: Vytvoření základního generátoru čárových kódů

První řádek kódu vytváří **generátor čárových kódů**, který bude generovat symbol Databar Omnidirectional. Výčtový typ `EncodeTypes.DatabarOmniDirectional` říká knihovně, kterou symbologii použít, a datový řetězec následuje syntaxi GS1 Application Identifier.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Proč je to důležité:** Objekt `BarcodeGenerator` je vstupním bodem pro každou operaci s čárovým kódem. Výběrem `DatabarOmniDirectional` zajistíte, že výstup bude odpovídat standardu GS1 pro maloobchodní skenování.

## Krok 3: Nastavení vlastní X‑dimenze (šířka modulu)

X‑dimenze řídí šířku nejúžšího pruhu. Nastavením malé hodnoty v pixelech získáte kompaktní čárový kód, zatímco větší hodnoty zvětší celkovou šířku.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Vysvětlení:** X‑dimenze 2 pixely je běžná volba pro vysoké rozlišení obrazovek. Upravit tuto hodnotu, pokud potřebujete hustší nebo řidší vizuální hustotu.

## Krok 4: Vytvoření prvního obrázku čárového kódu s konkrétní výškou

Výška čárového kódu je nezávislá na X‑dimenzi. Zde nastavíme výšku pruhu na **30 px** a poté uložíme obrázek jako PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Výsledek:** Nyní máte soubor s názvem `DatabarBarHeight30Pixels.png`, který zobrazuje Databar čárový kód vysoký 30 px. Toto demonstruje schopnost **vlastní velikosti čárového kódu** pro konkrétní případ použití, například malý štítek.

## Krok 5: Změna výšky čárového kódu pro větší verzi

Pokud se stejný čárový kód musí objevit na větším štítku, stačí upravit vlastnost výšky a znovu použít stejnou instanci generátoru.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Proč můžete generátor znovu použít:** Změna `BarHeight.Pixels` aktualizuje vnitřní rozvržení bez nutnosti znovu vytvářet objekt, což šetří paměť a zachovává datový řetězec beze změny. Toto je doporučený způsob, jak **měnit výšku čárového kódu** za běhu.

## Krok 6: Ověření výstupu

Otevřete oba PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět dva Databar Omnidirectional čárové kódy, které kódují stejný GTIN, ale liší se ve vertikální velikosti:

* `DatabarBarHeight30Pixels.png` – výška 30 px, vhodná pro kompaktní účtenky.
* `DatabarBarHeight60Pixels.png` – výška 60 px, ideální pro větší štítky na okraji regálu.

Oba obrázky zachovávají stejnou X‑dimenzi, takže poměr pruh‑mezera zůstává konzistentní, zatímco celková výška se mění.

## Běžné varianty a okrajové případy

| Situace | Jak to řešit |
|-----------|------------------|
| **Různá symbologie čárového kódu** | Nahraďte `EncodeTypes.DatabarOmniDirectional` jinou hodnotou enumu (např. `EncodeTypes.Code128`). Zbytek kódu zůstane beze změny. |
| **Rozměry jiné než pixely** | Použijte `generator.Parameters.Barcode.XDimension.Millimeters` nebo `BarHeight.Millimeters`, pokud potřebujete fyzické rozměry pro výstup připravený k tisku. |
| **Průhledné pozadí** | Nastavte `generator.Parameters.ImageBackgroundColor = Color.Transparent;` před voláním `Save`. |
| **Výstup ve vysokém rozlišení** | Zvyšte oba parametry `XDimension.Pixels` a `BarHeight.Pixels` proporcionálně, nebo uložte jako `BarCodeImageFormat.Tiff` pro bezztrátovou kvalitu. |
| **Více čárových kódů v jednom obrázku** | Vytvořte samostatné instance `BarcodeGenerator`, vykreslete každou do `Bitmap`, a poté je spojte pomocí `Graphics.DrawImage`. |

**Pro tip:** Vždy otestujte vygenerovaný čárový kód skutečným skenerem před nasazením do produkce. Skenery mohou interpretovat velmi tenké pruhy odlišně v závislosti na osvětlení a kvalitě senzoru.

## Úplný zdrojový kód pro referenci

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
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Zkopírujte kód do nového konzolového projektu, spusťte jej a uvidíte, že se ve výstupní složce objeví dva PNG soubory.

## Často kladené otázky

**Q: Mohu generovat čárový kód bez instalace licence?**  
A: Evaluační verze Aspose.BarCode funguje bez licence, ale přidává malý vodoznak. Pro produkční použití použijte zakoupenou licenci pomocí `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**Q: Ovlivňuje změna X‑dimenze čitelnost?**  
A: Ano. Velmi malé X‑dimenze mohou způsobit, že čárový kód bude nečitelný na tiskárnách s nízkým rozlišením. Doporučuje se minimálně 1 px pro vykreslování na obrazovce; pro tisk použijte alespoň 0,25 mm.

**Q: Co když potřebuji vygenerovat čárový kód ve formátu JPEG?**  
A: Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. Můžete také nastavit `generator.Parameters.ImageQuality` pro řízení komprese.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# pomocí Aspose.BarCode, jak **vytvořit Databar čárový kód**, upravit **vlastní velikost čárového kódu** a **změnit výšku čárového kódu** na požádání. Kompletní příklad demonstruje nejběžnější workflow a tabulka variant vás vybaví k řešení reálných okrajových případů.

Dále prozkoumejte související témata, jako je **vkládání čárových kódů do PDF dokumentů**, **hromadné generování více čárových kódů** a **používání QR kódů pro mobilní platby**. Každý z těchto scénářů staví na stejných principech, které jsou zde popsány, takže můžete toto znalosti rozšířit s jistotou.

Šťastné programování a ať vaše čárové kódy skenují bezchybně!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit obrázek čárového kódu – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Jak vygenerovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak vygenerovat čárový kód – konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}