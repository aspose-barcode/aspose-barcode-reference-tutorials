---
category: general
date: 2026-10-15
description: Jak rychle číst obrázky čárových kódů v C# pomocí BarCodeReader. Naučte
  se číst více čárových kódů a podívejte se na příklad čtečky čárových kódů v C#,
  který funguje s Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: cs
lastmod: 2026-10-15
og_description: Jak číst čárový kód v C# pomocí BarCodeReaderu. Tento tutoriál ukazuje
  kompletní příklad čtečky čárových kódů v C#, který zvládá více čárových kódů a extrahuje
  metadata Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Jak číst čárový kód v C# – krok za krokem příklad
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak číst obrázky čárových kódů v C# – kompletní příkladový návod
url: /cs/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst obrázky čárových kódů v C# – kompletní průvodce s příkladem

Pokud potřebujete **how to read barcode** data z obrázku v .NET aplikaci, tento průvodce vám poskytne připravené řešení. Uvidíte kompletní **c# barcode reader example**, který funguje se symboly Macro‑PDF417 a dokáže **read multiple barcodes** z jednoho obrázku.

Čtení čárových kódů je běžná potřeba pro inventární systémy, ověřování vstupenek a zpracování dokumentů. Na konci tohoto tutoriálu budete schopni:

* Inicializovat `BarCodeReader` pro libovolný podporovaný formát.  
* Získat základní informace, jako je typ kódu a dekódovaný text.  
* Získat specifická metadata Macro‑PDF417 (ID souboru, segment, kontrolní součet, …).  
* Zpracovat obrázky, které obsahují několik čárových kódů, bez dalšího kódu.

## Požadavky

Před začátkem se ujistěte, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný.  
* Vývojové prostředí (Visual Studio 2022, VS Code nebo Rider).  
* NuGet balíček **Aspose.BarCode for .NET** (`Aspose.BarCode`) – poskytuje třídu `BarCodeReader` použitou v příkladu.  
* Obrázkový soubor, který obsahuje čárový kód Macro‑PDF417 (např. `MacroPdf417.png`).  

Můžete nainstalovat NuGet balíček pomocí následujícího příkazu:

```bash
dotnet add package Aspose.BarCode
```

## Jak číst čárový kód pomocí BarCodeReader v C#

Jádro řešení spočívá ve čtyřech stručných krocích. Každý krok je zabalený do bloku `using`, aby se zajistilo včasné uvolnění neřízených prostředků.

### Krok 1: Inicializace `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Proč je to důležité:**  
`BarCodeReader` přijímá cestu k souboru a `DecodeType`. Zadání `DecodeType.MacroPdf417` říká knihovně, aby hledala pouze symboly Macro‑PDF417, což zvyšuje rychlost detekce a snižuje falešné poplachy.

### Krok 2: Přečíst všechny čárové kódy v obrázku

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Proč je to důležité:**  
Metoda `ReadBarCodes()` vrací pole, které může obsahovat jeden nebo více objektů `BarCodeResult`. Toto je místo, kde se projevuje schopnost **read multiple barcodes** – není potřeba samostatná smyčka pro každý možný čárový kód.

### Krok 3: Zobrazit základní podrobnosti čárového kódu

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Proč je to důležité:**  
`CodeTypeName` vám říká, která symbologie byla detekována (např. „MacroPDF417“), zatímco `CodeText` obsahuje dekódovanou hodnotu. Tato dvě pole jsou nejčastěji používaná v následné logice.

### Krok 4: Získat a zobrazit specifická metadata Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Proč je to důležité:**  
Macro‑PDF417 rozšiřuje běžný formát PDF417 o metadata na úrovni dokumentu. Přístup k vlastnosti `Extended.Pdf417` vám poskytne vše potřebné k rekonstrukci původního souboru, ověření integrity nebo směrování dat k správnému příjemci.

### Kompletní spustitelný program

Níže je samostatná konzolová aplikace, která spojuje všechny čtyři kroky. Zkopírujte kód do nového souboru `.cs`, upravte `imagePath` a spusťte `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Očekávaný výstup v konzoli

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Pokud obrázek obsahuje více než jeden symbol Macro‑PDF417, program vytiskne samostatný blok pro každý čárový kód, čímž demonstruje schopnost **read multiple barcodes** bez jakéhokoli dalšího kódu.

## Řešení běžných okrajových případů

| Situace | Co udělat | Důvod |
|-----------|------------|--------|
| **Soubor nenalezen** | Zabalte konstrukci `BarCodeReader` do bloku `try/catch (FileNotFoundException)` a zobrazte přátelskou zprávu. | Zabraňuje pádu aplikace a informuje uživatele o chybějícím souboru. |
| **Žádný čárový kód nebyl detekován** | Zkontrolujte `results.Length == 0` (jak je ukázáno v kompletním programu) a ošetřete to elegantně. | Poskytuje jasnou zpětnou vazbu, když obrázek neobsahuje žádnou podporovanou symbologii. |
| **Jiný typ čárového kódu** | Změňte `DecodeType.MacroPdf417` na `DecodeType.AllSupportedTypes` nebo jinou konkrétní hodnotu výčtu. | Umožňuje stejnému kódu pracovat s QR, Code128, DataMatrix atd., přičemž stále podporuje **read multiple barcodes**. |
| **Velké obrázky** | Nastavte `reader.AutoSize = true` nebo před předáním čtečce zmenšete obrázek. | Zlepšuje výkon a snižuje zatížení paměti CLR. |
| **Bezpečné použití v více vláknech** | Vytvořte samostatnou instanci `BarCodeReader` pro každé vlákno; třída není bezpečná pro více vláken. | Zabraňuje závodním podmínkám ve vícevláknových skenerech nebo webových službách. |

## Profesionální tipy pro produkční kód

* **Dispose early:** Příkaz `using` zajišťuje, že nativní prostředky (např. buffery obrázků) jsou uvolněny okamžitě. V dlouhodobě běžících službách uvolněte čtečku, jakmile dokončíte zpracování každého obrázku.  
* **Dávkové zpracování**

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Číst čárový kód z obrázku C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak vytvořit macro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak číst PDF417 v C# – kompletní příklad čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}