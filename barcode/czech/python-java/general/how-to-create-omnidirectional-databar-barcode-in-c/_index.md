---
category: general
date: 2026-09-29
description: Naučte se, jak vytvořit všesměrový Databar čárový kód v C# s Aspose.BarCode.
  Nastavte X‑rozměr, poměr stran a uložte PNG obrázky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: cs
lastmod: 2026-09-29
og_description: Vytvořte všesměrový Databar čárový kód v C# pomocí Aspose.BarCode.
  Naučte se nastavit X‑rozměr, upravit poměr stran a exportovat soubory PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Vytvořte všesměrový čárový kód Databar v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit všesměrový Databar čárový kód v C#
url: /cs/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit omnidirekcionální Databar čárový kód v C#

Pokud potřebujete **vytvořit omnidirekcionální Databar čárový kód** v aplikaci .NET, tento návod vám ukáže přesné kroky. Uvidíte, jak inicializovat DataBar stacked omnidirectional čárový kód, nastavit jeho X‑dimenzi, změnit poměr stran a vygenerovat PNG obrázky pomocí Aspose.BarCode.

Generování **DataBar stacked omnidirectional čárového kódu** je běžné, když musíte zakódovat identifikátory produktů pro maloobchodní skenery. V tomto tutoriálu se naučíte **nastavit poměr stran čárového kódu**, řídit velikost modulu a exportovat výsledek bez opuštění IDE.

## Požadavky

Než začnete, ujistěte se, že máte:

- .NET 6.0 nebo novější nainstalovaný
- Visual Studio 2022 (nebo jakékoli IDE kompatibilní s C#)
- NuGet balíček **Aspose.BarCode for .NET** (verze 23.12 nebo novější)

Balíček můžete přidat pomocí NuGet Package Manageru:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Inicializace omnidirekcionálního Databar čárového kódu

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která cílí na **DataBar stacked omnidirectional** symbologii. Konstruktor přijímá typ kódování a řetězec dat.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Proč je to důležité:** Hodnota `EncodeTypes.DatabarStackedOmniDirectional` říká Aspose.BarCode, aby vykreslil konkrétní omnidirekcionální Databar formát, který je vyžadován pro skenování v obou směrech.

## Krok 2: Definování X‑dimenze (velikost modulu)

X‑dimenze řídí šířku jednoho modulu čárového kódu v pixelech. Hodnota `2` pixely dobře funguje pro vykreslování na obrazovce i pro většinu tiskáren.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Proč je to důležité:** Konzistentní X‑dimenze zajišťuje, že čárový kód splňuje minimální velikostní specifikace pro maloobchodní skenery a zároveň udržuje velikost souboru obrázku na přijatelném levelu.

## Krok 3: Nastavení prvního poměru stran a uložení obrázku

**Poměr stran** určuje vztah výšky k šířce DataBaru. Poměr stran `15` vytváří kompaktní, vysoký čárový kód ideální pro úzké štítky.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Proč je to důležité:** Úprava poměru stran vám umožní umístit čárový kód do různých rozvržení štítků, aniž byste obětovali čitelnost. Uložený PNG lze prohlédnout v libovolném prohlížeči obrázků.

## Krok 4: Změna poměru stran a vygenerování druhého obrázku

Někdy je potřeba širší čárový kód – například když má štítek více horizontálního prostoru. Změna poměru na `30` vytvoří plošší vzhled.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Proč je to důležité:** Díky vlastnosti **set barcode aspect ratio** můžete z jedné základny kódu vytvořit více variant čárových kódů, což zjednodušuje automatizované pipeline pro generování štítků.

## Očekávaný výstup

Spuštěním programu se v výstupní složce aplikace vytvoří dva PNG soubory:

| Název souboru                | Poměr stran | Popis vizuálu |
|-----------------------------|-------------|----------------|
| `DatabarAspectRatio15.png`  | 15          | Vysoký, úzký čárový kód vhodný pro úzké štítky |
| `DatabarAspectRatio30.png`  | 30          | Širší čárový kód, který zaplní více horizontálního prostoru |

Tyto obrázky můžete vložit do reportů, vytisknout na obal produktu nebo odeslat webové službě k dalšímu zpracování.

![Vytvořit omnidirekcionální Databar čárový kód příklad](databar-example.png "Vytvořit omnidirekcionální Databar čárový kód příklad")

*Na snímku jsou vedle sebe zobrazeny dva vygenerované PNG soubory.*

## Často kladené otázky a okrajové případy

### Co když potřebuji jinou X‑dimenzi?

Můžete přiřadit libovolnou celočíselnou hodnotu `XDimension.Pixels`. Hodnoty pod `1` jsou ignorovány a hodnoty nad `10` mohou vytvořit příliš velké moduly, které překročí okraje tiskárny. Po každé změně otestujte vizuální výstup.

### Jak zakóduji jiná data generovaná AI (např. UPC, EAN)?

Nahraďte řetězec dat v konstruktoru `BarcodeGenerator` odpovídajícím identifikátorem aplikace (AI). Pro kód UPC‑A použijte `"012345678905"` bez AI předpony.

### Můžu exportovat do formátů jiných než PNG?

Ano. Metoda `Save` podporuje `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff` a `BarCodeImageFormat.Bmp`. Vyberte formát, který odpovídá vašemu následnému workflow.

## Pro tip: znovupoužití generátoru pro dávkové zpracování

Pokud potřebujete vygenerovat desítky čárových kódů s různými poměry stran, nechte instanci `BarcodeGenerator` aktivní a před každým `Save` jen upravte `DataBar.AspectRatio`. Tím se vyhnete režii opětovné tvorby generátoru pro každý obrázek.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Závěr

Nyní víte, jak **vytvořit omnidirekcionální Databar čárový kód** v C# pomocí Aspose.BarCode. Inicializací `BarcodeGenerator`, nastavením X‑dimenze, úpravou **set barcode aspect ratio** a uložením PNG souborů můžete vytvářet obrázky čárových kódů, které splňují různé požadavky na štítky.  

Dále prozkoumejte související témata, jako je **generate barcode image** pro QR kódy, validace **DataBar stacked omnidirectional barcode**, nebo integrace vygenerovaných PNG do PDF faktur pomocí Aspose.PDF. Experimentujte s různými poměry stran a velikostmi modulů, abyste našli optimální konfiguraci pro váš konkrétní tiskový hardware.

---


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode in C# – Complete Guide](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [How to generate barcode in C# – create barcode image c# with DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}