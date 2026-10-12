---
category: general
date: 2026-10-02
description: Naučte se, jak vytvořit čárový kód rm4scc v C# a jak generovat poštovní
  čárový kód s vlastní výškou. Obsahuje krok‑za‑krokem kód pro Planet čárové kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode
- how to generate postal barcode
- generate planet barcode
- how to set barcode height
language: cs
lastmod: 2026-10-02
og_description: Vytvořte čárový kód rm4scc v C# a naučte se generovat poštovní čárový
  kód s přesnými rozměry. Kompletní ukázkový kód a tipy na osvědčené postupy.
og_image_alt: Screenshot of RM4SCC and Planet barcodes generated with Aspose.BarCode
  in C#
og_title: Vytvořte čárový kód rm4scc s vlastní výškou – průvodce C#
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  headline: How to create rm4scc barcode and control its height in C#
  type: TechArticle
- description: Learn how to create rm4scc barcode in C# and how to generate postal
    barcode with custom height. Includes step‑by‑step code for Planet barcodes.
  name: How to create rm4scc barcode and control its height in C#
  steps:
  - name: 2.1 Create an RM4SCC barcode (auto height)
    text: '```csharp // RM4SCC with automatic height BarcodeGenerator rm4sccAuto =
      new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccAuto.Parameters.Barcode.XDimension.Pixels
      = 4; // controls bar width rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png",
      BarCodeImageFormat.Png); ```'
  - name: 2.2 Create a Planet barcode (auto height)
    text: '```csharp // Planet barcode with automatic height BarcodeGenerator planetAuto
      = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetAuto.Parameters.Barcode.XDimension.Pixels
      = 4; planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
      ```'
  - name: 3.1 Fixed-height RM4SCC barcode
    text: '```csharp // RM4SCC with fixed height of 100 px BarcodeGenerator rm4sccFixed
      = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456"); rm4sccFixed.Parameters.Barcode.XDimension.Pixels
      = 4; rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
      rm4sccFixed.Save($"{outputFolder}PostalRM'
  - name: 3.2 Fixed-height Planet barcode
    text: '```csharp // Planet barcode with fixed height of 100 px BarcodeGenerator
      planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456"); planetFixed.Parameters.Barcode.XDimension.Pixels
      = 4; planetFixed.Parameters.Barcode.BarHeight.Pixels = 100; planetFixed.Save($"{outputFolder}PostalPlanet_FixedH'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
- postal codes
title: Jak vytvořit čárový kód rm4scc a ovládat jeho výšku v C#
url: /cs/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód rm4scc a nastavit jeho výšku v C#

Pokud potřebujete **vytvořit čárový kód rm4scc** pro poštovní systém, tento návod vám přesně ukáže, jak generovat poštovní čárové kódy a nastavit přesnou výšku čáry. Uvidíte jak výchozí (automaticky velikost) přístup, tak techniku s explicitní výškou, takže si můžete vybrat metodu, která odpovídá vašim návrhovým požadavkům.

Generování poštovního čárového kódu je běžný úkol při tvorbě přepravních štítků, hromadného poštovního softwaru nebo jakéhokoli řešení, které integruje národní poštovní služby. Tento tutoriál pokrývá:

* **jak generovat poštovní čárový kód** pro symbologie RM4SCC a Planet  
* **generovat planet čárový kód** se stejným nastavením pro srovnání  
* **jak nastavit výšku čárového kódu** na pevnou hodnotu v pixelech  
* kompletní, spustitelný C# kód pomocí knihovny Aspose.BarCode  

Na konci článku budete mít připravený spustitelný konzolový program, který vytvoří čtyři PNG soubory – dva s automatickou výškou a dva s pevnou výškou 100 px.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.7+).  
* Visual Studio 2022 nebo jakékoli IDE, které umí sestavit C# projekty.  
* NuGet balíček **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`).  

Žádná další konfigurace není potřeba; knihovna interně zvládá veškeré vykreslování obrázků.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte nový konzolový projekt a přidejte potřebné `using` direktivy. Tento krok připraví prostředí pro generování čárových kódů.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generator
using Aspose.BarCode;               // For ImageFormat enum

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Define where the PNG files will be saved
            string outputFolder = "C:/Barcodes/";   // <-- adjust to a writable folder
            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);
```

*Proč je to důležité*: Deklarace `outputFolder` jednou eliminuje opakování a usnadňuje pozdější změnu cílové cesty. Volání `CreateDirectory` zaručuje, že operace ukládání nezkazí kvůli chybějící složce.

## Krok 2: Jak generovat poštovní čárový kód s výchozí výškou

### 2.1 Vytvoření čárového kódu RM4SCC (automatická výška)

```csharp
            // RM4SCC with automatic height
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);
```

### 2.2 Vytvoření čárového kódu Planet (automatická výška)

```csharp
            // Planet barcode with automatic height
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);
```

Obě volání vynechávají vlastnost `BarHeight`, takže knihovna vypočítá optimální výšku podle specifikací symbologie. Toto je nejjednodušší způsob **jak generovat poštovní čárový kód**, když nemáte přísná omezení rozvržení.

## Krok 3: Jak nastavit výšku čárového kódu pro přesné rozvržení

Když šablona štítku vyžaduje pevnou vizuální velikost, musíte výšku čáry nastavit explicitně. Následující kód ukazuje **jak nastavit výšku čárového kódu** na 100 pixelů pro obě symbologie.

### 3.1 Čárový kód RM4SCC s pevnou výškou

```csharp
            // RM4SCC with fixed height of 100 px
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100; // explicit height
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);
```

### 3.2 Čárový kód Planet s pevnou výškou

```csharp
            // Planet barcode with fixed height of 100 px
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);
```

*Proč to funguje*: Vlastnost `BarHeight.Pixels` přepíše automatický výpočet a donutí renderér použít přesně počet pixelů, který zadáte. To je nezbytné, když se čárový kód musí zarovnat s dalšími UI prvky nebo tištěnými šablonami.

## Krok 4: Ověření vygenerovaných obrázků

Po dokončení programu otevřete čtyři PNG soubory ve složce `outputFolder`. Měli byste vidět:

| Název souboru | Výška | Symbologie |
|---------------|-------|------------|
| `PostalRM4SCC_AutoHeight.png` | Automaticky vypočtená (≈ 50 px) | RM4SCC |
| `PostalPlanet_AutoHeight.png` | Automaticky vypočtená (≈ 50 px) | Planet |
| `PostalRM4SCC_FixedHeight.png` | **100 px** (přesná) | RM4SCC |
| `PostalPlanet_FixedHeight.png` | **100 px** (přesná) | Planet |

Obrázky s názvem “FixedHeight” mají čáry přesně 100 px vysoké, což splňuje požadavek **jak nastavit výšku čárového kódu** pro standardizovaný formát štítku.

## Krok 5: Časté úskalí a tipy pro nejlepší praxi

* **Neplatné hodnoty výšky** – Nastavení `BarHeight.Pixels` na záporné číslo vyvolá `ArgumentException`. Vždy před přiřazením validujte vstup uživatele.  
* **Vědomí rozlišení** – Vizuální velikost na obrazovce také závisí na DPI. Pokud později exportujete do PDF, zvažte nastavení `ImageResolution`, aby fyzické rozměry zůstaly konzistentní.  
* **X‑dimenze vs. výška čáry** – `XDimension.Pixels` řídí šířku čáry, nikoli výšku. Zapomenutí nastavit tuto hodnotu může způsobit, že čárový kód bude příliš tenký, zejména při nízkém DPI.  
* **Bezpečnost vlákna** – Instance `BarcodeGenerator` **nejsou** thread‑safe. Vytvořte novou instanci pro každé vlákno nebo synchronizujte přístup, pokud generujete mnoho čárových kódů paralelně.

## Kompletní zdrojový kód (spustitelný)

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change as needed
            string outputFolder = "C:/Barcodes/";
            System.IO.Directory.CreateDirectory(outputFolder);

            // -----------------------------------------------------------------
            // 1. RM4SCC – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccAuto.Save($"{outputFolder}PostalRM4SCC_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 2. Planet – automatic height
            // -----------------------------------------------------------------
            BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetAuto.Parameters.Barcode.XDimension.Pixels = 4;
            planetAuto.Save($"{outputFolder}PostalPlanet_AutoHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 3. RM4SCC – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
            rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;
            rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            rm4sccFixed.Save($"{outputFolder}PostalRM4SCC_FixedHeight.png", BarCodeImageFormat.Png);

            // -----------------------------------------------------------------
            // 4. Planet – fixed height of 100 px
            // -----------------------------------------------------------------
            BarcodeGenerator planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFixed.Parameters.Barcode.XDimension.Pixels = 4;
            planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;
            planetFixed.Save($"{outputFolder}PostalPlanet_FixedHeight.png", BarCodeImageFormat.Png);

            Console.WriteLine("All barcodes generated successfully.");
        }
    }
}
```

Zkopírujte kód do `Program.cs`, obnovte NuGet balíčky a spusťte `dotnet run`. Konzole potvrdí úspěšné vygenerování a PNG soubory se objeví v `C:/Barcodes/`.

## Závěr

Nyní víte, jak **vytvořit čárový kód rm4scc** a **generovat planet čárový kód** v C#, jak s automatickým velikostním nastavením, tak s ručně definovanou výškou čáry. Ovládáním `BarHeight.Pixels` odpovídáte na otázku **jak nastavit výšku čárového kódu**, což zajišťuje, že vaše poštovní čárové kódy perfektně zapadnou do jakéhokoli rozvržení štítku.

Dále můžete zkusit:

* **jak generovat poštovní čárový kód** v jiných formátech, jako PDF nebo SVG (`BarCodeImageFormat.Pdf`, `BarCodeImageFormat.Svg`).  
* Přidání lidsky čitelného textu pod čárový kód (`Parameters.Caption`).  
* Integraci generátoru do ASP.NET Core API pro poskytování čárových kódů na vyžádání.

Neváhejte experimentovat s různými hodnotami `XDimension`, barvami nebo pozadími, aby vaše značka odpovídala firemní identitě, a přitom zůstávala v souladu se standardy čárových kódů. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to create planet barcode PNG with C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}