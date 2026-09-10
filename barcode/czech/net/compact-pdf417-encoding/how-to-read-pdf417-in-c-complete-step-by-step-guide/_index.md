---
category: general
date: 2026-07-15
description: Jak číst PDF417 čárový kód v C# a číst více čárových kódů z obrázku.
  Naučte se číst čárový kód z obrázku v C# s podrobným kódem a tipy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcode image c#
- Aspose.BarCode PDF417
- C# barcode decoding
language: cs
lastmod: 2026-07-15
og_description: Jak rychle načíst čárový kód PDF417 v C#. Tento průvodce vám ukáže,
  jak načíst více čárových kódů z jednoho obrázku a dekódovat každou vlastnost.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Jak číst PDF417 v C# – Kompletní ukázkový kód a vysvětlení
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  headline: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  type: TechArticle
- description: How to read PDF417 barcode in C# and read multiple barcodes from an
    image. Learn to read barcode image C# with detailed code and tips.
  name: How to Read PDF417 in C# – Complete Step‑by‑Step Guide
  steps:
  - name: Why This Code Works
    text: '* **`BarCodeReader`** is the core class that streams the image, detects
      barcodes, and returns a collection of `BarCodeResult` objects. * Passing **`DecodeType.MacroPdf417`**
      tells the library to treat Macro‑PDF417 specially; it still returns plain PDF417
      symbols, which satisfies the **read multiple '
  - name: What if the image has both Macro‑PDF417 and regular PDF417 symbols?
    text: The same `BarCodeReader` call will return both. You can differentiate them
      by checking `result.CodeType` (`MacroPdf417` vs `Pdf417`). The extended properties
      will be `null` for a plain PDF417, so the `if (macro != null)` guard prevents
      a `NullReferenceException`.
  - name: My barcode is rotated or skewed—will the reader still work?
    text: Aspose.BarCode includes built‑in rotation and distortion compensation. As
      long as the barcode is at least 30 % of the image width, the decoder will usually
      succeed. For extreme cases you can enable `reader.Options.AllowInvertedBarcodes
      = true;` before calling `ReadBarCodes()`.
  - name: How do I handle large batches of images?
    text: Wrap the reading logic in a `foreach (var file in Directory.GetFiles(folder,
      "*.png"))` loop. The `using` pattern ensures each image’s native resources are
      freed before the next iteration, keeping memory usage low.
  type: HowTo
tags:
- C#
- barcode
- PDF417
- Aspose
title: Jak číst PDF417 v C# – Kompletní krok za krokem průvodce
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 v C# – Kompletní průvodce krok za krokem

Už jste se někdy ptali, **jak číst PDF417** z obrázku pomocí C#? Nejste v tom jediní. Většina vývojářů narazí na problém, když potřebují získat rozšířené pole Macro‑PDF417 ze skenovaného dokumentu. Dobrá zpráva? Pouhých několik řádků kódu vám umožní dekódovat PDF417, přečíst více čárových kódů na stejném obrázku a získat všechny skryté vlastnosti, které specifikace nabízí.

V tomto tutoriálu projdeme reálný příklad, který ukazuje **jak číst PDF417**, jak **číst více čárových kódů** z jediného souboru, a proč kód **read barcode image C#** vypadá tak, jak vypadá. Na konci budete mít připravenou konzolovou aplikaci, která vytiskne každou informaci, kterou můžete potřebovat — ID souboru, ID segmentu, kontrolní součet, časová razítka, a tak dál.

## Požadavky

Než se pustíme do práce, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód funguje také s .NET Core a .NET Framework).  
* Visual Studio 2022 (nebo jakýkoli editor, který preferujete).  
* Balíček NuGet **Aspose.BarCode for .NET** – to je knihovna, která skutečně parsuje PDF417.  
* Ukázkový obrázek, který obsahuje čárový kód Macro‑PDF417 (například `ExtPDF417Meta.png`).  

Žádná další konfigurace není potřeba; knihovna obsahuje všechny dekodéry, které potřebujete.

## Krok 1: Instalace Aspose.BarCode

Otevřete složku projektu v terminálu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Tento příkaz stáhne nejnovější stabilní verzi (k červenci 2026 je to 23.12). Pokud dáváte přednost Package Manager Console ve Visual Studiu, použijte:

```powershell
Install-Package Aspose.BarCode
```

> **Pro tip:** uzamkněte verzi (`23.12.0`) ve vašem `.csproj`, abyste se vyhnuli neúmyslným breaking changes později.

## Krok 2: Vytvoření kostry konzolové aplikace

Vytvořte nový konzolový projekt, pokud ještě žádný nemáte:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Nahraďte automaticky vygenerovaný `Program.cs` kódem níže. Každý blok vysvětlíme v následujících sekcích.

## Krok 3: Napište kompletní kód „Jak číst PDF417“

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Set the path to the image that contains one or more PDF417 codes
            // -----------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarCodeReader for MacroPdf417 decoding
            // -----------------------------------------------------------------
            // The DecodeType flag tells Aspose to look specifically for Macro‑PDF417,
            // but it will also pick up plain PDF417 symbols that happen to be in the
            // same image – perfect for the “read multiple barcodes” scenario.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // -----------------------------------------------------------------
                // 3️⃣  Iterate over every barcode found in the image
                // -----------------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -------------------------------------------------------------
                    // 4️⃣  Basic barcode information – works for any barcode type
                    // -------------------------------------------------------------
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // -------------------------------------------------------------
                    // 5️⃣  Macro‑PDF417 extended properties (the real reason you’re here)
                    // -------------------------------------------------------------
                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40)); // visual separator
                }
            }

            // -----------------------------------------------------------------
            // 6️⃣  Keep the console window open when running from VS
            // -----------------------------------------------------------------
            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

