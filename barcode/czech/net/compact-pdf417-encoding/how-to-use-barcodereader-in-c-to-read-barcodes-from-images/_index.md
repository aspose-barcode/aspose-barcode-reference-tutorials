---
category: general
date: 2026-11-23
description: Naučte se, jak používat BarCodeReader v C# k načítání čárových kódů z
  obrázku, včetně dekódování Macro PDF417, s kompletním příkladem kódu a jasnými vysvětleními.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use barcodereader
- read barcodes from image c#
language: cs
lastmod: 2026-11-23
og_description: Jak použít BarCodeReader v C# k načtení čárových kódů z obrázku. Postupujte
  podle tohoto krok‑za‑krokem průvodce a dekódujte Macro PDF417 a další formáty s
  připraveným kódem připraveným k okamžitému spuštění.
og_image_alt: Screenshot of BarCodeReader console output showing decoded Macro PDF417
  data
og_title: Jak používat BarCodeReader v C# – rychle číst čárové kódy z obrázků
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  headline: How to use BarCodeReader in C# to read barcodes from images
  type: TechArticle
- description: Learn how to use BarCodeReader in C# to read barcodes from an image,
    including Macro PDF417 decoding, with a complete code example and clear explanations.
  name: How to use BarCodeReader in C# to read barcodes from images
  steps:
  - name: 1. Decoding multiple barcode formats
    text: 'If you need to detect more than one format, pass a combined `DecodeType`
      flag:'
  - name: 2. Managing large images
    text: 'Large images can cause high memory usage. Downscale the image before passing
      it to the reader:'
  - name: 3. Error handling
    text: 'Wrap the reading logic in a try‑catch block to surface decoding failures:'
  type: HowTo
tags:
- barcode
- C#
- image-processing
title: Jak použít BarCodeReader v C# k načtení čárových kódů z obrázků
url: /cs/net/compact-pdf417-encoding/how-to-use-barcodereader-in-c-to-read-barcodes-from-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak používat BarCodeReader v C# pro čtení čárových kódů z obrázků

Pokud potřebujete **jak používat BarCodeReader** pro rychlé skenování čárových kódů, tento průvodce vám přesně ukáže, jak na to. Ať už vytváříte systém pokladny nebo automatizujete zpracování dokumentů, naučíte se číst čárové kódy z obrázků v C# projektech pomocí několika řádků kódu.

V tomto tutoriálu uvidíte kompletní, spustitelný příklad, který dekóduje čárový kód Macro PDF417, získá jeho rozšířené vlastnosti a vypíše užitečné informace do konzole. Není potřeba žádná externí dokumentace – vše, co potřebujete, je zde.

## Požadavky

* .NET 6.0 (nebo novější) nainstalovaný – kód cílí na nejnovější LTS verzi.
* Odkaz na NuGet balíček **Aspose.BarCode** (nebo jakýkoli kompatibilní), který poskytuje `BarCodeReader`.
* Soubor s obrázkem obsahujícím čárový kód Macro PDF417 (příklad používá `ExtPDF417Meta.png`).

> **Tip:** Pokud používáte Visual Studio, přidejte balíček pomocí `dotnet add package Aspose.BarCode` nebo přes UI NuGet Package Manager.

## Krok 1: Vytvořte instanci BarCodeReader

