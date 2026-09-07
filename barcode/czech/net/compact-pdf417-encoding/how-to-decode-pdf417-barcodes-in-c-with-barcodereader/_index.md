---
category: general
date: 2026-09-07
description: Naučte se, jak dekódovat čárové kódy PDF417 v C# pomocí BarCodeReader.
  Tento krok‑za‑krokem průvodce také vysvětluje, jak efektivně číst data PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: cs
lastmod: 2026-09-07
og_description: Jak dekódovat PDF417 čárové kódy v C# pomocí BarCodeReader. Sledujte
  tento tutoriál, abyste se naučili číst data PDF417 a extrahovat pole MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Jak dekódovat PDF417 čárové kódy v C# – kompletní průvodce
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Jak dekódovat PDF417 čárové kódy v C# pomocí BarCodeReader
url: /cs/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dekódovat PDF417 čárové kódy v C# pomocí BarCodeReader

Pokud potřebujete **jak dekódovat PDF417** čárové kódy v .NET aplikaci, tento průvodce vás provede celým procesem. Také objevíte **jak číst PDF417** data, jako jsou identifikátory souborů a segmentů MacroPdf417, vše pomocí několika řádků C#.

Dekódování PDF417 je běžné při práci s dopravními jízdenkami, řidičskými průkazy nebo přepravními štítky. Na konci tohoto tutoriálu budete mít spustitelný konzolový program, který vypíše každé pole MacroPdf417 vystavené SDK GroupDocs.Barcode.

## Požadavky

* .NET 6.0 SDK nebo novější (kód se kompiluje s .NET Core a .NET Framework)
* Visual Studio 2022 nebo jakékoli IDE podporující C#
* Balíček **GroupDocs.Barcode** NuGet (`GroupDocs.Barcode` ≥ 23.3)
* Obrázek obsahující čárový kód Macro PDF417 (např. `ExtPDF417Meta.png`)

> **Pro tip:** Nainstalujte balíček pomocí CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Jak dekódovat PDF417 čárové kódy v C#

Následující sekce rozdělí řešení do logických kroků. Každý krok obsahuje přesný kód, který potřebujete, a krátké vysvětlení, proč je důležitý.

### Krok 1: Připravte projekt a importujte jmenné prostory

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Proč?*  
`GroupDocs.Barcode` poskytuje třídu `BarCodeReader`, zatímco `GroupDocs.Barcode.Common` obsahuje výčtový typ `DecodeType` potřebný pro dekódování PDF417.

### Krok 2: Definujte cestu k obrázku

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Proč?*  
Čtečka funguje s libovolným formátem obrázku podporovaným .NET (`.png`, `.jpg`, `.bmp`). Zadání správné cesty zajišťuje, že SDK dokáže soubor najít.

### Krok 3: Inicializujte čtečku čárových kódů pro dekódování MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Proč?*  
`DecodeType.MacroPdf417` říká SDK, aby hledalo rozšířený formát Macro PDF417, který nese další metadata jako ID souboru a segmentu. Použití příkazu `using` zaručuje, že neřízené zdroje jsou uvolněny okamžitě.

### Krok 4: Přečtěte všechny čárové kódy nalezené na obrázku

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Proč?*  
Obrázek může obsahovat více čárových kódů. Metoda `ReadBarCodes()` vrací kolekci, což vám umožní zpracovat každý kód samostatně.

### Krok 5: Získejte a zobrazte specifická data Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Proč?*  
Objekt `Extended.Pdf417` odhaluje všechna pole Macro PDF417 definovaná specifikací. Jejich vytištění vám umožní ověřit, že dekódování bylo úspěšné, a poskytne data potřebná pro následné zpracování.

### Kompletní spustitelný příklad

Spojte výše uvedené úryvky do jediného souboru `Program.cs`:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Očekávaný výstup v konzoli** (hodnoty se liší podle obsahu čárového kódu):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Pokud obrázek neobsahuje čárový kód Macro PDF417, kolekce `ReadBarCodes()` bude prázdná a nic se nevytiskne.

## Běžné varianty a okrajové případy

| Situace | Jak upravit kód |
|-----------|----------------------|
| **Standardní (ne‑macro) PDF417** | Změňte `DecodeType.MacroPdf417` na `DecodeType.Pdf417`. Objekt `Extended.Pdf417` bude `null`, takže je třeba ošetřit nulové reference. |
| **Více obrázků** | Zabalte inicializaci čtečky do smyčky `foreach (var path in imagePaths)` . |
| **Velké obrázky** | Nastavte `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` pro omezení využití paměti. |
| **Výkonnostně kritické dávky** | Znovu použijte jedinou instanci `BarCodeReader` s `reader.SetImage(path)` místo vytváření nového objektu pro každý soubor. |

## Kontrolní seznam řešení problémů

* **Žádný výstup:** Ověřte, že `imagePath` ukazuje na existující soubor a že obrázek skutečně obsahuje PDF417 čárový kód. |
* **Null `Extended.Pdf417`:** Pravděpodobně jste použili `DecodeType.Pdf417` místo `MacroPdf417`. |
* **Výjimka `FileNotFoundException`:** Ujistěte se, že pracovní adresář odpovídá cestě, nebo použijte absolutní cestu. |
* **Nízké skóre důvěry:** Zvyšte kvalitu obrázku nebo upravte nastavení `reader.Options.Quality`. |

## Závěr

Nyní víte **jak dekódovat PDF417** čárové kódy v C# a **jak číst PDF417** metadata, jako jsou ID souborů Macro, ID segmentů a časová razítka. Kompletní příklad ukazuje inicializaci `BarCodeReader`, výběr správného typu dekódování, iteraci přes výsledky a extrakci všech dostupných polí MacroPdf417.

Odtud můžete:

* Integrovat získaná data do logistického nebo systému pro ověřování jízdenek.
* Rozšířit konzolovou aplikaci tak, aby zapisovala výsledky do databáze nebo souboru JSON.
* Prozkoumat další formáty čárových kódů podporované GroupDocs.Barcode (QR, DataMatrix, Code128, atd.) výměnou výčtu `DecodeType`.

Šťastné programování a nebojte se experimentovat s různými obrázky a nastavením čárových kódů, abyste si osvojili dekódování PDF417 ve svých .NET projektech!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak číst PDF417 v C# – Kompletní průvodce krok za krokem](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [Jak číst PDF417 v C# – Kompletní příklad čtečky čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Jak generovat PDF417 čárový kód – Kompletní programovací průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}