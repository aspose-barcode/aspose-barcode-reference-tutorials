---
category: general
date: 2026-11-23
description: Vytvořte poštovní planetový čárový kód v C# pomocí Aspose.BarCode. Naučte
  se, jak generovat planetový čárový kód, nastavit X‑rozměr a uložit vyplněné nebo
  prázdné pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: cs
lastmod: 2026-11-23
og_description: Vytvořte poštovní planetový čárový kód v C# a naučte se, jak generovat
  planetový čárový kód pomocí Aspose.BarCode. Postupujte podle kompletního příkladu
  a vytvořte vyplněné i prázdné pruhy.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Jak vytvořit čárový kód Postal Planet v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit čárový kód Postal Planet v C#
url: /cs/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit poštovní Planet barcode v C#

Pokud potřebujete **vytvořit poštovní Planet barcode** v .NET aplikaci, tento průvodce vám přesně ukáže **jak generovat Planet barcode** pomocí knihovny Aspose.BarCode. Uvidíte, jak nastavit X‑dimenzi, přepínat mezi plnými a prázdnými pruhy a ukládat obrázky ve formátu PNG.

Generování Planet barcode je běžné pro poštovní služby, které vyžadují vysoce husté, strojově čitelné symboly. Na konci tohoto tutoriálu budete mít dva PNG soubory – jeden s plnými pruhy a druhý s dutými pruhy – připravené k integraci do jakéhokoli poštovního workflow.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalovaný.
* Visual Studio 2022 (nebo jakýkoli editor C#) nakonfigurovaný pro .NET vývoj.
* Aktivní licence NuGet pro **Aspose.BarCode for .NET**. Nainstalujte balíček pomocí:

```bash
dotnet add package Aspose.BarCode
```

Nejsou vyžadovány žádné další externí služby; knihovna provádí veškeré kódování lokálně.

## Krok 1 – vytvořit poštovní Planet barcode

Prvním krokem je vytvořit instanci `BarcodeGenerator` pro symbologii **Planet** a poskytnout data k zakódování. Řetězec dat musí být číselný a mít maximálně 12 číslic podle poštovní specifikace.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Vytvoření generátoru alokuje všechny interní struktury potřebné pro vykreslování. Hodnota výčtu `EncodeTypes.Planet` vybírá správný algoritmus kódování pro poštovní formát.

## Krok 2 – nastavit X‑dimenzi pro lepší čitelnost

X‑dimenze určuje šířku jednoho modulu (nejmenšího prvku pruhu). Hodnota 4 pixely poskytuje jasnou vizuální reprezentaci bez zvětšování celkového obrázku.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Úprava X‑dimenze je nezbytná, když bude čárový kód tisknut na médiu s nízkým rozlišením. stejné nastavení bude znovu použito pro verzi s prázdnými pruhy, aby byly oba obrázky konzistentní.

## Krok 3 – uložit čárový kód s plnými pruhy

Ve výchozím nastavení generátor vykresluje **plné pruhy** (plné černé moduly). Uložení obrázku je jediný volání metody, které zapíše PNG soubor na disk.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Nahraďte `YOUR_DIRECTORY` skutečnou cestou, kam chcete výstupní soubory uložit. Výčet `BarCodeImageFormat.Png` zaručuje bezztrátovou kompresi, což je ideální pro následné zpracování.

## Krok 4 – vytvořit další Planet barcode generátor pro prázdné pruhy

Pro vytvoření verze, která používá **prázdné pruhy** (bílé moduly na černém pozadí), potřebujete druhou instanci `BarcodeGenerator`. Opětovné použití stejného řetězce dat zajišťuje, že oba obrázky představují stejný poštovní kód.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Vytvoření samostatného generátoru izoluje vlastnost `FilledBars`, což vám umožní přepínat vizuální styl, aniž by to ovlivnilo první obrázek.

## Krok 5 – nakonfigurovat generátor pro vykreslení prázdných pruhů

Příznak `FilledBars` přepíná režim vykreslování. Nastavením na `false` řeknete knihovně, aby kreslila pruhy jako prázdné (průhledné), zatímco pozadí zůstane plné.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Udržení X‑dimenze identické jako u verze s plnými pruhy zaručuje, že oba PNG soubory mají stejné rozměry, což zjednodušuje výpočty rozvržení v tiskových šablonách.

## Krok 6 – uložit čárový kód, který vykresluje prázdné pruhy

Nakonec zapíšete obrázek s prázdnými pruhy na disk. Používá se stejný formát PNG, ale můžete přejít na JPEG nebo BMP změnou hodnoty `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

V tomto okamžiku máte dva soubory:

* `PostalPlanetFilledBars.png` – plné černé pruhy.
* `PostalPlanetEmptyBars.png` – duté pruhy na černém pozadí.

Oba splňují poštovní specifikaci pro symbologii Planet.

## Kompletní zdrojový kód

Spojením všech kroků získáte kompaktní konzolovou aplikaci, kterou můžete spustit přímo.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Zkompilujte a spusťte program:

```bash
dotnet run
```

Konzole vypíše *Barcodes generated successfully.* a dva PNG soubory se objeví ve složce projektu.

## Očekávaný výstup

Níže je vizuální reprezentace obrázku s plnými pruhy. Verze s prázdnými pruhy vypadá identicky, jen pruhy jsou průhledné.

![Příklad vytvořeného poštovního Planet barcode s plnými pruhy](postal-planet-filled.png)

Oba obrázky mají ve výchozím nastavení 150 × 150 pixelů, ale můžete ovládat celkovou velikost pomocí parametrů `ImageWidth` a `ImageHeight`, pokud je vyžadováno jiné rozlišení.

## Volitelné varianty

### Změna formátu obrázku

Pokud váš následný systém preferuje JPEG, nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. JPEG zavádí kompresní artefakty, takže jej používejte jen když je velikost souboru kritickým omezením.

### Škálování čárového kódu

Můžete zvětšit čárový kód při zachování šířky modulu úpravou vlastnosti `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Vyšší hodnoty DPI zlepšují kvalitu tisku na laserových tiskárnách.

### Použití vlastní barvy pozadí

Pozadí lze nastavit pomocí:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

To je užitečné pro vizuální testování, ale mělo by se vyhnout v produkčních poštovních štítcích, které vyžadují bílé pozadí.

## Často kladené otázky

**Funguje to s .NET Core?**  
Ano. Knihovna Aspose.BarCode cílí na .NET Standard 2.0, který je kompatibilní s .NET 5, .NET 6 a .NET Core 3.1.

**Co když řetězec dat obsahuje ne‑číslicové znaky?**  
Planet barcode přijímá pouze číselný vstup. Zadání písmen nebo symbolů vyvolá `BarcodeException`. Ověřte vstup před vytvořením generátoru.

**Mohu generovat čárový kód v paměti bez zápisu na disk?**  
Použijte metodu `GenerateBarCodeImage` k získání objektu `System.Drawing.Image`, který můžete přímo streamovat do odpovědi nebo databáze.

## Závěr

Nyní víte, jak **vytvořit poštovní Planet barcode** v C# a rozumíte **jak generovat Planet barcode** s plnými i prázdnými pruhy. Tutoriál pokryl celý pracovní postup – od inicializace generátoru, nastavení X‑dimenze, přepínání příznaku `FilledBars` až po ukládání PNG souborů. Experimentujte s formáty obrázků, nastavením DPI a barvami pozadí, abyste přizpůsobili čárový kód vašemu konkrétnímu poštovnímu systému.

Pro další krok prozkoumejte další poštovní symbologie, jako jsou **POSTNET** nebo **Intelligent Mail**, pomocí stejného Aspose.BarCode API. Úprava parametrů jako `EncodeTypes.Postnet` následuje stejný vzor ukázaný zde, což vám umožní vytvořit komplexní sadu pro generování čárových kódů v jedné kódové základně.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit prázdný Planet barcode, generovat poštovní barcode v C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [Jak nastavit šířku a generovat Planet barcode v C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generovat poštovní barcode v C# – Kompletní průvodce s Planet barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}