---
category: general
date: 2026-09-28
description: Rychle čtěte PDF417 čárový kód v C# pomocí Aspose.BarCode. Dekódujte
  více čárových kódů z jednoho obrázku, extrahujte pole Macro‑PDF417 a řešte rotaci
  nebo dávkové zpracování.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read pdf417 barcode c#
- read multiple barcodes
- pdf417 c# decoding
- Aspose.BarCode PDF417
- barcode image c#
lastmod: 2026-09-28
og_description: Rychle čtěte PDF417 čárový kód v C# pomocí Aspose.BarCode. Tento průvodce
  ukazuje, jak dekódovat více čárových kódů z jednoho obrázku, extrahovat všechny
  vlastnosti Macro‑PDF417 a řešit otočené nebo dávkové obrázky.
og_image_alt: Screenshot of C# console output displaying PDF417 barcode details
og_title: Čtení PDF417 čárového kódu v C# – kompletní ukázkový kód a průvodce
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  headline: Read PDF417 barcode c# – complete step‑by‑step guide
  type: TechArticle
- description: Read PDF417 barcode c# and read multiple barcodes from an image. Learn
    to read barcode image C# with detailed code and tips.
  name: Read PDF417 barcode c# – complete step‑by‑step guide
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
title: Jak číst PDF417 čárový kód v C# – kompletní průvodce krok po kroku
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód PDF417 v C# – kompletní krok‑za‑krokem průvodce

Ever wondered **how to read PDF417** from an image using C#? You’re not the only one. Most developers hit a wall when they need to pull out the extended Macro‑PDF417 fields from a scanned document. The good news? With just a few lines of code you can **read PDF417 barcode c#**, decode multiple barcodes in the same picture, and grab every hidden property the spec offers.

## Rychlé odpovědi
- **Umí Aspose.BarCode dekódovat Macro‑PDF417?** Ano – stačí povolit `DecodeType.MacroPdf417` a knihovna vrátí všechna rozšířená pole.  
- **Kolik čárových kódů lze přečíst z jednoho obrázku?** Neomezeně; API vrací kolekci objektů `BarCodeResult`.  
- **Potřebuji licenci pro produkci?** Pro produkční použití je vyžadována komerční licence; pro hodnocení stačí bezplatná zkušební verze.  
- **Budou detekovány otočené čárové kódy?** Vestavěná kompenzace rotace funguje pro čárové kódy, které zabírají alespoň 30 % šířky obrázku.  
- **Je podpora dávkového zpracování?** Ano – zabalte čtečku do smyčky `foreach` a uvolněte každou instanci pomocí `using`.

## Co je čtení PDF417 čárového kódu v C#?
`read pdf417 barcode c#` odkazuje na proces použití .NET knihovny k dekódování symbolů PDF417 (včetně Macro‑PDF417) z obrazových souborů přímo v C# kódu. Aspose.BarCode SDK poskytuje jednorázové API, které zvládne načtení obrázku, detekci čárových kódů a extrakci všech ISO‑definovaných polí.

## Proč použít Aspose.BarCode pro dekódování PDF417?
Aspose.BarCode podporuje **více než 30 čárových kódů** a dokáže zpracovat obrázky až do **5000 × 5000 px** za méně než **0,1 s** na typickém serverovém hardware. Nabízí rovněž vestavěnou kompenzaci rotace, zkreslení a zpracování invertovaných čárových kódů, čímž odstraňuje potřebu vlastního předzpracování obrázků. Knihovna také obsahuje vestavěnou podporu pro čtení rozšířených polí Macro‑PDF417, což z ní činí komplexní řešení pro složité skenovací scénáře.

## Požadavky

* .NET 6.0 SDK nebo novější (kód funguje také s .NET Core a .NET Framework).  
* Visual Studio 2022 (nebo jakýkoli editor, který preferujete).  
* NuGet balíček **Aspose.BarCode for .NET** – to je knihovna, která skutečně parsuje PDF417.  
* Vzorový obrázek, který obsahuje Macro‑PDF417 čárový kód (například `ExtPDF417Meta.png`).  

Žádná další konfigurace není vyžadována; knihovna obsahuje všechny potřebné dekodéry.

## Jak číst PDF417 čárový kód v C#?

Načtěte obrázek pomocí `BarCodeReader`, zadejte `DecodeType.MacroPdf417` a projděte vrácenou kolekci `BarCodeResult` – to je kompletní řešení v méně než deseti řádcích kódu. Čtečka automaticky extrahuje jak čisté PDF417 symboly, tak rozšířená data Macro‑PDF417, takže získáte identifikátory souborů, čísla segmentů, časové značky a kontrolní součty bez dalšího parsování.

### Krok 1: nainstalovat Aspose.BarCode

Open your project folder in a terminal and run:

```bash
dotnet add package Aspose.BarCode
```

That command pulls the latest stable version (as of July 2026 it’s 23.12). If you prefer the Package Manager Console inside Visual Studio, use:

```powershell
Install-Package Aspose.BarCode
```

> **Tip:** uzamkněte verzi (`23.12.0`) ve vašem `.csproj`, abyste později předešli nechtěným breaking changes.

### Krok 2: vytvořit kostru konzolové aplikace

Create a new console project if you don’t already have one:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Replace the autogenerated `Program.cs` with the code below. We’ll explain each block in the next sections.

### Krok 3: napsat kompletní kód „jak číst PDF417“

`BarCodeReader` je hlavní třída, která načítá obrázek, detekuje čárové kódy a vrací kolekci objektů `BarCodeResult`.

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

