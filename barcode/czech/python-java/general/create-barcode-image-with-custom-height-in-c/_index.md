---
category: general
date: 2026-10-28
description: Vytvořte obrázek čárového kódu v C# a naučte se, jak upravit výšku pomocí
  API BarcodeGenerator. Krok za krokem průvodce nastavením vlastní výšky čárového
  kódu a změnou výšky čáry.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to adjust height
- c# barcode generator
- custom barcode height
- change barcode height
language: cs
lastmod: 2026-10-28
og_description: Vytvořte obrázek čárového kódu v C# a okamžitě zjistěte, jak upravit
  výšku. Postupujte podle tohoto kompletního příkladu a nastavte vlastní výšku čárového
  kódu pomocí BarcodeGeneratoru.
og_image_alt: Screenshot showing a generated barcode image with a custom height
og_title: Vytvořte obrázek čárového kódu s vlastní výškou v C# – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode image in C# and learn how to adjust height using the
    BarcodeGenerator API. Step‑by‑step guide for custom barcode height and changing
    bar height.
  headline: Create barcode image with custom height in C#
  type: TechArticle
tags:
- barcode
- C#
- image generation
- GS1‑Databar
title: Vytvořte obrázek čárového kódu s vlastní výškou v C#
url: /cs/python-java/general/create-barcode-image-with-custom-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření obrázku čárového kódu s vlastní výškou v C#

Pokud potřebujete **vytvořit obrázek čárového kódu** a řídit jeho rozměry, tento návod vám ukáže přesně jak. Pomocí knihovny Aspose.BarCode .NET můžete vygenerovat GS1‑Databar Omni‑Directional čárový kód a poté **upravit výšku**, aby vyhovovala jakémukoli požadavku na rozvržení.

Provedete kompletní, spustitelný program, který demonstruje **c# barcode generator**, vysvětlí každé nastavené vlastnosti a ukáže dva různé výstupy — jeden s výškou pruhu 30 pixelů a druhý s výškou 60 pixelů. Na konci budete schopni **změnit výšku čárového kódu** programově pro jakýkoli typ čárového kódu podporovaný knihovnou.

## Požadavky

- .NET 6.0 SDK nebo novější (kód funguje také s .NET Framework 4.6+)
- Visual Studio 2022 nebo jakýkoli editor, který umí sestavit projekty C#
- Aspose.BarCode pro .NET NuGet balíček (`Install-Package Aspose.BarCode`)
- Základní znalost syntaxe C#

> **Pro tip:** Pokud používáte CI pipeline, přidejte NuGet balíček do svého souboru `csproj`, aby se při sestavení automaticky obnovil.

## Krok 1: Nastavení projektu a import jmenných prostorů

Vytvořte nový konzolový projekt a přidejte požadované `using` direktivy. Jmenné prostory vám poskytují přístup k `BarcodeGenerator`, `EncodeTypes` a pomocníkům pro formáty obrázků.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // The rest of the tutorial code lives here.
        }
    }
}
```

> **Proč je to důležité:** Import správných jmenných prostorů zabraňuje chybám při kompilaci a umožňuje API objevit v IntelliSense.

## Krok 2: Inicializace **c# barcode generator** pro kód GS1‑Databar Omni‑Directional

Konstruktor přijímá dva argumenty: typ čárového kódu (`EncodeTypes.DatabarOmniDirectional`) a řetězec dat. Řetězec dat musí odpovídat formátu GS1 Application Identifier, např. `(01)12345678901231`.

```csharp
// Create a barcode generator for a GS1‑Databar Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional,
    "(01)12345678901231");
```

> **Vysvětlení:** Objekt `BarcodeGenerator` je vstupním bodem pro všechna nastavení související s čárovým kódem. Jakmile máte tuto instanci, můžete ladit rozměry, barvy a výstupní formát.

## Krok 3: Definování společné X‑dimenze (šířka nejúzkého pruhu v pixelech)

X‑dimenze 2 pixely je dobrý výchozí bod pro většinu scénářů zobrazení na obrazovce.

```csharp
// Set a 2‑pixel X‑dimension (width of the smallest bar)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč nastavit X‑dimenzi?** Řídí celkovou šířku čárového kódu. Konzistentní hodnota zajišťuje, že změna výšky pruhu nezkreslí vizuální rovnováhu.

## Krok 4: **Vytvoření obrázku čárového kódu** s výškou pruhu 30 pixelů

Nyní nastavíme výšku pruhu, uložíme první obrázek a poté změříme výšku pro druhý.

```csharp
// Configure a 30‑pixel bar height
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first image
string output30 = "DatabarBarHeight30Pixels.png";
barcodeGenerator.Save(output30, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 30 px height to {output30}");
```

> **Výsledek:** Získáte PNG soubor, kde je každý vertikální pruh vysoký 30 pixelů. X‑dimenze zůstává 2 pixely, takže celková šířka se nemění.

