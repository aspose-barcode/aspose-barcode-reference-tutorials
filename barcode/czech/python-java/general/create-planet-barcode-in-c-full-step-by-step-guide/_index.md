---
category: general
date: 2026-07-18
description: Rychle vytvořte čárový kód Planet pomocí C#. Naučte se generovat plné
  i prázdné pruhy, nastavit X‑rozměr a uložit PNG obrázky – vše v jednom tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: cs
lastmod: 2026-07-18
og_description: Vytvořte čárový kód Planet okamžitě. Tento průvodce ukazuje, jak nastavit
  X‑rozměr, přepínat mezi vyplněnými a prázdnými pruhy a exportovat PNG soubory pomocí
  Aspose.BarCode.
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: Vytvořte Planet Barcode v C# – Kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Vytvořte Planet Barcode v C# – Kompletní krok‑za‑krokem průvodce
url: /cs/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření Planet čárového kódu v C# – Kompletní průvodce krok za krokem

Už jste někdy potřebovali **vytvořit planet čárový kód** obrázky, ale nebyli jste si jisti, které vlastnosti upravit? Nejste v tom sami. Mnoho vývojářů narazí na problém, když výchozí plně vyplněné pruhy nesplňují požadavky specifikace, nebo když šířka pruhu musí odpovídat DPI tiskárny.  

V tomto tutoriálu se přesně naučíte, jak **vytvořit planet čárový kód** soubory pomocí knihovny Aspose.BarCode, jak ovládat **XDimension pixely** a jak přepínat mezi **vyplněnými pruhy** a **prázdnými pruhy** bez přepisování kódu. Na konci budete mít dva PNG soubory — jeden s plnými pruhy a jeden s dutými pruhy — připravené pro jakýkoli poštovní systém, který očekává symbologii Planet.

## Požadavky

- .NET 6.0 nebo novější (kód funguje také na .NET Framework 4.7 +)  
- Aspose.BarCode pro .NET NuGet balíček (`Install-Package Aspose.BarCode`)  
- Základní znalost C# (později uvidíte, proč používáme `using` příkazy)  
- Zapisovatelná složka na disku, kam budou PNG soubory uloženy  

Pokud máte vše připravené, můžeme rovnou přejít k implementaci.

## Krok 1 – Nastavení projektu a přidání knihovny

