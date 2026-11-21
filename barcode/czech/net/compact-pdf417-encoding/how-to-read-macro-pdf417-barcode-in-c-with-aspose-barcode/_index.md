---
category: general
date: 2026-11-20
description: Naučte se rychle číst makro PDF417 čárový kód v C#. Tento průvodce vám
  ukáže, jak číst čárové kódy z obrázku v C# pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read macro PDF417 barcode
- read barcodes from image C#
- Aspose.BarCode C#
- PDF417 extended data
- barcode decoding .NET
language: cs
lastmod: 2026-11-20
og_description: Čtěte makro PDF417 čárový kód v C# pomocí Aspose.BarCode. Postupujte
  podle tohoto tutoriálu, abyste četli čárové kódy z obrázku v C# a získali kompletní
  informace o makro PDF417.
og_image_alt: Screenshot showing a Macro PDF417 barcode being read in a C# console
  application
og_title: Čtení makro PDF417 čárového kódu v C# – kompletní krok‑za‑krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  headline: How to read macro PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to read macro PDF417 barcode in C# quickly. This guide shows
    you how to read barcodes from image C# using Aspose.BarCode.
  name: How to read macro PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
    text: '**`BarCodeReader` construction** – By passing `DecodeType.MacroPdf417`
      we tell Aspose.BarCode to look specifically for Macro PDF417 symbols and to
      populate the `Extended.Pdf417` object.'
  - name: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
    text: '**`ReadBarCodes()`** – Returns a collection because an image may contain
      more than one barcode. The loop handles each result independently.'
  - name: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
    text: '**`result.Extended.Pdf417`** – Holds the extended fields defined by the
      Macro PDF417 specification:'
  - name: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
    text: '**Console output** – Shows each field, making it easy to verify that the
      barcode was read correctly.'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- Aspose
title: Jak číst makro PDF417 čárový kód v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst makro PDF417 čárový kód v C# s Aspose.BarCode

Pokud potřebujete **číst makro PDF417 čárový kód** v .NET aplikaci, tento tutoriál vám ukáže kompletní, připravené řešení. Uvidíte, jak **číst čárové kódy z obrázku v C#** pomocí knihovny Aspose.BarCode, extrahovat všechna rozšířená pole Macro PDF417 a řešit běžné okrajové případy.

Průvodce pokrývá vše, co potřebujete vědět: nastavení projektu, procházení kódu, tipy na řešení problémů a nápady na další kroky pro pokročilejší scénáře.

## Co budete potřebovat

- **.NET 6.0** nebo novější (kód také funguje s .NET Framework 4.6+)
- **Visual Studio 2022** (nebo jakékoli IDE podporující .NET)
- NuGet balíček **Aspose.BarCode for .NET** (bezplatná zkušební verze nebo licencovaná verze)
- Soubor obrázku, který obsahuje makro PDF417 čárový kód (např. `ExtPDF417Meta.png`)

> **Tip:** Pokud nemáte ukázkový obrázek čárového kódu, můžete jej vygenerovat pomocí třídy `BarcodeGenerator` z Aspose.BarCode a nastavit `EncodeMode = EncodeMode.MacroPdf417`.

## Krok 1: Instalace Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

## Krok 2: Vytvoření kostry konzolové aplikace

Vytvořte nový konzolový projekt (pokud ještě žádný nemáte):

```bash
dotnet new console -n MacroPdf417Reader
cd MacroPdf417Reader
```

Nahraďte vygenerovaný soubor `Program.cs` následujícím kompletním příkladem. Kód je samostatný a po instalaci NuGet balíčku se kompiluje bez úprav.

## Krok 3: Kompletní ukázkový kód – čtení makro PDF417 čárového kódu

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace MacroPdf417Reader
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that holds the Macro PDF417 barcode.
            // Use an absolute path or place the image in the project folder and set
            // "Copy to Output Directory" = "Copy always" in Visual Studio.
            string imagePath = "ExtPDF417Meta.png";

            // Initialize the BarCodeReader for MacroPdf417 decoding.
            // DecodeType.MacroPdf417 tells the library to look for the extended
            // Macro PDF417 fields (FileID, SegmentID, FileName, etc.).
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Read all barcodes found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // The Extended property contains PDF417‑specific information.
                    var pdf417Info = result.Extended?.Pdf417;

                    if (pdf417Info != null)
                    {
                        Console.WriteLine($"Pdf417MacroFileID   : {pdf417Info.MacroPdf417FileID}");
                        Console.WriteLine($"Pdf417MacroSegmentID: {pdf417Info.MacroPdf417SegmentID}");
                        Console.WriteLine($"Pdf417MacroFileName : {pdf417Info.MacroPdf417FileName}");
                        Console.WriteLine($"Pdf417MacroFileSize : {pdf417Info.MacroPdf417FileSize}");
                        Console.WriteLine($"Pdf417MacroChecksum : {pdf417Info.MacroPdf417Checksum}");
                        // Add any other fields you need here.
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 information was found in this barcode.");
                    }
                }
            }

            Console.WriteLine("\nFinished reading macro PDF417 barcode.");
        }
    }
}
```

### Jak kód funguje

1. **`BarCodeReader` konstrukce** – Předáním `DecodeType.MacroPdf417` říkáme Aspose.BarCode, aby hledal konkrétně symboly Macro PDF417 a naplnil objekt `Extended.Pdf417`.
2. **`ReadBarCodes()`** – Vrací kolekci, protože obrázek může obsahovat více než jeden čárový kód. Smyčka zpracovává každý výsledek samostatně.
3. **`result.Extended.Pdf417`** – Obsahuje rozšířená pole definovaná specifikací Macro PDF417:
   - `MacroPdf417FileID` – Identifikátor celého souboru (užitečné, když jsou data rozdělena do několika symbolů).
   - `MacroPdf417SegmentID` – Index tohoto konkrétního segmentu.
   - `MacroPdf417FileName` – Volitelný název souboru vložený do čárového kódu.
   - `MacroPdf417FileSize` – Celková velikost původního souboru v bajtech.
   - `MacroPdf417Checksum` – Hodnota kontrolního součtu pro ověření integrity.
4. **Výstup do konzole** – Zobrazuje každé pole, což usnadňuje ověření, že byl čárový kód načten správně.

> **Proč použít `MacroPdf417` místo obyčejného `Pdf417`?**  
> Macro PDF417 přidává metadata, která umožňují rozdělení velkých datových nákladů do více symbolů. Pokud dekódujete jen běžný `Pdf417`, tato extra pole jsou ignorována a ztratíte informace potřebné k rekonstrukci původního souboru.

## Krok 4: Ověření výstupu

Spusťte program:

```bash
dotnet run
```

Typický výstup v konzoli vypadá takto:

```
Pdf417MacroFileID   : 12
Pdf417MacroSegmentID: 3
Pdf417MacroFileName : invoice_2026_11.pdf
Pdf417MacroFileSize : 45231
Pdf417MacroChecksum : 0x1A2B3C4D

