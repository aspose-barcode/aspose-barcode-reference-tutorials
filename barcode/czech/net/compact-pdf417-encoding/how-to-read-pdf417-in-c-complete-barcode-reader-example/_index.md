---
category: general
date: 2026-07-21
description: Jak číst čárový kód PDF417 v C# pomocí stručného příkladu čtečky čárových
  kódů. Rychle se naučte, jak načíst čárový kód z obrázku pomocí krok‑za‑krokem kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: cs
lastmod: 2026-07-21
og_description: Jak číst čárový kód PDF417 v C# s praktickým příkladem. Objevte, jak
  číst čárový kód z obrázku a okamžitě integrovat příklad čtečky čárových kódů v C#.
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: Jak číst PDF417 v C# – Kompletní průvodce čtečkou čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: Jak číst PDF417 v C# – Kompletní příklad čtečky čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 v C# – Kompletní příklad čtečky čárových kódů

Už jste se někdy ptali, **jak číst PDF417** v .NET projektu, aniž byste museli prohledávat nekonečné dokumentace? Nejste v tom sami. Ať už skenujete řidičské průkazy, palubní vstupenky nebo vlastní inventární štítky, spolehlivé získání těchto dat je reálná potřeba.  

V tomto průvodci projdeme **c# barcode reader example**, který načte veškerá metadata Macro PDF417 z jediného souboru s obrázkem. Na konci budete mít připravenou konzolovou aplikaci, která **reads barcode from image** a vypíše všechna rozšířená pole, která můžete potřebovat.

## Co budete potřebovat

- .NET 6.0 SDK nebo novější (můžete také cílit na .NET Framework 4.7+ – kód funguje stejně)
- Visual Studio 2022, VS Code nebo jakýkoli editor C#, který máte rádi
- NuGet balíček **Aspose.BarCode for .NET** (třída `BarCodeReader` pochází z této knihovny)
- Soubor s obrázkem, který obsahuje Macro PDF417 čárový kód (pro ukázku použijeme `ExtPDF417Meta.png`)

> **Tip:** Pokud nemáte po ruce vzor PDF417, Aspose poskytuje několik testovacích obrázků ve svém GitHub repozitáři – stačí si jeden stáhnout a vložit do složky projektu.

## Krok 1: Instalace knihovny pro čárové kódy

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá třídy `BarCodeReader`, `DecodeType` a vlastnost `Extended`, kterou později použijeme. Žádná další konfigurace není potřeba; knihovna funguje out‑of‑the‑box pro většinu formátů obrázků (PNG, JPEG, BMP, atd.).

## Krok 2: Vytvoření minimální konzolové aplikace

Vytvořte nový konzolový projekt, pokud jste tak ještě neučinili:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Nahraďte vygenerovaný soubor `Program.cs` kódem níže. Všimněte si, že každá část je okomentována, takže můžete sledovat logiku i když jste v oblasti čtení čárových kódů nováčkem.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### Proč to funguje

- **`DecodeType.MacroPdf417`** říká čtečce, aby očekávala rozšířený formát Macro PDF417, který nese další metadata (ID souboru, počet segmentů, časová razítka, atd.).
- Objekt **`Extended.Pdf417`** je naplněn pouze pro Macro PDF417 čárové kódy, takže přístup k těmto vlastnostem je bezpečný po volání `ReadBarCodes()`.
- Použití **`using`** bloku zaručuje uvolnění souborových handle, čímž se předejde problémům se zamčením souboru ve Windows.

## Krok 3: Spuštění aplikace

Zkompilujte a spusťte:

```bash
dotnet run
```

Pokud obrázek obsahuje platný Macro PDF417 čárový kód, měli byste vidět výstup podobný tomuto:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

Pokud se nic neobjeví, zkontrolujte, zda je cesta k obrázku správná a zda je čárový kód skutečně variantou Macro PDF417. Běžný PDF417 (bez makro rozšíření) se stále dekóduje, ale vlastnosti `Extended` budou prázdné.

## Řešení okrajových případů

### Více čárových kódů na jednom obrázku

Někdy jeden sken obsahuje více než jeden PDF417 segment (např. více‑stránkový dokument rozložený do několika symbolů). Smyčka `foreach` již enumeruje *všechny* detekované čárové kódy, takže není potřeba další logika – stačí shromáždit segmenty a případně je později znovu složit.

### Chybějící rozšířená data

Ne každý PDF417 nese makro informace. V takovém případě bude `result.Extended.Pdf417` vytvořen, ale jeho pole budou mít výchozí hodnoty (nula, prázdný řetězec nebo `false`). Můžete to ošetřit takto:

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### Tipy pro výkon

- **Dávkové zpracování:** Pokud máte složku s obrázky, zabalte vytvoření `BarCodeReader` do smyčky, která opakovaně používá stejnou instanci pomocí `barcodeReader.SetImage(imagePath)`. Tím snížíte režii alokací.
- **Paralelizace:** Pro velké objemy zvažte `Parallel.ForEach` nad seznamem souborů, ale pamatujte, že čtečka Aspose je thread‑safe pouze tehdy, když každý vláken používá vlastní instanci `BarCodeReader`.

## Kompletní výpis zdrojového kódu (připravený ke kopírování)

Níže je celý program znovu, připravený vložit do `Program.cs`. Nepotřebujete žádné další soubory kromě obrázku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                var macro = result.Extended.Pdf417;

                Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## Shrnutí: Jak rychle číst PDF417 v C#

- Nainstalujte **Aspose.BarCode** přes NuGet.
- Nastavte `BarCodeReader` na váš obrázek s `DecodeType.MacroPdf417`.
- Procházejte `ReadBarCodes()` a získávejte jak základní, tak rozšířená pole.
- Ošetřete chybějící makro data a zvažte optimalizace pro hromadné skeny.

## Další kroky a související témata

- **Read barcode from image** pomocí jiných formátů (QR, DataMatrix) – stačí zaměnit enum `DecodeType`.
- **Encode PDF417** pomocí `BarCodeGenerator`, pokud potřebujete generovat čárové kódy programově.
- Prozkoumejte **úrovně opravy chyb** a jak ovlivňují spolehlivost skenování.
- Integrujte tuto logiku do ASP.NET Core API a zpřístupněte čtení čárových kódů jako webovou službu.

Nebojte se experimentovat: změňte obrázek, pohrávejte si s příznakem `DecodeType` nebo uložte makro data do databáze. Základní vzor zůstává stejný a nyní máte solidní **c# barcode reader example** ve svém arzenálu.

Šťastné programování a ať jsou vaše skeny vždy čisté!


## Co byste se měli naučit dál?


Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create barcode quiet zone for Code 16K using Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}