---
category: general
date: 2026-10-02
description: Rychle vytvořte vrstvený databars čárový kód v C#. Naučte se nastavit
  XDimension, upravit poměr stran a exportovat PNG obrázky pomocí generátoru čárových
  kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create stacked databars barcode
- C# barcode generator
- DataBar stacked omnidirectional
- barcode aspect ratio
- XDimension pixel size
- BarCodeImageFormat PNG
language: cs
lastmod: 2026-10-02
og_description: Vytvořte vrstvený čárový kód databars v C# s kompletním příkladem
  kódu. Nastavte XDimension, změňte poměr stran a uložte PNG soubory během několika
  řádků.
og_image_alt: Screenshot showing a create stacked databars barcode example generated
  with C#
og_title: Vytvořte vrstvený čárový kód databars v C# – rychlý tutoriál
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create stacked databars barcode in C# quickly. Learn to set XDimension,
    adjust aspect ratio, and export PNG images with a barcode generator.
  headline: Create stacked databars barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- Aspose
- image generation
title: Vytvořte vrstvený čárový kód databars v C# – krok za krokem průvodce
url: /cs/python-java/general/create-stacked-databars-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření vrstveného čárového kódu DataBar v C# – krok za krokem

Pokud potřebujete **vytvořit vrstvený čárový kód DataBar** v projektu .NET, tento tutoriál vám přesně ukáže, jak na to. Uvidíte, jak nastavit X‑dimenzi, změnit poměr stran a uložit výsledek jako PNG soubory – vše pomocí knihovny Aspose.BarCode.

Generování vrstveného čárového kódu DataBar nevyžaduje složitý grafický řetězec. Na konci tohoto průvodce budete mít dva připravené PNG obrázky, které ukazují různé poměry stran, a pochopíte, proč jsou tyto parametry důležité pro spolehlivost skenování.

## Co budete potřebovat

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.6+)
- Visual Studio 2022 nebo jakékoli C# IDE
- **Aspose.BarCode for .NET** NuGet balíček  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Oprávnění k zápisu do složky, kde budou PNG soubory uloženy

## Krok 1: Nastavení projektu a importování jmenných prostorů

Vytvořte novou konzolovou aplikaci (nebo přidejte kód do existujícího projektu) a importujte požadované jmenné prostory:

```csharp
using System;
using Aspose.BarCode.Generation;   // BarcodeGenerator lives here
using Aspose.BarCode;               // BarCodeImageFormat enum
```

> **Proč je to důležité:** `Aspose.BarCode.Generation` poskytuje třídu `BarcodeGenerator`, zatímco `Aspose.BarCode` obsahuje výčtový typ `BarCodeImageFormat` používaný pro ukládání obrázků.

## Krok 2: Inicializace generátoru pro vrstvený omnidirekcionální DataBar

Hodnota `EncodeTypes.DatabarStackedOmniDirectional` vybírá vrstvenou symbologii DataBar. Řetězec dat musí odpovídat formátu GS1 Application Identifier (AI); zde používáme fiktivní hodnotu GTIN‑14.

```csharp
// Initialise a generator for a stacked omnidirectional DataBar barcode
var barcodeGen = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

> **Proč je to důležité:** Vybraný typ kódování říká knihovně, aby vykreslila *vrstvený* čárový kód, což je nezbytné pro vysoce husté štítky, kde je vertikální prostor omezený.

## Krok 3: Definování velikosti modulu (X‑dimenze) v pixelech

X‑dimenze určuje šířku nejmenšího pruhu (tzv. „modulu“). Hodnota 2 pixely funguje dobře pro většinu výstupů s rozlišením obrazovky.

```csharp
// Set the X‑dimension to 2 pixels (module width)
barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč je to důležité:** Skenery interpretují šířku modulu jako základní jednotku měření. Příliš malá hodnota může způsobit rozmazané výtisky; příliš velká plýtvá prostorem.

## Krok 4: Uložení prvního obrázku s poměrem stran 15

Vlastnost `AspectRatio` ovlivňuje poměr výšky k šířce každého vrstveného segmentu. Poměr stran 15 je běžná výchozí hodnota pro maloobchodní aplikace.