## Krok 5: **Jak upravit výšku** — změna výšky pruhu na 60 pixelů

Pro demonstraci **vlastní výšky čárového kódu** stačí přiřadit novou hodnotu ke stejné vlastnosti a znovu uložit.

```csharp
// Change the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second image
string output60 = "DatabarBarHeight60Pixels.png";
barcodeGenerator.Save(output60, BarCodeImageFormat.Png);
Console.WriteLine($"Saved barcode with 60 px height to {output60}");
```

> **Klíčový postřeh:** Vlastnost `BarHeight` je měnitelná; není nutné znovu vytvářet instanci `BarcodeGenerator`. To umožňuje levné generování více velikostí ve smyčce nebo dávkovém procesu.

## Krok 6: Ověření výstupu

Spusťte konzolový program (`dotnet run`). Po dokončení by se ve výstupní složce projektu měly objevit dva PNG soubory:

- `DatabarBarHeight30Pixels.png` — krátké pruhy (30 px)
- `DatabarBarHeight60Pixels.png` — dlouhé pruhy (60 px)

Oba obrázky obsahují stejná zakódovaná data, ale výška se liší, což je užitečné při integraci čárových kódů do formulářů, produktových štítků nebo UI komponent s různými prostorovými omezeními.

![Vytvoření obrázku čárového kódu s vlastní výškou](barcode-example.png){.align-center width="600" alt="Vytvoření obrázku čárového kódu s vlastní výškou"}

> **Tip:** Otevřete PNG soubory v libovolném prohlížeči obrázků. Vyšší čárový kód by měl být přesně dvakrát vyšší než nižší, zatímco horizontální rozestupy zůstanou stejné.

## Krok 7: Běžné varianty a okrajové případy

| Situace | Doporučené nastavení |
|-----------|---------------------|
| **Tisk na vysoce rozlišeném štítkovém tiskárně** | Použijte větší X‑dimenzi (např. 4 px) a zvyšte `BarHeight` proporcionálně. |
| **Zobrazení na obrazovce s nízkým DPI** | Udržujte `XDimension` na 1 px a `BarHeight` mezi 20‑40 px pro čitelnost. |
| **Generování QR kódů nebo 2‑D čárových kódů** | Vlastnost `BarHeight` se ignoruje; použijte `EncodeTypes.QR` a upravte `ImageHeight`. |
| **Dávkové generování mnoha výšek** | Procházejte pole výšek a volajte `Save` uvnitř smyčky; není nutné znovu vytvářet generátor v každé iteraci. |

### Zpracování neplatných výšek

Knihovna vyhodí `ArgumentOutOfRangeException`, pokud nastavíte `BarHeight` na ne‑kladnou hodnotu. Ochráníte se tím jednoduchou kontrolou:

```csharp
int desiredHeight = 0; // example invalid value
if (desiredHeight <= 0)
{
    throw new ArgumentException("Bar height must be greater than zero.");
}
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = desiredHeight;
```

## Kompletní zdrojový kód (připravený ke zkopírování)

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the barcode generator for GS1‑Databar Omni‑Directional
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231");

            // 2️⃣ Set a common 2‑pixel X‑dimension
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = "DatabarBarHeight30Pixels.png";
            barcodeGenerator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 30 px height to {path30}");

            // 4️⃣ Second image – 60 pixel bar height
            barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = "DatabarBarHeight60Pixels.png";
            barcodeGenerator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with 60 px height to {path60}");
        }
    }
}
```

> **Proč to funguje:** Všechna potřebná nastavení (`EncodeTypes`, `XDimension`, `BarHeight`) jsou aplikována před každým voláním `Save`. Stejná instance `BarcodeGenerator` je znovu použita, což je jak paměťově úsporné, tak snadno čitelné.

## Závěr

Nyní víte, jak **vytvořit obrázek čárového kódu** v C# a přesně **změnit výšku čárového kódu** pomocí API `BarcodeGenerator`. Úpravou `BarHeight.Pixels` dosáhnete **vlastní výšky čárového kódu** bez nutnosti znovu vytvářet generátor, což řešení činí ideálním pro dynamické vytváření štítků, renderování UI nebo dávkové zpracování.

Dále prozkoumejte související témata, jako je **úprava šířky**, **přidání lidsky čitelného textu** nebo **export do SVG pro škálovatelné použití na webu**. Stejný vzor — nastavte vlastnost, zavolejte `Save` — platí i pro tyto scénáře, takže můžete rozšířit tento příklad s jistotou.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to Change Barcode Height in C# – Complete Guide](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [Barcode generator example – create Planet and RM4SCC barcodes with custom height](/barcode/english/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/)
- [How to create rm4scc barcode and control its height in C#](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-control-its-height-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}