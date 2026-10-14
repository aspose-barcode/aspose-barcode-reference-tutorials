---
category: general
date: 2026-10-02
description: Naučte se, jak číst čárový kód z obrázku v C# s kompletním příkladem,
  který ukazuje, jak dekódovat čárový kód PDF417 pomocí Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: cs
lastmod: 2026-10-02
og_description: Čtěte čárový kód z obrázku v C# pomocí Aspose.BarCode. Tento tutoriál
  vysvětluje, jak dekódovat čárový kód PDF417 a extrahovat rozšířené metadata.
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: Čtení čárového kódu z obrázku v C# – krok za krokem
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak načíst čárový kód z obrázku v C# pomocí Aspose.BarCode
url: /cs/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód z obrázku c# pomocí Aspose.BarCode

Pokud potřebujete **číst čárový kód z obrázku c#**, tento průvodce vás provede kompletním, spustitelným řešením. Naučíte se, jak dekódovat PDF417 čárový kód, získat jeho rozšířená makro data a vytisknout výsledky do konzole.

Čtení čárových kódů z obrázků je běžná potřeba pro inventární systémy, ověřování vstupenek a zpracování dokumentů. Tento tutoriál pokrývá vše, co potřebujete: požadované balíčky, vysvětlení kódu, ošetření okrajových případů a očekávaný výstup. Žádná externí dokumentace není nutná; příklad funguje hned po vybalení s Aspose.BarCode .NET.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* NuGet referenci na **Aspose.BarCode** (verze 23.10 nebo novější)  
* Soubor obrázku, který obsahuje PDF417 čárový kód – například `ExtPDF417Meta.png`

Pokud některá z těchto položek chybí, nainstalujte .NET SDK, přidejte NuGet balíček pomocí `dotnet add package Aspose.BarCode` a umístěte obrázek do složky, na kterou můžete odkazovat z vašeho projektu.

## Jak číst čárový kód z obrázku c# – krok za krokem

Následující sekce rozdělují implementaci do logických kroků. Každý krok obsahuje úryvek kódu, vysvětlení **proč** je krok důležitý, a tip, který můžete použít v reálných projektech.

### Krok 1: Vytvořte `BarCodeReader` pro PDF417 obrázek

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**Proč je to důležité** – Konstruktor `BarCodeReader` přijímá cestu k obrázku a očekávaný typ čárového kódu. Zadání `MacroPdf417` zužuje hledání, což zlepšuje výkon a snižuje falešně pozitivní výsledky, když obrázek obsahuje více symbologií.

**Profesionální tip:** Pokud si nejste jisti typem čárového kódu, použijte `DecodeType.AllSupportedTypes` a výsledky později filtrujte.

### Krok 2: Procházejte všechny detekované čárové kódy

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**Proč je to důležité** – PDF417 makro obrázek může obsahovat několik segmentů. Metoda `ReadBarCodes()` vrací kolekci, která vám umožní zpracovat každý segment samostatně.

**Okrajový případ:** Pokud obrázek neobsahuje žádné PDF417 symboly, kolekce je prázdná a tělo smyčky se nikdy neprovede. Zvažte přidání kontroly po smyčce, která uživatele informuje.

### Krok 3: Získejte rozšířené PDF417 makro metadata

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**Proč je to důležité** – Vlastnost `Extended.Pdf417` vystavuje pole definovaná specifikací PDF417, jako je ID souboru, ID segmentu a název souboru. Tato data jsou nezbytná, když potřebujete znovu sestavit více‑stránkový dokument z oddělených skenů čárových kódů.

**Profesionální tip:** Vždy ověřte, že `barcodeResult.Extended` není `null`, než přistoupíte k `Pdf417`. Knihovna vrací `null` pro symbologie, které nepodporují rozšířená data.

### Krok 4: Vypište text čárového kódu a makro podrobnosti

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**Proč je to důležité** – Výstup do konzole vám okamžitě ukáže jak dekódovaný text, tak makro metadata. To je užitečné pro ladění i pro následné zpracování, například uložení informací do databáze.

**Očekávaný výstup** (při předpokladu, že ukázkový obrázek obsahuje jeden makro segment):

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

Pokud obrázek obsahuje tři segmenty, smyčka vytiskne tři bloky, každý s jiným `Segment ID`.

### Krok 5: Ošetřete chyby a uvolněte prostředky

Příkaz `using` automaticky uvolní `BarCodeReader`. Přesto byste měli zachytit výjimky, které mohou nastat při chybějících souborech nebo nepodporovaných formátech:

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**Proč je to důležité** – Robustní aplikace nespadnou jen proto, že soubor chybí nebo je obrázek poškozený. Poskytnutí jasné chybové zprávy pomáhá vám i vašemu podpoře rychle diagnostikovat problém.

## Jak dekódovat PDF417 čárový kód s Aspose.BarCode

Sekundární klíčové slovo **how to decode pdf417 barcode** se v této sekci objevuje přirozeně. Dekódování PDF417 čárového kódu následuje stejný vzor jako výše, ale můžete vynechat příznak `MacroPdf417`, pokud potřebujete jen čistý text:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**Proč byste si mohli vybrat tuto variantu** – Když čárový kód neobsahuje makro informace, použití `DecodeType.Pdf417` snižuje zátěž zpracování a zjednodušuje manipulaci s výsledkem.

**Často kladená otázka:** *Co když je čárový kód otočený?*  
Aspose.BarCode automaticky detekuje rotaci a koriguje ji, takže není potřeba další kód pro předzpracování obrázku.

## Kompletní, spustitelný příklad

Zkopírujte celý program níže do nového konzolového projektu (`dotnet new console`) a nahraďte `YOUR_DIRECTORY/ExtPDF417Meta.png` skutečnou cestou k vašemu obrázku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

Spuštěním programu se vytiskne typ čárového kódu, dekódovaný text a případná makro metadata. Pokud obrázek neobsahuje PDF417 makro, program vás o tom informuje elegantně.

## Závěr

Nyní víte, jak **číst čárový kód z obrázku c#** pomocí Aspose.BarCode, jak **dekódovat PDF417 čárový kód** a jak získat rozšířená pole macro‑PDF417. Řešení zahrnuje inicializaci, iteraci, přístup k metadatům, ošetření chyb a variantu pro čisté PDF417 dekódování.

Odtud můžete:

* Uložit získaná data do SQL databáze pro pozdější načtení.  
* Spojit více segmentů a obnovit původní dokument.  
* Prozkoumat další symbologie podporované Aspose.BarCode, a


## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobným vysvětlením krok za krokem, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}