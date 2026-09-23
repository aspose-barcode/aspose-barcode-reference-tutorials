---
category: general
date: 2026-08-09
description: Jak číst PDF417 v C# pomocí BarCodeReaderu. Naučte se číst soubory PNG
  s čárovými kódy, zpracovávat více čárových kódů a extrahovat rozšířené metadata.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: cs
lastmod: 2026-08-09
og_description: Jak číst PDF417 v C# s Aspose.BarCode. Tento tutoriál vám ukáže, jak
  číst soubory PNG s čárovým kódem, zpracovávat více čárových kódů v jednom obrázku
  a získat rozšířená metadata PDF417.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Jak číst PDF417 v C# – návod na čtečku čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Jak číst PDF417 v C# – kompletní průvodce čtečkou čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 v C# – kompletní průvodce čtečkou čárových kódů

Pokud potřebujete **jak číst PDF417** v .NET aplikaci, tento průvodce vám poskytne připravené řešení. Uvidíte, jak načíst PNG s čárovým kódem, zpracovat několik čárových kódů ve stejném obrázku a získat rozšířená pole PDF417, která mnoho skenerů skrývá.

Čtení čárových kódů PDF417 je běžné v logistice, prodeji vstupenek a správě dokumentů. Na konci tohoto tutoriálu budete umět dekódovat obrázek Macro PDF417, zobrazit každý výsledek a použít doplňující informace (ID souboru, počet segmentů, časová razítka atd.) ve své vlastní obchodní logice.

## Prerequisites

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakékoli C# IDE
- **Aspose.BarCode for .NET** (bezplatná zkušební verze nebo licencovaný NuGet balíček)
- PNG obrázek, který obsahuje čárový kód Macro PDF417 (vzorek souboru se jmenuje `ExtPDF417Meta.png`)

> **Tip:** Nainstalujte knihovnu pomocí NuGet konzole:  
> `dotnet add package Aspose.BarCode`

## How to read PDF417 with BarCodeReader in C#

Jádrem řešení je třída `BarCodeReader`. Přijímá cestu k obrázku a výčtový typ `DecodeType`, který říká enginu, jakou symbologii hledat.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Why this works

- `DecodeType.MacroPdf417` říká čtečce, aby hledala variantu Macro PDF417, která ukládá dodatečná pole, která vidíte v kroku 4.
- `using` blok automaticky uvolní čtečku, čímž uvolní souborové handle.
- `ReadBarCodes()` vrací **všechny** čárové kódy, které odpovídají požadovanému typu, což splňuje požadavek *číst více čárových kódů* i když obrázek obsahuje jen jeden.

Spuštěním programu se vytiskne výstup podobný:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Using C# barcode reader to read multiple barcodes

Pokud obrázek obsahuje několik symbolů Macro PDF417 (například naskenovanou stránku s dávkou vstupenek), stejný `foreach` cyklus zpracuje každý z nich. Není potřeba žádný další kód; čtečka interně agreguje výsledky.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Common pitfalls

- **Formát obrázku:** Čtečka podporuje PNG, JPEG, BMP a TIFF. Pokud zkusíte formát, který nedokáže dekódovat, získáte prázdnou kolekci. Proto tutoriál zdůrazňuje *číst čárový kód PNG*.
- **Rozlišení:** Nízké rozlišení obrázků (< 300 dpi) může způsobit chybějící segmenty. Pokud je to možné, zvyšte rozlišení nebo požádejte o sken v lepší kvalitě.
- **Makro příznak:** Zapomenutí `DecodeType.MacroPdf417` omezuje engine na obyčejný PDF417 a zahazuje rozšířená data. Vždy specifikujte makro typ, když potřebujete pole *číst rozšířené čárové kódy*.

## Reading barcode PNG files – best practices

Práce s PNG soubory je jednoduchá, protože formát zachovává bezztrátová pixelová data. Zde je rychlý kontrolní seznam:

1. Ověřte, že soubor existuje, než vytvoříte čtečku.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Používejte `Image.FromFile` pouze pokud potřebujete předzpracovat (otočit, oříznout). `BarCodeReader` může soubor otevřít přímo, což zabraňuje dalšímu alokování paměti.
3. Pokud PNG obsahuje průhlednost, čtečka stále funguje, protože čárový kód je vykreslen na neprůhledných pixelech.

## Accessing extended PDF417 metadata

Objekt `Extended.Pdf417` zpřístupňuje každé volitelné pole definované specifikací PDF417. Můžete tato pole mapovat na doménový model, uložit je do databáze nebo použít pro validaci.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Naplnění modelu:



## What Should You Learn Next?

Následující tutoriály pokrývají úzce související témata, která navazují na techniky předvedené v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Read DataMatrix barcode C# – Generate DataMatrix Mode (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}