```csharp
// Apply aspect ratio 15 and save the first PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

> **Proč je to důležité:** Nižší poměr stran dává plošší čárový kód, který může být snazší skenovat na některých materiálech štítků. Formát PNG zachovává bezztrátovou kvalitu pro testování.

## Krok 5: Změna poměru stran na 30 a uložení druhého obrázku

Zvýšení poměru stran způsobí, že každý vrstvený segment bude vyšší, což může zlepšit spolehlivost skenování na pozadích s nízkým kontrastem.

```csharp
// Apply aspect ratio 30 and save the second PNG
barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

> **Proč je to důležité:** Různí maloobchodníci nebo logistické partnery mohou vyžadovat specifické rozměry čárových kódů. Poskytnutí obou verzí vám umožní rychle porovnat výkon skenování.

## Kompletní, spustitelný příklad

Níže je kompletní program, který můžete zkopírovat a vložit do `Program.cs`. Po instalaci NuGet balíčku Aspose.BarCode se zkompiluje a spustí bez úprav.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace StackedDataBarDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for stacked omnidirectional DataBar
            var barcodeGen = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Define the module (X‑dimension) size in pixels
            barcodeGen.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Save first image with aspect ratio 15
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGen.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio15.png");

            // 4️⃣ Save second image with aspect ratio 30
            barcodeGen.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGen.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved DatabarAspectRatio30.png");
        }
    }
}
```

### Očekávaný výstup

Spuštěním programu se vytvoří dva soubory ve složce spuštění:

| Název souboru                  | Poměr stran | Popis vzhledu |
|-------------------------------|-------------|----------------|
| `DatabarAspectRatio15.png`    | 15          | Nižší, plošší vrstvený čárový kód |
| `DatabarAspectRatio30.png`    | 30          | Vyšší, více protáhlý vrstvený čárový kód |

Můžete otevřít PNG soubory v libovolném prohlížeči obrázků a ověřit, že čárový kód je vykreslen správně.

![Příklad vytvoření vrstveného čárového kódu databars](placeholder-image.png){alt="Příklad vytvoření vrstveného čárového kódu databars"}

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Mohu použít jinou X‑dimenzi?** | Ano. Typické hodnoty se pohybují od 1 do 4 pixelů. Větší hodnoty zvětší velikost čárového kódu, ale mohou zlepšit čitelnost na tiskárnách s nízkým rozlišením. |
| **Co když potřebuji jinou symbologii?** | Nahraďte `EncodeTypes.DatabarStackedOmniDirectional` jinou hodnotou `EncodeTypes`, například `DatabarStacked` (neomnidirekcionální) nebo `DatabarLimited`. |
| **Jak změním výstupní formát?** | Použijte `BarCodeImageFormat.Jpeg`, `Gif` nebo `Bmp` v metodě `Save`. |
| **Je formát GTIN‑14 povinný?** | Symbologie DataBar očekává číselný řetězec s předponou vhodného AI (např. `(01)` pro GTIN‑14). Přizpůsobte data podle svého použití. |
| **Co DPI nastavení?** | Generátor respektuje vlastnost `Resolution`. Pro vysoce rozlišené tisky nastavte `barcodeGen.Parameters.ImageResolution.DpiX` a `DpiY` podle potřeby. |

## Profesionální tipy

- **Dávkové generování:** Zabalte logiku ukládání do smyčky a předávejte jí seznam GTINů pro automatické vytvoření tisíců čárových kódů.
- **Validace:** Použijte `barcodeGen.Validate()` před uložením, aby se zachytily špatně formátovaná data včas.
- **Výkon:** Opětovné použití stejné instance `BarcodeGenerator` (pouze změna parametrů) je rychlejší než vytváření nového objektu pro každý obrázek.

## Další kroky

Nyní, když můžete **vytvořit vrstvený čárový kód DataBar** s vlastním poměrem stran, zvažte prozkoumání:

- Přidání lidsky čitelného textu pod čárový kód (`barcodeGen.Parameters.Barcode.CodeText`).
- Export do **PDF** pro tiskové listy štítků (`BarCodeImageFormat.Pdf`).
- Integrace generátoru do webového API pro poskytování čárových kódů na vyžádání.
- Experimentování s dalšími **sekundárními klíčovými slovy** jako *C# barcode generator* a *barcode aspect ratio* pro doladění implementace pro konkrétní hardware.

Šťastné programování a užijte si flexibilitu, kterou Aspose.BarCode přináší do vašich C# projektů s čárovými kódy!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit vrstvený čárový kód DataBar v C# – krok za krokem](/barcode/english/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/)
- [DataBar stacked omnidirectional barcode v C# – kompletní průvodce](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Jak vytvořit PNG obrázky DataBar s C# a Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}