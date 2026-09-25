---
category: general
date: 2026-08-19
description: Vytvořte soubory PNG s databar v C# pomocí Aspose.BarCode. Naučte se,
  jak generovat obrázky databar, konfigurovat parametry databar a uložit výstup ve
  formátu PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar png
- how to generate databar
- configure databar parameters
language: cs
lastmod: 2026-08-19
og_description: Vytvořte soubory PNG s databarem v C# pomocí Aspose.BarCode. Tento
  tutoriál vás provede generováním obrázků databaru, nastavením parametrů databaru,
  jako je X‑rozměr a poměr stran, a uložením vysoce kvalitních souborů PNG pro tisk
  nebo webové použití.
og_image_alt: create databar PNG example
og_title: Vytvořte PNG obrázky datových pruhů v C# – krok za krokem.
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Create databar PNG files in C# with Aspose.BarCode. Learn how to generate
    databar images, configure databar parameters, and save PNG output.
  headline: How to create databar PNG images with C# and Aspose.BarCode
  type: TechArticle
tags:
- barcode
- databar
- C#
- PNG
- Aspose.BarCode
title: Jak vytvořit PNG obrázky databar pomocí C# a Aspose.BarCode
url: /cs/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PNG obrázky databar s C# a Aspose.BarCode

Pokud potřebujete **vytvořit databar PNG** soubory v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který generuje vrstvené omnidirekcionální DataBar kódy, nastavuje klíčové parametry a ukládá dva PNG soubory s různými poměry stran.

Vytvoření DataBar obrázku není jen o zavolání jedné metody. Musíte také **nastavit parametry databar**, jako je X‑dimenze (šířka modulu) a poměr stran, aby vyhovovaly specifikacím tisku nebo skenování. Na konci tohoto tutoriálu pochopíte **jak generovat databar** grafiku, která spolehlivě funguje v reálných scénářích.

## Požadavky

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakékoli C#‑kompatibilní IDE
- Platná licence pro **Aspose.BarCode for .NET** (bezplatná zkušební verze funguje pro testování)
- Základní znalost syntaxe C#

> **Tip:** Pokud ještě nemáte licenci, můžete požádat o dočasný zkušební klíč na portálu Aspose. API se chová stejně; mění se jen vodoznak.

## Krok 1: Nainstalujte NuGet balíček Aspose.BarCode

Otevřete svůj projekt ve Visual Studiu, klikněte pravým tlačítkem na řešení a vyberte **Manage NuGet Packages**. Vyhledejte `Aspose.BarCode` a nainstalujte nejnovější stabilní verzi.

```bash
dotnet add package Aspose.BarCode
```

Tento příkaz přidá sestavení `Aspose.BarCode` do vašeho projektu a zpřístupní třídu `BarcodeGenerator`.

## Krok 2: Inicializujte generátor čárových kódů pro vrstvený omnidirekcionální DataBar

Konstruktor `BarcodeGenerator` přijímá dva argumenty: typ čárového kódu a řetězec surových dat. Pro vrstvený omnidirekcionální DataBar použijete `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace DatabarPngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Step 2: Initialize the generator with the desired DataBar type
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // GS1 Application Identifier for a 14‑digit GTIN
```

**Proč je to důležité:** Konstantní `EncodeTypes.DatabarStackedOmniDirectional` říká knihovně, aby vytvořila čárový kód, který lze číst z jakékoli orientace, což je ideální pro regálové etikety v maloobchodě.

## Krok 3: Nastavte X‑dimenzi (šířku modulu) v pixelech

X‑dimenze řídí velikost nejmenšího pruhu. Nastavením v pixelech získáte přesnou kontrolu nad konečnou velikostí obrázku.

```csharp
            // Step 3: Define the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Hodnota **2 pixely** představuje dobrý kompromis mezi čitelností a kompaktností pro většinu tiskáren etiket. Upravit tuto hodnotu můžete, pokud potřebujete větší nebo menší moduly.

## Krok 4: Nastavte první poměr stran a uložte PNG

Poměr stran ovlivňuje výšku vrstveného DataBar. Poměr **15** vytváří relativně krátký čárový kód, zatímco **30** jej prodlužuje.

```csharp
            // Step 4: Set an aspect ratio of 15 and save the image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
            barcodeGenerator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapíše vygenerovaný čárový kód do PNG souboru. PNG je bezztrátový formát, který zachovává ostré hrany potřebné pro skenery čárových kódů.

## Krok 5: Změňte poměr stran a uložte druhý PNG

Můžete znovu použít stejnou instanci `BarcodeGenerator` k vytvoření variant jednoduše změnou poměru stran.

```csharp
            // Step 5: Change the aspect ratio to 30 and save a new image
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
            barcodeGenerator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        }
    }
}
```

Nyní máte dva PNG soubory — `DatabarAspectRatio15.png` a `DatabarAspectRatio30.png` — každý s jinou vizuální hustotou.

## Krok 6: Ověřte výstup

Otevřete vygenerované PNG soubory v libovolném prohlížeči obrázků. Měli byste vidět čistý, vysokokontrastní DataBar čárový kód. Skenování obrázků pomocí čtečky čárových kódů ve smartphonu potvrdí, že oba poměry stran dekódují původní GTIN hodnotu `12345678901231`.

![create databar PNG example](databar_example.png)

*Obrázek výše zobrazuje dva PNG soubory vedle sebe. Levý obrázek používá poměr stran 15, pravý poměr stran 30.*

## Běžné varianty a okrajové případy

| Scénář | Co změnit | Důvod |
|----------|----------------|--------|
| **Různá data** | Nahraďte řetězec `(01)12345678901231` jakýmkoli platným GS1 identifikátorem aplikace a daty | Umožňuje kódovat ID produktů, sériová čísla atd. |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` na 3 nebo 4 | Potřebné, když bude čárový kód tištěn ve velkých rozměrech nebo skenován z větší vzdálenosti. |
| **Jiné typy DataBar** | Použijte `EncodeTypes.DatabarStacked` nebo `EncodeTypes.DatabarExpanded` | Vyberte typ, který nejlépe vyhovuje rozvržení vaší etikety. |
| **Průhledné pozadí** | Předávejte `BarCodeImageFormat.Png` s `barcodeGenerator.Save(..., BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })` | Užitečné pro překrytí čárového kódu na barevných etiketách. |

> **Pozor:** Nastavení X‑dimenze, která je příliš malá (< 1 pixel), může vytvořit čárový kód, který po...

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Vytvořit jednorozměrné GS1 kódování Databar s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Generovat Databar čárový kód pomocí Aspose.BarCode a .NET API – konfigurace řádků a sloupců](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}