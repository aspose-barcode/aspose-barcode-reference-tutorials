---
category: general
date: 2026-07-18
description: Naučte se, jak v C# generovat obrázek čárového kódu ve formátu MicroPdf417.
  Krok za krokem nastavení rozměrů a uložení jako PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- micro pdf417 barcode
- BarcodeGenerator class
- set barcode dimensions
- save barcode as png
language: cs
lastmod: 2026-07-18
og_description: Jak vygenerovat obrázek čárového kódu v C#? Postupujte podle tohoto
  návodu k vytvoření čárového kódu MicroPdf417, upravte jeho velikost a exportujte
  jej jako soubor PNG.
og_image_alt: Screenshot of a MicroPdf417 barcode image generated in C#
og_title: Jak vygenerovat obrázek čárového kódu v C# – Kompletní tutoriál MicroPdf417
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  headline: How to Generate Barcode Image in C# – MicroPdf417 Guide
  type: TechArticle
- description: Learn how to generate barcode image in C# using the MicroPdf417 format.
    Step‑by‑step setup for dimensions and saving as PNG.
  name: How to Generate Barcode Image in C# – MicroPdf417 Guide
  steps:
  - name: Change Image Format
    text: 'You aren’t limited to PNG. Switch to JPEG or BMP by adjusting the second
      argument of `Save`:'
  - name: Increase DPI for Print
    text: 'For high‑resolution prints, bump the `Resolution` property:'
  - name: Add Quiet Zone (Margin)
    text: 'A quiet zone helps scanners differentiate the barcode from surrounding
      graphics:'
  - name: Encode Different Data Types
    text: 'MicroPdf417 works with numeric, alphanumeric, and binary data. If you need
      to embed a URL, just replace the text:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Jak vygenerovat obrázek čárového kódu v C# – Průvodce MicroPdf417
url: /cs/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vygenerovat obrázek čárového kódu v C# – Průvodce MicroPdf417

Už jste se někdy zamýšleli **jak vygenerovat obrázek čárového kódu** v C# bez nekonečného prohledávání dokumentace? Nejste v tom sami. Ať už budujete systém pro vstupenky, katalog produktů nebo jen potřebujete rychlý QR‑styl kód, zvládnutí tvorby čárových kódů vám ušetří čas i starosti.

V tomto tutoriálu projdeme přesně kroky, jak vygenerovat **MicroPdf417 čárový kód** pomocí třídy `BarcodeGenerator`, upravit jeho rozměry a uložit výsledek jako PNG. Žádné zbytečnosti – jen kompletní, spustitelný příklad, který můžete dnes zkopírovat do svého projektu.

## Co se naučíte

- Nastavení `BarcodeGenerator` pro formát MicroPdf417  
- **Nastavení rozměrů čárového kódu** jako šířka modulu a počet sloupců  
- **Uložení čárového kódu jako PNG** do libovolné složky  
- Volitelné úpravy pro výstup ve vysokém rozlišení a ošetření chyb  

Na konci budete schopni s jistotou odpovědět na otázku *„jak vygenerovat obrázek čárového kódu“* a získáte pevný základ pro tvorbu i dalších typů čárových kódů.

---

## Požadavky

Než se pustíme dál, ujistěte se, že máte:

1. **.NET 6.0 nebo novější** (kód funguje i na .NET Framework 4.5+)  
2. Odkaz na knihovnu **Aspose.BarCode** (nebo jakoukoli knihovnu, která poskytuje `BarcodeGenerator`). Můžete ji získat přes NuGet:  

   ```bash
   dotnet add package Aspose.BarCode
   ```

3. Pohodlné IDE – Visual Studio, Rider nebo VS Code vám postačí.  
4. Oprávnění k zápisu do adresáře, kam budete PNG soubor ukládat.

> **Tip:** Pokud používáte jinou knihovnu pro čárové kódy, názvy tříd se mohou lišit, ale celkový postup zůstává stejný.

---

## Krok 1: Vytvořte generátor MicroPdf417

Prvním krokem je vytvořit instanci `BarcodeGenerator` nakonfigurovanou pro **formát MicroPdf417**. Tento objekt je motorem, který převádí váš text na vizuální kód.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialise the generator with MicroPdf417 and the desired text
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // Choose the MicroPdf417 format
    "Åspóse.Barcóde©");               // The data you want to encode