### Proč tento kód funguje

* **`BarCodeReader`** je hlavní třída, která načítá obrázek, detekuje čárové kódy a vrací kolekci objektů `BarCodeResult`.  
* Předáním **`DecodeType.MacroPdf417`** říkáte knihovně, aby zacházela s Macro‑PDF417 speciálně; stále vrací běžné PDF417 symboly, což splňuje požadavek na **read multiple barcodes**.  
* Objekt **`Extended.Pdf417.MacroPdf417`** obsahuje všechna volitelná pole definovaná standardem ISO/IEC 15438 — zde získáte `FileID`, `SegmentID`, `Checksum` a další.  
* `using` blok zajišťuje uvolnění nativních zdrojů, čímž zabraňuje únikům paměti v dlouho běžících službách.

## Krok 4: Spusťte aplikaci a ověřte výstup

Z terminálu:

```bash
dotnet run
```

Měli byste vidět něco podobného:

```
Code Type : MacroPdf417
Code Text : 1234567890...
File ID          : 12
Segment ID       : 1
Segments Count   : 3
File Name        : invoice2024.pdf
Checksum         : 9A3F
File Size        : 245760
Time Stamp       : 2024-11-02T14:23:00Z
Addressee        : Acme Corp
Sender           : Logistics Dept
Terminator       : 1
----------------------------------------
Done. Press any key to exit...
```

Pokud obrázek obsahuje více než jeden čárový kód, smyčka vytiskne oddělovací řádek (`----------------------------------------`) a pokračuje dalším výsledkem — přesně to, co **read multiple barcodes** v praxi vypadá.

## Časté otázky a okrajové případy

### Co když obrázek obsahuje jak Macro‑PDF417, tak běžné PDF417 symboly?

Stejný volání `BarCodeReader` vrátí oba. Můžete je odlišit kontrolou `result.CodeType` (`MacroPdf417` vs `Pdf417`). Rozšířené vlastnosti budou `null` pro běžný PDF417, takže podmínka `if (macro != null)` zabraňuje `NullReferenceException`.

### Můj čárový kód je otočený nebo zkreslený — bude čtečka stále fungovat?

Aspose.BarCode obsahuje vestavěnou kompenzaci rotace a zkreslení. Pokud je čárový kód alespoň 30 % šířky obrázku, dekodér obvykle uspěje. V extrémních případech můžete před voláním `ReadBarCodes()` povolit `reader.Options.AllowInvertedBarcodes = true;`.

### Jak zvládnout velké dávky obrázků?

Zabalte čtecí logiku do smyčky `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Vzor `using` zajišťuje, že nativní zdroje každého obrázku jsou uvolněny před dalším průchodem, což udržuje nízkou spotřebu paměti.

## Kompletní výpis zdrojového kódu (připravený ke kopírování)

Níže je celý program v jednom bloku pro rychlé kopírování. Žádné skryté závislosti — pouze balíček NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    var macro = result.Extended?.Pdf417?.MacroPdf417;
                    if (macro != null)
                    {
                        Console.WriteLine($"File ID          : {macro.FileID}");
                        Console.WriteLine($"Segment ID       : {macro.SegmentID}");
                        Console.WriteLine($"Segments Count   : {macro.SegmentsCount}");
                        Console.WriteLine($"File Name        : {macro.FileName}");
                        Console.WriteLine($"Checksum         : {macro.Checksum}");
                        Console.WriteLine($"File Size        : {macro.FileSize}");
                        Console.WriteLine($"Time Stamp       : {macro.TimeStamp}");
                        Console.WriteLine($"Addressee        : {macro.Addressee}");
                        Console.WriteLine($"Sender           : {macro.Sender}");
                        Console.WriteLine($"Terminator       : {macro.Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro‑PDF417 extended data found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Done. Press any key to exit...");
            Console.ReadKey();
        }
    }
}
```

## Shrnutí – Co jsme pokryli

* **Jak číst PDF417** pomocí Aspose.BarCode v C#.  
* Přesné kroky k **čtení více čárových kódů** z jednoho obrázku.  
* Jak **číst obrázek čárového kódu C#** a extrahovat všechna pole Macro‑PDF417.  
* Tipy pro rotaci, dávkové zpracování a řešení chybějících rozšířených dat.

## Další kroky a související témata

* **Encode PDF417** – vygenerujte vlastní Macro‑PDF417 čárové kódy pomocí `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – pomocí stejné třídy `BarCodeReader`.  
* **Integrate with ASP.NET Core** – vystavte webový endpoint, který přijímá nahraný obrázek a vrací JSON s dekódovanými poli.  

Klidně experimentujte: změňte cestu k obrázku, přidejte běžný PDF417 do stejné složky nebo upravte příznaky `DecodeType`, abyste viděli, jak se knihovna chová. Čím více si budete hrát, tím jistější budete v scénářích **read barcode image C#**.

Máte obtížný obrázek, který se nechce dekódovat? Zanechte komentář níže nebo otevřete issue v GitHub repozitáři ukázkového projektu. Šťastné kódování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak číst DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Číst DataMatrix čárový kód C# – Generovat DataMatrix režim (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}