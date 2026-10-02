---
category: general
date: 2026-09-07
description: Naučte se generovat mikro PDF417 čárový kód v C# s kompletním příkladem
  kódu, laděním X‑dimenze, konfigurací sloupců a exportem do PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- C# barcode generator
- MicroPdf417 encode type
- barcode X-dimension
- barcode column configuration
- save barcode as PNG
language: cs
lastmod: 2026-09-07
og_description: Vygenerujte mikro PDF417 čárový kód v C# pomocí tohoto stručného tutoriálu.
  Obsahuje nastavení X‑rozměru, výběr sloupců a export do PNG pro okamžité použití.
og_image_alt: Screenshot showing a generated micro pdf417 barcode saved as a PNG file
og_title: Generujte mikro PDF417 čárový kód v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to generate micro pdf417 barcode in C# with a complete code
    example, X‑dimension tuning, column configuration, and PNG export.
  headline: How to generate micro pdf417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- image export
title: Jak vygenerovat mikro PDF417 čárový kód v C# – krok za krokem
url: /cs/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat mikro pdf417 čárový kód v C# – krok za krokem průvodce

Pokud potřebujete **vygenerovat mikro pdf417 čárový kód** v aplikaci .NET, tento tutoriál vám ukáže připravené řešení. Uvidíte, jak nastavit X‑dimenzi čárového kódu, zvolit počet sloupců a exportovat výsledek jako PNG obrázek – vše pomocí knihovny Aspose.BarCode C#.

Generování mikro pdf417 čárového kódu je běžné, když musíte zakódovat kompaktní data pro mobilní vstupenky, štítky zásob nebo zabezpečené dokumenty. Na konci tohoto průvodce budete mít znovupoužitelný úryvek kódu, který můžete vložit do libovolného C# projektu.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 nebo novější (kód funguje také s .NET Framework 4.7+)
* Visual Studio 2022 (nebo jakékoli IDE podporující C#)
* NuGet balíček **Aspose.BarCode for .NET** (verze 23.9 nebo novější)

Balíček můžete nainstalovat z příkazové řádky:

```bash
dotnet add package Aspose.BarCode
```

Žádné další závislosti nejsou vyžadovány.

## Krok 1: Vytvoření generátoru čárového kódu pro MicroPdf417

Prvním úkolem je vytvořit instanci `BarcodeGenerator` s hodnotou výčtu `EncodeTypes.MicroPdf417` a textem, který chcete zakódovat. Text může obsahovat Unicode znaky, které knihovna zpracuje automaticky.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for MicroPdf417 with the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "Åspóse.Barcóde©"
);
```

**Proč je to důležité:**  
`EncodeTypes.MicroPdf417` říká knihovně, aby použila kompaktní symbologii MicroPdf417, která ukládá více dat v menším prostoru než plná PDF417. Zadání textu při konstrukci zajišťuje, že generátor přesně ví, co má zakódovat.

## Krok 2: Úprava X‑dimenze pro vyšší rozlišení

X‑dimenze (šířka modulu) určuje, kolik pixelů zabírá každý sloupec čárového kódu. Hodnota **2 pixely** poskytuje vysoce rozlišený čárový kód, který zůstává čitelný na většině skenerů.

```csharp
// Step 2: Set the X‑dimension (module width) to 2 pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tip:**  
Pokud cílíte na nízké rozlišení displejů nebo tiskáren, zvyšte hodnotu na 3‑4 pixely, abyste předešli rozmazaným hranám. Naopak pro vysoce husté štítky můžete snížit na 1 pixel, ale výsledek otestujte se svým skenerem.

## Krok 3: Výběr počtu sloupců

MicroPdf417 umožňuje **1 až 4 sloupce**. Více sloupců vede k kratšímu čárovému kódu, ale snižuje kapacitu korekce chyb. Pro většinu scénářů s vstupenkami poskytují **4 sloupce** kompaktní tvar při zachování robustnosti.

```csharp
// Step 3: Choose the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Proč byste to mohli změnit:**  
Pokud je zakódovaný text delší než výchozí kapacita, zvyšte počet sloupců, abyste předešli chybám přetečení. Snižte jej, když potřebujete úzký čárový kód pro omezený prostor.

## Krok 4: Definování výstupní složky a názvu souboru

Vyberte složku, do které bude vygenerovaný obrázek uložen. Použití `Path.Combine` zaručuje správné oddělovače cest napříč Windows, Linuxem a macOS.

```csharp
using System.IO;

