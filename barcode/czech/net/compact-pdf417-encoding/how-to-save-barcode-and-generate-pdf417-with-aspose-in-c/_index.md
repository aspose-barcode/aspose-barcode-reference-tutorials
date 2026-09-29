---
category: general
date: 2026-09-29
description: Jak uložit čárový kód pomocí Aspose.BarCode v C# a naučit se generovat
  PDF417 s makro metadaty. Postupujte podle průvodce krok po kroku.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: cs
lastmod: 2026-09-29
og_description: Jak uložit čárový kód pomocí Aspose.BarCode v C# je jednoduché. Tento
  tutoriál ukazuje, jak generovat PDF417 s makro metadata a nastavit všechny požadované
  parametry.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Jak uložit čárový kód pomocí Aspose – průvodce generováním PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Jak uložit čárový kód a generovat PDF417 pomocí Aspose v C#
url: /cs/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak uložit čárový kód a generovat PDF417 pomocí Aspose v C#

Ukládání čárového kódu pomocí Aspose.BarCode v C# je běžná potřeba, když potřebujete vložit data do souboru s obrázkem. Tento průvodce vás provede kompletním procesem generování čárového kódu PDF417 s makro‑metadata a uložením výsledku jako PNG obrázku. Na konci budete vědět **jak generovat PDF417**, **jak nastavit PDF417** možnosti a, co je nejdůležitější, **jak uložit čárový kód** programově.

Uvidíte kompletní, spustitelný příklad, který pokrývá každý krok – od přidání NuGet balíčku Aspose.BarCode po konfiguraci makro polí jako ID souboru, počet segmentů a kontrolní součet. Není potřeba žádná externí dokumentace; kód lze zkopírovat do nového konzolového projektu a okamžitě spustit. Tutorial předpokládá, že máte nainstalovaný Visual Studio 2022 (nebo novější) a .NET 6.0.

## Požadavky

- .NET 6.0 SDK (nebo jakákoli verze .NET podporovaná Aspose.BarCode 23.11+)
- Visual Studio 2022, VS Code nebo váš preferovaný C# IDE
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Základní znalost syntaxe C# a konzolových aplikací

> **Tip:** Použijte bezplatnou vývojářskou evaluační licenci od Aspose, pokud ještě nemáte komerční licenci. Evaluační licence funguje bez změn kódu.

## Jak uložit čárový kód – kompletní příklad

Následující kód vytvoří čárový kód **Macro PDF417**, vyplní všechna makro pole a uloží obrázek jako `ExtPDF417Meta.png`. Všechny potřebné `using` direktivy jsou zahrnuty, takže můžete vložit úryvek přímo do `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Proč je každý krok důležitý

1. **Vytvoření generátoru** – Konstruktor `BarcodeGenerator` přijímá typ čárového kódu (`EncodeTypes.MacroPdf417`) a data k zakódování. Macro PDF417 je speciální varianta, která přenáší informace o přenosu souboru, proto později vyplňujeme makro pole.
2. **Nastavení vzhledu** – `XDimension.Pixels` řídí šířku úzké čáry; úpravou této hodnoty měníte celkovou velikost obrázku, aniž byste ovlivnili integritu dat. `Pdf417.Columns` určuje rozložení matice čárového kódu.
3. **Makro metadata** – Tyto vlastnosti (`MacroPdf417FileID`, `MacroPdf417SegmentID` atd.) jsou nezbytné, když potřebujete rozdělit velký soubor na více segmentů čárového kódu. Správné nastavení zajišťuje, že skener dokáže rekonstruovat původní soubor.
4. **Ukládání obrázku** – Metoda `Save` zapíše vygenerovaný čárový kód na disk. Můžete zvolit libovolný podporovaný formát (`Png`, `Jpeg`, `Bmp` atd.). Tento řádek demonstruje přesnou operaci **jak uložit čárový kód**, která byla požadována.

> **Často kladená otázka:** *Co když potřebuji jiný formát obrázku?*  
> Změňte `BarCodeImageFormat.Png` na `BarCodeImageFormat.Jpeg` (nebo jakoukoli jinou podporovanou hodnotu enum) a podle toho upravte příponu souboru.

## Jak generovat PDF417 s makro metadata

Pokud potřebujete pouze běžný PDF417 (bez makro dat), můžete sekci s makrem přeskočit a použít základní generátor:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Výše uvedený kód rychle ilustruje **jak generovat PDF417**. Všimněte si, že enum `EncodeTypes.Pdf417` vybírá ne‑makro verzi.

## Jak nastavit PDF417 – pokročilé možnosti

Aspose.BarCode poskytuje mnoho parametrů specifických pro PDF417. Zde je několik, které můžete potřebovat:

| Vlastnost | Popis | Typické hodnoty |
|----------|-------|-----------------|
| `Pdf417.Columns` | Počet sloupců na řádek | 1‑30 (default 3) |
| `Pdf417.Rows` | Počet řádků (automaticky vypočítáno, pokud 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Úroveň opravy chyb (0‑8) | 2‑4 for balanced size/robustness |
| `Pdf417.RowsPerStrip` | Řádky na proužek pro velké čárové kódy | 0 (auto) |
| `Pdf417.Pdf417MacroFileID` | Identifikátor souboru při použití makra | Any 32‑bit integer |

Nastavení těchto hodnot následuje stejný vzor, jaký je ukázán v **kroku 2** hlavního příkladu. Upravte je před voláním `Save`.

## Očekávaný výstup

Spuštěním kompletního programu se vytvoří `ExtPDF417Meta.png` v pracovním adresáři spustitelného souboru. Obrázek obsahuje vysoce rozlišený PDF417 čárový kód se všemi vloženými makro poli. Naskenováním obrázku skenerem podporujícím PDF417 (nebo mobilní aplikací) získáte původní datový řetězec `"Åspóse.Barcóde©"` spolu s makro metadaty (ID souboru, ID segmentu atd.).

![Čárový kód uložený jako PNG – příklad jak uložit čárový kód](ExtPDF417Meta.png "Jak uložit čárový kód jako PNG s makro PDF417 metadaty")

*Text alternativy obrázku:* **jak uložit čárový kód jako PNG s PDF417 makro metadaty** (odpovídá hlavnímu klíčovému slovu).

## Závěr

V tomto tutoriálu jste se naučili **jak uložit čárový kód** pomocí Aspose.BarCode, **jak generovat PDF417**, **jak nastavit PDF417** parametry a **jak generovat čárový kód s Aspose** pro běžné i makro‑povolené scénáře.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárový kód s Aspose – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Jak generovat PDF417 čárový kód jako obrázek v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Jak generovat čárový kód v C# s Aspose.BarCode a přidat metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}