Prvním krokem při práci s knihovnou čárových kódů je vytvořit čtečku, která ukazuje na zdrojový obrázek a informuje API, jaké typy čárových kódů má hledat.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Step 1: Initialise BarCodeReader for a Macro PDF417 image
using (BarCodeReader barcodeReader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png",
           DecodeType.MacroPdf417))
{
    // The using block guarantees proper disposal of native resources.
```

*Proč je tento krok důležitý:*  
`BarCodeReader` otevře obrázek, alokuje nativní paměť a připraví dekódovací algoritmy pro zadaný `DecodeType`. Omezením typu na `MacroPdf417` snížíte zátěž CPU a zlepšíte přesnost detekce.

## Krok 2: Přečtěte všechny čárové kódy nalezené na obrázku

Jeden obrázek může obsahovat více čárových kódů, zejména při práci s makro‑kódovanými daty. Metoda `ReadBarCodes` vrací výčtový typ objektů `BarCodeResult`, z nichž každý představuje jeden detekovaný kód.

```csharp
    // Step 2: Iterate over every barcode found
    foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
    {
```

*Proč je tento krok důležitý:*  
Iterací přes kolekci zajistíte zachycení každé instance, což je nezbytné pro scénáře dávkového zpracování nebo když dokument obsahuje několik kódů.

## Krok 3: Přístup k rozšířeným vlastnostem Macro PDF417

Macro PDF417 ukládá další metadata, jako jsou identifikátory souborů, čísla segmentů a celkový počet segmentů. Tyto hodnoty jsou zpřístupněny přes vlastnost `Extended.Pdf417` objektu `BarCodeResult`.

```csharp
        // Step 3: Pull extended Macro PDF417 information
        var macroInfo = barcodeResult.Extended.Pdf417;
```

*Proč je tento krok důležitý:*  
Rozšířené pole vám umožní zrekonstruovat více‑segmentové dokumenty nebo ověřit, že všechny části patří ke stejnému zdroji. Vynechání tohoto kroku vám poskytne pouze surový text a ztratíte cenný kontext.

## Krok 4: Výstup nejdůležitějších informací

Nakonec zapište data do konzole (nebo jakéhokoli loggeru), abyste mohli ověřit operaci čtení. Příklad vypisuje typ kódu, dekódovaný text a několik makro polí.

```csharp
        // Step 4: Display key details
        Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
        Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
        Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
        // Additional macro fields are available:
        // macroInfo.MacroPdf417SegmentID
        // macroInfo.MacroPdf417SegmentsCount
    }
}
```

**Očekávaný výstup v konzoli**

```
Code Type: MacroPdf417
Code Text: 1234567890
Macro PDF417 File ID: 42
```

> **Poznámka:** Pokud obrázek neobsahuje čárový kód Macro PDF417, `ReadBarCodes()` vrátí prázdnou kolekci a tělo smyčky se nikdy neprovede. V produkčním kódu vždy kontrolujte, zda výsledek není prázdný.

## Čtení čárových kódů z obrázku v C# – řešení běžných scénářů

### 1. Dekódování více formátů čárových kódů

Pokud potřebujete detekovat více než jeden formát, předávejte kombinovaný příznak `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(
           "sample.png",
           DecodeType.Pdf417 | DecodeType.QR | DecodeType.DataMatrix))
{
    // Same iteration logic as before
}
```

### 2. Správa velkých obrázků

Velké obrázky mohou způsobovat vysokou spotřebu paměti. Před předáním čtečce zmenšete obrázek:

```csharp
using (Bitmap original = new Bitmap("large.png"))
using (Bitmap resized = new Bitmap(original, new Size(1024, 768)))
{
    // Save resized image to a temporary stream and feed it to BarCodeReader
}
```

### 3. Ošetření chyb

Zabalte logiku čtení do bloku try‑catch, aby se zobrazily chyby dekódování:

```csharp
try
{
    // reading code from previous steps
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Kompletní funkční příklad

Níže je kompletní program, který můžete zkopírovat, vložit a spustit. Obsahuje všechny kroky, potřebné `using` direktivy a jednoduchý rámec pro ošetření chyb.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(
                       imagePath,
                       DecodeType.MacroPdf417))
            {
                bool anyFound = false;

                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    anyFound = true;
                    var macroInfo = barcodeResult.Extended.Pdf417;

                    Console.WriteLine($"Code Type: {barcodeResult.CodeTypeName}");
                    Console.WriteLine($"Code Text: {barcodeResult.CodeText}");
                    Console.WriteLine($"Macro PDF417 File ID: {macroInfo.MacroPdf417FileID}");
                    Console.WriteLine($"Segment ID: {macroInfo.MacroPdf417SegmentID}");
                    Console.WriteLine($"Segments Count: {macroInfo.MacroPdf417SegmentsCount}");
                    Console.WriteLine(new string('-', 40));
                }

                if (!anyFound)
                {
                    Console.WriteLine("No barcodes were detected in the image.");
                }
            }
        }
        catch (BarCodeException ex)
        {
            Console.Error.WriteLine($"Error reading barcode: {ex.Message}");
        }
    }
}
```

**Spuštění programu** vypíše každý detekovaný Macro PDF417 čárový kód a jeho rozšířená pole, nebo vás informuje, že nebyly nalezeny žádné čárové kódy.

## Závěr

Nyní víte **jak používat BarCodeReader** k čtení čárových kódů z obrázků v C# aplikacích, včetně získávání metadat Macro PDF417. Řešení zahrnuje inicializaci, iteraci, přístup k rozšířeným vlastnostem a praktické tipy pro práci s více formáty, velkými obrázky a chybami.

Dále můžete zkoumat:

* **Čtení QR kódů** – nahraďte `DecodeType.MacroPdf417` za `DecodeType.QR`.
* **Ukládání dekódovaných dat** do databáze nebo JSON souboru pro následné zpracování.
* **Integraci s ASP.NET Core** pro přijímání nahraných obrázků přes webové API.

Neváhejte experimentovat s různými typy čárových kódů a zdroji obrázků. Šťastné programování!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [c# tutorial čtečky čárových kódů – čtení Macro PDF417 kódů krok za krokem pomocí GroupDocs.Barcode](/barcode/english/net/compact-pdf417-encoding/c-barcode-reader-tutorial-read-macro-pdf417-barcodes-step-by/)
- [Jak použít generátor čárových kódů C# pro Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/)
- [Čtení čárového kódu z obrázku C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}