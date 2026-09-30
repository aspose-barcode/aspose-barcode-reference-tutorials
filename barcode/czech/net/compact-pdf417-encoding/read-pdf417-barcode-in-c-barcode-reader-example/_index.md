---
category: general
date: 2026-08-03
description: Načtěte čárový kód PDF417 z obrázku pomocí C# BarCodeReader – kompletní
  příklad čtečky čárových kódů, který také ukazuje, jak načíst více čárových kódů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: cs
lastmod: 2026-08-03
og_description: Rychle načtěte čárový kód PDF417 pomocí příkladu C# BarCodeReader.
  Postupujte podle tohoto krok‑za‑krokem průvodce, abyste dekódovali macro PDF417
  a načetli více čárových kódů z obrázku.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Čtení PDF417 čárového kódu v C# – kompletní příklad čtečky čárových kódů
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Čtení PDF417 čárového kódu v C# – příklad čtečky čárových kódů
url: /cs/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Čtení čárového kódu PDF417 v C# – příklad čtečky čárových kódů

Pokud potřebujete načíst data čárového kódu PDF417 z obrázku, tento průvodce vám ukáže, jak to provést pomocí třídy **BarCodeReader** v C#. Naučíte se příklad čtečky čárových kódů, který také zvládá macro PDF417 a dokáže načíst více čárových kódů v jednom obrázku.

Práce s čárovými kódy často zahrnuje různé zdroje obrázků, proměnlivé osvětlení a někdy složená data, jako jsou segmenty macro PDF417. Tento tutoriál pokrývá vše, co potřebujete k dekódování čárového kódu PDF417, extrakci jeho rozšířených polí a zpracování několika čárových kódů ze stejného obrázku. Na konci budete mít spustitelný konzolový program, který načte čárové kódy ze souboru s obrázkem a vypíše podrobné informace do konzole.

## Co budete potřebovat

* .NET 6.0 SDK nebo novější nainstalovaný  
* Aktuální verze NuGet balíčku **Aspose.BarCode for .NET** (nebo jakékoli kompatibilní knihovny, která poskytuje `BarCodeReader` a `DecodeType.MacroPdf417`)  
* Obrázkový soubor obsahující čárový kód PDF417 nebo macro PDF417 (ve vzoru se používá `ExtPDF417Meta.png`)  
* Editor kódu nebo IDE, např. Visual Studio 2022  

Žádné další služby ani externí API nejsou vyžadovány.

## Nastavení projektu pro čtení čárových kódů

1. **Create a new console project**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Add the barcode library**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Copy the barcode image**  

   Place `ExtPDF417Meta.png` (or any image that contains a PDF417 barcode) into the project folder.  
   For this tutorial we assume the file resides at `YOUR_DIRECTORY/ExtPDF417Meta.png`.

   Umístěte `ExtPDF417Meta.png` (nebo jakýkoli obrázek obsahující čárový kód PDF417) do složky projektu. Pro tento tutoriál předpokládáme, že soubor se nachází v `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Projekt je nyní připraven ke kompilaci a spuštění příkladu čtečky čárových kódů.

## Jak číst čárový kód PDF417 pomocí BarCodeReader

Jádrem řešení je blok `using`, který vytvoří instanci `BarCodeReader`, specifikuje `DecodeType.MacroPdf417` a iteruje přes každý detekovaný čárový kód. Následující kód je kompletní, samostatný program, který můžete vložit do souboru `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Proč to funguje**:  

* `DecodeType.MacroPdf417` říká čtečce, aby hledala makro rozšíření PDF417, které obsahuje další metadata jako ID souboru, počet segmentů a časová razítka.  
* `using` příkaz zajišťuje, že neřízené prostředky (souborové handly, nativní dekódovací buffery) jsou uvolněny okamžitě.  
* `foreach` smyčka automaticky zpracuje **všechny** čárové kódy, které obrázek obsahuje, čímž splňuje požadavek na *čtení více čárových kódů*.

Když spustíte program (`dotnet run`), měli byste vidět výstup podobný následujícímu:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Pokud obrázek obsahuje více než jeden PDF417 čárový kód, smyčka vytiskne samostatný blok pro každý čárový kód, čímž demonstruje, jak **číst více čárových kódů** z jednoho obrázku.

## Čtení více čárových kódů z obrázku

Stejná instance `BarCodeReader` může najednou dekódovat několik typů čárových kódů. Pro rozšíření rozsahu z pouhého macro PDF417 na jakýkoli PDF417 (nebo dokonce QR, Code128 atd.) upravte příznak `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* je bitová maska, takže můžete kombinovat libovolný počet podporovaných formátů. Tato flexibilita dělá úryvek **příkladem čtečky čárových kódů**, který funguje pro širokou škálu případů použití, jako je skenování štítků produktů, vstupenek nebo ID karet.

## Bezpečný přístup k polím macro PDF417

Macro PDF417 přidává bohatou sadu rozšířených vlastností. Nicméně ne každý čárový kód obsahuje všechna pole. Přístup k chybějící vlastnosti může vyvolat `NullReferenceException`. Nejbezpečnější přístup je ověřit každou vlastnost před jejím vytištěním:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Proč je to důležité*: V reálných nasazeních můžete obdržet čisté PDF417 čárové kódy, které postrádají macro data. Defenzivní kontrola zajišťuje, že vaše aplikace bude nadále běžet bez zhroucení.

## Časté úskalí a osvědčené postupy

| Problém | Proč k tomu dochází | Doporučené řešení |
|-------|----------------|-----------------|
| Cesta k obrázku je nesprávná | `BarCodeReader` vyvolá výjimku soubor‑nenalezen před jakýmkoli dekódováním | Použijte `Path.Combine` a ověřte, že soubor existuje pomocí `File.Exists` |
| Obrázek s nízkým rozlišením | Dekodér nedokáže najít hrany čárového kódu, což vede k nulovým detekcím | Zajistěte minimální rozlišení 300 dpi pro spolehlivé výsledky |
| Čárový kód otočený > 45° | Mnoho knihoven předpokládá svislou orientaci | Povolte `reader.RecognitionOptions.RotateImage = true`, pokud je |

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak číst DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Čtení DataMatrix čárového kódu C# – Generování DataMatrix režimu (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Čtení čárového kódu z obrázku – Ovládání extrakce oblasti čárového kódu v Java s Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}