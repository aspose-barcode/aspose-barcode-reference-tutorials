---
category: general
date: 2026-10-21
description: Naučte se, jak v C# generovat obrázky čárových kódů a jak exportovat
  soubory čárových kódů jako PNG pomocí Aspose.BarCode pro rychlé a spolehlivé výsledky.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to export barcode
language: cs
lastmod: 2026-10-21
og_description: Jak generovat obrázky čárových kódů v C# a jak exportovat soubory
  čárových kódů jako PNG. Sledujte tento kompletní tutoriál pro vytvoření čárových
  kódů Planet a RM4SCC pomocí Aspose.BarCode.
og_image_alt: Screenshot showing how to generate barcode images with C# code
og_title: Jak generovat obrázky čárových kódů a exportovat je v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Learn how to generate barcode images in C# and how to export barcode
    files as PNG using Aspose.BarCode for fast, reliable results.
  headline: How to generate barcode images and export them in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Jak generovat obrázky čárových kódů a exportovat je v C#
url: /cs/python-java/general/how-to-generate-barcode-images-and-export-them-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat obrázky čárových kódů a exportovat je v C#

Pokud potřebujete **jak generovat čárový kód** obrázky v .NET aplikaci, tento průvodce vám ukáže přesné kroky k vytvoření čárových kódů Planet a RM4SCC a následně **jak exportovat čárový kód** soubory jako PNG soubory. Dostanete připravený ukázkový kód, popis každého nastavení a tipy na běžné úskalí.

The tutorial covers:

* Přidání NuGet balíčku Aspose.BarCode
* Konfigurace šířky modulu a volitelné výšky čáry
* Ukládání vygenerovaných čárových kódů na disk
* Ověření výstupních souborů

> **Prerequisite** – .NET 6+ SDK, Visual Studio 2022 (nebo jakékoli IDE) a internetové připojení pro stažení balíčku Aspose.BarCode.

## Co dosáhnete

Na konci tohoto článku budete schopni:

* Vygenerovat **Planet** čárový kód s automatickou výškou čáry.
* Vygenerovat **RM4SCC** čárový kód s automatickou výškou čáry.
* Přepsat výchozí výšku a vytvořit čárový kód vysoký 100 pixelů.
* Exportovat každý čárový kód do PNG souboru ve vámi zvolené složce.

## Krok 1: Instalace Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček poskytuje třídu `BarcodeGenerator` a výčtový typ `EncodeTypes`, které jsou použity v následujícím kódu.

## Krok 2: Nastavení výstupní složky

Vytvořte složku, kde budou uloženy PNG soubory. Složka může být absolutní nebo relativní k kořeni projektu.

```csharp
// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

> **Tip:** Použití `Path.Combine` eliminuje pevně zakódované oddělovače cest a funguje na Windows, macOS i Linuxu.

## Krok 3: Generování čárových kódů s automatickou výškou čáry

Když neuvedete výšku čáry, Aspose.BarCode zvolí velikost, která odpovídá zakódovaným datům. Následující kód vytvoří dva čárové kódy — Planet a RM4SCC — s šířkou modulu 4 pixelů.

```csharp
using Aspose.BarCode.Generation;