// Step 4: Define the output folder and file name
string outputFolder = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "Barcodes"
);
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");
```

**Ošetření okrajových případů:**  
Pokud je cesta ke složce neplatná nebo aplikace nemá oprávnění k zápisu, `Directory.CreateDirectory` vyvolá výjimku. Pro produkční kód obalte logiku ukládání do bloku `try/catch`.

## Krok 5: Uložení čárového kódu jako PNG obrázek

Nakonec exportujte čárový kód do souboru PNG. PNG zachovává ostré hrany a podporuje průhlednost, což je ideální pro vykreslování v UI nebo tisk.

```csharp
using Aspose.BarCode;

// Step 5: Save the generated barcode as a PNG image
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Po spuštění najdete **MicroPdf417.png** ve složce `Barcodes` na ploše. Otevřením souboru uvidíte jasný, vysoce rozlišený mikro pdf417 čárový kód připravený ke skenování.

### Očekávaný výstup

Uložený obrázek vypadá podobně jako ilustrace níže (skutečný vzor závisí na zakódovaném textu).

![Vygenerovaný mikro pdf417 čárový kód uložený jako PNG](https://example.com/placeholder-micro-pdf417.png "Snímek obrazovky vygenerovaného mikro pdf417 čárového kódu uloženého jako PNG soubor")

*Alt text:* vygenerovat mikro pdf417 čárový kód uložený jako PNG obrázek

## Kompletní, spustitelný příklad

Spojením všech kroků získáte jediný, samostatný program:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create generator with MicroPdf417 and Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // 2️⃣ Set X‑dimension for high‑resolution output
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Choose 4 columns to keep the barcode compact
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 4️⃣ Prepare output folder on the desktop
        string outputFolder = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "Barcodes"
        );
        Directory.CreateDirectory(outputFolder);
        string outputPath = Path.Combine(outputFolder, "MicroPdf417.png");

        // 5️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

Spusťte program (`dotnet run` ze složky projektu) a ověřte, že se PNG soubor objeví podle očekávání.

## Časté otázky a řešení problémů

| Otázka | Odpověď |
|----------|--------|
| **Mohu generovat čárový kód jako JPEG místo PNG?** | Ano. Nahraďte `BarCodeImageFormat.Png` za `BarCodeImageFormat.Jpeg`. JPEG komprimuje obrázek, ale může zavést artefakty, které ovlivní čitelnost skenerem. |
| **Co když text obsahuje znaky, které MicroPdf417 nepodporuje?** | MicroPdf417 podporuje celý rozsah Unicode. Pokud obdržíte `ArgumentException`, ověřte, že řetězec je správně zakódován (např. vyhněte se párovým surrogate znakům, které překračují kapacitu symbolu). |
| **Jak změnit barvu popředí?** | Použijte `generator.Parameters.Barcode.BarColor = Color.Blue;` před voláním `Save`. |
| **Existuje způsob, jak vložit čárový kód přímo do PDF?** | Ano. Použijte `generator.Save(stream, BarCodeImageFormat.Pdf);` nebo přidejte obrázek do PDF dokumentu pomocí PDF knihovny, jako je Aspose.PDF. |
| **Můj skener nedokáže čárový kód přečíst – co mám zkontrolovat?** | Ujistěte se, že X‑dimenze je alespoň 2 pixely pro většinu skenerů, ověřte, že počet sloupců odpovídá rozsahu podporovanému skenerem, a potvrďte, že tištěná velikost splňuje minimální velikost modulu skeneru (obvykle 0,5 mm). |

## Závěr

Nyní víte, jak **vygenerovat mikro pdf417 čárový kód** v C# od začátku až do konce. Průvodce pokrýval vytvoření `BarcodeGenerator`, nastavení X‑dimenze a počtu sloupců, přípravu výstupní cesty a uložení výsledku jako PNG. Úpravou sekundárních nastavení – jako je barva čáry, formát obrázku nebo úroveň korekce chyb – můžete čárový kód přizpůsobit jakékoli aplikaci, od mobilních vstupenek po štítky zásob.

### Další kroky

* Experimentujte s hodnotami **X‑dimenze čárového kódu**, abyste našli rovnováhu mezi velikostí a čitelností.  
* Prozkoumejte další symbologie (např. `EncodeTypes.Pdf417`, `EncodeTypes.QR`) pomocí stejného vzoru generátoru.  
* Integrovejte vygenerovaný PNG do PDF zprávy pomocí **Aspose.PDF** nebo jej vložte přímo do WinForms/WPF UI.  

Šťastné programování a užijte si flexibilitu, kterou knihovna Aspose.BarCode přináší do generování čárových kódů v C#!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Návod na generátor čárových kódů: Jak vygenerovat PDF417 čárový kód v C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [Jak uložit čárový kód v C# – Generovat PDF417 čárové kódy](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Jak vygenerovat PDF417 čárový kód – Kompletní programovací průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}