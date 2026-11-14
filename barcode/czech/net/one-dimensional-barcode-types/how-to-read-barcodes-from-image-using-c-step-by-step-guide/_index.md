---
category: general
date: 2026-11-14
description: Naučte se číst čárové kódy z obrázku v C# pomocí kompletního tutoriálu
  čtečky čárových kódů v C#. Obsahuje nastavení, kompletní kód a práci s poli Macro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: cs
lastmod: 2026-11-14
og_description: Čtěte čárové kódy z obrázku v C# pomocí tohoto tutoriálu čtečky čárových
  kódů v C#. Získejte kompletní funkční příklad a naučte se extrahovat data Macro
  PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Čtení čárových kódů z obrázku v C# – kompletní návod
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Jak číst čárové kódy z obrázku pomocí C# – krok za krokem
url: /cs/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst čárové kódy z obrázku pomocí C# – krok za krokem průvodce

Pokud potřebujete **číst čárové kódy z obrázku** v .NET aplikaci, tento průvodce vám přesně ukáže, jak na to. Na konci tutoriálu budete mít kompletní, spustitelný program, který extrahuje jak základní data čárového kódu, tak specifická pole Macro PDF417.

V tomto **barcode reader tutorial c#** pokryjeme nastavení projektu, požadovaný NuGet balíček a kompletní ukázkový kód, který funguje s nejnovějším .NET 8 SDK. Nejsou potřeba žádné externí služby—vše běží lokálně.

## Co se naučíte

- Jak přidat knihovnu Aspose.BarCode (nebo podobnou) do C# projektu.  
- Jak vytvořit `BarCodeReader`, který cílí na konkrétní soubor obrázku.  
- Jak iterovat přes všechny detekované čárové kódy a vypsat jejich typ, text a metadata Macro PDF417.  
- Tipy pro práci s obrázky obsahujícími více čárových kódů nebo různé typy dekódování.

### Předpoklady

- .NET 8 SDK (nebo .NET 6+, pokud dáváte přednost) nainstalovaný.  
- Základní znalost C# konzolových aplikací.  
- Soubor obrázku, který obsahuje čárový kód Macro PDF417 (např. `MacroPdf417.png`).  

---

## Krok 1: Nastavte nový konzolový projekt

Otevřete terminál a spusťte:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Tím se vytvoří minimální konzolová aplikace pojmenovaná **BarcodeReaderDemo**. Soubor projektu (`BarcodeReaderDemo.csproj`) bude použit v dalším kroku.

## Krok 2: Nainstalujte knihovnu pro čtení čárových kódů

Pro tento tutoriál používáme knihovnu **Aspose.BarCode for .NET**, protože podporuje Macro PDF417 přímo. Nainstalujte ji pomocí NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Proč tato knihovna?** Poskytuje jedinou třídu `BarCodeReader`, podporuje desítky symbologií a vystavuje vlastnost `Extended`, která obsahuje pole Macro PDF417.

## Krok 3: Napište kód čtečky čárových kódů (barcode reader tutorial c#)

Nahraďte obsah souboru `Program.cs` následujícím kompletním příkladem. Ukazuje **jak číst čárové kódy z obrázku** a vypisuje jak obecné, tak specifické informace pro Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Vysvětlení každého kroku

| Krok | Proč je to důležité |
|------|----------------|
| **1️⃣ Definujte cestu k obrázku** | Čtečka pracuje s cestou k souboru nebo streamem. Použití relativní cesty usnadňuje příklad při kopírování. |
| **2️⃣ Vytvořte BarCodeReader** | Předáním `DecodeType.MacroPdf417` omezíte skenování na tuto symbologii, což zvyšuje rychlost a zajišťuje, že pole `Extended` jsou vyplněna. |
| **3️⃣ Iterujte výsledky** | Obrázek může obsahovat více čárových kódů; smyčka `foreach` zaručuje, že je zachytíme všechny. |
| **4️⃣ Obecný výstup** | `CodeTypeName` a `CodeText` jsou nejčastěji potřebné informace pro vývojáře. |
| **5️⃣ Pole Macro PDF417** | Macro PDF417 vkládá další data (ID souboru, ID segmentu, počet segmentů). Přístup k `result.Extended.Pdf417` poskytuje tyto hodnoty bez dalšího parsování. |
| **6️⃣ Volitelná extra pole** | Knihovna vystavuje další makro pole (např. `MacroPdf417FileName`). Můžete rozšířit výstup podle vašich potřeb. |
| **7️⃣ Nechte konzoli otevřenou** | Užitečné při spuštění z Visual Studio nebo `dotnet run`, aby bylo možné vidět výstup před zavřením okna. |

## Krok 4: Spusťte program a ověřte výstup

Umístěte soubor `MacroPdf417.png` do složky, na kterou odkazuje `imagePath`. Poté spusťte:

```bash
dotnet run
```

Typický výstup v konzoli vypadá takto:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Pokud obrázek obsahuje více symbolů Macro PDF417, program vypíše každou sadu hodnot postupně.

## Běžné varianty a okrajové případy

### Čtení jiných symbologií

Pokud potřebujete **číst čárové kódy z obrázku**, které nejsou Macro PDF417, nahraďte `DecodeType.MacroPdf417` čárkou odděleným seznamem, např.:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

Vlastnost `Extended` bude `null` pro symbologie, které neposkytují extra data, takže vždy před přístupem zkontrolujte, zda není `null`.

### Práce s velkými obrázky

Velké PNG nebo JPEG soubory mohou zvýšit využití paměti. Pro udržení lehkosti procesu můžete před předáním do `BarCodeReader` zmenšit rozlišení obrázku:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Práce se streamy místo cest k souborům

Když obrázek pochází z databáze nebo webového požadavku, předávejte `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Profi tipy pro plynulý zážitek s čtečkou čárových kódů

- **Pro tip:** Vždy nastavte `DecodeType` na nejúžejší sadu symbologií, kterou očekáváte. Tím se sníží falešné pozitivy a zrychlí zpracování.  
- **Watch out for:** Obrázky s nízkým kontrastem nebo silnou kompresí mohou způsobit neúspěšné čtení. Předzpracujte obrázek (upravit jas/kontrast), pokud zaznamenáte nízkou úspěšnost detekce.  
- **Tip:** Třída `BarCodeReader` implementuje `IDisposable`; použití bloku `using` zaručuje, že nativní zdroje jsou uvolněny okamžitě.  

---

## Závěr

Nyní víte, jak **číst čárové kódy z obrázku** v C# a extrahovat jak standardní, tak specifické informace pro Macro PDF417. Tento **barcode reader tutorial c#** poskytuje kompletní, samostatné řešení, které můžete vložit do libovolného .NET projektu.

Odtud můžete:

- Prozkoumejte další typy dekódování (QR, DataMatrix, Code128).  
- Integrujte čtečku do ASP.NET Core API pro zpracování nahrávek za běhu.  
- Uložte extrahovaná makro pole do databáze pro pozdější agregaci.

Šťastné kódování a nebojte se experimentovat s různými zdroji obrázků a formáty čárových kódů!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s krok za krokem vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak dekódovat PDF417 čárové kódy v C# a číst obrázek čárového kódu C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [Jak číst čárový kód z obrázku c# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Číst čárový kód z obrázku C# – kompletní průvodce s Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}