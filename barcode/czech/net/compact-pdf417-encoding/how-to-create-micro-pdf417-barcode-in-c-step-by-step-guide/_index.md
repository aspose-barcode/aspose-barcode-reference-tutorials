---
category: general
date: 2026-08-22
description: Naučte se, jak vytvořit mikro PDF417 čárový kód v C# a vygenerovat PNG
  obrázek čárového kódu. Zahrnuje nastavení rozměrů čárového kódu a uložení souboru.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: cs
lastmod: 2026-08-22
og_description: Vytvořte mikro PDF417 čárový kód v C# a exportujte jej jako PNG. Postupujte
  podle tohoto návodu, abyste nastavili rozměry čárového kódu a rychle vygenerovali
  obrázek čárového kódu.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Vytvořte mikro PDF417 čárový kód v C# – kompletní programovací tutoriál
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Jak vytvořit mikro PDF417 čárový kód v C# – krok za krokem průvodce
url: /cs/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit mikro PDF417 čárový kód v C# – krok za krokem

Pokud potřebujete **vytvořit mikro PDF417 čárový kód** pro tiketovací systém, štítek zásob nebo mobilní skenování, tento tutoriál vám ukáže přesně jak. Uvidíte kompletní C# program, který generuje PNG čárového kódu, naučíte se nastavit rozměry kódu a pochopíte každou konfigurační volbu.

Na konci tohoto průvodce budete schopni vygenerovat vysoce rozlišený obrázek čárového kódu, přizpůsobit X‑rozměr, zvolit počet sloupců a uložit výsledek jako PNG soubor – vše pomocí několika řádků kódu.

## Co budete potřebovat

- .NET 6.0 SDK nebo novější (kód funguje s .NET Core i .NET Framework)
- Visual Studio 2022 nebo jakékoli IDE podporující C#
- NuGet balíček **Aspose.BarCode for .NET** (nebo libovolná knihovna, která podporuje `EncodeTypes.MicroPdf417`)
- Základní znalost syntaxe C#

> **Tip:** Bezplatná komunitní edice Aspose.BarCode stačí pro vývoj a testování. Pro produkční nasazení si pořiďte licenci, která odstraní evaluační vodoznaky.

## Krok 1: Instalace knihovny pro čárové kódy

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Tím se přidá sestavení `Aspose.BarCode`, které poskytuje třídu `BarcodeGenerator` používanou k **vytvoření čárového kódu v C#** aplikacích.

## Krok 2: Inicializace generátoru – vytvoření mikro PDF417 čárového kódu

První akční řádek vytvoří instanci `BarcodeGenerator` nakonfigurovanou pro symbologii Micro PDF417 a předá data, která chcete kódovat.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Proč je to důležité*: Výčtový typ `EncodeTypes.MicroPdf417` říká knihovně, aby použila kompaktní verzi PDF417, což je ideální pro malé štítky a mobilní obrazovky.

## Krok 3: Jak nastavit rozměry čárového kódu v C#

Doladění šířky modulu (X‑rozměr) řídí vizuální hustotu čárového kódu. Menší hodnota dává ostřejší obrázek, větší hodnota usnadňuje skenování z větší vzdálenosti.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Proč nastavit rozměry**: Bez úpravy X‑rozměru může výchozí hodnota vytvořit čárový kód, který vypadá rozmazaně při vykreslení na vysokém DPI. Hodnota 2 pixely je dobrá rovnováha pro většinu skenování na obrazovce.

## Krok 4: Výběr počtu sloupců – řízení šířky čárového kódu

Micro PDF417 umožňuje od 1 do 4 sloupců. Více sloupců data horizontálně komprimuje a snižuje celkovou šířku obrázku.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Hraniční případ*: Pokud požádáte o 5 sloupců, knihovna vyhodí `ArgumentOutOfRangeException`. Vždy se držte dokumentovaného rozsahu.

## Krok 5: Jak vygenerovat PNG čárového kódu – uložení obrázku

Nyní můžete exportovat vygenerovaný čárový kód do PNG souboru. PNG zachovává bezztrátovou kvalitu, což je nezbytné pro spolehlivé skenování.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Po spuštění programu uvidíte zprávu v konzoli potvrzující umístění souboru. Výsledný `MicroPdf417.png` vypadá takto:

![Screenshot showing a generated micro PDF417 barcode created with C#](micro-pdf417-example.png "Generated micro PDF417 barcode")

*Alternativní text obrázku*: **micro PDF417 barcode generated in C#** – ukazuje finální výstup po aplikaci rozměrů a nastavení sloupců.

## Krok 6: Spusťte a ověřte výstup

1. Sestavte projekt: `dotnet build`.
2. Spusťte: `dotnet run`.
3. Otevřete `MicroPdf417.png` na ploše a naskenujte jej pomocí mobilní aplikace pro čtení čárových kódů.

Měli byste vidět dekódovaný text **„Sample text“**. Pokud skener hlásí chybu, zkontrolujte X‑rozměr a počet sloupců – extrémní hodnoty mohou učinit čárový kód příliš hustým pro některá zařízení.

## Běžné varianty a řešení problémů

| Situace | Úprava |
|-----------|------------|
| **Potřeba většího čárového kódu pro nízké rozlišení tiskáren** | Zvyšte `XDimension.Pixels` na 3 nebo 4. |
| **Chcete vyšší čárový kód bez změny šířky** | Nastavte `generator.Parameters.Barcode.Pdf417.Rows` (rozsah řádků 3‑90). |
| **Generování více čárových kódů ve smyčce** | Znovu použijte stejnou instanci `BarcodeGenerator` a před každým `Save` změňte pouze `CodeText`. |
| **Ukládání jako JPEG místo PNG** | Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. |
| **Běh na .NET Framework 4.7** | Stejný kód funguje; stačí odkazovat na odpovídající `Aspose.BarCode.dll`. |

## Kompletní zdrojový kód (spustitelný)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Očekávaný výstup** – PNG soubor o rozměrech 200 × 100 pixelů obsahující ostrý Micro PDF417 čárový kód, který dekóduje „Sample text“.

## Závěr

Nyní víte, jak **vytvořit mikro PDF417 čárový kód** v C#, **nastavit rozměry čárového kódu** a **vygenerovat PNG obrázek** čárového kódu. Kompletní příklad demonstruje každý potřebný krok – od instalace knihovny po uložení finálního souboru – takže můžete generování čárových kódů přímo začlenit do svých aplikací.

Dále prozkoumejte související témata, jako je **vytváření QR kódů s Aspose.BarCode**, **přizpůsobení barev** nebo **vkládání čárových kódů do PDF dokumentů**. Všechna tato témata staví na stejných základech `BarcodeGenerator`, které jsou zde popsány.

Nebojte se experimentovat s různými řetězci dat, počty sloupců a hodnotami X‑rozměru, aby vyhovovaly vašemu konkrétnímu skenovacímu prostředí. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to create Aztec barcode with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}