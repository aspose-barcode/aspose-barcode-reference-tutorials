---
category: general
date: 2026-07-27
description: Jak rychle načíst čárový kód PDF417 v C#. Naučte se číst více čárových
  kódů, dekódovat obrázky a získat metadata Macro PDF417 v kompletním příkladu čárového
  kódu v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: cs
lastmod: 2026-07-27
og_description: Jak číst čárový kód PDF417 v C# pomocí tohoto krok‑za‑krokem průvodce.
  Dekódujte obrázky, pracujte s více čárovými kódy a extrahujte metadata Macro PDF417
  v připraveném příkladu.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Jak číst PDF417 v C# – Kompletní příklad čárového kódu
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Jak číst PDF417 v C# – Kompletní příklad čárového kódu
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 v C# – Kompletní příklad čárového kódu

Už jste se někdy zamysleli **jak číst PDF417** čárový kód v aplikaci C# bez toho, abyste si trhali vlasy? Nejste v tom sami. Ať už vytváříte logistický skener, validátor vstupenek nebo jen potřebujete získat data z PDF417‑kódovaného ID, proces může na první pohled působit trochu tajemně.  

V tomto tutoriálu projdeme **c# barcode example**, který načte obrázek PDF417, zvládne **read multiple barcodes**, pokud jsou přítomny, a extrahuje veškerá užitečná metadata Macro PDF417, která můžete potřebovat.

## Co si vytvoříte

Na konci tohoto návodu budete mít malý konzolový program, který:

1. Načte obrázek čárového kódu z disku.  
2. Dekóduje **PDF417** (včetně Macro PDF417) čárové kódy.  
3. Vytiskne základní informace, jako je typ kódu a text.  
4. Vypíše kompletní sadu polí Macro PDF417 (file ID, segment ID, checksum atd.).  

Žádné externí služby, jen jediný NuGet balíček a několik řádků C#.

## Předpoklady – Co potřebujete před zahájením

- **.NET 6.0** nebo novější (kód funguje také na .NET Framework 4.6+).  
- Nedávná verze knihovny **Aspose.BarCode for .NET** – nainstalujte ji přes NuGet (`Install-Package Aspose.BarCode`).  
- Soubor obrázku, který obsahuje PDF417 čárový kód (demo používá `ExtPDF417Meta.png`).  
- Základní pochopení C# konzolových aplikací (pokud jste napsali „Hello World“, jste v pořádku).

> **Tip:** Pokud nemáte po ruce vzor PDF417, vygenerujte jej na demo stránce Aspose nebo použijte aplikaci pro chytrý telefon, která dokáže vytvářet PDF417 tagy.

## Krok 1: Nastavení projektu a instalace knihovny

Nejprve vytvořte nový konzolový projekt:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Tím se načtou závislosti **c# barcode example**, které potřebujeme. Otevřete `Program.cs` a nahraďte výchozí kód následujícím kostrou:

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
            // We'll fill this in in the next steps.
        }
    }
}
```

## Krok 2: Inicializace Barcode Readeru pro PDF417

Srdcem řešení je třída `BarCodeReader`. Řekneme jí, který soubor má skenovat a o jaký typ čárového kódu nám jde – v tomto případě `DecodeType.Pdf417` nebo makro variantu `DecodeType.MacroPdf417`. Použití makro typu zajišťuje zachycení rozšířených polí.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Proč použít `MacroPdf417` místo obyčejného `Pdf417`? Macro PDF417 nese další metadata (file ID, počet segmentů, časová razítka atd.), na která se spoléhá mnoho reálných aplikací – představte si například přepravní manifesty rozdělené na několik stránek.

## Krok 3: Načtení všech čárových kódů nalezených na obrázku

Jeden obrázek může obsahovat **read multiple barcodes** – například QR kód vedle PDF417. Metoda `ReadBarCodes()` vrací `IEnumerable<BarCodeResult>`, přes který můžeme iterovat.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Pokud obrázek obsahuje jen jeden PDF417, smyčka se stále provede jednou, což udržuje kód flexibilní pro budoucí scénáře, kdy můžete potřebovat **read multiple barcodes** ze stejného skenu.

## Krok 4: Zobrazení základních informací o čárovém kódu

Než se ponoříte do makro polí, je užitečné zobrazit typ čárového kódu a dekódovaný text. To vám pomůže ověřit, že čtečka skutečně rozpoznala PDF417 a ne jinou symbologii.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` bude obsahovat *MacroPdf417* (nebo *Pdf417*, pokud není nastaven příznak macro), zatímco `CodeText` obsahuje surová data zakódovaná v čárovém kódu.

## Krok 5: Extrakce metadat Macro PDF417

Vlastnost `Extended` vám poskytuje podrobný pohled do struktury specifické pro PDF417. Každé pole, které níže vytiskneme, odpovídá přímo specifikaci Macro PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Každý řádek získává jiný kus makro nákladu:

- **FileID** – jedinečný identifikátor pro celý soubor dokumentů.  
- **SegmentID** – která část multi‑segmentního souboru je právě zobrazena.  
- **SegmentsCount** – celkový očekávaný počet segmentů.  
- **FileName, Checksum, FileSize** – užitečné pro ověření integrity přenášeného souboru.  
- **TimeStamp, Addressee, Sender** – volitelná pole, která mnoho logistických systémů zahrnuje.  

Pokud některé z těchto polí v původním čárovém kódu chybí, knihovna vrátí `null` nebo `0`, což můžete podle potřeby ošetřit.

## Krok 6: Spuštění kompletního příkladu

Spojením všeho dohromady získáte kompletní, připravený k spuštění program:

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
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Očekávaný výstup

Když spustíte program proti platnému `ExtPDF417Meta.png`, měli byste vidět něco podobného:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Pokud obrázek obsahuje více než jeden čárový kód,

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak generovat PDF417 čárové kódy – Kompaktní PDF417 kódování](/barcode/english/net/compact-pdf417-encoding/)
- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak číst DataMatrix čárové kódy s Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}