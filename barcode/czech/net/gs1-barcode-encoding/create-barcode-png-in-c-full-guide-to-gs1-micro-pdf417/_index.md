---
category: general
date: 2026-08-12
description: Vytvořte PNG čárový kód v C# rychle s Aspose.BarCode. Naučte se, jak
  generovat PDF417 čárový kód v C# a ovládněte používání generátoru čárových kódů
  v jednom tutoriálu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: cs
lastmod: 2026-08-12
og_description: Vytvořte čárový kód PNG v C# pomocí Aspose.BarCode. Tento tutoriál
  vám ukáže, jak v C# generovat čárový kód PDF417 a efektivně používat generátor čárových
  kódů.
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: Vytvořte čárový kód PNG v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Vytvořte PNG čárový kód v C# – kompletní průvodce GS1 Micro PDF417
url: /cs/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření barcode PNG v C# – kompletní průvodce GS1 Micro PDF417

Pokud potřebujete **create barcode PNG** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Naučíte se generovat PDF417 čárový kód v C# a seznámíte se s **barcode generator usage** vzory, které fungují v produkci.

Generování obrázku čárového kódu je běžnou požadavkem pro inventární systémy, přepravní štítky a platformy pro vstupenky. Na konci tohoto tutoriálu budete mít samostatný konzolový program, který zapíše PNG soubor obsahující GS1 Micro PDF417 čárový kód, připravený pro další zpracování.

## Požadavky

* .NET 6.0 SDK nebo novější nainstalováno (kód také funguje s .NET Framework 4.7.2+).
* Aktuální verze NuGet balíčku **Aspose.BarCode for .NET**. Nainstalujte jej pomocí  
  `dotnet add package Aspose.BarCode`.
* Základní znalost C# konzolových projektů.
* Oprávnění k zápisu do složky, kam bude PNG uloženo.

Tyto požadavky udržují příklad lehký a zároveň odrážejí reálné nastavení.

## Krok 1: Nastavení C# projektu

Vytvořte nový konzolový projekt a přidejte odkaz na Aspose.BarCode:

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

`dotnet` CLI vytvoří soubor `Program.cs` a obnoví NuGet balíček. Tento krok je nezbytný pro **barcode generator usage**, protože knihovna obsahuje třídu `BarcodeGenerator`, kterou použijeme.

## Krok 2: Napište kompletní kód pro generování čárového kódu

Nahraďte obsah souboru `Program.cs` následujícím kódem. Obsahuje každý řádek, který potřebujete k **create barcode PNG** od začátku až do konce.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### Proč je každý řádek důležitý

| Řádek | Důvod |
|------|--------|
| `EncodeTypes.Gs1MicroPdf417` | Vybere konkrétní variantu PDF417 požadovanou pro aplikace GS1. |
| Data string `"(01)12345678901231(10)ABC123"` | Ukazuje syntaxi GS1 AI pro GTIN (01) a číslo šarže (10). |
| `XDimension.Pixels = 2` | Řídí fyzickou velikost čárového kódu; běžná výchozí hodnota pro zobrazení na obrazovce. |
| `ImageResolution = 300` | Zvyšuje DPI, což zajišťuje, že PNG bude ostrý při tisku. |
| `BackgroundColor = Transparent` | Zpřístupňuje PNG pro překrytí v UI kompozici. |
| `Save(..., BarCodeImageFormat.Png)` | Uloží čárový kód jako PNG, což splňuje cíl **create barcode PNG**. |

## Krok 3: Spusťte program a ověřte výstup

Spusťte konzolovou aplikaci:

```bash
dotnet run
```

Měli byste vidět potvrzovací zprávu a najít soubor `output.png` ve složce projektu. Otevřením souboru se zobrazí GS1 Micro PDF417 čárový kód, který kóduje ukázková data.

![příklad vytvoření barcode PNG](barcode-example.png)

*Alt text: příklad vytvoření barcode PNG ukazující kód GS1 Micro PDF417.*

### Očekávaný vizuální výsledek

PNG obsahuje obdélníkový čárový kód s rovnoměrně rozmístěnými černými moduly. Skenováním pomocí GS1‑kompatibilního skeneru získáte řetězec `(01)12345678901231(10)ABC123`, což potvrzuje, že **generate PDF417 barcode C#** byl úspěšný.

## Krok 4: Prozkoumejte běžné varianty

### Změna symbologie

Pokud potřebujete běžný PDF417 místo mikro verze, nahraďte typ kódování:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### Úprava formátu obrázku

Aspose.BarCode podporuje mnoho formátů. Pro vytvoření JPEG místo toho:

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### Ukládání do streamu (užitečné pro webové API)

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

Tyto úryvky ukazují flexibilní **barcode generator usage** mimo základní scénář ukládání do souboru.

## Profesionální tipy a úskalí

* **Validate data length** – GS1 Micro PDF417 má maximální kapacitu dat; překročení vyvolá výjimku. Použijte `generator.Parameters.Barcode.IsValidData(data)` pro předběžnou kontrolu.
* **Avoid tiny XDimension values** – hodnoty pod 1 pixel mohou vytvořit nečitelné čárové kódy na zařízeních s nízkým rozlišením.
* **Set `QuietZone`** pokud vkládáte PNG do větší grafiky; výchozí tichá zóna zajišťuje, že skenery dokážou najít start/stop vzory.
* **Thread safety** – instance `BarcodeGenerator` nejsou thread‑safe. Vytvořte nový generátor pro každý požadavek ve webové službě.

## Závěr

Nyní víte, jak **create barcode PNG** soubory v C# pomocí Aspose.BarCode, jak **generate PDF417 barcode C#** s variantou GS1 Micro, a jaké jsou základní vzory pro efektivní **barcode generator usage**. Kompletní, spustitelný příklad můžete vložit do libovolného .NET projektu a můžete jej rozšířit o různé symbologie, formáty obrázků nebo výstupy do streamu.

### Co dál?

* Prozkoumejte **barcode reader integration** pro automatické ověřování vygenerovaných obrázků.  
* Experimentujte s **custom colors** a **logo embedding** pro čárové kódy šité na míru značce.  
* Prostudujte dokumentaci Aspose.BarCode pro pokročilá nastavení korekce chyb a generování více‑stránkových PDF417.

Šťastné programování a ať vaše aplikace mluví jazykem strojů s ostrými, spolehlivými barcode PNG!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak uložit PNG pomocí DataMatrix C40 s Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [Jak generovat čárový kód – Code 39 konfigurace s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}