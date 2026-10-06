---
category: general
date: 2026-10-05
description: Čtení čárového kódu z obrázku v C# pomocí Aspose.BarCode. Naučte se krok
  za krokem skenování čárových kódů v C#, dekódování Macro PDF417 a práci s rozšířenými
  vlastnostmi.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- C# barcode scanning
- Macro PDF417 decoding
- Aspose.BarCode for .NET
- decode barcode image C#
language: cs
lastmod: 2026-10-05
og_description: Číst čárový kód z obrázku v C# s Aspose.BarCode. Tento tutoriál ukazuje,
  jak naskenovat makro‑PDF417 čárový kód, získat rozšířená pole a pracovat s více
  kódy.
og_image_alt: Screenshot of C# console output showing barcode type and Macro PDF417
  properties
og_title: Čtení čárového kódu z obrázku v C# – kompletní návod krok po kroku
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Read barcode from image C# using Aspose.BarCode. Learn step‑by‑step
    C# barcode scanning, decode Macro PDF417 and handle extended properties.
  headline: Read barcode from image C# – complete guide with Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- image-processing
title: Čtení čárového kódu z obrázku v C# – kompletní průvodce s Macro PDF417
url: /cs/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Číst čárový kód z obrázku C# – kompletní průvodce s Macro PDF417

Pokud potřebujete **číst čárový kód z obrázku C#**, tento tutoriál vám ukáže připravené řešení. Pomocí knihovny Aspose.BarCode pro .NET dekódujete čárový kód Macro PDF417, získáte jeho základní data a vytáhnete všechny rozšířené vlastnosti, které formát poskytuje.

Čtení čárových kódů z obrázků je běžná potřeba – ať už vytváříte systém pro ověřování vstupenek, zpracováváte přepravní štítky nebo extrahujete metadata ze skenovaných dokumentů. V následujících krocích uvidíte, proč je třída `BarCodeReader` doporučeným přístupem, jak ji nakonfigurovat pro Macro PDF417 a co dělat s výsledky.

---

## Co se naučíte

* Nainstalovat a odkazovat na **Aspose.BarCode for .NET** (knihovna, která pohání příklad).  
* Vytvořit `BarCodeReader` nakonfigurovaný pro **dekódování Macro PDF417**.  
* Iterovat přes všechny čárové kódy v obrázku a vypisovat jak standardní, tak rozšířená pole.  
* Zpracovávat více čárových kódů, správně spravovat prostředky a řešit běžné problémy.

**Požadavky**

* .NET 6.0 SDK nebo novější (kód také funguje s .NET Framework 4.6+).  
* Základní znalost C# konzolových aplikací.  
* Obrázkový soubor, který obsahuje čárový kód Macro PDF417 (např. `ExtPDF417Meta.png`).  

---

## Krok 1: Přidejte Aspose.BarCode do svého projektu (C# skenování čárových kódů)

1. Otevřete terminál ve složce řešení.  
2. Spusťte příkaz NuGet:

```bash
dotnet add package Aspose.BarCode
```

Balíček obsahuje třídu `BarCodeReader`, výčtový typ `DecodeType` a objekt `BarCodeResult`, který se používá v celém tutoriálu.

> **Pro tip:** Pokud cílíte na .NET Framework, použijte Package Manager Console ve Visual Studio:  
> `Install-Package Aspose.BarCode`

---

## Krok 2: Nastavte konzolový program (dekódování čárového kódu z obrázku C#)

Vytvořte nový konzolový projekt (nebo přidejte kód do existujícího):

```csharp
using System;
using Aspose.BarCode;               // Core namespace
using Aspose.BarCode.BarCodeRecognition; // For DecodeType and BarCodeReader

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains a Macro PDF417 barcode.
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Step 2.1: Initialise the BarCodeReader for Macro PDF417.
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath, DecodeType.MacroPdf417))
            {
                // Step 2.2: Read every barcode present in the image.
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    // Step 2.3: Output basic information.
                    Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                    // Step 2.4: Output Macro PDF417 extended properties.
                    PrintMacroPdf417Properties(barcodeResult);
                }
            }

            // Keep console window open for inspection.
            Console.WriteLine("\nPress any key to exit...");
            Console.ReadKey();
        }

        /// <summary>
        /// Writes all Macro PDF417 extended fields to the console.
        /// </summary>
        /// <param name="result">Result object returned by BarCodeReader.</param>
        private static void PrintMacroPdf417Properties(BarCodeResult result)
        {
            // The Extended property is null if the barcode type does not support it.
            if (result?.Extended?.Pdf417 == null)
            {
                Console.WriteLine("No Macro PDF417 extended data available.");
                return;
            }

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
        }
    }
}
```

