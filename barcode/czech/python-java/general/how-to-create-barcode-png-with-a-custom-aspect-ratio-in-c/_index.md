---
category: general
date: 2026-10-05
description: Vytvořte PNG čárový kód v C# a naučte se, jak nastavit poměr stran 15
  pro vrstvené DataBar omnidirekcionální čárové kódy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: cs
lastmod: 2026-10-05
og_description: Vytvořte PNG čárový kód v C# a zjistěte, jak nastavit poměr stran
  15 pro vrstvené DataBar omnidirekcionální čárové kódy během několika kroků.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Vytvořte PNG čárový kód v C# – nastavení poměru stran 15 tutoriál
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak vytvořit PNG čárového kódu s vlastním poměrem stran v C#
url: /cs/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit PNG čárového kódu s vlastním poměrem stran v C#

Pokud potřebujete **vytvořit PNG čárového kódu** v C#, tento průvodce vám ukáže **jak nastavit poměr stran** 15 pro vrstvený DataBar omnidirekcionální čárový kód. Provedeme vás každým voláním API, vysvětlíme, proč je poměr stran důležitý, a poskytneme vám kompletní, spustitelný příklad, který můžete vložit do libovolného .NET projektu.

Generování obrázku čárového kódu je běžnou požadavkem pro inventární systémy, přepravní štítky a maloobchodní aplikace v místech prodeje. Na konci tohoto tutoriálu budete mít PNG soubor, který splňuje přesné vizuální specifikace požadované vaším obchodním partnerem. Žádné externí nástroje, žádná ruční úprava obrázku—pouze kód.

## Předpoklady

* .NET 6.0 nebo novější (příklad používá .NET 6, ale funguje i s .NET 5+)
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)
* **Aspose.BarCode for .NET** NuGet balíček  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Oprávnění k zápisu do složky, kam chcete PNG soubor uložit

Tyto požadavky jsou minimální; stejný kód funguje v .NET Core, .NET Framework nebo v konzolové aplikaci.

## Vytvoření PNG čárového kódu s Aspose.BarCode

Prvním krokem je vytvořit instanci třídy `BarcodeGenerator` s správným typem čárového kódu. V tomto případě používáme `EncodeTypes.DatabarStackedOmniDirectional`, který vytváří vrstvený DataBar, který lze číst z libovolného směru.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Proč je to důležité:* Konstruktor přijímá dva argumenty—**symbologii čárového kódu** a **datový řetězec**. Formát DataBar očekává identifikátor aplikace GS1, což je důvod, proč ukázková data začínají `(01)`.

## Jak nastavit poměr stran pro vrstvený DataBar

Vizuální šířka DataBaru je řízena vlastností **aspect ratio**. Vyšší poměr dělá pruhy širší, což může zlepšit spolehlivost skenování na tiskárnách s nízkým rozlišením.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` určuje velikost jednoho modulu (nejmenšího pruhu nebo mezery). Udržení této hodnoty na 2 px poskytuje ostrý, vysokohustotní obrázek vhodný pro většinu tiskáren štítků.

## Nastavení poměru stran 15 – průchod kódem

Nyní aplikujeme požadavek **nastavit poměr stran 15**. Toto je jádro tutoriálu a ukazuje přesné volání API, které potřebujete.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Proč 15?* Výchozí poměr stran pro vrstvený DataBar je 12. Zvýšením na 15 se šířka každého pruhu rozšíří o 25 %, což často odpovídá specifikacím logistických poskytovatelů, kteří vyžadují širší čárový kód pro rychlejší skenování.

## Uložení čárového kódu jako PNG

Po nastavení generátoru je posledním krokem zapsat obrázek na disk. Metoda `Save` přijímá cestu k souboru a výčtový typ formátu obrázku.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Formát PNG zachovává bezztrátovou kvalitu, což zajišťuje, že čárový kód se vykreslí přesně tak, jak byl navržen, na jakémkoli displeji nebo tiskárně.

## Kompletní příklad a očekávaný výstup

Níže je celý program, který můžete zkopírovat do metody `Main` konzolové aplikace. Obsahuje všechny výše popsané kroky a také malou ověřovací zprávu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Očekávaný výstup**

Spuštěním programu se vytvoří soubor s názvem `DatabarAspectRatio15.png`, který obsahuje čistý, široký vrstvený DataBar čárový kód. Když otevřete PNG, měli byste vidět vodorovně roztažený čárový kód, který stále splňuje specifikace GS1 DataBar.

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Text alternativy obrázku:* **vytvořit PNG čárového kódu zobrazujícího vrstvený DataBar s poměrem stran 15**

### Tipy a běžné úskalí

| Situace | Doporučení |
|-----------|----------------|
| **Obrázek vypadá rozmazaně** | Zvyšte `XDimension.Pixels` na 3 px nebo více, ale udržujte celkovou velikost obrázku pod 500 px, aby nedošlo k příliš velkým souborům. |
| **Skenner nemůže kód přečíst** | Ověřte, že datový řetězec odpovídá formátu GS1 (prefix `(01)`). Také zajistěte, aby rozlišení tiskárny bylo alespoň 300 dpi. |
| **Potřebujete jiný formát souboru** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif`—API podporuje všechny hlavní rastrové formáty. |
| **Běží v webové aplikaci** | Použijte `generator.Save(Stream, BarCodeImageFormat.Png)` pro přímý zápis do HTTP odpovědi bez zásahu do souborového systému. |

### Rozšíření příkladu

* **Více čárových kódů v jednom obrázku:** Vytvořte další instance `BarcodeGenerator` a vykreslete je na jediný `Bitmap` pomocí `Graphics`.  
* **Přidání lidsky čitelného textu:** Nastavte `generator.Parameters.Caption.Visible = true` a upravte font pomocí `generator.Parameters.Caption.Font`.  
* **Dynamický poměr stran:** Načtěte hodnotu poměru ze souboru konfigurace nebo databáze a generujte čárové kódy s různými šířkami za běhu.  

## Závěr

V tomto tutoriálu jste se naučili, jak **vytvořit PNG čárového kódu** v C# a přesně **nastavit poměr stran** 15 pro vrstvený DataBar omnidirekcionální čárový kód. Kompletní, spustitelný kód demonstruje každé požadované volání API, vysvětluje, proč je každé nastavení důležité, a poskytuje praktické tipy pro nasazení v reálném světě.  

Dále můžete prozkoumat **jak nastavit poměr stran** pro jiné typy čárových kódů (např. QR Code nebo Code 128) nebo integrovat generátor do služby ASP .NET Core, která na požádání vrací obrázky čárových kódů. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit PNG obrázky databar s C# a Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [Jak vytvořit vrstvený databar čárový kód v C# s Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Přizpůsobení poměru stran vrstveného omnidirekcionálního databar v .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}