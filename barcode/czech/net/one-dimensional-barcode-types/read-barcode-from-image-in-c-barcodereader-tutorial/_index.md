---
category: general
date: 2026-08-15
description: Čtěte čárový kód z obrázku v C# pomocí BarCodeReader. Naučte se, jak
  číst více čárových kódů v C#, číst čárový kód PDF417 a podívejte se na kompletní
  příklad BarCodeReader v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: cs
lastmod: 2026-08-15
og_description: Čtěte čárový kód z obrázku v C# pomocí krok‑za‑krokem průvodce. Objevte,
  jak číst více čárových kódů v C#, dekódovat symboly PDF417 a spustit kompletní příklad
  C# BarCodeReader.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Načíst čárový kód z obrázku v C# – BarCodeReader tutoriál
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Čtení čárového kódu z obrázku v C# – tutoriál BarCodeReader
url: /cs/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Načíst čárový kód z obrázku v C# – BarCodeReader tutoriál

Pokud potřebujete **číst čárový kód z obrázku** v .NET aplikaci, tento průvodce vám přesně ukáže, jak to provést pomocí třídy `BarCodeReader`. Také uvidíte, jak **číst více čárových kódů v C#**, dekódovat symbol PDF417 a získat kompletní **C# BarCodeReader příklad**, který můžete zkopírovat do svého projektu.

Tutoriál pokrývá každý krok — od přidání požadovaného NuGet balíčku až po výpis rozšířených PDF417 polí — takže skončíte s funkční konzolovou aplikací. Není potřeba žádná externí dokumentace; veškerý kód a vysvětlení jsou zahrnuty.

## Co budete potřebovat

Než začnete, ujistěte se, že máte:

* .NET 6.0 SDK nebo novější (kód funguje s .NET Core i .NET Framework)
* Visual Studio 2022 nebo jakýkoli editor kompatibilní s C#
* Balíček NuGet `Aspose.BarCode` (nebo ekvivalentní knihovna, která poskytuje `BarCodeReader`)
* Obrázkový soubor, který obsahuje čárový kód Macro PDF417 (např. `ExtPDF417Meta.png`)

Mít tyto předpoklady zajišťuje, že ukázka se zkompiluje bez další konfigurace.

## Načíst čárový kód z obrázku pomocí BarCodeReader

Prvním krokem je vytvořit instanci `BarCodeReader`, která ukazuje na soubor s obrázkem a říká knihovně, jaký typ čárového kódu má hledat.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Proč to funguje:**  
`BarCodeReader` otevře obrázek, prohledá jej podle zadaného `DecodeType` a vrátí kolekci objektů `BarCodeResult`. Každý výsledek obsahuje obecná data čárového kódu (`CodeTypeName`, `CodeText`) a pro Macro PDF417 objekt `Extended.Pdf417`, který vystavuje všechna dodatečná pole definovaná standardem.

## Číst více čárových kódů v C# na jednom obrázku

Někdy obrázek obsahuje více než jeden čárový kód (např. QR kód vedle PDF417). Pro tento scénář stačí vynechat explicitní `DecodeType` nebo předat `DecodeType.AllSupported` a projít výsledky ve smyčce.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Proč to potřebujete:**  
Zadání `AllSupported` říká enginu, aby vyzkoušel každý formát čárového kódu, který zná, což zaručuje zachycení všech symbolů na obrázku. Toto je doporučený přístup, když předem nevíte, jaké typy čárových kódů se mohou objevit.

## Jak číst PDF417 čárový kód pomocí C#

Pokud vás zajímá jen klasický PDF417 (ne‑macro) formát, změňte `DecodeType` na `Pdf417`. Zbytek kódu zůstane stejný, jen rozšířená pole nebudou k dispozici.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Proč na tom záleží:**  
Klasický PDF417 neexponuje makro‑specifické vlastnosti, takže blok `Extended.Pdf417` není potřeba. Použití přesného `DecodeType` také urychluje skenování, protože knihovna přeskočí nepodporované algoritmy.

## Kompletní C# BarCodeReader příklad, který můžete zkopírovat

Níže je kompletní program, který spojuje všechny tři scénáře do jedné snadno spustitelné konzolové aplikace. Nahraďte `YOUR_DIRECTORY/ExtPDF417Meta.png` skutečnou cestou k vašemu obrázku.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Očekávaný výstup

Když ukázkový obrázek obsahuje Macro PDF417 čárový kód, konzole vypíše něco podobného:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Pokud obrázek obsahuje jen běžný PDF417, sekce „Macro PDF417“ bude prázdná a sekce „Classic PDF417“ zobrazí dekódovaný text.

## Závěr

Nyní už víte, jak **číst čárový kód z obrázku** v C# pomocí `BarCodeReader`, jak **číst více čárových kódů v C#** v jednom souboru a jaké jsou přesné kroky k **čtení PDF417 čárového kódu** — včetně makro i klasické varianty. Kompletní **C# BarCodeReader příklad** je připraven k vložení do jakéhokoli .NET projektu a můžete jej rozšířit o další formáty nebo integrovat do většího pipeline pro zpracování obrázků.

**Další kroky**

* Prozkoumejte vzory pro zpracování chyb, jako je `try / catch` kolem bloku čtečky.  
* Experimentujte s objektem `ReaderParameters` pro ladění rychlosti a přesnosti detekce.  
* Kombinujte čtení čárových kódů s knihovnami pro předzpracování obrázků (

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vlastních projektech.

- [Jak číst DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Číst DataMatrix čárový kód v C# – Generovat DataMatrix režim (Auto)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Číst čárový kód z obrázku – Mistrovství extrakce oblasti čárového kódu v Javě s Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}