### Proč tato struktura?

* **`using` statement** – zajišťuje, že `BarCodeReader` uvolní nativní prostředky (důležité pro velké obrázky).  
* **`DecodeType.MacroPdf417`** – říká knihovně, aby konkrétně hledala Macro PDF417; jiné typy (např. QR, Code128) by rozšířená pole ignorovaly.  
* **`ReadBarCodes()`** – vrací enumerable, což umožňuje zpracovat **více čárových kódů** ve stejném obrázku bez dalšího kódu.  
* **Separate `PrintMacroPdf417Properties` method** – odděluje logiku rozšířených polí, usnadňuje čtení hlavní smyčky a zjednodušuje budoucí údržbu.

---

## Krok 3: Spusťte program a ověřte výstup (dekódování Macro PDF417)

Otevřete příkazový řádek, přejděte do složky projektu a spusťte:

```bash
dotnet run
```

Měli byste vidět výstup podobný následujícímu (hodnoty se liší podle konkrétního čárového kódu):

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B3C4D
Pdf417MacroFileSize: 1048576
Pdf417MacroTimeStamp: 2023-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True

Press any key to exit...
```

Pokud obrázek neobsahuje čárový kód Macro PDF417, konzole zobrazí **„No Macro PDF417 extended data available.“** Toto elegantní zpracování zabraňuje výjimkám typu null‑reference.

---

## Krok 4: Běžné varianty a okrajové případy (tipy pro skenování čárových kódů v C#)

| Situace | Doporučené úpravy |
|-----------|------------------------|
| **Více typů čárových kódů v jednom obrázku** | Inicializujte čtečku s `DecodeType.AllSupported` a prohlédněte `barcodeResult.CodeTypeName`, abyste rozvětvili logiku. |
| **Velké obrázky (≥10 MP)** | Zvyšte `barcodeReader.Options.MaxBarCodeCount` nebo použijte `barcodeReader.SetResolution(300)` pro zlepšení rychlosti detekce. |
| **Chybějící rozšířená pole** | Některé skenery odstraňují Macro data; ověřte, že zdrojový obrázek obsahuje pole pomocí nástroje pro kontrolu čárových kódů před kódováním. |
| **Běh na Linux/macOS** | Ujistěte se, že jsou přítomny nativní binární soubory pro Aspose.BarCode (`Aspose.BarCode.Native` NuGet balíček) nebo nastavte `Environment.SetEnvironmentVariable("DOTNET_SYSTEM_GLOBALIZATION_INVARIANT", "1")`, pokud potřebujete jen ASCII data. |
| **Smyčky kritické na výkon** | Uložte instanci `BarCodeReader` do cache a znovu ji použijte pro dávku obrázků; uvolněte ji až po dokončení dávky. |

---

## Krok 5: Závěr a další kroky (čtení čárového kódu z obrázku C#)

Nyní máte **kompletní, samostatné řešení** pro čtení čárového kódu Macro PDF417 z obrázku v C#. Příklad ukazuje:

* Správnou **instalaci** knihovny Aspose.BarCode.  
* Vytvoření **`BarCodeReader`** nakonfigurovaného pro **Macro PDF417**.  
* Iteraci přes **všechny čárové kódy** v dodaném obrázku.  
* Extrahování **standardních** (`CodeTypeName`, `CodeText`) **a rozšířených** metadat Macro PDF417.  

### Co prozkoumat dál?

* **Dekódovat jiné formáty** – nahraďte `DecodeType.MacroPdf417` za `DecodeType.QR`, `DecodeType.Code128` atd.  
* **Integrace s ASP.NET Core** – vystavte Web API endpoint, který přijímá nahrání obrázku a vrací JSON s daty čárového kódu.  
* **Ukládat výsledky** – uložte extrahovaná metadata do databáze pro pozdější analýzu.  
* **Kombinovat s OCR** – použijte Aspose.OCR k načtení textu, který není zakódován jako čárový kód.

Neváhejte experimentovat se vzorovým obrázkem, upravit cestu k souboru nebo vložit logiku do větší aplikace. Třída **`BarCodeReader`** poskytuje robustní základ pro jakýkoli **C# scénář skenování čárových kódů**.

--- 

*Šťastné programování! Pokud narazíte na problémy, dvakrát zkontrolujte, že obrázek skutečně obsahuje čárový kód Macro PDF417 a že verze Aspose.BarCode odpovídá vašemu .NET runtime.*

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Číst čárový kód z obrázku v C# – tutoriál BarCodeReader](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/)
- [Jak vygenerovat obrázek PDF417 čárového kódu v C# pomocí Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}