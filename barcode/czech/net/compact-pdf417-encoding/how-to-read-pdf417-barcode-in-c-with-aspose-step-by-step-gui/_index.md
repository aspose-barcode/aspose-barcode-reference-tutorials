---
category: general
date: 2026-10-24
description: Naučte se, jak číst čárový kód PDF417 v C# pomocí Aspose.BarCode. Tento
  tutoriál pokrývá čtení obrázku čárového kódu, extrakci polí Macro PDF417 a řešení
  běžných scénářů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: cs
lastmod: 2026-10-24
og_description: Jak číst čárový kód PDF417 v C# pomocí Aspose.BarCode. Sledujte tento
  kompletní tutoriál, abyste dekódovali obrázky, získali metadata Macro PDF417 a vyhnuli
  se běžným úskalím.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Jak číst čárový kód PDF417 v C# s Aspose – kompletní průvodce
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Jak číst čárový kód PDF417 v C# s Aspose – krok za krokem
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód PDF417 v C# s Aspose – krok za krokem průvodce

Pokud potřebujete **jak číst čárový kód PDF417** v aplikaci .NET, tento průvodce vám ukáže přesně, jak číst čárový kód PDF417 v C# pomocí knihovny Aspose.BarCode. Ať už zpracováváte skenované dokumenty, mobilní snímky nebo dávkově importované obrázky, níže uvedený kód dekóduje čárový kód a získá všechny vlastnosti Macro PDF417, které můžete potřebovat.

Čtení obrázku s čárovým kódem v C# může působit zastrašujícím dojmem, zejména když čárový kód obsahuje rozšířené metadata. Tento tutoriál odstraňuje hádání tím, že poskytuje kompletní, spustitelný příklad, vysvětluje každý řádek a pokrývá okrajové případy, jako jsou chybějící makro segmenty nebo poškozené obrázky. Na konci budete schopni s jistotou integrovat dekódování PDF417 do libovolného C# projektu.

## Požadavky

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli IDE podporující .NET)  
* Licenci nebo bezplatnou zkušební verzi **Aspose.BarCode for .NET** – dočasný klíč získáte na webu Aspose  
* Soubor obrázku, který obsahuje Macro PDF417 čárový kód (např. `ExtPDF417Meta.png`)

> **Tip:** Pokud chcete jen experimentovat, Aspose nabízí 30‑denní zkušební verzi, která zahrnuje plnou funkčnost pro čtení čárových kódů.

## Krok 1: Instalace NuGet balíčku Aspose.BarCode

Otevřete složku projektu v terminálu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček přidá jmenný prostor `Aspose.BarCode.ReadRecognition`, který obsahuje třídu `BarCodeReader` používanou k dekódování obrázků.

## Krok 2: Vytvoření BarCodeReader pro PDF417 obrázek

Konstruktor `BarCodeReader` přijímá dva argumenty: cestu k souboru obrázku a `DecodeType`, který chcete cílit. Zadání `DecodeType.MacroPdf417` říká Aspose, aby hledal symboly Macro PDF417 a automaticky naplnil rozšířené vlastnosti.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Proč použít `DecodeType.MacroPdf417`?

* **Macro PDF417** ukládá další pole (ID souboru, počet segmentů, časová razítka atd.), která nejsou přítomna ve standardním PDF417.  
* Vlastnost `Extended` objektu `BarCodeResult` je naplněna pouze při požadavku na makro typ, což vám ušetří samostatný krok parsování.

## Krok 3: Procházení všech detekovaných čárových kódů

Jeden obrázek může obsahovat více PDF417 symbolů (například když je dokument rozdělen na několik stránek). Metoda `ReadBarCodes()` vrací `IEnumerable<BarCodeResult>`, přes který můžete iterovat.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Pokud obrázek neobsahuje žádný čárový kód, smyčka se jednoduše neprovede a program se ukončí elegantně. Toto chování činí kód bezpečným pro dávkové zpracování, kde některé soubory mohou být bez čárových kódů.

## Krok 4: Výpis rozšířených vlastností Macro PDF417

Vlastnost `Extended.Pdf417` seskupuje všechna makro‑specifická pole. Každé pole mapuje přímo na specifikaci PDF417, takže je můžete uložit do databáze, zalogovat nebo použít pro další validaci.

