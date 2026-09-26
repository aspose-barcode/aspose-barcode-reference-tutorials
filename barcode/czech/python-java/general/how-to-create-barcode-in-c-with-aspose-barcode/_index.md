---
category: general
date: 2026-09-26
description: Naučte se, jak vytvořit čárový kód v C# pomocí Aspose.BarCode. Tento
  krok‑za‑krokem průvodce obsahuje příklad generátoru čárových kódů a ukazuje, jak
  upravit výšku čáry.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: cs
lastmod: 2026-09-26
og_description: Vytvořte čárový kód v C# pomocí Aspose.BarCode. Postupujte podle tohoto
  návodu, abyste vygenerovali čárový kód, upravili výšku čar a uložili PNG obrázky.
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: Vytvořte čárový kód v C# pomocí Aspose.BarCode – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Jak vytvořit čárový kód v C# pomocí Aspose.BarCode
url: /cs/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit čárový kód v C# s Aspose.BarCode  

Pokud potřebujete rychle **create barcode c#** projekty, Aspose.BarCode poskytuje plynulé API, které řeší těžkou práci. V tomto tutoriálu uvidíte kompletní **barcode generator example**, naučíte se **how to adjust bar height** a exportujete výsledek jako PNG soubory.  

Ať už budujete systém pokladny v maloobchodě, generujete štítky zásob nebo automatizujete přepravní štítky, schopnost programově změnit vizuální velikost čárového kódu je nezbytná. Tento průvodce předpokládá, že máte základní znalosti C# a vývojové prostředí jako Visual Studio 2022.  

## Požadavky  

Před začátkem se ujistěte, že máte:  