Finished reading macro PDF417 barcode.
```

Pokud obrázek neobsahuje symbol Macro PDF417, program vypíše *„No Macro PDF417 information was found in this barcode.“* Tato zpráva vám pomůže rozlišit mezi nepodporovaným čárovým kódem a selháním dekódování.

## Krok 5: Časté úskalí při **čtení čárových kódů z obrázku v C#**

| Symptom | Pravděpodobná příčina | Oprava |
|---------|----------------------|--------|
| `reader.ReadBarCodes()` returns an empty collection | Špatná cesta k obrázku nebo soubor není zkopírován do výstupní složky. | Použijte absolutní cestu nebo nastavte vlastnost souboru obrázku **Copy to Output Directory** na **Copy always**. |
| `result.Extended.Pdf417` is `null` | Čárový kód není symbolem Macro PDF417 (např. obyčejný PDF417 nebo jiný formát). | Ujistěte se, že čárový kód byl vygenerován s `EncodeMode = EncodeMode.MacroPdf417`. |
| Decoding fails on low‑resolution images | Čárový kód je rozmazaný nebo příliš malý pro výchozí nastavení knihovny. | Zvyšte rozlišení obrázku nebo povolte `reader.Parameters.BarcodeReaderOptions` jako `AutoRotate` a úpravy `Quality`. |
| Checksum mismatch | Obrázek byl poškozen během přenosu nebo ukládání. | Znovu vygenerujte čárový kód nebo ověřte integritu zdrojového souboru. |

Řešení těchto problémů včas šetří čas při **čtení čárových kódů z obrázku v C#** v produkčních systémech.

## Krok 6: Pokročilé možnosti a další kroky

- **Dávkové zpracování** – Zabalte logiku čtečky do metody, která přijímá cestu ke složce a automaticky zpracuje každý soubor PNG/JPG.
- **Asynchronní dekódování** – Použijte `Task.Run` k dekódování velkých dávek bez blokování UI vlákna v desktopových nebo webových aplikacích.
- **Ukládání extrahovaných dat** – Zapište makro pole do JSON souboru pro následné zpracování:

  ```csharp
  var json = System.Text.Json.JsonSerializer.Serialize(pdf417Info);
  File.WriteAllText($"metadata_{pdf417Info.MacroPdf417SegmentID}.json", json);
  ```

- **Integrace s dalšími produkty Aspose** – Kombinujte dekódovaná data s Aspose.PDF k rekonstrukci původního dokumentu z jeho makro segmentů.

## Závěr

Nyní víte, jak **číst makro PDF417 čárový kód** v C# pomocí Aspose.BarCode, a rozumíte tomu, jak **číst čárové kódy z obrázku v C#** při extrakci všech rozšířených polí Macro PDF417. Kompletní, spustitelný příklad demonstruje nastavení projektu, provedení kódu a tipy na řešení problémů.

Odtud můžete zkoumat dávkové dekódování, asynchronní zpracování nebo integrovat extrahovaná metadata s dalšími knihovnami pro práci s dokumenty. Experimentujte s různými kvalitou obrázků, soubory s více segmenty a vlastním zpracováním chyb, aby vyhovovaly vašemu konkrétnímu případu použití.

--- 

*Připraveno to vyzkoušet sami? Klonujte repozitář, nahraďte `ExtPDF417Meta.png` vlastním obrázkem čárového kódu a spusťte program. Pokud narazíte na problémy, výše uvedená tabulka s řešením by vám měla nasměrovat správným směrem.*

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Číst čárový kód z obrázku C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak vytvořit makro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak číst PDF417 čárový kód v C# s Aspose – krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}