---
category: general
date: 2026-09-26
description: Naučte se, jak dekódovat PDF417 v C# pomocí krok‑za‑krokem příkladu čtečky
  čárových kódů. Tento průvodce vám ukáže, jak číst obrázek čárového kódu v C# pomocí
  Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: cs
lastmod: 2026-09-26
og_description: Jak rychle dekódovat PDF417 v C#. Sledujte tento příklad čtečky čárových
  kódů, jak načíst obrázek čárového kódu v C# pomocí Aspose.BarCode a získat podrobnosti
  makra.
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: Jak dekódovat PDF417 v C# – kompletní průvodce čtečkou čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: Jak dekódovat PDF417 v C# – příklad čtečky čárových kódů
url: /cs/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekódovat PDF417 v C# – příklad čtečky čárových kódů

Pokud potřebujete **jak dekódovat PDF417** v .NET aplikaci, tento tutoriál poskytuje kompletní, připravené řešení. Ukážeme si, jak pomocí knihovny Aspose.BarCode v C# načíst obrázek čárového kódu, získat rozšířené informace PDF417 macro a zobrazit všechna relevantní pole.

Dekódování PDF417 není omezeno jen na prostý text; formát může nést data o segmentaci souboru, časová razítka a kontrolní součty. Tento průvodce vás provede každým krokem, vysvětlí, proč je kód strukturován tak, jak je, a upozorní na běžné úskalí, na která můžete narazit při implementaci příkladu čtečky čárových kódů v C#.

## Předpoklady

Než začnete, ujistěte se, že máte:

