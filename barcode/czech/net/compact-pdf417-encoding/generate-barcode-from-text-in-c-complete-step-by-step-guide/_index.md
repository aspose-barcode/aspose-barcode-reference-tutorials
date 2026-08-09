---
category: general
date: 2026-08-09
description: Generujte čárový kód z textu v C# pomocí Aspose.BarCode. Naučte se, jak
  generovat čárový kód, zacházet se speciálními znaky a rychle vytvořit PDF417 čárový
  kód v C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: cs
lastmod: 2026-08-09
og_description: Generujte čárový kód z textu v C# pomocí Aspose.BarCode. Tento tutoriál
  ukazuje, jak generovat čárový kód, podporovat speciální znaky a vytvořit PDF417
  čárový kód v C# s kompletním kódem.
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: Vytvořte čárový kód z textu v C# – rychlý krok‑za‑krokem průvodce
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Generování čárového kódu z textu v C# – kompletní krok‑za‑krokem průvodce
url: /cs/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generovat čárový kód z textu v C# – kompletní průvodce krok za krokem

Pokud potřebujete **generovat čárový kód z textu** v .NET aplikaci, tento průvodce vás provede celým procesem. Uvidíte, jak generovat čárový kód, spravovat speciální znaky a vytvořit implementaci PDF417 čárového kódu v C#, která funguje ihned.

Generování čárového kódu z textu je běžnou požadavkem pro inventární systémy, platformy pro prodej vstupenek a pracovní postupy s dokumenty. Na konci tohoto tutoriálu budete mít spustitelnou C# konzolovou aplikaci, která pomocí Aspose.BarCode vytvoří PNG obrázek MicroPdf417. Žádné externí služby nejsou potřeba a kód zvládá Unicode znaky jako “Å”, “©” a “é”.

## Požadavky

- .NET 6.0 SDK nebo novější (kód také funguje s .NET Core 3.1 a .NET Framework 4.7+)
- Visual Studio 2022 (nebo jakékoli IDE podporující C#)
- **Aspose.BarCode for .NET** NuGet balíček  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Základní znalost syntaxe C#

## Generovat čárový kód z textu – nastavení generátoru

Prvním krokem je vytvořit instanci `BarcodeGenerator`, která ví, jaký **typ kódování čárového kódu** chcete. V tomto tutoriálu používáme `EncodeTypes.MicroPdf417`, což je kompaktní varianta PDF417 vhodná pro krátké datové řetězce.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Proč to funguje:**  
- `EncodeTypes.MicroPdf417` říká knihovně, aby použila rodinu PDF417, čímž splňuje požadavek **create pdf417 barcode c#**.  
- Konstruktor přijímá surový text, což je podstata **generate barcode from text**.  
- Podpora Unicode je vestavěná, takže znaky jako “Å” a “©” jsou kódovány správně, což řeší **barcode with special characters**.

## Jak generovat čárový kód se speciálními znaky

Když vaše data obsahují ne‑ASCII symboly, musíte zajistit, aby generátor používal kódování UTF‑8. Aspose.BarCode automaticky detekuje Unicode, ale můžete explicitně nastavit kódování textu, pokud narazíte na problémy:

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Přidání tohoto řádku před `ConfigureGenerator` zaručuje, že **barcode with special characters** se vykreslí správně na jakékoli platformě.

### Praktický tip
Pokud výstup vypadá poškozeně, ověřte, že písmo použité renderérem čárových kódů podporuje požadované glyfy. Vlastní TrueType písmo můžete vložit pomocí:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Typy kódování čárových kódů, které můžete zvolit

Aspose.BarCode podporuje desítky **barcode encode types**, z nichž každý je vhodný pro různé případy použití:

| Encode type                | Typické použití                     |
|----------------------------|--------------------------------------|
| `EncodeTypes.Code128`      | Štítky pro dopravu, inventář           |
| `EncodeTypes.QR`           | Mobilní platby, URL                    |
| `EncodeTypes.Pdf417`       | Řidičské průkazy, palubní vstupenky   |
| `EncodeTypes.MicroPdf417`  | Malé datové náklady, omezený prostor   |
| `EncodeTypes.DataMatrix`   | Malé položky, vysoká datová hustota    |

Změna typu kódování je tak jednoduchá, jako vyměnit hodnotu enumu v konstruktoru:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Tato flexibilita vám umožní odpovědět na otázky ohledně **barcode encode types** bez opuštění IDE.

## Vytvořit PDF417 čárový kód v C# – poslední kroky a ověření

Po nastavení generátoru je poslední částí **create pdf417 barcode c#** uložení obrázku a potvrzení výsledku.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Spusťte program (`dotnet run`) a měli byste vidět zprávu v konzoli podobnou této:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Otevřete PNG soubor; uvidíte ostrý MicroPdf417 čárový kód, který kóduje řetězec “Åspóse.Barcóde©”. Skenování pomocí mobilního skeneru čárových kódů (např. ZXing) vrátí původní text, což dokazuje, že **generate barcode from text** funguje i se speciálními znaky.

### Okrajový případ: velmi dlouhý text

MicroPdf417 má maximální kapacitu dat 1 KB. Pokud váš vstup překročí tento limit, knihovna vyhodí `ArgumentException`. Pro elegantní ošetření:

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

Pro větší náklady přepněte na plnou `EncodeTypes.Pdf417` nebo `EncodeTypes.DataMatrix`.

## Časté úskalí a jak se jim vyhnout

| Problém                               | Příčina                                   | Řešení |
|---------------------------------------|-------------------------------------------|--------|
| Čárový kód je rozmazaný               | XDimension příliš nízký (např. 1 px)       | Zvyšte `XDimension.Pixels` na 2‑3 px |
| Unicode znaky se mění na `?`         | Výchozí kódování textu je ASCII            | Nastavte `TextEncoding = Encoding.UTF8` |
| Soubor obrázku nebyl vytvořen         | Výstupní adresář neexistuje                | Použijte `Directory.CreateDirectory` před `Save` |
| Skener nedokáže čárový kód přečíst    | Příliš mnoho sloupců pro krátká data       | Snižte `Pdf417.Columns` (např. 3‑4) |

## Kompletní zdrojový kód (připravený ke kopírování)

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**Očekávaný výstup:** soubor pojmenovaný `MicroPdf417.png` umístěný ve složce `output`, obsahující čistý MicroPdf417 čárový kód, který kóduje původní řetězec se speciálními znaky.

## Závěr

Nyní víte, jak **generovat čárový kód z textu** v C# pomocí Aspose.BarCode, jak zacházet s **barcode with special characters**, a jak **create pdf417 barcode c#** s plnou kontrolou nad možnostmi kódování. Úpravou **barcode encode types** můžete vytvářet QR kódy, Code128, DataMatrix nebo jakýkoli jiný podporovaný formát.

Dále prozkoumejte následující témata, abyste prohloubili své znalosti o čárových kódech:

- **How to generate barcode** ve šarži pro tisíce záznamů (použijte `Parallel.ForEach` pro rychlost)
- Přizpůsobení barev a přidání loga uvnitř čárového kódu
- Integrace generování čárových kódů do ASP.NET Core API pro okamžité doručování obrázků
- Použití dalších knihoven jako ZXing.Net nebo IronBarcode jako open‑source alternativy

Neváhejte experimentovat s různými rozměry, nastavením sloupců a typy kódování. Šťastné programování a ať vaše aplikace skenují bezchybně!

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, které vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy k implementaci ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat čárový kód – Konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generovat čárový kód – Jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}