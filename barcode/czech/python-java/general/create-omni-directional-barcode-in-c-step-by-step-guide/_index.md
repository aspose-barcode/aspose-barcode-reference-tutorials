---
category: general
date: 2026-07-15
description: Rychle vytvořte všesměrový čárový kód v C# pomocí Aspose.BarCode – naučte
  se generovat čárový kód v C# s nastavitelnou výškou čáry a X‑rozměrem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni-directional barcode
- how to generate barcode c#
- GS1 DataBar Omni-Directional
- barcode XDimension
- barcode BarHeight
language: cs
lastmod: 2026-07-15
og_description: vytvořte všesměrový čárový kód v C# s Aspose.BarCode. Ovládněte, jak
  generovat čárový kód v C# úpravou XDimension a BarHeight pro dokonalé výsledky.
og_image_alt: Screenshot showing a create omni-directional barcode generated in C#
  with 60 px bar height
og_title: Vytvořte omnidirekční čárový kód v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  headline: create omni-directional barcode in C# – Step‑by‑Step Guide
  type: TechArticle
- description: create omni-directional barcode in C# quickly with Aspose.BarCode –
    learn how to generate barcode C# with adjustable bar height and X‑dimension.
  name: create omni-directional barcode in C# – Step‑by‑Step Guide
  steps:
  - name: Expected output
    text: '- `DatabarBarHeight30Pixels.png` – a 30 px tall omni‑directional barcode.
      - `DatabarBarHeight60Pixels.png` – the same data, but with a 60 px tall barcode.'
  - name: What if I need a different X‑dimension?
    text: Simply assign a new value before calling `Save`. For ultra‑high‑density
      printing you might go down to 1 px, but test with your scanner first—some devices
      struggle with sub‑2 px bars.
  - name: Can I add human‑readable text below the barcode?
    text: Yes. Set `barcodeGenerator.Parameters.Barcode.CodeText` to a string and
      optionally adjust `barcodeGenerator.Parameters.Barcode.CodeLocation` to `BarCodeTextLocation.Below`.
      This is handy for retail environments where the numeric GTIN must be visible.
  - name: Is PNG the best format for printing?
    text: PNG is lossless, which preserves the sharp edges needed for barcode scanners.
      If your downstream system expects a different format (TIFF, BMP), just change
      the `BarCodeImageFormat` enum.
  type: HowTo
tags:
- barcode
- C#
- Aspose
- GS1
- DataBar
title: Vytvořte všesměrový čárový kód v C# – průvodce krok za krokem
url: /cs/python-java/general/create-omni-directional-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# vytvořte omni‑directional čárový kód v C# – krok za krokem průvodce

Už jste se někdy zamýšleli, jak v C# vygenerovat čárový kód, který splňuje symbologii GS1 DataBar Omni‑Directional? Nejste sami. V tomto tutoriálu **vytvoříme omni‑directional čárový kód** od nuly, upravíme X‑dimenzi a pohráváme si s výškou čáry — vše pomocí knihovny Aspose.BarCode.

Projdeme reálný scénář: potřebujete kompaktní, vysoce hustý čárový kód pro maloobchodní štítek a chcete mít úplnou kontrolu nad jeho vizuální velikostí. Na konci budete mít dva PNG soubory — jeden s výškou čáry 30 px a druhý s 60 px — připravené k nasazení do jakéhokoli tiskového workflow.

## Prerequisites

- .NET 6 (nebo jakékoli aktuální .NET runtime) nainstalovaný na vašem počítači.  
- Visual Studio 2022 nebo VS Code — váš oblíbený IDE bude stačit.  
- Bezplatný NuGet balíček Aspose.BarCode pro .NET (`Aspose.BarCode`).

Žádné další závislosti nejsou potřeba. Pokud jste s NuGetem nikdy nepracovali, stačí otevřít Package Manager Console a spustit:

```powershell
Install-Package Aspose.BarCode
```

## vytvořte omni‑directional čárový kód – pochopení základů

**GS1 DataBar Omni‑Directional** symbologie je navržena pro skenování v libovolné orientaci, což ji činí ideální pro štítky na okrajích regálů. Když zavoláte `new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, data)`, knihovna udělá těžkou práci: zakóduje data, aplikuje pravidla symbologie a připraví rastrový obrázek.

> **Pro tip:** Vždy zabalte surová data do odpovídajícího formátu Application Identifier (AI), např. `"(01)12345678901231"` pro GTIN‑14. Tím řadič ví, co číslice představují.

## Step 1 – Set Up the Barcode Generator (how to generate barcode c#)

Nejprve vytvoříme objekt generátoru. Toto je základ **how to generate barcode c#** s Aspose.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for the GS1 DataBar Omni‑Directional symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Hodnota výčtu `EncodeTypes.DatabarOmniDirectional` říká enginu, kterou symbologii použít. Druhý argument je řetězec surových dat, již zabalený v GTIN AI.

