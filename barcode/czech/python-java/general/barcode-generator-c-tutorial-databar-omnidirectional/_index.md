---
category: general
date: 2026-11-14
description: Návod na generátor čárových kódů v C#, který ukazuje, jak vytvořit DataBar
  Omnidirectional čárové kódy, nastavit X‑rozměr a upravit výšku čáry v pixelech.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: cs
lastmod: 2026-11-14
og_description: Návod na generátor čárových kódů v C# krok za krokem vysvětluje, jak
  generovat DataBar Omnidirectional čárový kód, nastavit XDimension v pixelech a změnit
  výšku čáry pro PNG výstup.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 'Generátor čárových kódů C# – tutoriál: vytvořte DataBar kódy'
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Generátor čárových kódů C#: DataBar omnidirekcionální'
url: /cs/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generátor čárových kódů C# – vytvoření DataBar Omnidirectional čárových kódů

Pokud hledáte **barcode generator C# tutorial**, jste na správném místě. Tento průvodce vás provede vytvořením DataBar Omnidirectional čárového kódu, nastavením XDimension v pixelech a úpravou výšky čáry pro vytvoření PNG obrázků.

Uvidíte kompletní, spustitelný příklad, který pokrývá vše od inicializace generátoru až po uložení několika obrázků s různými výškami čar. Není potřeba žádná externí dokumentace – stačí zkopírovat kód, spustit jej a získáte dva soubory s čárovými kódy připravené k použití.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější nainstalovaný  
* Odkaz na knihovnu čárových kódů, která poskytuje `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat` (například Aspose.BarCode pro .NET)  
* Základní znalost syntaxe C# a Visual Studio nebo vašeho preferovaného IDE  

> **Pro tip:** Pokud používáte Aspose.BarCode, přidejte do projektu NuGet balíček `Aspose.BarCode`.

## Generátor čárových kódů C# tutorial – krok 1: vytvoření generátoru

Prvním krokem je vytvořit instanci `BarcodeGenerator` s typem kódování `DatabarOmniDirectional` a daty, která chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Proč je to důležité:* `EncodeTypes.DatabarOmniDirectional` říká knihovně, aby vytvořila čárový kód, který lze číst z libovolného směru, což je ideální pro maloobchodní balení a logistiku.

## Nastavení XDimension v pixelech pro čárový kód

X‑dimenze určuje šířku nejmenšího modulu („pixelu“) v čárovém kódu. Nastavením v pixelech získáte přesnou kontrolu nad vizuální hustotou čárového kódu.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Vysvětlení:* Hodnota `2` pixely poskytuje čárový kód, který je dostatečně ostrý pro většinu skenerů a zároveň udržuje velikost souboru obrázku na rozumné úrovni.

## Úprava výšky čáry a uložení obrázků

Výška čáry určuje, jak vysoké čáry budou vypadat. Můžete generovat více obrázků s různými výškami změnou vlastnosti `BarHeight.Pixels` a opětovným voláním `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Hodnota výčtu `BarCodeImageFormat.Png` zajišťuje, že výstup bude bezztrátový PNG soubor, což je doporučený formát pro grafiku čárových kódů, protože zachovává přesné rozměry.

## Změna výšky čáry pro vytvoření více obrázků

Často potřebujete stejný čárový kód v různých velikostech – například jeden pro malý štítek a druhý pro velký plakát. Změňte výšku čáry a použijte stejnou instanci generátoru:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Hraniční případ:* Pokud je výška čáry nastavena příliš nízko (např. pod 10 px), mohou některé skenery mít potíže s načtením kódu. Vždy testujte vygenerované obrázky s vaším cílovým skenerovým hardwarem.

## Kompletní zdrojový kód

Níže je kompletní program, který můžete zkopírovat a vložit do nového konzolového projektu. Obsahuje všechny potřebné `using` direktivy a ukazuje obě varianty výšky čáry.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Spusťte program, nahraďte `YOUR_DIRECTORY` platnou cestou ke složce a najdete dva PNG soubory:

* `DatabarBarHeight30Pixels.png` – čáry vysoké 30 px  
* `DatabarBarHeight60Pixels.png` – čáry vysoké 60 px  

![výstup generátoru čárových kódů C# tutorial](images/databar-example.png "Generátor čárových kódů C# tutorial ukazující dva DataBar obrázky")

## Často kladené otázky

| Otázka | Odpověď |
|----------|--------|
| **Mohu změnit formát obrázku?** | Ano. Nahraďte `BarCodeImageFormat.Png` hodnotou `Jpeg`, `Bmp` nebo `Gif` podle potřeby. PNG je preferováno pro bezztrátovou kvalitu. |
| **Co když potřebuji jinou XDimension?** | Upravit `generator.Parameters.Barcode.XDimension.Pixels` na libovolné celé číslo. Větší hodnoty zvětší celkovou šířku čárového kódu. |
| **Je DataBar Omnidirectional vhodný pro mobilní skenování?** | Ano, pokud tištěná velikost splňuje minimální velikost modulu skeneru (obvykle 0.33 mm). Pixel‑závislá XDimension vám pomůže tuto podmínku splnit. |
| **Jak vložit čárový kód do PDF?** | Po uložení PNG použijte PDF knihovnu (např. iTextSharp) k vložení obrázku na stránku PDF. |

## Závěr

Tento **barcode generator C# tutorial** vám ukázal, jak vytvořit DataBar Omnidirectional čárový kód, nastavit XDimension v pixelech a generovat PNG soubory s různými výškami čar. Nyní máte znovupoužitelný úryvek kódu, který můžete přizpůsobit libovolnému C# projektu vyžadujícímu tvorbu čárových kódů.

### Co dál?

* Prozkoumejte další `EncodeTypes`, jako jsou `Code128` nebo `QR`, a rozšiřte tak své portfolio čárových kódů.  
* Kombinujte vygenerovaný PNG s knihovnou pro tvorbu PDF a vytvořte tisknutelné faktury.  
* Experimentujte s `generator.Parameters.Barcode.Color` a přidejte vlastní barvy, přičemž zůstanete v mezích specifikací skenerů.

Neváhejte upravit příklad, vyzkoušet další výšky čar nebo změnit výstupní formát. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobným krok‑za‑krokem vysvětlením, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [How to set barcode height, generate DataBar barcode in C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [How to create omnidirectional Databar barcode in C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}