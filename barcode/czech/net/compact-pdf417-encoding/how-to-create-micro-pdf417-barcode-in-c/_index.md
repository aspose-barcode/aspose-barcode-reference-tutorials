---
category: general
date: 2026-11-14
description: Vytvořte mikro PDF417 čárový kód v C# s Aspose.BarCode – krok za krokem
  průvodce zahrnující nastavení generátoru, X‑dimenzi, sloupce a export do PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: cs
lastmod: 2026-11-14
og_description: Vytvořte mikro PDF417 čárový kód v C# pomocí Aspose.BarCode. Naučte
  se nakonfigurovat generátor, nastavit XDimension, vybrat sloupce a exportovat jako
  PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Vytvořte mikro PDF417 čárový kód v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Jak vytvořit mikro PDF417 čárový kód v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit micro PDF417 čárový kód v C#

Pokud potřebujete rychle **vytvořit micro PDF417 čárový kód**, tento průvodce vám ukáže kompletní, připravené řešení. Ukážeme si, jak vytvořit generátor čárových kódů, nastavit X‑dimenzi, vybrat počet sloupců a nakonec uložit výsledek jako PNG obrázek – vše pomocí knihovny Aspose.BarCode pro .NET.

Generování micro PDF417 čárového kódu nevyžaduje složitý build pipeline. Na konci tohoto tutoriálu budete mít jediný soubor C#, který vytvoří vysoce kvalitní obrázek čárového kódu, který můžete vložit do reportů, štítků nebo mobilních aplikací.

## Požadavky

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.7+).  
* Vývojové prostředí, např. Visual Studio 2022, VS Code nebo Rider.  
* Licence Aspose.BarCode pro .NET (nebo bezplatný evaluační klíč). Můžete ji získat na [Aspose website](https://purchase.aspose.com/barcode/net).  

> **Tip:** Pokud používáte evaluační verzi, vygenerovaný PNG bude obsahovat malý vodoznak „Evaluation“. Licencovaná verze jej automaticky odstraní.

## Krok 1: Nastavení projektu

Vytvořte nový konzolový projekt a přidejte NuGet balíček Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Příkaz `dotnet add package` stáhne závislosti **Aspose.BarCode C# example**, takže nemusíte ručně spravovat DLL soubory.

## Krok 2: Napište kompletní kód

Nahraďte automaticky vygenerovaný soubor `Program.cs` následujícím kódem. Ukazuje, jak **vytvořit micro pdf417 čárový kód** od začátku až do konce.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Proč je každý řádek důležitý

* **BarcodeGenerator constructor** – Vytvoří **micro pdf417 generátor čárových kódů** s textem, který chcete zakódovat.  
* **XDimension.Pixels** – Řídí šířku modulu; nastavení na `2` pixely vytvoří hustý, vysoké‑rozlišení čárový kód vhodný pro většinu skenerů.  
* **Pdf417.Columns** – MicroPDF417 podporuje pouze 1‑4 sloupce. Výběrem `4` snížíte výšku čárového kódu, což je užitečné, když máte omezený vertikální prostor.  
* **Save method** – Uloží čárový kód do PNG souboru. PNG je bezztrátový formát, který zajišťuje, že skener přečte přesně vygenerovaný vzor.

## Krok 3: Sestavení a spuštění

Zkompilujte a spusťte program:

```bash
dotnet run
```

Měli byste vidět výstup v konzoli:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Soubor s názvem **MicroPdf417.png** se objeví ve složce projektu. Otevřete jej v libovolném prohlížeči obrázků; uvidíte ostrý micro PDF417 čárový kód, který kóduje řetězec `"Åspóse.Barcóde©"`.

![Vygenerovaný příklad micro PDF417 čárového kódu](MicroPdf417.png "Vygenerovaný příklad micro PDF417 čárového kódu"){.center-image width=400 alt="Vygenerovaný obrázek micro PDF417 čárového kódu"}

*Obrázek výše je výsledkem kódu uvedeného v kroku 2.*

## Krok 4: Běžné varianty a okrajové případy

| Situace | Jak upravit kód |
|-----------|----------------------|
| **Různá délka dat** | MicroPDF417 dokáže zakódovat až 1 200 znaků. Stačí změnit druhý argument u `BarcodeGenerator`. |
| **Vyšší rozlišení** | Zvyšte `XDimension.Pixels` na `3` nebo `4`. Větší moduly zlepšují čitelnost na nízkorozlišovacích skenerech, ale zvětší velikost obrázku. |
| **Vlastní barvy** | Po vytvoření generátoru nastavte `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` a `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Ukládání do jiných formátů** | Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Bmp` nebo `Gif` podle vašich požadavků. |
| **Vložení do PDF** | Použijte `generator.Save(\"barcode.pdf\", BarCodeImageFormat.Pdf);` a poté sloučte PDF s dalšími dokumenty pomocí Aspose.PDF. |

> **Pozor:** Nastavení `XDimension.Pixels` pod `1` vyvolá `ArgumentOutOfRangeException`. Vždy jej ponechte na `1` nebo vyšší.

## Krok 5: Ověření čárového kódu

Pro zajištění, že čárový kód se načte správně:

1. Otevřete PNG v prohlížeči obrázků.  
2. Použijte libovolnou aplikaci pro skenování čárových kódů na smartphonu, která podporuje PDF417 (většina aplikací „QR‑code scanner“ jej zahrnuje).  
3. Naskenujte obrázek; aplikace by měla zobrazit původní text `"Åspóse.Barcóde©"`.

Pokud skenování selže, zkontrolujte nastavení **X‑dimenze** a **sloupců** – příliš malá šířka modulu nebo nepodporovaný počet sloupců může způsobit nečitelnost vzoru.

## Závěr

Nyní víte, jak **vytvořit micro pdf417 čárový kód** v C# pomocí Aspose.BarCode. Tutoriál pokryl:

* Instanciaci **micro pdf417 generátoru čárových kódů**.  
* **Nastavení XDimension pixelů** pro kontrolu šířky modulu.  
* **Definování sloupců čárového kódu** pro úpravu tvaru.  
* **Uložení čárového kódu jako PNG** pro bezztrátový výstup obrázku.  

Odtud můžete zkoumat další funkce, jako je přizpůsobení barev, vložení čárového kódu do PDF nebo generování čárových kódů za běhu v ASP.NET Core webových API. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořit PNG čárového kódu v C# – kompletní průvodce GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Jak vytvořit macro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Vytvořit PDF417 čárový kód v C# pomocí Aspose.BarCode – krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}