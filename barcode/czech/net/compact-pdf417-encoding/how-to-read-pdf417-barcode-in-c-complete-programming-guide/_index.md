---
category: general
date: 2026-11-27
description: Jak číst čárový kód PDF417 v C# z obrázku pomocí Aspose.BarCode – krok
  za krokem průvodce s kompletním ukázkovým kódem a tipy na řešení problémů.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- C# barcode decoding
- BarCodeReader class
- DecodeType.MacroPdf417
- BarCodeResult properties
language: cs
lastmod: 2026-11-27
og_description: Jak rychle načíst čárový kód PDF417 v C#. Naučte se dekódovat čárové
  kódy PDF417 z obrázků pomocí Aspose.BarCode, kompletní kód a osvědčené postupy.
og_image_alt: Console output showing how to read PDF417 barcode in C#
og_title: Jak číst čárový kód PDF417 v C# – krok za krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  headline: How to read PDF417 barcode in C# – complete programming guide
  type: TechArticle
- description: how to read pdf417 barcode in C# from an image using Aspose.BarCode
    – step‑by‑step guide with full code example and troubleshooting tips.
  name: How to read PDF417 barcode in C# – complete programming guide
  steps:
  - name: Create a new console project
    text: 'Open a terminal (or PowerShell) and run:'
  - name: Install the Aspose.BarCode NuGet package
    text: 'Aspose.BarCode provides the `BarCodeReader` class used in the example.
      Install it with:'
  - name: Add the code shown above
    text: Replace the content of `Program.cs` with the full snippet from the previous
      section. The code demonstrates **C# barcode decoding** and shows how to access
      **BarCodeResult properties** such as `CodeTypeName`, `CodeText`, and the macro‑specific
      `MacroPdf417FileID`.
  - name: Run the application
    text: '```bash dotnet run ```'
  - name: Handle multiple barcodes and error cases
    text: 'Real‑world images may hold more than one barcode or none at all. Wrap the
      reading logic in a `try`/`catch` block to surface parsing errors, and check
      `reader.HasBarcodes` before iterating:'
  - name: Optional – Decode other barcode types from the same image
    text: 'If you later need to **read barcode from image c#** for other symbologies,
      simply change the `DecodeType` argument:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Jak číst čárový kód PDF417 v C# – kompletní programovací průvodce
url: /cs/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak číst PDF417 čárový kód v C# – kompletní programovací průvodce

Pokud potřebujete **jak číst pdf417 čárový kód** z obrázku, tento průvodce vám ukáže přesné kroky. Pomocí Aspose.BarCode pro .NET můžete dekódovat PDF417 čárový kód jedním voláním metody a průvodce vás provede každým potřebným řádkem kódu.

Čtení čárového kódu z obrázku je běžný úkol při tvorbě skenerů inventáře, systémů ověřování vstupenek nebo pipeline pro zpracování dokumentů. V tomto tutoriálu se naučíte, jak nastavit prostředí, nainstalovat potřebný balíček a napsat robustní C# program, který čte PDF417 čárový kód a extrahuje jeho rozšířená datová pole. Žádné externí služby nejsou vyžadovány; vše běží lokálně.

> **Požadavky**  
> • Nainstalovaný .NET 6.0 SDK nebo novější  
> • Základní znalost C# a konzolových aplikací  
> • Přístup k souboru obrázku, který obsahuje PDF417 (nebo Macro PDF417) čárový kód  

Také se podíváme na alternativy **read barcode from image c#**, vysvětlíme nejužitečnější vlastnosti objektu `BarCodeResult` a poskytneme tipy pro zpracování více čárových kódů na jednom obrázku.

---

## Jak číst PDF417 čárový kód z obrázku v C#

