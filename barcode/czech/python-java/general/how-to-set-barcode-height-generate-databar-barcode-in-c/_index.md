---
category: general
date: 2026-10-12
description: Jak nastavit výšku čárového kódu a vygenerovat DataBar čárový kód v C#
  pomocí Aspose.BarCode. Sledujte krok‑za‑krokem průvodce s kompletním kódem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: cs
lastmod: 2026-10-12
og_description: Jak nastavit výšku čárového kódu v C# a vygenerovat DataBar čárový
  kód pomocí Aspose.BarCode. Naučte se kompletní kód, proč je každý krok důležitý,
  a jak změnit výšku čárového kódu.
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: Jak nastavit výšku čárového kódu a vygenerovat DataBar čárový kód v C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak nastavit výšku čárového kódu, generovat DataBar čárový kód v C#
url: /cs/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit výšku čárového kódu, generovat DataBar čárový kód v C#

Pokud potřebujete **how to set barcode** rozměry programově, tento průvodce vám ukáže přesné kroky. Naučíte se, jak vygenerovat DataBar Omni‑directional čárový kód, upravit jeho výšku a uložit oba varianty jako PNG soubory.

Změna výšky čárových kódů je běžnou požadavkou při integraci čárových kódů do účtenek, produktových štítků nebo mobilních obrazovek. Níže uvedený příklad používá knihovnu Aspose.BarCode, která podporuje kompletní sadu symbologií GS1 DataBar.

## Co dosáhnete

Do konce tohoto tutoriálu budete schopni:

* **how to set barcode** výšku pro DataBar Omni‑directional čárový kód  
* **generate barcode c#** kód, který vytvoří dva obrázky s různými výškami  
* pochopit **how to create databar** symboly a proč výška čáry má význam  
* aplikovat logiku **change barcode height** bez opětovného vytvoření generátoru  

Žádné externí nástroje nejsou potřeba kromě balíčku Aspose.BarCode NuGet a .NET 6+ runtime.

## Požadavky

* .NET 6 SDK nebo novější nainstalováno  
* Visual Studio 2022 (nebo jakýkoli C# editor)  
* Aspose.BarCode pro .NET – nainstalujte pomocí `dotnet add package Aspose.BarCode`  

> **Pro tip:** Použijte bezplatnou zkušební licenci od Aspose, pokud nemáte komerční klíč; API funguje stejným způsobem.

## Krok 1: Nainstalujte balíček Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode`, který obsahuje třídu `BarcodeGenerator`, kterou použijeme k **generate barcode c#** obrázkům.

## Krok 2: Vytvořte DataBar generátor čárových kódů

Prvním konkrétním krokem pro parametry **how to set barcode** je vytvořit instanci `BarcodeGenerator` s požadovanou symbologií a datovým řetězcem.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*Proč je to důležité:* `EncodeTypes.DatabarOmniDirectional` vytváří kompaktní, omnidirekcionální DataBar, který lze skenovat z jakéhokoli úhlu — ideální pro malé štítky.

## Krok 3: Nastavte společné parametry čárového kódu (včetně počáteční výšky čáry)

Nyní odpovídáme na **how to set barcode** X‑dimenzi a výšku čáry před uložením prvního obrázku.

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimenze řídí celkovou šířku každé čáry; nastavení na 2 pixely poskytuje čitelný, ostrý obrázek na většině obrazovek. Krok **change barcode height** později znovu použije stejný generátor, čímž ušetří čas a paměť.

## Krok 4: Uložte první obrázek čárového kódu (výška 30 pixelů)

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

Soubor `DatabarHeight30.png` nyní obsahuje DataBar čárový kód s výškou čáry 30 pixelů.

## Krok 5: Změňte pouze výšku čáry na 60 pixelů

Pro demonstraci **change barcode height** upravíme pouze vlastnost `BarHeight`. Všechna ostatní nastavení zůstávají beze změny, což je nejefektivnější způsob, jak vytvořit více velikostí z jednoho generátoru.

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## Krok 6: Uložte druhý obrázek čárového kódu (výška 60 pixelů)

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

Nyní máte dva PNG soubory, každý s jinou výškou čáry, ale se stejnými daty a X‑dimenzí.

## Kompletní spustitelný příklad

Níže je kompletní program, který můžete zkopírovat a vložit do nové konzolové aplikace (`dotnet new console`) a okamžitě spustit.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### Očekávaný výstup

Spuštěním programu se vytvoří dva soubory v pracovním adresáři spustitelného souboru:

* `DatabarHeight30.png` – DataBar čárový kód s 30 pixelovými vysokými čárami.  
* `DatabarHeight60.png` – stejný čárový kód, ale každá čára je dvakrát vyšší.

Oba obrázky lze otevřít v libovolném prohlížeči obrázků nebo vložit přímo do PDF, HTML stránek či tištěných štítků.

## Proč úprava výšky čáry má význam

* **Spolehlivost skenování:** Některé skenery mají problémy s velmi krátkými čárami na médiích s nízkým rozlišením; zvýšení výšky zlepšuje detekci.  
* **Designové omezení:** Mobilní aplikace může potřebovat kompaktní čárový kód (30 px), zatímco tištěná účtenka může vyžadovat větší (60 px).  
* **Regulační shoda:** Některá odvětví vyžadují minimální výšku čáry pro symboly GS1 DataBar.

Opětovným použitím stejné instance `BarcodeGenerator` se vyhnete režii znovu‑parsování datového řetězce, což je zvláště výhodné v prostředích s vysokou propustností.

## Běžné varianty a okrajové případy

| Situace | Doporučená úprava |
|-----------|-------------------|
| Potřebujete jinou X‑dimenzi | Změňte `XDimension.Pixels` před prvním voláním `Save`. |
| Chcete jinou symbologii (např. DataBar Stacked) | Použijte `EncodeTypes.DatabarStacked` při vytváření `BarcodeGenerator`. |
| Musíte vložit čárový kód do PDF | Použijte `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)` a přidejte stream do PDF knihovny. |
| Běží na .NET Framework 4.6 | Stejný kód funguje; stačí odkazovat na odpovídající sestavení Aspose.BarCode. |

## Pro tipy pro spolehlivé generování čárových kódů

* **Ukládejte generátor do cache** při generování mnoha čárových kódů se stejnými daty, ale různými velikostmi.  
* **

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak vytvořit PNG obrázky databar pomocí C# a Aspose.BarCode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Jak generovat čárový kód s vlastní velikostí a uložit obrázek v C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}