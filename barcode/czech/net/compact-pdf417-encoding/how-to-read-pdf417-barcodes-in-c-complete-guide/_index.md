---
category: general
date: 2026-08-22
description: Jak číst PDF417 čárové kódy v C# pomocí průvodce krok po kroku, zahrnujícího
  čtení více čárových kódů z obrázku a extrakci detailů MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: cs
lastmod: 2026-08-22
og_description: Jak rychle číst PDF417 čárové kódy v C#. Tento tutoriál vám ukáže,
  jak načíst více čárových kódů z obrázku a získat rozšířené informace MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Jak číst čárové kódy PDF417 v C# – kompletní programovací průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak číst čárové kódy PDF417 v C# – kompletní průvodce
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 čárové kódy v C# – kompletní průvodce

Pokud potřebujete **jak číst PDF417** čárové kódy v .NET aplikaci, tento tutoriál vám poskytne připravené řešení. Naučíte se, jak načíst více čárových kódů z jedné obrázku, extrahovat kompletní sadu dat MacroPdf417 a zobrazit je v konzoli. Přístup funguje s knihovnou Aspose.BarCode pro .NET a vyžaduje jen několik řádků kódu.

Čtení čárových kódů z obrázku je běžný úkol v inventárních systémech, validaci vstupenek a správě dokumentů. Na konci tohoto průvodce budete schopni dekódovat jakýkoli PDF417 nebo MacroPdf417 čárový kód, zpracovat několik kódů na jedné fotografii a pochopit rozšířená pole, která MacroPdf417 poskytuje.

## Požadavky

- .NET 6.0 SDK nebo novější (kód také kompiluje s .NET Framework 4.7+)
- Visual Studio 2022 nebo jakýkoli C# editor, který preferujete
- Aspose.BarCode pro .NET NuGet balíček (`Install-Package Aspose.BarCode`)
- Vzorek obrázku, který obsahuje MacroPdf417 čárový kód (např. `MacroPdf417.png`)

Žádná další konfigurace není vyžadována; knihovna interně zajišťuje načítání obrázku a dekódování.

## Jak číst PDF417 čárové kódy z obrázku v C#

Jádrem řešení je třída `BarCodeReader`. Otevře obrázek, detekuje všechny čárové kódy zadaného typu a vrátí kolekci objektů `BarCodeResult`. Následující kód ukazuje kompletní konzolový program.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Proč je každý řádek důležitý

| Krok | Účel |
|------|------|
| **1️⃣ Inicializace** | Vytvoří `BarCodeReader` svázaný s obrázkovým souborem a omezuje detekci na symbologii MacroPdf417, což urychluje zpracování. |
| **2️⃣ Iterace** | `ReadBarCodes()` vrací **všechny** čárové kódy, které odpovídají požadovanému typu, což vám umožní **číst více čárových kódů** bez dalších smyček. |
| **3️⃣ Základní výstup** | Zobrazuje obecný `CodeTypeName` a lidsky čitelný `CodeText`. To je užitečné pro logování nebo rychlou validaci. |
| **4️⃣ Rozšířená data** | MacroPdf417 nese další metadata (ID souboru, počet segmentů, časová razítka atd.). Objekt `Extended.Pdf417` přímo vystavuje každé pole, takže můžete uložit nebo ověřit celý datový paket. |

Spuštěním programu na platném MacroPdf417 obrázku získáte výstup v konzoli podobný následujícímu:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Výstup potvrzuje, že knihovna úspěšně načetla čárový kód, extrahovala text a poskytla všechna pole MacroPdf417.

## Čtení více čárových kódů z jednoho obrázku

Mnoho reálných scénářů umisťuje několik PDF417 symbolů na jeden štítek – představte si přepravní manifest, který obsahuje kód dopravce, sledovací číslo a celní deklaraci. Výše uvedený kód již **čte více čárových kódů**, protože `ReadBarCodes()` vrací výčtový typ se všemi shodami. Žádná další konfigurace není potřeba; stačí projít výsledky ve smyčce, jak je ukázáno.

Pokud chcete omezit čtečku na standardní PDF417 (ne‑macro), zatímco stále zpracováváte několik kódů, nahraďte `DecodeType.MacroPdf417` za `DecodeType.Pdf417`. Zbytek logiky zůstane beze změny.

## Porozumění rozšířeným datům MacroPdf417

MacroPdf417 je rozšířením běžné specifikace PDF417. Rozděluje velké payloady do více segmentů a přidává malou hlavičku, která popisuje celý soubor. Nejrelevantnější pole jsou:

- **MacroPdf417FileID** – jedinečný identifikátor sdílený všemi segmenty stejného souboru.
- **MacroPdf417SegmentID** – pořadové číslo aktuálního segmentu.
- **MacroPdf417SegmentsCount** – celkový očekávaný počet segmentů.
- **MacroPdf417FileName** – volitelný název souboru přenášený s čárovým kódem.
- **MacroPdf417Checksum** – kontrolní hodnota pro celý soubor.
- **MacroPdf417FileSize** – velikost původního binárního payloadu.
- **MacroPdf417TimeStamp** – ISO‑8601 časové razítko, kdy byl čárový kód vygenerován.
- **MacroPdf417Addressee / Sender** – volitelná textová pole pro směrování.
- **MacroPdf417Terminator** – označuje, zda je tento segment poslední.

Když obdržíte všechny segmenty, můžete rekonstruovat původní soubor seřazením podle `MacroPdf417SegmentID` a spojováním hodnot `CodeText`. Tato logika je jednoduchá na implementaci, jakmile máte pole k dispozici.

## Časté úskalí a tipy

- **Kvalita obrázku má význam** – nízké rozlišení nebo silně komprimované PNG/JPEG soubory mohou způsobit neúspěšné detekce. Používejte DPI alespoň 300 dpi pro tištěné čárové kódy.
- **Smíšené symbologie** – pokud obrázek obsahuje jak MacroPdf417, tak běžný PDF417, vytvořte dvě čtečky (jednu pro každý `DecodeType`) nebo použijte `DecodeType.AllSupported` a filtrujte výsledky podle `result.CodeTypeName`.
- **Spotřeba paměti** – příkaz `using` okamžitě uvolní `BarCodeReader`, čímž zabrání tomu, aby velké obrazové buffery zůstaly v paměti.
- **Bezpečnost vlákna** – `BarCodeReader` není thread‑safe. Vytvořte samostatnou instanci pro každé vlákno, pokud dekódujete obrázky paralelně.
- **Zpracování chyb** – obalte volání `ReadBarCodes()` do try/catch bloku a zachyťte `BarCodeException` pro poškozené obrázky.

## Přehled kompletního funkčního příkladu

Níže je kompletní program, který můžete zkopírovat do nového konzolového projektu. Obsahuje všechny `using` direktivy, konstantu pro cestu k obrázku a vzor pro uvolnění prostředků.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
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

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Zkompilujte pomocí `dotnet build` a spusťte pomocí `dotnet run`. Konzole vypíše základní data každého čárového kódu a celý payload MacroPdf417.

## Další kroky

- **Rekonstruovat multipart soubory** – shromáždit všechny segmenty, seřadit podle `MacroPdf417SegmentID` a spojit `CodeText` do

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak generovat PDF417 čárový kód – Kompaktní PDF417 kódování](/barcode/english/net/compact-pdf417-encoding/)
- [Jak číst PDF417 čárové kódy s tureckými znaky v Javě](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Jak používat Aspose pro PDF417 čárový kód (čínština) v Javě](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}