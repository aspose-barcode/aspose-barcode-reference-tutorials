---
category: general
date: 2026-07-24
description: Vytvořte čárový kód PDF417 v C# pomocí Aspose.BarCode. Naučte se během
  několika minut, jak vytvořit PDF417 čárový kód v C# s kompaktním režimem.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: cs
lastmod: 2026-07-24
og_description: Rychle generujte čárový kód PDF417 v C# pomocí Aspose.BarCode. Tento
  tutoriál vám ukáže, jak vytvořit PDF417 čárový kód v C# v kompaktním režimu, včetně
  nastavení, kódu a ověření.
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: Generování PDF417 čárového kódu v C# – Rychlý průvodce
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Generovat čárový kód PDF417 v C# – Vytvořit čárový kód PDF417 v C#
url: /cs/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření PDF417 čárového kódu v C# – Kompletní programový průvodce

Už jste se někdy zamýšleli, jak **vytvořit PDF417 čárový kód** v aplikaci C# bez nekonečného prohledávání fór? Nejste v tom sami. Ať už budujete systém pro vstupenky, zabezpečenou identifikační kartu nebo jen potřebujete rychlý způsob, jak vložit data do tisknutelného formátu, ovládnutí formátu PDF417 vám může ušetřit hodiny pokus‑a‑chyba.

V tomto návodu projdeme **kompletní, připravený příklad**, který vám ukáže, jak **vytvořit PDF417 čárový kód v C#** pomocí populární knihovny Aspose.BarCode. Pokryjeme vše od instalace NuGet balíčku až po ladění kompaktního režimu, takže můžete kód zkopírovat‑vložit a okamžitě vidět výsledek.

## Co se naučíte

- Jak nastavit knihovnu Aspose.BarCode v .NET projektu.  
- Přesné C# příkazy potřebné k **vytvoření PDF417 čárového kódu** s vlastním textem, velikostí modulu a počtem sloupců.  
- Proč má přepínání možnosti *Compact* (Truncate) význam u hustých dat.  
- Jak uložit čárový kód jako PNG a ověřit výstup.  

Předchozí zkušenost s čárovými kódy není nutná; stačí základní znalost C# a Visual Studia (nebo libovolného IDE, které preferujete). Na konci budete mít znovupoužitelnou metodu, kterou můžete vložit do libovolného projektu vyžadujícího obrázek PDF417.

## Předpoklady

| Požadavek | Proč je důležitý |
|-----------|-------------------|
| .NET 6.0 nebo novější (nebo .NET Framework 4.7+) | Aspose.BarCode podporuje obojí; novější runtime poskytuje lepší výkon. |
| Visual Studio 2022 (nebo VS Code s C# rozšířeními) | Poskytuje IntelliSense a snadné ladění. |
| Internetové připojení (pro první obnovení NuGet) | Knihovna se stahuje z NuGet.org. |
| Základní znalost C# | Potřebná pro pochopení struktur tříd a volání metod. |

Pokud už máte vše připravené, skvěle – pojďme na to.

## Instalace NuGet balíčku Aspose.BarCode

Otevřete složku projektu v terminálu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Nebo ve Visual Studiu klikněte pravým tlačítkem na **Dependencies → Manage NuGet Packages**, vyhledejte *Aspose.BarCode* a klikněte na **Install**. Tento jediný řádek přinese všechny typy, které budeme používat, včetně `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat`.

> **Tip:** Po instalaci vyčistěte a znovu sestavte řešení, aby byl assembly správně referencován.

## Vytvoření PDF417 čárového kódu – nastavení a závislosti

Nejprve potřebujeme `using` blok, který načte potřebné jmenné prostory.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Tyto jmenné prostory nám poskytují přístup ke generátoru a výčtu typů čárových kódů. Nic složitého – jen tři řádky a můžeme začít vytvářet čárový kód.

## Vytvoření PDF417 čárového kódu v C# – krok za krokem

Níže je **samostatný konzolový program**, který vytvoří kompaktní PDF417 čárový kód ze řetězce `"Åspóse.Barcóde©"` a uloží jej jako `CompactPdf417.png`. Klidně nahraďte text čímkoli potřebujete; generátor zvládne Unicode znaky bez dalších úprav.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Proč je každý krok důležitý

1. **Definice dat** – PDF417 může uložit až ~1850 znaků, ale pro ukázku držíme text krátký. Podpora Unicode znamená, že tyto diakritické znaky neporuší žádný proces.  
2. **Konstrukce generátoru** – Hodnota výčtu `EncodeTypes.Pdf417` říká Aspose, jakou symbologii použít; výměna za `EncodeTypes.QR` by vám vygenerovala QR kód.  
3. **X‑dimenze** – Řídí šířku každého modulu (malých čtverečků tvořících čárový kód). Hodnota `2` pixelů dává ostrý obrázek, který je stále čitelný při tisku 300 dpi.  
4. **Možnosti PDF417** – `Columns` ovlivňuje poměr stran čárového kódu; méně sloupců vede k vyššímu obrázku, což může být užitečné pro účtenky. `Truncate` (také nazývaný *Compact mode*) odstraňuje výplň start/stop vzoru, čímž snižuje velikost souboru bez ztráty integrity dat.  
5. **Cesta k výstupu** – Použití `Environment.CurrentDirectory` zajišťuje, že obrázek skončí vedle spustitelného souboru, což usnadňuje jeho nalezení během vývoje.  
6. **Ukládání** – `BarCodeImageFormat.Png` poskytuje bezztrátovou kvalitu, ideální pro další zpracování nebo vkládání do PDF.

Spusťte program (`dotnet run` nebo stiskněte **F5** ve Visual Studiu). Po několika sekundách by se měla v konzoli objevit zpráva potvrzující umístění souboru a PNG se objeví ve složce projektu.

![Příklad generování PDF417 čárového kódu](generated-pdf417.png)

*Alt text obrázku: příklad generování pdf417 čárového kódu – PNG obrázek kompaktního PDF417 čárového kódu vytvořeného v C#.*

## Konfigurace kompaktního režimu – c# barcode generator pdf417 Options

Pokud potřebujete větší čárový kód (například pro skenování z větší vzdálenosti), upravte vlastnosti `Columns` a `Rows`. Zde je rychlý úryvek, který ukazuje alternativní konfigurace:

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **Často kladená otázka:** *Způsobí vypnutí Truncate problémy se stávajícími skenery?*  
> Obvykle ne. Většina moderních skenerů rozumí jak plné, tak kompaktní verzi PDF417. Pokud však cílíte na starší hardware, nechte `Truncate` nastavený na `false`.

## Uložení a ověření – jak vygenerovat pdf417 barcode Output

Po uložení můžete PNG otevřít v libovolném prohlížeči obrázků. Pro dvojitou kontrolu, že čárový kód kóduje požadovaná data, použijte `BarCodeReader` od Aspose:



## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak vygenerovat Aztec čárový kód s vlastním poměrem stran pomocí Aspose.BarCode pro .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java barcode library – Přidat čárový kód do PDF pomocí Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}