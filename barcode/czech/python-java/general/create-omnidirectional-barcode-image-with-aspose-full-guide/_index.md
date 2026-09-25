---
category: general
date: 2026-07-27
description: Vytvořte všesměrový obrázek čárového kódu pomocí Aspose.BarCode. Naučte
  se, jak generovat čárový kód s Aspose, upravit poměr stran a uložit soubory PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: cs
lastmod: 2026-07-27
og_description: Vytvořte všesměrový obrázek čárového kódu pomocí Aspose. Postupujte
  podle tohoto návodu, jak generovat čárový kód s Aspose, upravovat poměry stran a
  exportovat PNG soubory.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Vytvořte všesměrový obrázek čárového kódu pomocí Aspose – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Vytvořte všesměrový obrázek čárového kódu pomocí Aspose – kompletní průvodce
url: /cs/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření omnidirekčního obrázku čárového kódu pomocí Aspose – Kompletní průvodce

Už jste někdy potřebovali **vytvořit omnidirekční obrázek čárového kódu**, ale nebyli jste si jisti, kterou knihovnu zvolit? Nejste v tom sami. V mnoha logistických a maloobchodních projektech je formát DataBar Stacked Omnidirectional tajnou ingrediencí pro kompaktní, vysoce husté kódování.

Dobrá zpráva? S **Aspose.BarCode** můžete tento čárový kód vygenerovat během několika řádků, upravit jeho poměr stran a uložit PNG přímo na disk. Níže uvidíte přesně, jak **vygenerovat čárový kód pomocí Aspose**, proč je každé nastavení důležité a na co si dát pozor při změně poměru stran.

---

## Co tento tutoriál pokrývá

Projdeme celý životní cyklus:

1. Nastavení výstupní složky.
2. Vytvoření generátoru DataBar Stacked Omnidirectional.
3. Konfigurace rozměrů pixelů a poměrů stran.
4. Uložení čárového kódu jako PNG soubory.
5. Rozšíření příkladu o další formáty a okrajové případy.

Na konci budete mít připravenou C# konzolovou aplikaci, která vygeneruje dva odlišné obrázky čárových kódů. Žádné externí nástroje, jen čistý kód Aspose.

**Požadavky**

- .NET 6.0 SDK nebo novější (kód funguje také na .NET Framework 4.7.2).
- NuGet balíček Aspose.BarCode pro .NET (`Install-Package Aspose.BarCode`).
- Složka na disku, kam lze zapisovat obrázky.

Pokud je již máte, pojďme na to.

---

## Krok 1: Připravte výstupní složku

Nejprve řekněte programu, kam má ukládat PNG soubory. Hard‑coding cesty funguje pro ukázku, ale v produkci byste ji pravděpodobně načítali z konfigurace.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Proč je to důležité:* `Directory.CreateDirectory` je idempotentní; pokud složka již existuje, nevyhodí výjimku, čímž vám ušetří try‑catch blok.

---

## Krok 2: Vytvořte generátor DataBar Stacked Omnidirectional

Nyní spustíme generátor s konkrétním typem kódování a ukázkovými daty. Řetězec `"(01)12345678901231"` odpovídá syntaxi GS1 Application Identifier pro 14‑ciferný GTIN.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Vysvětlení:* `EncodeTypes.DatabarStackedOmniDirectional` říká Aspose, aby použil omnidirekční variantu, která je čitelná z jakéhokoli směru — ideální pro malé štítky, které mohou být otočeny.

---

## Krok 3: Nastavte společné parametry čárového kódu

Než něco vykreslíme, definujeme nejmenší velikost elementu (X‑Dimension). Hodnota **2 pixely** poskytuje ostrý obrázek, aniž by zvětšovala velikost souboru.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Tip:* Pokud potřebujete vyšší rozlišení pro tisk, zvyšte tuto hodnotu na 3 nebo 4. Pamatujte, že větší X‑Dimension zvětšuje šířku i výšku úměrně.

---

## Krok 4: Vygenerujte a uložte s poměrem stran 15