* .NET 6.0 SDK nebo novější nainstalovaný.  
* Visual Studio 2022 (nebo jakékoli C# IDE).  
* Aktivní licence Aspose.BarCode (bezplatná zkušební verze funguje pro výuku).  

Budete také potřebovat přidat NuGet balíček Aspose.BarCode do svého projektu:

```bash
dotnet add package Aspose.BarCode
```

> **Tip:** Pokud plánujete generovat mnoho čárových kódů ve smyčce, znovu použijte jedinou instanci `BarcodeGenerator` a měňte jen parametry, které se mění. To snižuje alokace paměti a zlepšuje výkon.

## Jak vytvořit čárový kód v C# s Aspose.BarCode  

Následující sekce vás provede každým krokem **barcode generator example**. Kód je samostatný; zkopírujte jej do nové konzolové aplikace a spusťte.  

### Krok 1: Importujte požadované jmenné prostory  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Tyto jmenné prostory vám poskytují přístup ke třídě `BarcodeGenerator` a výčtu `EncodeTypes`.  

### Krok 2: Inicializujte generátor čárových kódů  

Vygenerujeme symbol **Databar Omni‑Directional**, který kóduje hodnotu GTIN‑14. Konstruktor přijímá symbologii a řetězec s daty.

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Hodnota `EncodeTypes.DatabarOmniDirectional` říká Aspose.BarCode, který standard čárových kódů použít. Řetězec dat následuje formát GS1 Application Identifier, který je běžný pro maloobchodní čárové kódy.  

### Krok 3: Nastavte běžné parametry čárového kódu  

Dva vizuální parametry se nejčastěji upravují: X‑dimenze (šířka úzkého pruhu) a celková výška pruhu.  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** řídí hustotu čárového kódu, zatímco **BarHeight** určuje vertikální velikost každého pruhu. Úprava **BarHeight** je přesně to, co potřebujete, když chcete **change barcode height** pro různé tiskové média.  

### Krok 4: Uložte první obrázek (výška 30 pixelů)  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapíše vykreslený obrázek na disk. Název souboru jasně uvádí použité výšky, což pomáhá při porovnávání různých výstupů.  

### Krok 5: Změňte výšku pruhu na 60 pixelů  

Nyní ukazujeme **how to adjust bar height** za běhu. Stejná instance `generator` se znovu použije; mění se pouze vlastnost `BarHeight`.  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Protože generátor zachovává všechna ostatní nastavení (symbologie, data, X‑dimension), jediný vizuální rozdíl mezi dvěma PNG soubory je vertikální velikost pruhů.  

### Kompletní zdrojový kód  

Skládáním všeho dohromady získáte stručný, spustitelný program:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**Očekávaný výstup**  

Spuštěním programu se vytvoří dva PNG soubory v pracovním adresáři spustitelného souboru:

* `DatabarBarHeight30Pixels.png` – čárový kód s výškou pruhu 30 px.  
* `DatabarBarHeight60Pixels.png` – stejný čárový kód, ale každý pruh je dvakrát vyšší.

Otevřete obrázky v libovolném prohlížeči; uvidíte, že celkový vzor zůstává stejný, zatímco vertikální rozměr se mění, což potvrzuje, že operace **change barcode height** byla úspěšná.  

## Pokročilé varianty  

### Přepnutí na jinou symbologii  

Pokud potřebujete QR kód místo Databar, nahraďte hodnotu `EncodeTypes`:

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Všechna ostatní nastavení parametrů (X‑dimension, BarHeight) stále platí tam, kde mají smysl.  

### Použití `BarHeight` v milimetrech  

Aspose.BarCode také podporuje fyzické jednotky. Pro nastavení výšky 10 mm:

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

To je užitečné, když generujete čárové kódy pro tiskové rozvržení, které vyžaduje přesná měření.  

### Zpracování chyb  

Pokud řetězec dat neodpovídá vybrané symbologii, `BarcodeGenerator` vyhodí `ArgumentException`. Zabalte logiku generování do bloku try‑catch, aby se zobrazila přátelská zpráva:

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## Často kladené otázky  

* **Ovlivňuje změna BarHeight čitelnost?**  
  Čárový kód zůstává čitelný, pokud X‑dimension a celková tichá zóna splňují specifikace symbologie. Zvýšení výšky pouze prodlužuje pruhy; nikdy nesnižuje kontrast.  

* **Mohu nastavit různé výšky pro jednotlivé pruhy?**  
  Ne. Vlastnost `BarHeight` se aplikuje jednotně na celý symbol. Pro návrhy s proměnnou výškou byste potřebovali vlastní renderovací rutinu mimo rozsah Aspose.BarCode.  

* **Je PNG nejlepší formát pro tisk?**  
  PNG zachovává bezztrátová pixelová data, což je ideální pro zobrazení na obrazovce. Pro vysoce rozlišené tiskové úlohy zvažte `BarCodeImageFormat.Tiff` nebo `Pdf`, aby se zachovaly vektorové informace.  

## Závěr  

Nyní víte, jak **create barcode c#** aplikace s Aspose.BarCode, viděli jste kompletní **barcode generator example** a rozumíte **how to adjust bar height**, abyste splnili různé požadavky na rozvržení. Opakovaným použitím stejné instance generátoru a úpravou pouze `BarHeight` můžete efektivně **change barcode height** bez nutnosti přestavovat celý objekt.  

Od sem můžete dále zkoumat:

* Generování dalších symbologií (`EncodeTypes.Code128`, `EncodeTypes.EAN13`).  
* Export do SVG nebo PDF pro škálovatelnou grafiku.  
* Vkládání čárových kódů přímo do dokumentů Word nebo Excel pomocí Aspose.Words nebo Aspose.Cells.  

Šťastné programování a užívejte si flexibilitu, kterou Aspose.BarCode přináší vašim C# projektům s čárovými kódy!  


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat a upravit výšku čárového kódu pro jednorozměrný Databar pomocí Aspose.BarCode pro .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Jak vytvořit PNG soubor čárového kódu s nastavitelnou výškou v C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [Jak generovat čárový kód v C# – Kompletní průvodce Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}