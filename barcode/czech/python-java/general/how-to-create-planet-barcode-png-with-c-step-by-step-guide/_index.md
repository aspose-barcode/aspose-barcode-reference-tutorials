---
category: general
date: 2026-09-07
description: Vytvořte PNG planetového čárového kódu v C# rychle. Naučte se, jak generovat
  obrázky planetových čárových kódů pomocí Aspose.BarCode s vyplněnými a prázdnými
  pruhy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: cs
lastmod: 2026-09-07
og_description: Vytvořte planet barcode PNG v C# rychle. Postupujte podle tohoto průvodce
  a naučte se, jak generovat obrázky planet barcode s vyplněnými a prázdnými pruhy
  pomocí Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Vytvořte planetární čárový kód PNG v C# – kompletní programovací tutoriál
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak vytvořit planetární čárový kód PNG v C# – průvodce krok za krokem
url: /cs/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit planet barcode PNG v C# – krok za krokem průvodce

Pokud potřebujete **vytvořit planet barcode PNG** soubory v C#, tento průvodce vám ukáže přesné kroky. Ať už vytváříte integraci poštovní služby nebo logistický dashboard, naučíte se **jak generovat planet barcode** obrázky s vyplněnými i prázdnými pruhy pomocí knihovny Aspose.BarCode.

V tomto tutoriálu se naučíte:

* Nastavit výstupní složku pro vaše obrázky.  
* Nakonfigurovat `BarcodeGenerator` pro symbologii Planet.  
* Vytvořit PNG s výchozím stylem vyplněných pruhů.  
* Vytvořit PNG s prázdnými pruhy pro vizuální kontrast.  

Žádné externí služby nejsou vyžadovány — vše běží lokálně na .NET 6 nebo novějším.

## Prerequisites

Před začátkem se ujistěte, že máte:

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6 SDK (or newer) | Poskytuje runtime pro C# konzolovou aplikaci. |
| Visual Studio 2022 or VS Code | Jakékoli IDE, které dokáže kompilovat C# projekty. |
| Aspose.BarCode for .NET (NuGet package `Aspose.BarCode`) | Poskytuje třídu `BarcodeGenerator` používanou k vykreslení Planet čárových kódů. |
| Write permission to a folder on disk | PNG soubory budou uloženy do tohoto umístění. |

Nainstalujte NuGet balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Vytvořte nový konzolový projekt

Otevřete terminál a spusťte:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Tím se vytvoří minimální C# konzolová aplikace pojmenovaná **PlanetBarcodeDemo**.

## Krok 2: Definujte výstupní adresář

První část kódu určuje, kde budou uložené vygenerované PNG soubory. Použití absolutní nebo relativní cesty funguje; jen se ujistěte, že složka existuje nebo nechte program ji vytvořit.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Proč tento krok?* Oddělení výstupu od zdrojového kódu udržuje projekt přehledný a zabraňuje neúmyslnému přepsání.

## Krok 3: Vygenerujte Planet čárový kód s vyplněnými pruhy

Planet barcode se skládá z koncentrovaných kruhů (ve výchozím nastavení vyplněných). Nakonfigurujeme X‑dimension (šířku pixelu každého pruhu) a poté uložíme obrázek jako PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Vysvětlení**

* `EncodeTypes.Planet` říká Aspose, aby použil symbologii Planet, která je běžná pro poštovní služby.  
* `XDimension.Pixels = 4` poskytuje jasnou, tisknutelnou velikost bez ručního škálování.  
* Metoda `Save` zapíše PNG soubor; můžete také zvolit JPEG nebo BMP změnou `BarCodeImageFormat`.

## Krok 4: Vygenerujte Planet čárový kód s prázdnými pruhy

Někdy je potřeba vizuál s prázdnými (průhlednými) pruhy — například když je čárový kód překrytý barevným pozadím. Nastavením `FilledBars` na `false` získáte tento styl.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Vysvětlení**

* `FilledBars = false` zakáže plné kruhy, zůstane jen obrys.  
* Všechna ostatní nastavení (X‑dimension, datový řetězec) zůstávají stejné, což zaručuje, že oba obrázky představují stejná data.

## Krok 5: Spusťte program a ověřte výstup

Zkompilujte a spusťte:

```bash
dotnet run
```

Měli byste vidět zprávy v konzoli potvrzující uložení souborů a složka `Barcodes` bude obsahovat:

* `PostalPlanetFilledBars.png` – klasický Planet čárový kód s vyplněnými pruhy.  
* `PostalPlanetEmptyBars.png` – stejná data vykreslená s prázdnými pruhy.

Otevřete PNG v libovolném prohlížeči obrázků. Oba obrázky kódují číselný řetězec **123456** a mohou být načteny standardními poštovními čtečkami čárových kódů.

## Časté otázky a řešení okrajových případů

### Co když potřebuji jiný formát dat?

Planet barcodes přijímají číselné řetězce až do 12 číslic. Pokud předáte ne‑číselnou hodnotu, Aspose vyhodí `ArgumentException`. Ověřte vstup před vytvořením generátoru:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Jak změním velikost obrázku bez úpravy tloušťky pruhu?

Použijte vlastnost `Resolution` nebo po uložení škálujte výsledný bitmap:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Mohu generovat jiné formáty obrázků?

Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`, `Bmp` nebo `Gif`. API podporuje všechny běžné rastrové formáty.

### Co s přizpůsobením barev?

Nastavte `BarColor` a `BackColor` na parametrech `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Tyto možnosti fungují pro verze s vyplněnými i prázdnými pruhy.

## Profesionální tipy pro produkční použití

* **Ukládejte generator do cache** když potřebujete vykreslovat mnoho čárových kódů se stejným nastavením — opakovaná inicializace objektu přidává režii.  
* **Uvolněte** objekty `BarcodeGenerator`, pokud je vytváříte ve smyčce (implementují `IDisposable`).  
* **Ověřte výstupní složku** již na začátku, aby se předešlo výjimkám za běhu při zápisu do chráněných adresářů.  

## Závěr

Nyní víte, jak **vytvořit planet barcode PNG** soubory v C# a rozumíte **jak generovat planet barcode** obrázky s vyplněnými i prázdnými pruhy. Kompletní, spustitelný příklad ukazuje nastavení výstupní složky, konfiguraci `BarcodeGenerator` a uložení výsledků jako PNG soubory.

Dále můžete zkoumat:

* Přidání **čitelného textu** pod čárový kód (`planetFilled.Parameters.Caption.Visible = true`).  
* Integraci vygenerovaných PNG do **PDF faktury** pomocí Aspose.PDF.  
* Přepnutí na jiné poštovní symbologie jako **IMB** nebo **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Neváhejte experimentovat s tloušťkou pruhů, barvami a rozlišením obrázku, aby vyhovovaly vašim konkrétním požadavkům. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Vytvořit Planet Barcode obrázek v C# – Jak generovat poštovní čárový kód](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Vytvořit Planet Barcode v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generovat PNG čárový kód s Aspose.BarCode pro .NET: Jednorozměrné vyplněné pruhy](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}