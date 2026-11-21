---
category: general
date: 2026-11-20
description: Naučte se generovat PDF417 čárový kód v C# pomocí BarcodeGeneratoru.
  Tento krok‑za‑krokem průvodce zahrnuje nastavení X‑rozměru, nastavení sloupců a
  export do PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: cs
lastmod: 2026-11-20
og_description: Rychle vygenerujte čárový kód PDF417 v C#. Postupujte podle tohoto
  průvodce a nastavte rozměry, sloupce a exportujte čárový kód jako PNG obrázek.
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: Vytvořte čárový kód PDF417 v C# – kompletní krok‑za‑krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: Jak generovat čárový kód PDF417 v C# pomocí BarcodeGenerator
url: /cs/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak generovat PDF417 čárový kód v C# s BarcodeGenerator

Pokud potřebujete **generovat PDF417 čárový kód** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který nastaví X‑Dimension, vybere počet sloupců a uloží výsledek jako PNG obrázek.

Generování PDF417 čárového kódu je běžné, když musíte zakódovat velké množství dat—například řidičský průkaz, palubní vstupenku nebo inventární záznam—do kompaktního, strojově čitelného obrázku. V tomto tutoriálu používáme třídu **BarcodeGenerator** z knihovny Aspose.BarCode, ale koncepty platí pro jakoukoli knihovnu, která podporuje PDF417.

Na konci tohoto článku budete schopni:

* Inicializovat `BarcodeGenerator` pro kódování PDF417.  
* Upravit velikost modulu pomocí **set XDimension pixels**.  
* Ovládat rozvržení pomocí **configure PDF417 columns**.  
* **Uložit čárový kód jako PNG** pro použití na webových stránkách, v mobilních aplikacích nebo tištěném materiálu.  

> **Požadavky**  
> * .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+).  
> * Odkaz na NuGet balíček **Aspose.BarCode** (`Install-Package Aspose.BarCode`).  
> * Základní znalost C# a Visual Studio (nebo libovolného IDE, které preferujete).

---

## Jak generovat PDF417 čárový kód v C#

Jádrem řešení je krátký čtyřkrokový proces. Každý krok je zabalen do samostatné metody, takže můžete logiku znovu použít ve větších projektech.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Proč jsou tyto čtyři kroky důležité

1. **Inicializovat generátor** – `BarcodeGenerator` spojuje zvolenou symbologii (`EncodeTypes.Pdf417`) s daty, která chcete zakódovat. Bez tohoto objektu nemáte přístup k dalším nastavením.  
2. **Nastavit X‑Dimension** – PDF417 je složen z malých obdélníkových modulů. Změna `XDimension.Pixels` vám umožní řídit vizuální hustotu čárového kódu, což je klíčové pro čitelnost na nízkých rozlišeních displejů nebo tiskáren.  
3. **Konfigurovat sloupce** – PDF417 může uspořádat své kódové slova v proměnném počtu sloupců. Méně sloupců vytváří vyšší čárový kód, zatímco více sloupců jej zplošťuje. Přizpůsobte to prostoru, kam bude obrázek umístěn.  
4. **Uložit jako PNG** – PNG je bezztrátový formát, který zachovává ostré hrany potřebné pro přesné skenování. Můžete také zvolit JPEG nebo BMP, ale PNG je nejbezpečnější výchozí volba.

---

## Nastavení rozměrů čárového kódu (X‑Dimension)

Krok **set XDimension pixels** přímo ovlivňuje, jak skenery interpretují čárový kód. Pokud je modul příliš malý, kamery nízké kvality mohou jednotlivé pruhy minout; pokud je příliš velký, čárový kód může být zbytečně velký.

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**Best practice:** Otestujte vygenerovaný obrázek v zamýšlené velikosti tisku. Pro vysoce hustý tisk (300 dpi a více) funguje hodnota `1` nebo `2` dobře. Pro zobrazení na obrazovce při 96 dpi dává `2`–`3` jasný vizuál.

---

## Nastavení sloupců PDF417

Krok **configure PDF417 columns** vám umožní rozhodnout o tvaru čárového kódu.

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### Kdy změnit počet sloupců

| Sloupce | Výsledný tvar | Typický případ použití |
|---------|----------------|------------------------|
| 1–3     | Vysoký, úzký   | Štítky s omezenou šířkou |
| 4–9     | Vyvážený       | Obecné skenování |
| 10+    | Široký, nízký  | Velké značení nebo webová grafika |

Pokud váš datový payload překročí výchozí kapacitu, knihovna automaticky přidá další řádky, ale stále můžete ovlivnit poměr stran úpravou počtu sloupců.

---

## Export čárového kódu do PNG

Uložení čárového kódu jako PNG obrázku je jednoduché:

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Proč PNG?**  
* Bezztrátová komprese zachovává ostré hrany potřebné pro čtečky čárových kódů.  
* PNG podporuje průhlednost, což může být užitečné, pokud později překryjete čárový kód barevným pozadím.

Pokud potřebujete jiný formát, nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Svg`—API provede konverzi automaticky.

---

## Časté problémy a řešení

| Problém | Pravděpodobná příčina | Řešení |
|-------|--------------|-----|
| Čárový kód je rozmazaný | X‑Dimension je příliš malý pro výstupní rozlišení | Zvyšte `XDimension.Pixels` na 3 nebo 4. |
| Skener nedokáže kód přečíst | Unicode znaky nejsou podporovány zvoleným fontem | Ujistěte se, že font knihovny podporuje znaky, nebo je nahraďte ASCII ekvivalenty. |
| Výstupní soubor nebyl vytvořen | Neplatná cesta nebo chybějící oprávnění k zápisu | Použijte absolutní cestu a ověřte přístup k zápisu do složky. |
| Příliš mnoho řádků, čárový kód je vysoký | Počet sloupců je příliš nízký pro délku dat | Zvyšte `Pdf417.Columns` na vyšší číslo (např. 6). |

---

## Kompletní funkční příklad – shrnutí

Níže je **kompletní program**, který můžete zkopírovat a vložit do nového konzolového projektu. Žádný další kód není potřeba kromě `using` direktiv a balíčku Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**Očekávaný výstup:** Soubor pojmenovaný `Pdf417Basic.png` obsahující čistý PDF417 čárový kód, který kóduje řetězec `Åspóse.Barcóde©`. Po otevření by měl obrázek zobrazovat řadu naskládaných obdélníkových pruhů s vyšší hustotou na levé straně (kvůli třísloupcovému rozložení).

---

## Závěr

Nyní víte, jak **generovat PDF417 čárový kód** v C# pomocí třídy `BarcodeGenerator`. Tutoriál pokryl inicializaci generátoru, **set XDimension pixels**, **configure PDF417 columns** a **save barcode as PNG**—základní kroky pro jakýkoli produkčně připravený workflow čárových kódů.

Odtud můžete:

* Experimentovat s různými `EncodeTypes` (např. QR, Code128).  
* Přidat úrovně korekce chyb pomocí `generator.Parameters.Barcode.Pdf417.ErrorLevel`.  
* Vykreslit čárový kód přímo do `MemoryStream` pro webová API.  

Neváhejte upravit kód podle svého projektu a sdílet své výsledky v komentářích nebo na Stack Overflow s tagem `#pdf417`. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Generovat PDF417 čárový kód jako PNG v C# – krok za krokem guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [Jak generovat PDF417 čárový kód v C# – krok za krokem guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [Jak generovat PDF417 čárový kód v C# s vlastními rozměry](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}