* .NET 6.0 (nebo novější) SDK nainstalované  
* Visual Studio 2022 (nebo jakékoli IDE kompatibilní s C#)  
* **Aspose.BarCode for .NET** NuGet balíček (`Aspose.BarCode`)  
* Ukázkový obrázek Macro PDF417 (např. `ExtPDF417Meta.png`)

Tyto požadavky zajišťují, že kód se zkompiluje a spustí bez další konfigurace.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Prvním krokem v jakémkoli **read barcode image C#** projektu je přidání knihovny pro čárové kódy. Otevřete terminál ve složce řešení a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček poskytuje `BarCodeReader`, `DecodeType` a vlastnost `Extended`, která slouží k přístupu k makro datům. Jednorázová instalace zpřístupní třídy v celém projektu.

## Krok 2: Vytvoření čtečky čárových kódů pro obrázek Macro PDF417

Nyní můžete vytvořit instanci `BarCodeReader` s cestou k obrázku a specifikovat `DecodeType.MacroPdf417`. Tím řeknete knihovně, aby hledala rozšířený formát PDF417 obsahující makro informace.

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**Proč je to důležité:**  
`DecodeType.MacroPdf417` aktivuje parser specifický pro makra. Pokud jej vynecháte, čtečka vrátí jen prostý textový payload a ignoruje makro pole, která pravděpodobně potřebujete pro rekonstrukci souboru.

## Krok 3: Načtení všech čárových kódů nalezených na obrázku

Jeden obrázek může obsahovat více symbolů PDF417, zejména když jsou data rozdělena do segmentů. Procházení pomocí `ReadBarCodes()` zaručuje, že zachytíte každý segment.

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**Proč smyčka:**  
Makro data PDF417 se často objevují v několika segmentech. Zpracování každého `BarCodeResult` zajistí, že shromáždíte kompletní sadu makro polí, jako jsou `MacroPdf417FileID` a `MacroPdf417SegmentsCount`.

## Krok 4: Získání a zobrazení základních dat čárového kódu

Objekt `BarCodeResult` obsahuje typ a dekódovaný text. Zobrazení těchto hodnot pomáhá ověřit, že čtečka správně identifikovala symbol, než se pustíte do detailů makra.

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**Tip:** Pokud je `CodeText` prázdný, může být obrázek poškozený nebo je nastaven nesprávný režim dekódování. Zkontrolujte použité `DecodeType` při inicializaci.

## Krok 5: Extrakce rozšířených informací PDF417 macro

Makro data jsou uložena pod `barcodeResult.Extended.Pdf417`. Každá vlastnost odpovídá poli definovanému ve specifikaci PDF417.

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**Co jednotlivá pole znamenají**

| Property | Description |
|----------|-------------|
| `MacroPdf417FileID` | Identifikátor, který seskupuje všechny segmenty patřící ke stejnému logickému souboru. |
| `MacroPdf417SegmentID` | Index aktuálního segmentu (počínaje 1). |
| `MacroPdf417SegmentsCount` | Celkový počet segmentů potřebných k rekonstrukci původního souboru. |
| `MacroPdf417FileName` | Volitelný název souboru vložený do makra. |
| `MacroPdf417Checksum` | CRC‑16 kontrolní součet pro ověření integrity. |
| `MacroPdf417FileSize` | Očekávaná velikost rekonstruovaného souboru (v bajtech). |
| `MacroPdf417TimeStamp` | Datum‑čas, kdy bylo makro vygenerováno. |
| `MacroPdf417Addressee` | Volitelný identifikátor příjemce. |
| `MacroPdf417Sender` | Volitelný identifikátor odesílatele. |
| `MacroPdf417Terminator` | Příznak terminátoru; měl by být `true` u posledního segmentu. |

Porozumění těmto polím vám umožní znovu sestavit původní soubor, ověřit integritu dat a implementovat vlastní obchodní logiku (např. odmítnout zastaralé dokumenty).

## Krok 6: Zpracování více segmentů a znovuvytvoření původního souboru (pokročilé)

Když je `MacroPdf417SegmentsCount` větší než 1, musíte shromáždit každý segment, seřadit je podle `MacroPdf417SegmentID` a spojit hodnoty `CodeText`. Níže je stručná implementace:

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**Proč je to důležité:**  
Bez řazení a spojování by dekódovaná data byla neúplná nebo poškozená. Úryvek také ukazuje obranné programování kontrolou počtu segmentů.

## Krok 7: Závěr s ošetřením chyb a osvědčenými postupy

Produkčně připravený **c# barcode reader example** by měl předvídat IO chyby, nepodporované formáty a poškozené obrázky.

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**Seznam osvědčených postupů**

* Ověřte cestu k obrázku před vytvořením `BarCodeReader`.  
* Používejte `using` bloky k zajištění uvolnění neřízených prostředků.  
* Logujte makro pole pro auditní stopy — zejména `MacroPdf417Checksum` a `MacroPdf417TimeStamp`.  
* Při práci s velkými soubory zvažte streamování spojeného payloadu na disk místo jeho úplného uložení v paměti.

## Očekávaný výstup

Spuštění kompletního programu proti platnému souboru `ExtPDF417Meta.png` vygeneruje výstup podobný tomuto:

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

Pokud jsou přítomny všechny tři segmenty, blok pro rekonstrukci vytiskne celý payload po ověřovací zprávě.

## Závěr

Nyní už víte **jak dekódovat PDF417** v C# pomocí robustního příkladu čtečky čárových kódů. Tutoriál pokryl instalaci Aspose.BarCode, inicializaci `BarCodeReader` pro Macro PDF417, iteraci přes více čárových kódů, extrakci makro polí, sestavení segmentovaných dat a implementaci ošetření chyb.  

Dále můžete:

* Integrovat čtečku do webového API, které přijímá nahrané obrázky.  
* Ukládat makro metadata do databáze pro auditní účely.  
* Rozšířit řešení na další 2‑D symbologie změnou `DecodeType` (e

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vlastních projektech.

- [Jak číst PDF417 v C# – kompletní příklad čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Jak vytvořit PDF417 čárový kód s Aspose – kompletní průvodce krok za krokem](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Číst PDF417 čárový kód v C# – příklad čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}