// Planet barcode, automatic height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
planetAuto.Save(Path.Combine(outputFolder, "PlanetAutoHeight.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode, automatic height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccAuto.Parameters.Barcode.XDimension.Pixels = 4; // Set module width
rm4sccAuto.Save(Path.Combine(outputFolder, "RM4SCCAutoHeight.png"),
                BarCodeImageFormat.Png);
```

**Proč to funguje:**  
* `EncodeTypes.Planet` a `EncodeTypes.RM4SCC` říkají generátoru, kterou symbologii použít.  
* `XDimension.Pixels` určuje šířku jednoho modulu čárového kódu; hodnota 4 px poskytuje čistý, čitelný obrázek.  
* Protože `BarHeight` není nastaven, knihovna automaticky vypočítá optimální výšku.

## Krok 4: Generování čárových kódů s pevnou výškou 100 pixelů

Pokud váš design vyžaduje konkrétní výšku čáry, můžete přepsat automatický výpočet:

```csharp
// Planet barcode, fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
planetFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
planetFixed.Save(Path.Combine(outputFolder, "PlanetHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode, fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccFixed.Parameters.Barcode.XDimension.Pixels = 4;      // Module width
rm4sccFixed.Parameters.Barcode.BarHeight.Pixels = 100;   // Fixed height
rm4sccFixed.Save(Path.Combine(outputFolder, "RM4SCCHeight100.png"),
                 BarCodeImageFormat.Png);
```

**Proč můžete potřebovat pevnou výšku:**  
Specifikace designu pro přepravní štítky často určují přesné rozměry čárových kódů, aby byla zajištěna kompatibilita se skenery. Nastavení `BarHeight.Pixels` zaručuje jednotnost napříč všemi vygenerovanými obrázky.

## Krok 5: Ověření exportovaných souborů

Po spuštění programu obsahuje složka `Barcodes` čtyři PNG soubory:

* `PlanetAutoHeight.png`
* `RM4SCCAutoHeight.png`
* `PlanetHeight100.png`
* `RM4SCCHeight100.png`

Otevřete kterýkoli z nich v prohlížeči obrázků nebo je vložte do PDF, abyste potvrdili, že se zobrazují správně. Pokud skener nedokáže čárový kód přečíst, zvyšte hodnotu `XDimension.Pixels` nebo zkontrolujte délku vstupního řetězce.

```bash
# Example verification command (Linux/macOS)
file Barcodes/*.png
```

Měli byste vidět výstup podobný:

```
Barcodes/PlanetAutoHeight.png: PNG image data, 180 x 100, 8-bit/color RGBA, non-interlaced
```

## Časté otázky a okrajové případy

| Otázka | Odpověď |
|----------|--------|
| **Mohu exportovat do formátů jiných než PNG?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp`, `Gif` nebo `Tiff`. |
| **Co když moje data obsahují znaky, které nejsou v symbologii povoleny?** | Generátor vyhodí `ArgumentException`. Ověřte vstup nebo přepněte na symbologii, která podporuje danou znakovou sadu. |
| **Jak změním barvy popředí/pozadí?** | Nastavte `Parameters.Barcode.ForeColor` a `Parameters.Barcode.BackColor` před voláním `Save`. |
| **Existuje způsob, jak generovat čárové kódy v paměti místo ukládání na disk?** | Zavolejte `GenerateBarCodeImage()` a získáte objekt `System.Drawing.Image`, který můžete dále upravovat nebo streamovat. |

## Profesionální tip: hromadné zpracování

Když potřebujete vytvořit mnoho čárových kódů (např. pro poštovní seznam), zabalte logiku generování do smyčky `foreach`:

```csharp
var values = new[] { "001122", "334455", "667788" };
int index = 0;

foreach (var value in values)
{
    var generator = new BarcodeGenerator(EncodeTypes.Planet, value);
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Save(Path.Combine(outputFolder, $"Planet_{index++}.png"),
                   BarCodeImageFormat.Png);
}
```

Tento vzor škáluje na tisíce čárových kódů a přitom zůstává kód stručný.

## Závěr

Nyní víte **jak generovat čárový kód** obrázky v C# a **jak exportovat čárový kód** soubory jako PNG pomocí Aspose.BarCode. Kompletní příklad ukazuje jak automatické, tak i generování s pevnou výškou pro symbologie Planet a RM4SCC, což vám poskytuje solidní základ pro jakýkoli projekt související s čárovými kódy.

**Další kroky**

* Prozkoumejte další symbologie jako Code128, QR nebo DataMatrix.  
* Experimentujte s přizpůsobením barev (`ForeColor`, `BackColor`).  
* Integrovat vygenerované PNG do PDF faktur nebo přepravních štítků pomocí PDF knihovny.  

Šťastné programování a ať vaše čárové kódy fungují bez problémů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/english/net/datamatrix-barcode-configuration/)
- [Vytvořte GS1 čárové kódy v C# – Jak rychle generovat čárový kód v C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [jak generovat obrázek čárového kódu s Aspose.BarCode v C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}