---
category: general
date: 2026-11-17
description: Naučte se generování čárových kódů pomocí Aspose s podrobným návodem
  krok za krokem, jak přizpůsobit velikost čárového kódu, nastavit šířku modulu a
  upravit rozměry čárového kódu pro dokonalé výsledky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generation
- customize barcode size
- barcode with module width
- adjust barcode dimensions
language: cs
lastmod: 2026-11-17
og_description: Generování čárových kódů Aspose vám umožňuje přizpůsobit velikost
  čárového kódu, nastavit šířku modulu a upravit rozměry. Postupujte podle tohoto
  návodu pro kompletní, spustitelné řešení.
og_image_alt: Screenshot of a barcode created with Aspose barcode generation showing
  customized size
og_title: 'Generování čárových kódů Aspose: přizpůsobení velikosti a šířky modulu
  v C#'
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn Aspose barcode generation with step‑by‑step guide to customize
    barcode size, set module width, and adjust barcode dimensions for perfect results.
  headline: How to use Aspose barcode generation to customize barcode size in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- barcode customization
title: Jak použít generování čárových kódů Aspose k přizpůsobení velikosti čárového
  kódu v C#
url: /cs/python-java/general/how-to-use-aspose-barcode-generation-to-customize-barcode-si/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít generování čárových kódů Aspose k přizpůsobení velikosti čárového kódu v C#

Pokud potřebujete provádět generování čárových kódů Aspose a řídit přesnou velikost výstupu, tento průvodce vám ukáže kompletní proces. Uvidíte, jak nastavit šířku modulu, změnit výšku čáry a uložit výsledek jako PNG obrázek – vše během několika stručných kroků.

Přizpůsobení rozměrů čárového kódu je nezbytné, když obrázek musí zapadnout do konkrétního štítku, UI komponenty nebo tiskové šablony. V tomto tutoriálu se naučíte, jak vygenerovat čárový kód GS1 DataBar Omni‑Directional, upravit jeho velikost a ověřit výstup.

## Požadavky

- .NET 6.0 nebo novější nainstalováno
- Licence pro **Aspose.BarCode** (bezplatná zkušební verze funguje pro hodnocení)
- Visual Studio 2022 nebo jakékoli C# IDE, které preferujete
- Základní znalost C# konzolových aplikací

## Krok 1: Nastavení generování čárových kódů Aspose v C# projektu

Vytvořte nový konzolový projekt a přidejte NuGet balíček Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Knihovna `Aspose.BarCode` poskytuje třídu `BarcodeGenerator`, která je jádrem generování čárových kódů Aspose. Přidání balíčku zpřístupní API pro následující kroky.

## Krok 2: Inicializace generátoru čárových kódů a výběr symbologie

První blok kódu vytváří generátor pro čárový kód GS1 DataBar Omni‑Directional. Tato symbologie je ideální pro maloobchodní aplikace, které vyžadují kompaktní číselná data.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

// Step 1: Create a barcode generator for GS1 DataBar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Proč je to důležité:** Hodnota výčtu `EncodeTypes.DatabarOmniDirectional` říká generování čárových kódů Aspose, jaká pravidla kódování použít. Řetězec dat `"(01)12345678901231"` odpovídá formátu GS1 Application Identifier, což zajišťuje, že čárový kód lze načíst standardními maloobchodními skenery.

## Krok 3: Přizpůsobení velikosti čárového kódu pomocí šířky modulu a výšky čáry

Generování čárových kódů Aspose vám umožňuje nezávisle řídit **šířku modulu** (nejmenší čára nebo mezera) a **výšku čáry**. Úprava těchto parametrů přímo ovlivňuje vizuální velikost čárového kódu.

```csharp
// Step 2: Set visual parameters – X dimension (module width) and bar height
generator.Parameters.Barcode.XDimension.Pixels = 2;      // 2 px module width
generator.Parameters.Barcode.BarHeight.Pixels = 30;    // 30 px bar height
```

