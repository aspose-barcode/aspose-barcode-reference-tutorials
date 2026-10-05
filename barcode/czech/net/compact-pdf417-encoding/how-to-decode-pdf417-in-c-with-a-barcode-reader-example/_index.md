---
category: general
date: 2026-09-19
description: Jak dekódovat PDF417 v C# – naučte se číst čárové kódy z obrázku pomocí
  stručného příkladu čtečky čárových kódů, který extrahuje kompletní data Macro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: cs
lastmod: 2026-09-19
og_description: Jak dekódovat PDF417 v C# pomocí krok‑za‑krokem příkladu čtečky čárových
  kódů. Extrahujte každé pole Macro PDF417 z obrázku během několika sekund.
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: Jak dekódovat PDF417 v C# – kompletní průvodce čtečkou čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Jak dekódovat PDF417 v C# s příkladem čtečky čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekódovat PDF417 v C# s příkladem čtečky čárových kódů

Pokud potřebujete dekódovat PDF417 v C#, tento průvodce vám přesně ukáže, jak dekódovat PDF417 z obrázkového souboru. Naučíte se číst čárové kódy z obrázku, přistupovat k rozšířeným polím Macro PDF417 a integrovat řešení do libovolného projektu .NET.

Dekódování čárových kódů PDF417 je běžné v logistice, prodeji vstupenek a ověřování identity. Tento tutoriál pokrývá vše potřebné pro produkčně připravenou implementaci, včetně potřebných knihoven, kompletního zdrojového kódu a tipů pro řešení okrajových případů.

## Požadavky

- .NET 6.0 nebo novější nainstalováno  
- Visual Studio 2022 (nebo jakékoli IDE podporující C#)  
- NuGet balíček **Aspose.BarCode for .NET** (verze 23.11 nebo novější)  

Balíček můžete přidat následujícím příkazem:

```bash
dotnet add package Aspose.BarCode
```

Třída `BarCodeReader` z této knihovny podporuje typ dekódování `MacroPdf417`, který je potřebný pro úplné získání PDF417.

## Krok 1: Jak dekódovat PDF417 v C# – inicializace čtečky

Prvním krokem je vytvoření instance `BarCodeReader`, která cílí na obrázek Macro PDF417. Příznak `DecodeType.MacroPdf417` říká knihovně, aby parsovala rozšířená pole Macro.

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**Proč je to důležité:** Inicializace s `MacroPdf417` umožňuje vlastnost `Extended.Pdf417` u každého `BarCodeResult`, což vám poskytuje přístup k metadatům na úrovni souboru, jako jsou ID segmentů a časová razítka.

## Krok 2: Čtení čárových kódů z obrázku

Obrázek PDF417 může obsahovat více makro segmentů. Metoda `ReadBarCodes()` vrací výčet všech detekovaných čárových kódů, takže je můžete bezpečně projít v cyklu.

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**Tip:** Pokud očekáváte pouze jeden čárový kód, můžete po první iteraci přerušit, ale procházení všech výsledků zaručuje zachycení každého segmentu ve vícestránkových dokumentech.

## Krok 3: Dekódování čárového kódu PDF417 – extrakce základních a rozšířených dat

Uvnitř smyčky vypište jak obecné informace o čárovém kódu, tak makro‑specifická pole. Objekt `Extended.Pdf417` obsahuje všechny metadaty definované standardem PDF417.

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
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
    }
}
```

**Vysvětlení klíčových polí**

| Field | Význam |
|-------|--------|
| `MacroPdf417FileID` | Identifikátor, který seskupuje všechny segmenty patřící ke stejnému logickému souboru |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (začíná od 0) |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů očekávaných pro soubor |
| `MacroPdf417FileName` | Volitelný název souboru vložený do makra |
| `MacroPdf417Checksum` | Kontrolní součet CRC‑16 pro integritu dat |
| `MacroPdf417FileSize` | Původní velikost souboru v bajtech |
| `MacroPdf417TimeStamp` | Časové razítko, kdy bylo makro vygenerováno |
| `MacroPdf417Addressee` | Určený příjemce makro dat |
| `MacroPdf417Sender` | Odesílatel makro dat |
| `MacroPdf417Terminator` | Boolean příznak označující poslední segment |

Přístup k těmto polím vám umožní rekonstruovat původní dokument, ověřit integritu nebo směrovat data na základě informací o odesílateli/příjemci.

## Krok 4: Kompletní příklad čtečky čárových kódů v C# – spojení všeho dohromady

Níže je kompletní spustitelný program. Nahraďte `YOUR_DIRECTORY` složkou, která obsahuje váš soubor `MacroPdf417.png`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
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

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**Očekávaný výstup v konzoli (příklad)**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

Přesné hodnoty se budou lišit v závislosti na obsahu vašeho makro PDF417 čárového kódu.

## Řešení běžných okrajových případů

| Situace | Doporučený přístup |
|-----------|----------------------|
| **Žádný čárový kód nebyl detekován** | Ověřte cestu k obrázku, ujistěte se, že soubor není poškozený, a potvrďte, že čárový kód je viditelný (dostatečný kontrast). |
| **Částečné makro segmenty** | Použijte `MacroPdf417SegmentsCount` k detekci chybějících částí. Můžete požádat o zbývající segmenty ze zdrojového systému a znovu spustit dekodér. |
| **Velké obrázky způsobující tlak na paměť** | Načtěte obrázek do `System.Drawing.Bitmap` s nižším rozlišením před předáním do `BarCodeReader`. |
| **Ne‑Macro PDF417** | Změňte `DecodeType.MacroPdf417` na `DecodeType.Pdf417`, pokud potřebujete pouze prostý text čárového kódu. |

## Profesionální tipy

- **Batch processing:** Zabalte logiku čtečky do metody, která přijímá seznam cest k souborům. Znovu použijte jednu instanci `BarCodeReader` na vlákno, aby se snížila režie alokací.  
- **Performance:** Pro scénáře s vysokou propustností povolte vlastnost `ReaderOptions` `ReadQuality`, abyste vyvážili rychlost a přesnost.  
- **Security:** Ověřte `CodeText` před jeho použitím v operacích souborového systému, aby se zabránilo útokům typu path traversal.

## Závěr

V tomto tutoriálu jste se naučili, jak dekódovat PDF417 v C# čtením čárových kódů z obrázku, extrahováním všech polí Macro PDF417 a vytvořením kompletního příkladu čtečky čárových kódů v C#. Řešení funguje s nejnovější knihovnou Aspose.BarCode, zpracovává makra s více segmenty a poskytuje praktické rady pro reálné projekty.

Dále prozkoumejte související témata, jako je **čtení QR kódů**, **dávkové zpracování čárových kódů** a **generování PDF417 čárových kódů**, abyste rozšířili svůj nástroj pro automatizaci dokumentů. Klidně experimentujte s různými zdroji obrázků, integrujte kód do služeb ASP.NET nebo jej rozšiřte o ukládání extrahovaných metadat do databáze. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohly zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak číst PDF417 v C# – kompletní příklad čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Jak generovat obrázek PDF417 čárového kódu v C# s Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Čtení čárového kódu z obrázku – příklad čtečky čárových kódů v C#](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}