## Step 2 – Adjust the X‑Dimension (barcode XDimension)

**barcode XDimension** řídí šířku nejmenší čáry. Hodnota 2 px je dobrá rovnováha mezi čitelností a kompaktností pro většinu tiskáren štítků.

```csharp
// Step 2: Define common barcode parameters (2 px X‑dimension)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Pokud potřebujete jemnější nebo hrubší vzhled, stačí změnit číslo. Pamatujte: X‑dimenze je základní jednotka; všechny ostatní šířky čar jsou násobky této hodnoty.

## Step 3 – Create the First Image with a 30 px Bar Height (barcode BarHeight)

Nyní nastavíme **barcode BarHeight** na 30 px a uložíme obrázek. To vytvoří středně velký čárový kód, který se pěkně vejde na standardní štítek.

```csharp
// Step 3: Set a 30 px bar height and save the first image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Metoda `Save` zapíše PNG soubor na disk. Můžete zaměnit `BarCodeImageFormat.Jpeg`, pokud dáváte přednost výstupu JPEG.

## Step 4 – Increase Bar Height to 60 px for Larger Labels (barcode BarHeight)

Někdy je potřeba větší čárový kód — například pro štítek na regálu, který je dál od skeneru. Zdvojnásobíme výšku.

```csharp
// Step 4: Increase the bar height to 60 px for a larger barcode
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

Všimněte si, že **nepotřebujeme** znovu vytvářet generátor; jen upravíme parametr a použijeme stejný objekt. Tím šetříme paměť a kód zůstává přehledný.

## Step 5 – Save the Second Image (how to generate barcode c#)

Nakonec uložíme druhý PNG. Nyní máte dva soubory, které se liší jen výškou čáry.

```csharp
// Step 5: Save the second image with the updated height
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

### Expected output

- `DatabarBarHeight30Pixels.png` – 30 px vysoký omni‑directional čárový kód.  
- `DatabarBarHeight60Pixels.png` – stejné data, ale s 60 px vysokým čárovým kódem.

Otevřete soubory v libovolném prohlížeči obrázků; uvidíte ostré, skenovatelné čáry, které splňují specifikaci GS1 DataBar Omni‑Directional.

## Common Questions & Edge Cases

### What if I need a different X‑dimension?

Jednoduše přiřaďte novou hodnotu před voláním `Save`. Pro ultra‑vysokou hustotu tisku můžete jít až na 1 px, ale nejprve to otestujte se svým skenerem — některá zařízení mají problémy s čárami pod 2 px.

### Can I add human‑readable text below the barcode?

Ano. Nastavte `barcodeGenerator.Parameters.Barcode.CodeText` na řetězec a případně upravte `barcodeGenerator.Parameters.Barcode.CodeLocation` na `BarCodeTextLocation.Below`. To je užitečné v maloobchodních prostředích, kde musí být viditelné číselné GTIN.

```csharp
barcodeGenerator.Parameters.Barcode.CodeText = "(01)12345678901231";
barcodeGenerator.Parameters.Barcode.CodeLocation = BarCodeTextLocation.Below;
```

### Is PNG the best format for printing?

PNG je bezztrátový, což zachovává ostré hrany potřebné pro skenery čárových kódů. Pokud váš downstream systém očekává jiný formát (TIFF, BMP), stačí změnit výčet `BarCodeImageFormat`.

## Full Working Example (create omni-directional barcode)

Níže je kompletní, připravený program. Zkopírujte jej do nového konzolového projektu a stiskněte **F5**.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace OmniDirectionalDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension (2 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ First image – 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ Second image – 60 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two omni‑directional barcodes created successfully.");
        }
    }
}
```

Spusťte program, podívejte se do výstupní složky a uvidíte dva PNG soubory přesně tak, jak bylo popsáno.

## Recap

Ukázali jsme **how to generate barcode C#** kód, který vytváří **create omni-directional barcode** pomocí Aspose.BarCode. Úpravou **barcode XDimension** a **barcode BarHeight** získáte jemnou kontrolu nad vizuální velikostí bez ztráty spolehlivosti skenování.

## What’s Next?

- Experimentujte s dalšími nastaveními **GS1 DataBar Omni-Directional**, jako jsou `Color` nebo `Margin`.  
- Kombinujte více čárových kódů na jedné plátně pomocí `Graphics` pro složité návrhy štítků.  
- Integrovejte generátor do webového API, aby vaše e‑commerce platforma mohla na požádání generovat čárové kódy.

Máte nějaký tip, který byste chtěli sdílet? Zanechte komentář a pojďme konverzaci posunout dál. Šťastné kódování!

## What Should You Learn Next?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak generovat čárový kód – konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro ITF-14 pomocí Aspose.BarCode pro .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Jak vytvořit tichou zónu čárového kódu pro Code 16K pomocí Aspose.BarCode pro .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}