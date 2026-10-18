---
category: general
date: 2026-10-18
description: Naučte se, jak číst čárový kód z obrázku v C# pomocí Aspose.BarCode,
  včetně extrakce metadat Macro PDF417 a kompletního ukázkového kódu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: cs
lastmod: 2026-10-18
og_description: Jak načíst čárový kód z obrázku pomocí C# Aspose.BarCode. Postupujte
  podle tohoto tutoriálu krok za krokem, abyste extrahovali metadata Macro PDF417
  a řešili běžné scénáře.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Jak načíst čárový kód z obrázku v C# – kompletní průvodce Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak načíst čárový kód z obrázku v C# pomocí Aspose.BarCode
url: /cs/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárový kód z obrázku v C# pomocí Aspose.BarCode

Pokud potřebujete **jak číst čárový kód z obrázku** v .NET aplikaci, tento průvodce ukazuje přesné kroky s Aspose.BarCode. Ať už zpracováváte naskenované dokumenty, účtenky nebo inventární štítky, uvidíte, jak číst čárový kód, získat metadata Macro PDF417 a řešit typické okrajové případy.

Čtení čárového kódu z obrázku je rutinní úkol, ale extrahování rozšířených polí Macro PDF417 přidává vrstvu složitosti. Tento tutoriál pokrývá kompletní pracovní postup, od nastavení projektu až po plně spustitelný příklad, takže můžete kód zkopírovat‑vložit a okamžitě vidět výsledky.

## Co se naučíte

- Jak nastavit Aspose.BarCode pro C# projekty.  
- Správný způsob vytvoření **C# barcode reader** pro obrázek s Macro PDF417.  
- Jak iterovat přes každý detekovaný čárový kód a vypisovat základní informace.  
- Jak získat **Macro PDF417 metadata** jako ID souboru, ID segmentu a kontrolní součet.  
- Tipy pro zpracování chybějících metadat, velkých obrázků a běžných chyb dekódování.  

**Požadavky**

- .NET 6.0 (nebo novější) nainstalováno.  
- Základní znalost C# a Visual Studio (funguje jakékoli IDE).  
- Obrázkový soubor, který obsahuje čárový kód Macro PDF417 (např. `ExtPDF417Meta.png`).  

## Krok 1: Instalace Aspose.BarCode

Otevřete terminál ve složce projektu a spusťte:

```bash
dotnet add package Aspose.BarCode
```

Balíček obsahuje **BarCodeReader class**, který implementuje funkčnost **C# barcode reader** potřebnou pro tento tutoriál.

## Krok 2: Nastavení vývojového prostředí

Vytvořte novou konzolovou aplikaci, pokud ještě žádnou nemáte:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Přidejte `using` direktivy na začátek souboru `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Tyto jmenné prostory zpřístupňují **BarCodeReader class** a výčtový typ `DecodeType` potřebný pro dekódování Macro PDF417.

## Krok 3: Inicializace BarCodeReader pro Macro PDF417

Jádrem **jak číst čárový kód z obrázku** je vytvoření instance `BarCodeReader`, která cílí na konkrétní `DecodeType`. Pro Macro PDF417 musíte předat `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Proč je to důležité:**  
Volba `DecodeType.MacroPdf417` říká knihovně, aby hledala rozšířený formát Macro PDF417, který obsahuje další pole nad rámec základních dat čárového kódu. Pokud použijete obecný `DecodeType.Pdf417`, tyto extra pole budou ignorována.

## Krok 4: Iterace přes detekované čárové kódy

Jeden obrázek může obsahovat více čárových kódů. Metoda `ReadBarCodes()` vrací výčtovou kolekci objektů `BarCodeResult`. Projděte je v cyklu a vypište základní informace o každém čárovém kódu:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` vám udává přesnou symbologii čárového kódu (např. “MacroPdf417”), zatímco `CodeText` obsahuje dekódovaný řetězec.

## Krok 5: Extrakce a zobrazení metadat Macro PDF417

Když je čárový kód typu Macro PDF417, vlastnost `Extended.Pdf417` poskytuje bohatou sadu metadatových polí. Přistupujte k nim přímo, jak je ukázáno níže:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Tato pole vám poskytují vše potřebné k rekonstrukci původního souboru s více segmenty, ověření integrity a přiřazení čárového kódu ke konkrétnímu dokumentu nebo odesílateli.

### Očekávaný výstup v konzoli

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Pokud obrázek neobsahuje čárový kód Macro PDF417, objekt `Extended.Pdf417` bude `null`. Ošetřete to, aby nedošlo k `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Krok 6: Řešení běžných chyb a okrajových případů

### Velké obrázky

Čtení velmi velkých obrázků může spotřebovat značnou paměť. Použijte přetížení `BarcodeReader`, které přijímá `ReaderParameters`, k omezení maximální velikosti obrázku:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Chybějící nebo poškozená metadata

Pokud některá z polí Macro chybí, odpovídající vlastnost vrátí `null` nebo `0`. Zaznamenejte tyto případy a rozhodněte, zda čárový kód považovat za neúplný.

### Více typů čárových kódů v jednom obrázku

Pokud obrázek může obsahovat jiné formáty čárových kódů, můžete předat pole hodnot `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Tento přístup udržuje logiku **jak číst čárový kód z obrázku** flexibilní, aniž by se snížil výkon.

## Krok 7: Kompletní zdrojový kód

Níže je kompletní, připravený k spuštění program. Nahraďte `YOUR_DIRECTORY/ExtPDF417Meta.png` cestou k vašemu vlastnímu obrázku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Spusťte program pomocí:

```bash
dotnet run
```

Měli byste vidět typ čárového kódu, dekódovaný text a všechna dostupná pole Macro PDF417 vytištěná v konzoli.

## Závěr

V tomto tutoriálu jste se naučili **jak číst čárový kód z obrázku** pomocí Aspose.BarCode pro C#. Průvodce pokryl nastavení **C# barcode reader**,

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční příklady kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Číst čárový kód z obrázku C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [Jak vytvořit macro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak číst PDF417 čárový kód v C# – kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}