- **čárový kód s šířkou modulu** – Nastavení `XDimension.Pixels` určuje, kolik pixelů představuje jeden modul. Menší hodnoty vytvářejí kompaktnější čárový kód, zatímco větší hodnoty zvyšují celkovou šířku.
- **úprava rozměrů čárového kódu** – `BarHeight.Pixels` řídí vertikální velikost čar. Zvýšením této hodnoty se čárový kód prodlouží, aniž by se změnila šířka.

Tyto dva nastavení dohromady umožňují **přizpůsobit velikost čárového kódu** tak, aby vyhovovala jakémukoli požadavku na rozvržení.

## Krok 4: Uložení čárového kódu jako souboru obrázku

Po nastavení velikosti exportujte čárový kód do PNG souboru. PNG zachová přesné pixelové rozměry, které jste definovali.

```csharp
// Step 3: Save the barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY/DatabarBarHeight30Pixels.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Metoda `Save` zapíše obrázek s rozměry, které jste nastavili dříve. Výsledný soubor bude mít šířku určenou délkou kódovaných dat vynásobenou šířkou modulu a výšku 30 px, jak je uvedeno.

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat, vložit a spustit. Obsahuje všechny potřebné `using` direktivy a ukazuje celý tok od inicializace po uložení.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Customize size: set module width and bar height
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // barcode with module width = 2 px
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // adjust barcode dimensions (height)

            // Save the barcode image
            string outputPath = @"DatabarBarHeight30Pixels.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode generated and saved to {outputPath}");
        }
    }
}
```

**Očekávaný výstup:** Po spuštění programu najdete `DatabarBarHeight30Pixels.png` ve složce projektu. Obrázek zobrazuje jasný čárový kód GS1 DataBar Omni‑Directional se šířkou úměrnou délce dat a výškou 30 px. Soubor můžete otevřít v libovolném prohlížeči obrázků a ověřit rozměry.

![příklad generování čárových kódů Aspose ukazující přizpůsobenou velikost čárového kódu](https://example.com/placeholder.png "příklad generování čárových kódů Aspose ukazující přizpůsobenou velikost čárového kódu")

*Text alternativy obrázku:* *příklad generování čárových kódů Aspose ukazující přizpůsobenou velikost čárového kódu* – popisuje vizuální výsledek tutoriálu.

## Praktické tipy a běžné úskalí

- **Pro tip:** Pokud cílíte na vysoce rozlišené tiskárny, zvyšte šířku modulu alespoň na 3 px, aby nedošlo k pixelaci.
- **Dejte si pozor na:** Nastavení šířky modulu, která je příliš malá, může způsobit, že čárový kód bude nečitelný na nízkokvalitních skenerech. Otestujte s reálným skenerem před finálním nastavením velikosti.
- **Hraniční případ:** Při kódování dlouhých číselných řetězců může celková šířka překročit typické velikosti štítků. V takových případech zvažte snížení šířky modulu nebo přechod na kompaktní symbologii jako `DatabarLimited`.
- **Poznámka o kompatibilitě:** Kód funguje s .NET 6.0, .NET 7.0 a .NET Framework 4.8. Ujistěte se, že odkazujete na správnou verzi `Aspose.BarCode.dll`, pokud cílíte na plný framework.

## Závěr

Nyní máte kompletní průvodce generováním čárových kódů Aspose, který pokrývá, jak **přizpůsobit velikost čárového kódu**, nastavit konkrétní **čárový kód se šířkou modulu** a **upravit rozměry čárového kódu** pro jakýkoli C# projekt. Dodržením těchto kroků můžete vytvářet čárové kódy, které se dokonale vejdou do vašeho UI, štítků nebo tištěných materiálů.

Chcete-li objevovat dál? Zkuste změnit `EncodeTypes` pro vytvoření QR kódů nebo experimentujte s barvami pozadí a okraji pomocí objektu `Parameters`. API Aspose.BarCode nabízí rozsáhlé možnosti pro jemné ladění každého vizuálního aspektu čárového kódu. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak přizpůsobit rozměry čárového kódu v Javě s Aspose](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [Jak nastavit vlastní velikost čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/configuring-custom-size-barcode/)
- [Nastavení okrajů čárového kódu v Javě – Úprava mezery obrázku čárového kódu s Aspose](/barcode/english/java/image-manipulation/setting-margins-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}