Prvním hlavním krokem je vytvoření `BarCodeReader`, který ukazuje na soubor obrázku a říká knihovně, jaký typ čárového kódu má hledat. Zadáním `DecodeType.MacroPdf417` omezíte skenování na varianty PDF417, což zvyšuje rychlost a přesnost.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image that contains the PDF417 barcode
            string imagePath = @"C:\Barcodes\Pdf417Sample.png";

            // Initialize the reader for Macro PDF417 barcodes
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type : {result.CodeTypeName}");
                    Console.WriteLine($"Code Text : {result.CodeText}");

                    // Macro PDF417 specific extended information
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID : {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    // Show confidence and symbology details
                    Console.WriteLine($"Code Confidence : {result.CodeTextConfidence}");
                    Console.WriteLine($"Is Mirror Image : {result.IsMirrored}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

**Why this works** – Konstruktor `BarCodeReader` přijímá cestu k obrázku a `DecodeType`. `MacroPdf417` říká enginu, aby hledal rodinu PDF417, včetně makro rozšíření, které nese další metadata jako ID souboru. Metoda `ReadBarCodes()` vrací výčtový seznam objektů `BarCodeResult`, z nichž každý představuje detekovaný čárový kód.

### Krok 1: Vytvořte nový konzolový projekt

Otevřete terminál (nebo PowerShell) a spusťte:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

Vytvoření nového projektu izoluje ukázku a zaručuje, že soubor `csproj` obsahuje pouze závislosti, které přidáte dále.

### Krok 2: Nainstalujte NuGet balíček Aspose.BarCode

Aspose.BarCode poskytuje třídu `BarCodeReader` použitou v příkladu. Nainstalujte ji pomocí:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

Balíček zahrnuje podporu všech 1D a 2D symbologií, včetně PDF417 a jeho makro varianty.

### Krok 3: Přidejte výše uvedený kód

Nahraďte obsah souboru `Program.cs` úplným úryvkem z předchozí sekce. Kód demonstruje **C# dekódování čárových kódů** a ukazuje, jak přistupovat k **vlastnostem BarCodeResult**, jako jsou `CodeTypeName`, `CodeText` a makro‑specifické `MacroPdf417FileID`.

### Krok 4: Spusťte aplikaci

```bash
dotnet run
```

Pokud obrázek obsahuje čitelný PDF417 čárový kód, konzole vypíše něco podobného:

```
Code Type : PDF417
Code Text : https://example.com/invoice/12345
Macro PDF417 File ID : 7
Code Confidence : 98.7
Is Mirror Image : False
----------------------------------------
```

Pokud obrázek neobsahuje PDF417 čárový kód, smyčka se jednoduše ukončí bez výpisu.

### Krok 5: Zpracování více čárových kódů a chybových situací

Reálné obrázky mohou obsahovat více než jeden čárový kód nebo žádný. Zabalte logiku čtení do bloku `try`/`catch`, abyste odhalili chyby parsování, a před iterací zkontrolujte `reader.HasBarcodes`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    if (!reader.HasBarcodes)
    {
        Console.WriteLine("No PDF417 barcodes detected.");
        return;
    }

    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // existing processing code...
    }
}
```

**Pro tip:** Upravte vlastnost `Resolution` na `BarCodeReader` (např. `reader.Resolution = 300;`) při práci s nízkou rozlišením skenů. Vyšší rozlišení zlepšuje detekci, ale může zvýšit zatížení CPU.

### Krok 6: Volitelné – Dekódujte jiné typy čárových kódů ze stejného obrázku

Pokud později budete potřebovat **read barcode from image c#** pro jiné symbologie, stačí změnit argument `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupportedTypes))
{
    // This will detect QR, Code128, DataMatrix, etc.
}
```

Stejná třída `BarCodeResult` funguje pro každý typ, takže můžete znovu použít smyčku zpracování bez úprav.

---

## Porozumění klíčovým třídám

| Třída | Účel | Nejužitečnější členové |
|-------|------|------------------------|
| `BarCodeReader` | Otevře obrázek a skenuje čárové kódy | `ReadBarCodes()`, `HasBarcodes`, `Resolution` |
| `BarCodeResult` | Obsahuje informace o jednom detekovaném čárovém kódu | `CodeTypeName`, `CodeText`, `CodeTextConfidence`, `Extended` |
| `Extended.Pdf417` | Poskytuje makro‑specifická data pro PDF417 | `MacroPdf417FileID`, `MacroPdf417SegmentCount`, `MacroPdf417SegmentIndex` |

## Časté úskalí a jak se jim vyhnout

* **Nesprávný `DecodeType`** – Použití `DecodeType.Pdf417` místo `MacroPdf417` způsobí, že makro rozšíření bude přehlédnuto. Vyberte přesný typ, který odpovídá vašemu čárovému kódu.
* **Nepodporovaný formát obrázku** – Aspose.BarCode čte PNG, JPEG, BMP, TIFF a GIF. Pokud máte RAW obrázek, nejprve jej převeďte.
* **Nízký kontrast obrázku** – Před předáním `BarCodeReader` předzpracujte obrázek (zvyšte kontrast nebo binarizujte). Knihovna také nabízí `reader.ImageProcessingOptions`.
* **Velké soubory** – Pro velmi vysoké rozlišení skenů nastavte `reader.MaxBarcodesPerPage`, aby se omezila spotřeba paměti.

## Závěr

Nyní víte **jak číst pdf417 čárový kód** v C# pomocí Aspose.BarCode, od nastavení projektu až po zpracování makro‑specifických polí. Kompletní, spustitelný příklad demonstruje **C# dekódování čárových kódů**, ukazuje, jak přistupovat k **vlastnostem BarCodeResult**, a poskytuje praktické tipy pro spolehlivé skenování.  

Dále prozkoumejte související témata, jako je **read barcode from image c#** pro QR kódy, integrujte čtení čárových kódů do ASP.NET Core API nebo experimentujte s dávkovým zpracováním více obrázků. Stejná třída `BarCodeReader` funguje napříč všemi podporovanými symbologiemi, takže můžete tuto řešení rozšířit na jakýkoli čárový kód, se kterým se vaše aplikace setká.

Šťastné programování a neváhejte upravit ukázku tak, aby vyhovovala vašemu vlastnímu workflow!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak číst makro PDF417 čárový kód v C# s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-macro-pdf417-barcode-in-c-with-aspose-barcode/)
- [Jak číst PDF417 čárový kód v C# – kompletní průvodce čtečkou čárových kódů](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/)
- [Jak vytvořit PDF417 čárový kód s Aspose – kompletní krok‑za‑krokem průvodce](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}