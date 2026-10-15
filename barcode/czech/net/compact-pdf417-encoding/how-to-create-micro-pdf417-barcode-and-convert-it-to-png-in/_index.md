---
category: general
date: 2026-10-12
description: Naučte se vytvářet mikro PDF417 čárový kód a převádět čárový kód do PNG
  pomocí C#. Průvodce krok za krokem s kompletním kódem a tipy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: cs
lastmod: 2026-10-12
og_description: Vytvořte mikro PDF417 čárový kód a převěďte jej do PNG pomocí C#.
  Postupujte podle tohoto kompletního návodu a vytvořte jak standardní, tak GS1 verzi.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Vytvořte mikro PDF417 čárový kód a převeďte jej do PNG – C# tutoriál
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Jak vytvořit mikro PDF417 čárový kód a převést jej do PNG v C#
url: /cs/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit mikro PDF417 čárový kód a převést jej do PNG v C#

Pokud potřebujete **vytvořit mikro PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám přesně ukáže, jak na to. Uvidíte kompletní, spustitelný příklad, který generuje jak standardní Micro PDF417 čárový kód, tak i verzi splňující GS1, a poté **převede čárový kód do PNG** pro následné použití, například tisk nebo zobrazení na webu.

Generování čárového kódu je více než jen volání jediné metody — výběr správné velikosti modulu, počtu sloupců a formátu kódování určuje spolehlivost skenování. Na konci tohoto průvodce pochopíte, proč je každé nastavení důležité a jak jej upravit pro své vlastní projekty.

## Požadavky

| Požadavek | Důvod |
|-------------|--------|
| .NET 6.0 SDK nebo novější | Poskytuje runtime pro C# konzolovou aplikaci |
| Visual Studio 2022 (nebo jakékoli C# IDE) | Usnadňuje úpravy a ladění |
| **Aspose.BarCode for .NET** NuGet balíček | Dodává třídy `BarcodeGenerator`, `EncodeTypes` a `BarCodeImageFormat` |
| Oprávnění zápisu do výstupní složky | Vyžadováno pro volání `Save`, která vytváří PNG soubory |

Balíček Aspose.BarCode můžete přidat pomocí CLI:

```bash
dotnet add package Aspose.BarCode
```

## Krok 1: Nastavení minimálního konzolového projektu

Vytvořte nový konzolový projekt a odkažte na knihovnu čárových kódů. Následující soubor `Program.cs` obsahuje veškerý potřebný kód; žádné externí soubory nejsou vyžadovány.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Proč je každý řádek důležitý

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – První vytváří běžný Micro PDF417 čárový kód, zatímco druhý dodržuje standardy GS1 a vkládá identifikátory aplikací (AI). Vyberte podle toho, zda váš následný systém očekává data GS1.
* **`XDimension.Pixels = 2`** – Řídí šířku modulu. Menší hodnoty vytvářejí hustší obrázek, ale mohou být nečitelné na skenerech s nízkým rozlišením. Dva pixely jsou bezpečná výchozí hodnota pro většinu tiskáren štítků.
* **`Pdf417.Columns = 4`** – Micro PDF417 umožňuje omezit počet sloupců, čímž se snižuje celková šířka. Čtyři sloupce udržují čárový kód kompaktní, aniž by se snížila kapacita dat pro krátké payloady.
* **`BarCodeImageFormat.Png`** – PNG zachovává bezztrátovou kvalitu, což je klíčové pro čitelnost čárového kódu. Proto **převádíme čárový kód do PNG** místo JPEG.

## Krok 2: Spusťte program a ověřte výstup

1. Sestavte projekt: `dotnet build`.
2. Spusťte: `dotnet run`.

Měli byste vidět zprávy v konzoli podobné těmto:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Otevřete vygenerované PNG soubory v libovolném prohlížeči obrázků. Oba obrázky zobrazují ostrý, vysokokontrastní čárový kód připravený ke skenování.

### Očekávaný vizuální výsledek

| Typ čárového kódu | Vzhled |
|--------------|------------|
| **Micro PDF417** | Malý obdélníkový vzor se 4 sloupci, čitelný většinou 2‑D skenerů. |
| **GS1 Micro PDF417** | Stejná velikost, ale kóduje GS1 AI; skener, který rozumí GS1, vrátí GTIN a sériové číslo. |

Pokud skener nedokáže obrázek přečíst, zkuste zvýšit `XDimension.Pixels` na **3** nebo **4**, nebo snížit počet sloupců pro standardní Micro PDF417.

## Časté úskalí a jak se jim vyhnout

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Rozmazaný čárový kód po tisku | Nastavení tiskárny s nízkým DPI | Exportujte PNG s 300 dpi nebo vyšším, nebo nechte ovladač tiskárny provést škálování. |
| Skener vrací “invalid data” | Chybějící nebo špatně formátovaný GS1 AI | Ujistěte se, že každý AI je uzavřen v závorkách a odpovídá specifikaci GS1 (např. `(01)` pro GTIN‑14). |
| Soubor obrázku nebyl vytvořen | Výstupní složka nemá oprávnění k zápisu | Spusťte program s vyššími právy nebo zvolte složku jako `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Čárový kód je příliš velký pro štítek | Výchozí počet sloupců je příliš vysoký | Snižte `Pdf417.Columns` (např. na **3**) nebo zvětšete `XDimension`, aby se celková velikost zmenšila. |

## Rozšíření příkladu

* **Různé formáty obrázků** – Nahraďte `BarCodeImageFormat.Png` za `Jpeg` nebo `Bmp`, pokud to váš workflow vyžaduje. PNG zůstává nejlepší volbou pro bezztrátovou kvalitu.
* **Dynamická data** – Předávejte uživatelský vstup nebo hodnoty z databáze do konstruktoru `BarcodeGenerator` pro tvorbu čárových kódů za běhu.
* **Dávkové generování** – Zabalte logiku tvorby do smyčky, která načítá řádky z CSV souboru a ukládá každý čárový kód pod jedinečným názvem souboru.

## Závěr

Nyní víte, jak **vytvořit mikro PDF417 čárový kód** v C# a **převést čárový kód do PNG** pro standardní i GS1‑kompatibilní scénáře. Kompletní, spustitelný kód demonstruje klíčová nastavení — X dimenzi, počet sloupců a typ kódování — aby bylo možné řešení přizpůsobit libovolnému .NET projektu, který potřebuje kompaktní, vysoce kvalitní 2‑D čárové kódy.

*Další kroky*: prozkoumejte další symbologie podporované Aspose.BarCode (např. QR, DataMatrix), experimentujte s různými hodnotami `XDimension` pro tisk ve vysokém rozlišení, nebo integrujte vygenerované PNG do webového API, které poskytuje čárové kódy na vyžádání.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit mikro pdf417 čárový kód v C# a uložit jej jako PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Vytvořit PNG čárového kódu v C# – kompletní průvodce GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Generovat Micro PDF417 čárový kód v C# – kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}