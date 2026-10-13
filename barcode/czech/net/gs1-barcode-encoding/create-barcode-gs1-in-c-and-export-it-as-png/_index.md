---
category: general
date: 2026-09-29
description: Vytvořte GS1 čárový kód v C# a generujte PNG obrázky čárových kódů pomocí
  BarcodeGenerator. Postupujte podle krok‑za‑krokem průvodce pro efektivní export
  obrázku čárového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: cs
lastmod: 2026-09-29
og_description: Vytvořte GS1 čárový kód v C# a generujte PNG soubory čárových kódů
  pomocí BarcodeGenerator. Postupujte podle tohoto kompletního průvodce pro rychlý
  export obrázku čárového kódu.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Vytvořte GS1 čárový kód v C# – exportujte do PNG během několika minut
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Vytvořte GS1 čárový kód v C# a exportujte jej jako PNG
url: /cs/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte čárový kód GS1 v C# a exportujte jej jako PNG

Pokud potřebujete **vytvořit čárový kód GS1** v .NET aplikaci, tento návod vám přesně ukáže, jak na to. Uvidíte stručné řešení, které generuje PNG obrázek čárového kódu a exportuje obrázek čárového kódu na disk, vše pomocí třídy Aspose.BarCode `BarcodeGenerator`.

Generování čárového kódu GS1 je běžnou požadavkem pro systémy inventarizace, přepravy a pokladny. Na konci tohoto tutoriálu budete schopni napsat malý program v C#, který vytvoří GS1‑kompatibilní MicroPDF417 čárový kód a uloží jej jako vysoce kvalitní PNG soubor.

## Požadavky

* **.NET 6** (nebo jakákoli novější verze .NET) nainstalována.
* **Visual Studio 2022** nebo jakékoli IDE podporující C#.
* NuGet balíček **Aspose.BarCode for .NET** (`Aspose.BarCode`) – poskytuje API `BarcodeGenerator` použité v příkladech.
* Základní znalost syntaxe C#.

> **Tip:** Používejte bezplatnou komunitní edici Aspose.BarCode při experimentování; plná verze odstraňuje všechny evaluační vodoznaky.

## Krok 1 – Vytvořte čárový kód GS1 pomocí BarcodeGenerator

Prvním krokem je vytvořit instanci `BarcodeGenerator` pro formát *MicroPDF417* a předat mu řetězec s GS1 daty. Identifikátory aplikací GS1 (AI) jsou uzavřeny v závorkách, např. `(01)` pro GTIN‑14 a `(21)` pro sériové číslo.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Proč je to důležité:**  
`EncodeTypes.MicroPdf417` automaticky zachází s vstupem jako s GS1 daty, pokud řetězec obsahuje platné AI. Tím se zajišťuje, že vygenerovaný čárový kód splňuje specifikaci GS1 bez další konfigurace.

## Krok 2 – Nastavte rozměry čárového kódu pro optimální velikost

Vizuální velikost čárového kódu je řízena jeho **X‑dimenzí** (šířka jednoho modulu). Úprava `XDimension.Pixels` vám umožní jemně doladit konečnou velikost obrázku při zachování čitelnosti.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Jak generovat PNG čárového kódu** – X‑dimenze neovlivňuje zakódovaná data; pouze mění fyzické rozměry vygenerovaného obrázku. Pokud potřebujete větší čárový kód pro tisk ve vysokém rozlišení, zvýšte tuto hodnotu (např. `3` nebo `4`).

## Krok 3 – Generujte PNG čárového kódu a exportujte obrázek čárového kódu

Nyní můžete vykreslit čárový kód a zapsat jej do PNG souboru. Metoda `Save` přijímá cílovou cestu a požadovaný formát obrázku.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Co se děje pod kapotou:**  
`BarcodeGenerator.Save` rasterizuje čárový kód do bitmapy, použije X‑dimenzi nastavenou dříve a zakóduje bitmapu jako PNG soubor. Výsledný soubor může být použit přímo ve webových stránkách, tištěn na štítcích nebo vložen do PDF.

## Kompletní ukázka zdrojového kódu

Níže je kompletní, samostatná konzolová aplikace, kterou můžete zkopírovat, vložit a spustit. Ukazuje **jak generovat PNG soubory čárových kódů**, **exportovat obrázek čárového kódu** a obsahuje základní ošetření chyb.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Očekávaný výstup

Po spuštění programu byste měli vidět:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Otevření PNG souboru zobrazí čistý **GS1 MicroPDF417** čárový kód, který kóduje GTIN‑14 `12345678901234` a sériové číslo `ABC123`. Naskenováním libovolným GS1‑kompatibilním skenerem získáte původní řetězec dat.

## Časté úskalí a osvědčené postupy

| Issue | Why it happens | How to avoid it |
|-------|----------------|-----------------|
| **Nesprávné formátování AI** | Chybějící závorky nebo špatné pořadí způsobí, že čárový kód není GS1. | Vždy uzavřete každý AI do závorek, např. `(01)`. |
| **Příliš malá X‑dimenze** | Čárový kód se stane nečitelným na zařízeních s nízkým rozlišením. | Udržujte `XDimension.Pixels` ≥ 2 pro většinu tiskáren; pro výstup s vysokým DPI zvýšte hodnotu. |
| **Výstupní složka neexistuje** | `Save` vyvolá `DirectoryNotFoundException`. | Použijte `Directory.CreateDirectory` před voláním `Save`. |
| **Použití nesprávného EncodeType** | Některé typy (např. `Code128`) nepodporují GS1 data přímo. | Vyberte `EncodeTypes.MicroPdf417` nebo jakýkoli GS1‑kompatibilní typ. |
| **Chybějící odkaz na NuGet** | Chyby při kompilaci jako `The type or namespace name 'Aspose' could not be found`. | Nainstalujte balíček `Aspose.BarCode` přes NuGet. |

## Rozšíření příkladu

* **Různé formáty obrázků** – Nahraďte `BarCodeImageFormat.Png` za `Jpeg`, `Gif` nebo `Bmp`, pokud potřebujete jiný formát.
* **Výstup ve vyšším rozlišení** – Nastavte `generator.Parameters.ImageResolution.DpiX` a `DpiY` před uložením.
* **Vkládání do PDF** – Použijte `Aspose.Pdf` k umístění PNG do PDF faktury nebo štítku.

## Závěr

Nyní víte, jak **vytvořit čárový kód GS1** v C# pomocí Aspose.BarCode `BarcodeGenerator`, **generovat PNG čárového kódu** a **exportovat obrázek čárového kódu** do souborového systému. Tento návod pokryl každý krok – od inicializace generátoru s GS1 daty, úpravy X‑dimenze až po uložení finálního PNG souboru – a zároveň se zabýval běžnými chybami a nabídl nápady na rozšíření.

Neváhejte experimentovat s dalšími GS1 identifikátory aplikací, různými symbologiemi čárových kódů nebo obrázky ve vyšším rozlišení. Jakmile si osvojíte tyto základy, generování kompatibilních čárových kódů pro inventář, přepravu nebo maloobchod se stane běžnou součástí vaší .NET sady nástrojů.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto návodu. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Vytvořte obrázky GS1 čárových kódů v C# – Jak rychle generovat čárový kód v C#](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Vytvořte PNG čárového kódu v C# – krok za krokem průvodce](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Vytvořte obrázek čárového kódu v C# – kompletní programovací průvodce](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}