Rodina DataBar vám umožňuje upravit **poměr stran**, který řídí vztah výšky k šířce. Poměr stran **15** je běžná výchozí hodnota pro omnidirekční čárové kódy.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Co uvidíte:* Relativně vysoký čárový kód, který se stále pohodlně vejde na štítek 2 × 1 cm. Formát PNG zachovává bezztrátovou kvalitu, ideální pro další zpracování nebo tisk.

---

## Krok 5: Změňte poměr stran na 30 a uložte znovu

Chcete plošší čárový kód? Stačí upravit vlastnost `AspectRatio` a znovu zavolat `Save`. Není potřeba generátor znovu vytvářet.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Proč znovu použít stejný generátor?* Objekt Aspose je lehký; změna vlastnosti a opětovné uložení je rychlejší než vytvoření nové instance a zaručuje, že nastavení kódování (např. X‑Dimension) zůstane konzistentní.

---

## Kompletní funkční příklad

Spojením všech částí získáte kompletní, samostatný program, který můžete zkopírovat a vložit do nového konzolového projektu.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Očekávaný výstup**

Spuštěním programu se vytvoří podsložka `Barcodes` obsahující:

- `DatabarAspectRatio15.png` – vyšší, klasický vzhled.
- `DatabarAspectRatio30.png` – plošší, vhodnější pro široké štítky.

Oba obrázky zobrazují stejná GTIN data; liší se pouze vizuálními proporcemi.

---

## Rozšíření příkladu (okrajové případy a varianty)

### 1. Různé formáty obrázků

Aspose podporuje BMP, JPEG, TIFF a SVG kromě PNG. Vyměňte hodnotu enumu:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG je vektorový, což znamená, že jej můžete škálovat bez ztráty ostrosti — užitečné pro responzivní webové aplikace.

### 2. Přizpůsobení barev

Možná budete potřebovat bílý čárový kód na tmavém pozadí. Nastavte `ForeColor` a `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Zpracování neplatných poměrů stran

Aspose ověřuje rozsah (obvykle 5‑50). Pokud předáte hodnotu mimo rozsah, je vyvolána `ArgumentException`. Zabalte volání `Save` do try‑catch a zobrazte přátelskou zprávu:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Dávkové generování

Když máte seznam GTINů, projděte jej v cyklu, aktualizujte `CodeText` a uložte každý soubor pod jedinečným názvem. Objekt generátoru lze znovu použít, což udržuje nízkou spotřebu paměti.

---

## Časté úskalí a profesionální tipy

- **Nikdy nezapomeňte nastavit `XDimension`** před uložením; výchozí hodnota (0,33 mm) může na nízkém rozlišení zobrazit rozmazané obrázky.
- **Poměr stran je výška‑k‑šířce**, ne naopak. Větší číslo způsobí, že čárový kód bude *kratší* ve výšce.
- **Cesty k souborům:** Používejte `Path.Combine`, abyste se vyhnuli problémům s oddělovači specifickými pro platformu — zejména pokud kód běží v Linux kontejneru.
- **Licencování:** Aspose.BarCode je komerční. V režimu zkušební verze se na obrázku objeví vodoznak. Zaregistrujte licenci co nejdříve, abyste se vyhnuli překvapením v produkci.

---

## Závěr

Nyní víte, jak **vytvořit omnidirekční obrázek čárového kódu** pomocí Aspose, upravit poměr stran a exportovat PNG soubory — vše během méně než 30 řádků C#. Tento tutoriál ukázal krok za krokem proces, vysvětlil, proč je každé nastavení důležité, a pokryl rozšíření jako různé formáty, barvy a dávkové zpracování.

Jste připraveni na další výzvu? Zkuste generovat QR kódy, vložit čárový kód do PDF nebo integrovat výstup do ASP.NET Core API. Stejné principy **generování čárového kódu pomocí Aspose** platí pro všechny typy čárových kódů, takže můžete využít to, co jste se dnes naučili.

Máte otázky nebo chcete sdílet své úpravy? Zanechte komentář níže — šťastné kódování!

---

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Jak vytvořit čárový kód Aspose Java – úprava kvality obrázku](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Jak generovat obrázek čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}