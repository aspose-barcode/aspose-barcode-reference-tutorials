---
category: general
date: 2026-09-22
description: Naučte se číst PDF417 čárové kódy v C# s kompletním příkladem čtečky
  čárových kódů. Tento tutoriál vám ukáže, jak rychle a spolehlivě číst obrázek čárového
  kódu v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: cs
lastmod: 2026-09-22
og_description: Jak číst čárové kódy PDF417 v C# pomocí stručného příkladu čtečky
  čárových kódů. Postupujte podle průvodce pro dekódování obrázků Macro PDF417 a extrahování
  metadat.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Jak číst PDF417 čárové kódy v C# – kompletní příklad čtečky čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Jak číst čárové kódy PDF417 v C# – kompletní průvodce krok za krokem
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 čárové kódy v C# – kompletní krok‑za‑krokem průvodce

Pokud potřebujete **how to read pdf417** v .NET aplikaci, tento průvodce vám ukáže přesný kód a úvahy, které potřebujete. Na konci prvních dvou vět budete vědět, jak číst obrázek čárového kódu v C# pomocí populární třídy `BarCodeReader`, a budete mít připravený příklad, který extrahuje každý kus metadat Macro PDF417.

Čtení PDF417 čárových kódů je běžnou potřebou při zpracování přepravních štítků, palubních vstupenek nebo zabezpečených dokumentů. Tento tutoriál pokrývá vše od nastavení čtečky po řešení okrajových případů, takže můžete integraci skenování čárových kódů provádět s jistotou.

## Co dosáhnete

- Dekódujte soubor s obrázkem Macro PDF417.
- Vytiskněte základní informace o čárovém kódu (typ a text).
- Získejte přístup ke všem rozšířeným polím Macro PDF417, jako je ID souboru, počet segmentů a časové razítko.
- Pochopte běžné úskalí při práci s více‑segmentovými PDF417 kódy.

**Požadavky**

- .NET 6.0 nebo novější (kód také funguje s .NET Framework 4.7+).
- Odkaz na SDK pro čárové kódy, které poskytuje `BarCodeReader`, `DecodeType` a `BarCodeResult` (např. Aspose.BarCode, Dynamsoft nebo jakoukoli knihovnu vystavující stejné API).
- Obrázkový soubor (`ExtPDF417Meta.png`) obsahující Macro PDF417 čárový kód.

> **Tip:** Umístěte obrázek do složky relativní k kořenu projektu a nastavte jeho vlastnost **Copy to Output Directory** na *Copy if newer*, aby cesta fungovala během ladění.

![Jak číst PDF417 čárový kód pomocí C#](https://example.com/placeholder-image.png)

## Jak číst PDF417 čárový kód v C# – kompletní kód

Níže je samostatný program, který můžete vložit do konzolové aplikace. Vytvoří čtečku čárových kódů, iteruje přes každý dekódovaný výsledek a vypíše jak standardní, tak rozšířená pole Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
```

### Proč je každý krok důležitý

1. **Vytvoření čtečky s `DecodeType.MacroPdf417`** – Macro PDF417 je speciální varianta, která může nést metadata na úrovni souboru. Specifikování typu dekódování zajišťuje, že SDK parsuje tato extra pole místo toho, aby kód považovalo za obyčejný PDF417.
2. **Iterace přes `ReadBarCodes()`** – Obrázek může obsahovat více než jeden čárový kód (např. QR kód vedle PDF417). Smyčka zaručuje, že zachytíte každý výsledek.
3. **Výpis `CodeTypeName` a `CodeText`** – Jedná se o nejčastěji používané vlastnosti; poskytují název symbologie a lidsky čitelný obsah.
4. **Přístup k `Extended.Pdf417`** – Objekt `Extended` se objeví pouze pro typy dekódování související s PDF417. Každá vlastnost mapuje přímo na specifikaci Macro PDF417, což vám umožní znovu sestavit původní soubor nebo ověřit pořadí segmentů.

## Běžné varianty a okrajové případy

### Čtení ne‑macro PDF417 čárového kódu

Pokud vaše zdrojové obrázky obsahují běžné PDF417 kódy (bez macro metadat), nahraďte `DecodeType.MacroPdf417` za `DecodeType.Pdf417`. Zbytek kódu zůstane stejný, ale blok `Extended.Pdf417` bude prázdný, protože tato pole jednoduše neexistují.

### Zpracování více‑segmentových PDF

Macro PDF417 může rozdělit velký dokument na několik segmentů čárových kódů. Pro znovusestavení původního souboru musíte:

1. Shromáždit `Pdf417MacroSegmentID` každého segmentu.
2. Seřadit segmenty podle jejich ID.
3. Ověřit, že `Pdf417MacroSegmentsCount` odpovídá počtu přijatých segmentů.
4. Spojit `CodeText` každého segmentu ve správném pořadí.
5. Volitelně ověřit `Pdf417MacroChecksum`.

Níže je stručný úryvek, který demonstruje logiku znovusestavení:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Práce s poškozenými obrázky

- **Nízký kontrast** – Zvyšte předzpracování obrazu (např. ekvalizace histogramu) před předáním do `BarCodeReader`.
- **Rotace** – Použijte `barcodeReader.SetRotateAngle(90)` nebo povolte automatickou rotaci, pokud SDK podporuje.
- **Částečné skeny** – Zajistěte, aby rozlišení obrázku bylo alespoň 300 dpi; jinak SDK může minout malé segmenty.

## c# příklad čtečky čárových kódů – osvědčené postupy

| Postup | Důvod |
|----------|--------|
| **Uvolněte čtečku pomocí `using`** | Zaručuje, že nativní zdroje jsou uvolněny okamžitě, což zabraňuje únikům paměti. |
| **Ověřte, že `result.Extended` není null** | Některá SDK vrací `null` pro ne‑macro kódy; kontrola zabraňuje `NullReferenceException`. |
| **Zaznamenejte `Pdf417MacroFileID`** | Tento identifikátor je jedinečný pro každý soubor a užitečný pro auditní záznamy. |
| **Zabalte dekódování do try/catch** | I/O chyby (chybějící soubor) nebo nepodporované formáty vyvolají výjimky, které by měly být ošetřeny elegantně. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Očekávaný výstup

Spuštěním celého programu proti správně formátovanému `ExtPDF417Meta.png` získáte výstup podobný tomuto:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Pokud obrázek obsahuje více segmentů, smyčka vypíše metadata každého segmentu postupně.

## Závěr

Nyní víte, **jak číst pdf417** čárové kódy v C# a máte **c# příklad čtečky čárových kódů**, který extrahuje každé pole Macro PDF417. Řešení pokrývá základní dekódování, extrakci metadat, znovusestavení více‑segmentových souborů a ošetření chyb, což vám poskytuje produkčně připravený základ pro jakýkoli workflow zpracování dokumentů.

### Další kroky

- Prozkoumejte techniky **read barcode image C#** pro jiné symbologie (QR, DataMatrix) pomocí stejného API `BarCodeReader`.
- Integrujte dekodér čárových kódů do služby ASP.NET Core pro zpracování nahrávek za běhu.
- Experimentujte s knihovnami pro předzpracování obrazu (např. `OpenCvSharp`) pro zvýšení úspěšnosti při skenování nízké kvality.

Šťastné programování a klidně upravte příklad tak, aby vyhovoval vašemu konkrétnímu případu použití!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok‑za‑krokem vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak uložit čárový kód v C# – Generování PDF417 čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Jak číst PDF417 v C# – Kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Jak nastavit úroveň chyb v PDF417 čárovém kódu – Kompletní průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}