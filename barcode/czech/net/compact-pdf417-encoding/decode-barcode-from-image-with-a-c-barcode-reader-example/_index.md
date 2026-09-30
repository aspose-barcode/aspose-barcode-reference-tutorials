---
category: general
date: 2026-09-10
description: Naučte se, jak dekódovat čárový kód z obrázku pomocí stručného příkladu
  čtečky čárových kódů v C#, který čte kódy Macro PDF417 během několika řádků.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: cs
lastmod: 2026-09-10
og_description: Dekódujte čárový kód z obrázku pomocí krátkého příkladu čtečky čárových
  kódů v C#. Postupujte podle průvodce krok za krokem a okamžitě přečtěte data Macro
  PDF417.
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: Dekódujte čárový kód z obrázku pomocí příkladu čtečky čárových kódů v C#.
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Dekódujte čárový kód z obrázku pomocí příkladu čtečky čárových kódů v C#
url: /cs/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dekódujte čárový kód z obrázku pomocí příkladu čtečky čárových kódů v C#

Pokud potřebujete **dekódovat čárový kód z obrázku**, tento průvodce vám přesně ukáže, jak to provést v C#. Pomocí kompaktního **příkladu čtečky čárových kódů v C#** přečtete data Macro PDF417 pomocí jen několika řádků kódu.

Uvidíte kompletní spustitelný program, pochopíte, proč je každá část důležitá, a naučíte se tipy, které zabraňují běžným chybám. Žádná externí dokumentace není potřeba — vše, co potřebujete, je zde.

## Co se naučíte

- Nastavit požadovaný NuGet balíček pro dekódování čárových kódů.  
- Napsat **příklad čtečky čárových kódů v C#**, který otevře soubor s obrázkem a extrahuje každý čárový kód.  
- Přistupovat k rozšířeným polím Macro PDF417, jako je ID souboru.  
- Ověřit výstup a přizpůsobit kód pro jiné typy čárových kódů.

### Předpoklady

- .NET 6.0 SDK nebo novější (kód také funguje s .NET Core 3.1 a .NET Framework 4.7+).  
- Základní znalost C# konzolových aplikací.  
- Soubor s obrázkem, který obsahuje čárový kód Macro PDF417 (např. `MacroPdf417.png`).  

## Krok 1: Nainstalujte knihovnu pro čárové kódy

Příklad používá **Aspose.BarCode for .NET**, široce používanou knihovnu, která podporuje dekódování Macro PDF417.

```bash
dotnet add package Aspose.BarCode
```

> **Proč tato knihovna?**  
> Poskytuje jedinou třídu `BarCodeReader`, která zvládá mnoho formátů, nabízí vysokou přesnost a vrací rozšířené informace pro kódy Macro PDF417 — vše bez další konfigurace.

## Krok 2: Vytvořte příklad čtečky čárových kódů v C#

Vytvořte nový konzolový projekt a nahraďte vygenerovaný soubor `Program.cs` kódem níže. Příklad provádí tři jasné kroky:

1. **Inicializovat** `BarCodeReader` pro cílový obrázek.  
2. **Iterovat** přes každý detekovaný čárový kód.  
3. **Vytisknout** standardní a rozšířená data Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### Vysvětlení jednotlivých částí

- **Konstruktor `BarCodeReader`** – První argument je cesta k obrázku; druhý říká knihovně, aby hledala konkrétně kódy Macro PDF417. Toto zaměřené dekódování zlepšuje výkon oproti skenování všech možných formátů.  
- **`ReadBarCodes()`** – Vrací výčtový seznam všech čárových kódů detekovaných na obrázku, což vám umožní zpracovat více kódů v jednom souboru.  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 ukládá další metadata (ID souboru, počet segmentů atd.). Příklad kontroluje, zda není null, aby se předešlo `NullReferenceException`, když obrázek obsahuje ne‑Macro čárový kód.

## Krok 3: Spusťte program a ověřte výstup

Build and run the console application:

```bash
dotnet run
```

Měli byste vidět výstup podobný:

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

Pokud obrázek neobsahuje čárový kód Macro PDF417, program stále vypíše všechny ostatní detekované formáty, ale rozšířené pole bude vynecháno.

## Profesionální tip: Dekódujte jiné typy čárových kódů bez velkých úprav kódu

Pro **dekódování čárového kódu z obrázku** pro jiný formát změňte hodnotu enumu `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

Můžete také předat `DecodeType.AllSupportedTypes`, aby knihovna detekovala jakýkoli čárový kód, který zná.

## Časté problémy a jak se jim vyhnout

| Příznak | Příčina | Oprava |
|---------|----------|--------|
| Žádný výstup | Špatná cesta k obrázku nebo nepodporovaný formát souboru | Ověřte cestu, ujistěte se, že soubor je podporovaný obrázek (PNG, JPEG, BMP) |
| `result.Extended` je null pro Macro PDF417 | Čárový kód není variantou Macro PDF417 | Potvrďte, že zdrojový obrázek skutečně obsahuje kód Macro PDF417 |
| Výjimka `System.IO.FileNotFoundException` | Chybějící NuGet balíček za běhu | Spusťte `dotnet restore` a ujistěte se, že `Aspose.BarCode.dll` je zkopírována do výstupního adresáře |

## Kompletní výpis zdrojového kódu pro rychlé zkopírování

Níže je celý program, připravený ke zkopírování do `Program.cs`. Žádné další soubory nejsou potřeba.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## Další kroky

- **Prozkoumat další rozšířená pole** jako `MacroPdf417SegmentID` nebo `MacroPdf417FileSize` pro vytvoření workflow pro rekonstrukci celých dokumentů.  
- **Integrovat čtečku do webového API**, aby klienti mohli nahrávat obrázky a okamžitě získávat dekódovaná data.  
- **Měřit výkon** dekódováním velkých dávek obrázků; `BarCodeReader` podporuje asynchronní zpracování v novějších verzích Aspose.

---

Podle tohoto **příkladu čtečky čárových kódů v C#** nyní máte spolehlivý způsob, jak **dekódovat čárový kód z obrázku** a získat bohaté informace Macro PDF417. Experimentujte s různými hodnotami `DecodeType`, kombinujte tuto logiku s monitorováním souborů nebo ji vložte do mobilních backendů — vaše schopnosti zpracování čárových kódů jsou připraveny na škálování.

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}