* `BarCodeReader` — hlavní třída zodpovědná za čtení a dekódování čárových kódů z obrázků.  
* `DecodeType.MacroPdf417` — příznak, který říká SDK, aby zacházel s Macro‑PDF417 zvláštně, přičemž stále vrací i čisté PDF417 symboly.  
* `Extended.Pdf417.MacroPdf417` — objekt, který obsahuje všechna volitelná pole definovaná v ISO/IEC 15438, jako `FileID`, `SegmentID` a `Checksum`.  

Blok `using` zajišťuje uvolnění nativních zdrojů, čímž zabraňuje únikům paměti v dlouho běžících službách.

### Krok 4: spustit aplikaci a ověřit výstup

From the terminal:

```bash
dotnet run
```

You should see something like:

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

If the image contains more than one barcode, the loop prints a separator line (`----------------------------------------`) and continues with the next result—exactly what **read multiple barcodes** looks like in practice.

## Časté otázky a okrajové případy

### Co když obrázek obsahuje jak Macro‑PDF417, tak běžné PDF417 symboly?

Stejný volání `BarCodeReader` vrátí oba. Můžete je rozlišit kontrolou `result.CodeType` (`MacroPdf417` vs `Pdf417`). Rozšířená vlastnost bude `null` u čistého PDF417, takže podmínka `if (macro != null)` zabraňuje `NullReferenceException`.

### Můj čárový kód je otočený nebo zkreslený – bude čtečka stále fungovat?

Aspose.BarCode obsahuje vestavěnou kompenzaci rotace a zkreslení. Pokud čárový kód zabírá alespoň 30 % šířky obrázku, dekodér obvykle uspěje. V extrémních případech můžete před voláním `ReadBarCodes()` povolit `reader.Options.AllowInvertedBarcodes = true;`.

### Jak zvládnout velké dávky obrázků?

Zabalte logiku čtení do smyčky `foreach (var file in Directory.GetFiles(folder, "*.png"))`. Vzor `using` zajišťuje uvolnění nativních zdrojů každého obrázku před další iterací, čímž udržuje nízkou spotřebu paměti.

## Kompletní výpis zdrojového kódu (připravený ke kopírování)

Níže je celý program v jednom bloku pro rychlé kopírování. Žádné skryté závislosti – jen NuGet balíček Aspose.BarCode.

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

## Shrnutí – co jsme probrali

* **Jak číst PDF417 čárový kód v C#** pomocí Aspose.BarCode.  
* Přesné kroky k **čtení více čárových kódů** z jednoho obrázku.  
* Jak **číst obrázek čárového kódu v C#** a extrahovat všechna pole Macro‑PDF417.  
* Tipy pro rotaci, dávkové zpracování a zacházení s chybějícími rozšířenými daty.

## Další kroky a související témata

* **Encode PDF417** – generujte vlastní Macro‑PDF417 čárové kódy pomocí `BarCodeBuilder`.  
* **Read other 2‑D symbologies** – QR, DataMatrix, Aztec – pomocí stejné třídy `BarCodeReader`.  
* **Integrate with ASP.NET Core** – vystavte webový endpoint, který přijme nahraný obrázek a vrátí JSON s dekódovanými poli.  

### Další užitečné odkazy
- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)  
- [Jak vytvořit čárový kód – Compact PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)  
- [Číst DataMatrix čárový kód C# – Generovat DataMatrix režim (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

Feel free to experiment: change the image path, drop a plain PDF417 into the same folder, or tweak the `DecodeType` flags to see how the library behaves. The more you play, the more comfortable you’ll become with **read barcode image c#** scenarios.

Got a tricky image that refuses to decode? Drop a comment below or open an issue on the GitHub repo of the sample project. Happy coding!

## Často kladené otázky

**Q: Mohu to použít v komerční aplikaci?**  
A: Ano, můžete používat Aspose.BarCode v komerčních projektech, pokud máte platnou licenci; pro hodnocení je k dispozici bezplatná zkušební verze.

**Q: Podporuje čtečka obrázky chráněné heslem?**  
A: SDK funguje s jakýmkoli standardním formátem obrázku; ochrana heslem se nevztahuje na rastrové obrázky, pouze na PDF, které jsou zpracovávány samostatnou komponentou Aspose.PDF.

**Q: Jaké verze .NET jsou podporovány?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ a .NET 6+ jsou plně podporovány aktuálním vydáním Aspose.BarCode.

**Q: Jak mohu zlepšit výkon při velmi velkých dávkách obrázků?**  
A: Povolte `reader.Options.Quality = QualityMode.HighPerformance` a zpracovávejte obrázky paralelně pomocí `Parallel.ForEach`, přičemž stále obalujte každý `BarCodeReader` do bloku `using`.

**Q: Existuje způsob, jak získat pouze pole Macro‑PDF417 bez iterace všech výsledků?**  
A: Ano – po volání `ReadBarCodes()` filtrujte kolekci pomocí `result => result.CodeType == DecodeType.MacroPdf417` a poté přistupte k vlastnosti `Extended.Pdf417.MacroPdf417`.

---

**Poslední aktualizace:** 2026-09-28  
**Testováno s:** Aspose.BarCode 23.12 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Jak vygenerovat PDF417 čárový kód jako obrázek v C# s Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)  
- [Vytvořit PDF417 čárový kód s Aspose Barcode – krok za krokem průvodce](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)  
- [Číst více čárových kódů v C – kompletní průvodce s PDF417](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}