```

**Proč je to důležité:**  
`EncodeTypes.MicroPdf417` říká knihovně, aby použila kompaktní variantu PDF417, která je ideální pro krátké řetězce a omezený prostor. Text může obsahovat Unicode znaky, jak je ukázáno výše, takže nejste omezeni jen na čisté ASCII.

---

## Krok 2: Nastavte rozměry čárového kódu

Jakmile máte generátor, pravděpodobně budete chtít řídit, jak velký bude každý modul (malý čtvereček) a kolik sloupců kód zabere. Zde vstupuje do hry klíčové slovo **set barcode dimensions**.

```csharp
// Step 2: Adjust appearance – module width and column count
generator.Parameters.Barcode.XDimension.Pixels = 2;   // Module width in pixels
generator.Parameters.Barcode.Pdf417.Columns = 4;    // Number of columns (affects height)
```

- **`XDimension.Pixels`** – Větší hodnoty usnadní skenování, ale zvětší velikost souboru.  
- **`Pdf417.Columns`** – Méně sloupců komprimuje kód vertikálně; více sloupců jej roztáhne horizontálně.

> **Pozor:** Nastavení šířky modulu příliš nízko (např. 1 pixel) může na obrazovkách s vysokým DPI vytvořit rozmazaný obrázek. Hodnota mezi 2‑4 pixely funguje dobře pro většinu tiskáren.

---

## Krok 3: Uložte obrázek čárového kódu jako PNG

Po nastavení generátoru je posledním krokem zapsat grafiku na disk. Tím splníte požadavek **save barcode as png**.

```csharp
// Step 3: Export the barcode to a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Co se děje pod kapotou?**  
`Save` vykreslí čárový kód do bitmapy, zakóduje ji jako PNG (bezeztrátová komprese) a zapíše bajty na zadané místo. Pokud adresář neexistuje, `Save` vyhodí výjimku – proto je dobré tento kód obalit do `try/catch` bloku v produkčním prostředí.

---

## Kompletní funkční příklad

Spojením všech částí získáte samostatnou konzolovou aplikaci, kterou můžete spustit okamžitě:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set dimensions
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // 3️⃣ Define output path
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");

        // 4️⃣ Save as PNG
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"❌ Failed to save barcode: {ex.Message}");
        }
    }
}
```

**Očekávaný výstup:** Ostrý soubor `MicroPdf417.png` na ploše, zobrazující zakódovaný řetězec `Åspóse.Barcóde©`. Otevřete jej v libovolném prohlížeči obrázků a ověřte, že čárový kód je čitelný a skenovatelný.

---

## Pokročilé možnosti (volitelné)

Pokud chcete rozšířit základní postup, zvažte následující úpravy – každá z nich odpovídá sekundárnímu klíčovému slovu z našeho seznamu.

### Změna formátu obrázku

Nejste omezeni jen na PNG. Přepněte na JPEG nebo BMP úpravou druhého argumentu metody `Save`:

```csharp
generator.Save(outputPath.Replace(".png", ".jpg"), BarCodeImageFormat.Jpeg);
```

### Zvýšení DPI pro tisk

Pro tisk ve vysokém rozlišení zvyšte vlastnost `Resolution`:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

### Přidání tiché zóny (okraj)

Tichá zóna pomáhá skenerům odlišit čárový kód od okolní grafiky:

```csharp
generator.Parameters.Barcode.QR.QrQuietZone = 4; // 4 modules of margin
```

### Kódování různých typů dat

MicroPdf417 funguje s číselnými, alfanumerickými i binárními daty. Pokud potřebujete vložit URL, stačí nahradit text:

```csharp
generator.CodeText = "https://example.com";
```

---

## Časté problémy a jak je řešit

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Čárový kód je rozmazaný | `XDimension.Pixels` nastaveno na 1 nebo obrázek byl po uložení změněn velikost | Použijte minimálně 2 pixely a vyhněte se následnému škálování |
| Skener kód nečte | Příliš mnoho sloupců pro danou délku dat | Snižte `Pdf417.Columns` nebo nechte knihovnu automaticky nastavit (`Columns = 0`) |
| Unicode znaky se zobrazují jako � | Zastaralá verze knihovny nebo chybějící podpora fontů | Aktualizujte Aspose.BarCode na nejnovější verzi a zajistěte správné kódování |
| `Save` vyhodí `DirectoryNotFoundException` | Výstupní složka neexistuje | Vytvořte adresář předem nebo použijte `Path.Combine` s ověřenými složkami |

---

## Testování vašeho čárového kódu

Po vygenerování obrázku jej můžete ověřit pomocí libovolné aplikace pro skenování čárových kódů (většina chytrých telefonů už má vestavěné čtečky). Nasmerujte kameru na PNG soubor na obrazovce nebo jej vytiskněte – pokud aplikace přečte `Åspóse.Barcóde©`, úspěšně jste odpověděli na otázku **jak vygenerovat obrázek čárového kódu**.

---

## Závěr

Probrali jsme vše, co potřebujete vědět k **jak vygenerovat obrázek čárového kódu** pomocí C# a formátu MicroPdf417:

1. **Vytvořte** `BarcodeGenerator` s vašimi daty.  
2. **Nastavte rozměry čárového kódu** pro kontrolu velikosti a čitelnosti.  
3. **Uložte čárový kód jako PNG** (nebo jiný podporovaný formát).  

Odtud můžete experimentovat s různými typy čárových kódů, upravovat DPI pro tisk nebo vkládat obrázek přímo do PDF či reportů. Základní stavební kameny jsou stejné, takže klidně zaměníte `EncodeTypes.MicroPdf417` za `EncodeTypes.QR` nebo `EncodeTypes.Code128` a postup zopakujte.

Máte otázky ohledně jiných standardů čárových kódů nebo potřebujete pomoci s úpravou vzhledu? Zanechte komentář níže a šťastné kódování!

## Co se naučíte dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční kódové příklady s podrobným krok‑za‑krokem vysvětlením, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode - One-Dimensional Barcode Types](/barcode/english/net/one-dimensional-barcode-types/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}