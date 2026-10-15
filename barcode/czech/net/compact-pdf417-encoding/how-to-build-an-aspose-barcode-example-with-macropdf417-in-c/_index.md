---
category: general
date: 2026-10-12
description: Naučte se, jak vytvořit příklad čárového kódu Aspose v C#, který generuje
  kód MacroPdf417 s kompletními metadaty a načte jej zpět pomocí BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: cs
lastmod: 2026-10-12
og_description: Příklad čárového kódu Aspose v C#, který ukazuje, jak vygenerovat
  čárový kód MacroPdf417 s vloženými metadaty a jak jej načíst zpět pomocí BarCodeReaderu.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Vytvořte příklad čárového kódu Aspose s MacroPdf417 v C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Jak vytvořit příklad čárového kódu Aspose s MacroPdf417 v C#
url: /cs/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit příklad Aspose barcode s MacroPdf417 v C#

Pokud potřebujete **aspose barcode example**, který vytvoří kód MacroPdf417 a přečte jeho vložená metadata, tento průvodce vám ukáže kompletní postup. Uvidíte, jak nakonfigurovat generátor, vložit informace na úrovni souboru, uložit obrázek a poté dekódovat stejná data pomocí `BarCodeReader`.

Tutoriál pokrývá vše, co potřebujete vědět pro **C# barcode generation** s Aspose.BarCode, včetně běžných úskalí a tipů pro práci s velkými ID souborů nebo vlastními časovými razítky.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější (kód funguje s .NET Core a .NET Framework)
* Visual Studio 2022 nebo jakékoli IDE podporující C#
* Aktivní licence Aspose.BarCode (bezplatná zkušební verze funguje pro vývoj)
* NuGet balíček `Aspose.BarCode` nainstalovaný ve vašem projektu

Tyto předpoklady zajišťují, že příklad běží bez další konfigurace.

## Krok 1: Nastavení projektu s příkladem Aspose barcode

Vytvořte novou konzolovou aplikaci a přidejte knihovnu Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Balíček `Aspose.BarCode` poskytuje `BarcodeGenerator`, `BarCodeReader` a všechny typy potřebné pro práci s MacroPdf417.

### Proč je tento krok důležitý
Přidání NuGet balíčku vyřeší výčty `EncodeTypes`, `DecodeType` a `BarCodeImageFormat`, které jsou použity později. Bez balíčku by kompilátor nepoznal tyto symboly a příklad by selhal při sestavování.

## Krok 2: Vytvoření generátoru kódu MacroPdf417

Otevřete **Program.cs** a nahraďte šablonový kód následujícím blokem. Tento blok vytvoří `BarcodeGenerator` nakonfigurovaný pro symbologii MacroPdf417 a nastaví základní parametry vzhledu.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Vysvětlení klíčových vlastností

| Vlastnost | Účel | Typický rozsah / poznámky |
|----------|------|---------------------------|
| `MacroPdf417FileID` | Unikátní identifikátor celého souboru | Musí být ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Index aktuálního segmentu | Začíná na 0 |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů v souboru | Musí být ≥ SegmentID |
| `MacroPdf417FileName` | Lidsky čitelný název souboru | Až 255 znaků |
| `MacroPdf417Checksum` | CCITT‑16 kontrolní součet původního souboru | Vypočítá se externím nástrojem, pokud je potřeba |
| `MacroPdf417FileSize` | Velikost původního souboru v bajtech | Užitečné pro validaci |
| `MacroPdf417TimeStamp` | Datum/čas vytvoření souboru | Použijte UTC pro konzistenci |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Volitelná směrovací informace | Jakýkoli řetězec až 255 znaků |
| `MacroPdf417Terminator` | Označuje poslední segment | Použijte `Set` pro poslední segment |

Tyto pole tvoří **barcode metadata**, která může čtečka později extrahovat.

## Krok 3: Dekódování kódu a zobrazení metadat

Po uložení obrázku program pokračuje otevřením souboru pomocí `BarCodeReader`. Přidejte následující kód do metody `Main`, po předchozím bloku `using`:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Proč je zpětné čtení důležité
`BarCodeReader` ověřuje, že vložená metadata jsou správně zakódována. Pokud některá vlastnost chybí nebo je mimo rozsah, čtečka vrátí `null` pro toto pole, což vám umožní elegantně zpracovat chyby.

## Krok 4: Spuštění a ověření výstupu

Spusťte program:

```bash
dotnet run
```

Měli byste vidět výstup v konzoli podobný:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Pokud hodnoty odpovídají těm, které jste nastavili ve Krok 2, **aspose barcode example** funguje podle očekávání.

## Okrajové případy a tipy na osvědčené postupy

| Situace | Na co si dát pozor | Doporučené řešení |
|-----------|-------------------|----------------------|
| **FileID překračuje 32‑bitový rozsah** | Aspose vyhodí `ArgumentOutOfRangeException`. | Udržujte ID ≤ 2 147 483 647 nebo rozdělte soubor do více bloků MacroPdf417. |
| **Časové razítko v místním čase** | Čtečky v jiné časové zóně mohou hodnotu špatně interpretovat. | Ukládejte časová razítka v UTC (`DateTime.UtcNow`) a při zobrazení je případně převedete. |
| **Velká velikost souboru** | `MacroPdf417FileSize` je typu `int`; hodnoty > 2 GB přetečou. | Použijte vlastní pole nebo rozdělte soubor na menší segmenty. |
| **Chybějící segment** | Pokud `SegmentID` není sekvenční, rekonstrukce selže. | Ověřte pořadí segmentů před kódováním nebo použijte nastavení korekce chyb. |
| **Nesprávný formát obrázku** | Ukládání jako BMP může dramaticky zvětšit velikost. | PNG je dobrá výchozí volba; JPEG lze použít, pokud akceptujete ztrátovou kompresi. |

**Pro tip:** Když generujete mnoho kódů najednou, znovu použijte jednu instanci `BarcodeGenerator` a měňte jen `EncodeTypes` a zdrojový text. Tím snížíte alokace paměti a urychlíte zpracování.

## Související témata, která můžete prozkoumat dál

* **Other macro symbologies** – Aspose také podporuje MacroPdf417 s úrovněmi korekce chyb.
* **Embedding barcodes in PDFs** – Kombinujte `Aspose.PDF` s generátorem kódů pro vytvoření tisknutelných dokumentů.
* **ASP.NET Core integration** – Poskytněte generované kódy přímo z webového API.
* **Scanning via mobile devices** – Použijte SDK `Aspose.BarCode.Cloud` pro multiplatformní dekódování.

Tyto navazující témata přirozeně rozšiřují **aspose barcode example** a prohlubují vaši odbornost v **C# barcode generation**.

## Závěr

Nyní máte plně funkční **aspose barcode example**, který vytváří kód MacroPdf417, vkládá bohatá **barcode metadata**, ukládá obrázek a čte data zpět pomocí `BarCodeReader`. Dodržením výše uvedených kroků můžete kód přizpůsobit různým ID souborů, časovým razítkům nebo dokonce jiným typům kódů podporovaným společností Aspose.

Neváhejte experimentovat s dalšími poli metadat, změnit formát obrázku nebo integrovat generátor do větší aplikace. Šťastné programování!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}