```csharp
        // Macro PDF417 extended properties
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

### Co jednotlivé vlastnosti znamenají

| Vlastnost | Popis |
|----------|-------|
| **MacroPdf417FileID** | Jedinečný identifikátor celého více‑segmentového dokumentu. |
| **MacroPdf417SegmentID** | Index aktuálního segmentu (počínaje 0). |
| **MacroPdf417SegmentsCount** | Celkový počet segmentů, které patří k souboru. |
| **MacroPdf417FileName** | Volitelný název souboru vložený do čárového kódu. |
| **MacroPdf417Checksum** | CRC‑16 kontrolní součet pro blok makro dat. |
| **MacroPdf417FileSize** | Původní velikost souboru v bajtech. |
| **MacroPdf417TimeStamp** | Časové razítko, kdy byl makro čárový kód vygenerován. |
| **MacroPdf417Addressee** | Zamýšlený příjemce dokumentu. |
| **MacroPdf417Sender** | Odesílatel dokumentu. |
| **MacroPdf417Terminator** | Příznak ukončení označující konec makro sekvence. |

Tato pole jsou zvláště užitečná, když rekonstruujete velký PDF nebo obrázek, který byl rozdělen do několika PDF417 symbolů pro tisk na nízké rozlišení.

## Krok 5: Ošetření běžných okrajových případů

### Chybějící makro pole

Někdy je PDF417 čárový kód vygenerován bez volitelných makro polí. Přístup k neexistující vlastnosti vrátí `null` nebo `0`. Ošetřete to, pokud plánujete hodnoty ukládat:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Poškozené nebo nízkokvalitní obrázky

Pokud je obrázek rozmazaný, můžete zlepšit detekci povolením možností kvality `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Tyto nastavení jsou volitelná, ale mohou dramaticky zvýšit úspěšnost u skenovaných dokumentů.

### Více formátů čárových kódů v jednom obrázku

Pokud máte podezření, že v obrázku mohou být i jiné typy čárových kódů, použijte `DecodeType.AllSupported` a filtrujte výsledky:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Kompletní spustitelný příklad

Zkopírujte následující program do nového konzolového projektu (`dotnet new console`) a spusťte jej. Nahraďte proměnnou `imagePath` cestou k vašemu vlastnímu Macro PDF417 obrázku.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Očekávaný výstup** (hodnoty se liší podle vašeho obrázku):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Pokud obrázek neobsahuje žádné Macro PDF417 symboly, program nic nevypíše a ukončí se tiše – ideální pro dávkové úlohy zpracovávající mnoho souborů.

## Často kladené otázky

**Q: Můžu pomocí stejného kódu číst standardní PDF417 (bez makra)?**  
A: Ano. Změňte `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Vlastnost `Extended` bude prázdná, ale `CodeText` a `CodeTypeName` zůstanou dostupné.

**Q: Podporuje Aspose.BarCode čtení ze streamu místo cesty k souboru?**  
A: Rozhodně. Použijte přetížení `new BarCodeReader(Stream, DecodeType)` a předávejte `FileStream` nebo `MemoryStream`. To je užitečné, když obrázek pochází z webového API.

**Q: Jak ověřím kontrolní součet?**  
A: Pole `MacroPdf417Checksum` obsahuje surovou hodnotu CRC‑16. Můžete znovu vypočítat kontrolní součet na rekonstruovaném souboru a porovnat jej, abyste zajistili integritu dat.

## Další kroky a související témata

* **Vytváření PDF417 čárových kódů** – prozkoumejte `BarCodeGenerator` pro tvorbu makro čárových kódů pro testování.  
* **Kombinace více segmentů** – po načtení všech segmentů je seřaďte podle `MacroPdf417SegmentID` a spojte `CodeText` pro rekonstrukci původního payloadu.  
* **Ladění výkonu** – pro scénáře s vysokou propustností znovu použijte jedinou instanci `BarCodeReader` napříč mnoha obrázky a

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vašich projektech.

- [Jak číst PDF417 v C# – Kompletní příklad čárového kódu](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [Jak vytvořit macro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Čtení čárového kódu z obrázku v C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}