Nejprve vytvořte novou konzolovou aplikaci (nebo jakýkoli C# projekt) a odkazujte na knihovnu **Planet barcode generator**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **Tip:** Ve Visual Studiu klikněte pravým tlačítkem na projekt → *Manage NuGet Packages* → vyhledejte **Aspose.BarCode** a klikněte na *Install*. Tím získáte přístup k `BarcodeGenerator` a všem **BarcodeGenerator parametrům**, které budete potřebovat.

## Krok 2 – Inicializace Planet čárového kódu

Nyní skutečně **vytvoříme planet čárový kód** generátor a předáme mu data, která chceme zakódovat (`"123456"` v tomto příkladu). Enum `EncodeTypes.Planet` říká knihovně, kterou symbologii použít.

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **Proč je to důležité:** Příznak `EncodeTypes.Planet` automaticky použije správný kontrolní součet a pravidla rozložení pro planetární poštovní čárový kód, takže je nemusíte počítat ručně.

## Krok 3 – Nastavení X‑Dimension (šířka pruhu)

Většina tiskáren očekává, že každý pruh bude mít konkrétní počet pixelů. Zde nastavíme **XDimension pixely** na `4`, což je běžná hodnota pro 203 dpi termální tiskárny.

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **Hraniční případ:** Pokud cílíte na 300 dpi tiskárnu, možná budete potřebovat `3` nebo `5` pixelů. Hodnotu upravte podle dokumentace vašeho zařízení.

## Krok 4 – Uložení verze s vyplněnými pruhy

Ve výchozím nastavení generátor vytváří **vyplněné pruhy** (plné černé obdélníky). Uložme je na disk:

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Nahraďte `YOUR_DIRECTORY` absolutní nebo relativní cestou, do které může vaše aplikace zapisovat. Po spuštění tohoto řádku najdete PNG soubor, který vypadá jako klasický Planet čárový kód — ideální pro testování na poštovním skeneru.

## Krok 5 – Přepnutí na prázdné pruhy

Některé poštovní služby vyžadují styl „prázdných pruhů“, kde jsou pruhy vyřezány z bílého pozadí místo aby byly černě natřeny. Knihovna poskytuje jednoduchý přepínač:

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

Nastavení `FilledBars` na `false` říká rendereru, aby invertoval logiku vyplnění pruhu. Není potřeba vytvářet novou instanci `BarcodeGenerator`; stačí upravit existující **BarcodeGenerator parametry**.

## Krok 6 – Uložení verze s prázdnými pruhy

Nakonec exportujte druhý obrázek:

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Nyní máte dva odlišné PNG soubory, každý splňující jiný vizuální požadavek.

## Kompletní funkční příklad

Sestavením všech částí získáte kompletní program připravený ke zkopírování a vložení:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**Očekávaný výstup** (v konzoli):

```
Both Planet barcode images have been generated successfully.
```

A ve složce `C:\Barcodes\` uvidíte:

- `PostalPlanetFilledBars.png` – plné černé pruhy  
- `PostalPlanetEmptyBars.png` – bílé pruhy s černými obrysy  

Otevřete je v libovolném prohlížeči obrázků; oba by měly odpovídat specifikaci Planet.

## Často kladené otázky a tipy

### „Mohu změnit formát obrázku?“

Samozřejmě. Metoda `Save` přijímá `BarCodeImageFormat.Jpeg`, `Bmp`, `Gif` atd. Stačí nahradit `BarCodeImageFormat.Png` požadovaným formátem.

### „Co když potřebuji jinou výšku čárového kódu?“

Použijte `planetBarcode.Parameters.Barcode.BarHeight` (v bodech) pro zvýšení nebo snížení vertikální velikosti. Například:

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### „Existuje způsob, jak přidat čitelný popisek?“

Ano. Nastavte vlastnost `CodeText` na `planetBarcode.Parameters.Caption`:

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### „Musím generátor uvolnit?“

`BarcodeGenerator` implementuje `IDisposable`. Zabalte jej do `using` bloku, pokud vytváříte mnoho čárových kódů v cyklu:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### „Jak řešit chyby?“

Obalte volání `Save` do `try…catch` bloku, abyste zachytili `IOException` (problémy s diskem) nebo `ArgumentException` (neplatné parametry). Příklad:

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## Shrnutí

Probrali jsme vše, co potřebujete k **vytvoření planet čárového kódu** v C#:

1. Inicializujte **Planet barcode generator** s vašimi daty.  
2. Upravit **XDimension pixely** podle specifikací tiskárny.  
3. Uložte PNG s **vyplněnými pruhy**.  
4. Přepněte `FilledBars` pro vytvoření **prázdných pruhů**.  
5. Uložte druhý PNG.  

Odtud můžete zkoumat další **BarcodeGenerator parametry**, experimentovat s jinými symbologiemi (`EncodeTypes.Postnet`, `EncodeTypes.Code128` atd.) nebo integrovat obrázky do poštovního workflow.

---

**Připravený na další krok?** Zkuste přidat QR kód do stejného dokumentu nebo vygenerovat dávku Planet čárových kódů ze seznamu CSV pomocí smyčky `foreach`. API Aspose.BarCode je dostatečně flexibilní pro hromadné operace, vlastní barvy i vektorový výstup SVG.

Pokud narazíte na problémy, zanechte komentář níže nebo si prostudujte oficiální dokumentaci Aspose.BarCode pro podrobnější informace o pokročilých funkcích. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}