---
category: general
date: 2026-10-09
description: Zjistěte, jak generovat barcode c# pomocí Aspose.BarCode, zpracovávat
  speciální znaky a rychle vytvářet PDF417 barcode obrázky v .NET.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode c#
- barcode generator .net
- create barcode image c#
- barcode with special characters
- pdf417 barcode c#
lastmod: 2026-10-09
og_description: Generujte barcode c# pomocí Aspose.BarCode v .NET console app. Tento
  krok‑za‑krokem průvodce ukazuje, jak zpracovávat Unicode, vybrat encode types a
  vytvářet PDF417 barcode obrázky.
og_image_alt: Developer view of a MicroPdf417 barcode PNG generated with Aspose.BarCode
og_title: Generování barcode c# – rychlý krok‑za‑krokem průvodce pro .NET
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Generate barcode c# with Aspose.BarCode. Learn how to generate barcode,
    support special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode c# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: Generování barcode c# – kompletní krok‑za‑krokem průvodce
url: /cs/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Generovat čárový kód c# – kompletní krok‑za‑krokem průvodce

Pokud potřebujete **generovat čárový kód c#** v aplikaci .NET, tento průvodce vás provede celým procesem. Uvidíte, jak vygenerovat čárový kód, spravovat speciální znaky a vytvořit implementaci PDF417 čárového kódu v C#, která funguje ihned.

Generování čárového kódu z textu je běžná potřeba pro inventární systémy, platformy pro prodej vstupenek a pracovní postupy s dokumenty. Na konci tohoto tutoriálu budete mít spustitelnou C# konzolovou aplikaci, která pomocí Aspose.BarCode vytvoří PNG obrázek MicroPdf417. Nepotřebujete žádné externí služby a kód zvládá Unicode znaky jako “Å”, “©” a “é”.

## Rychlé odpovědi
- **Jakou knihovnu bych měl použít?** Aspose.BarCode pro .NET poskytuje nejúplnější sadu typů kódování a nativní podporu Unicode.  
- **Mohu to spustit na .NET 6?** Ano, kód cílí na .NET 6 a také funguje s .NET Core 3.1 a .NET Framework 4.7+.  
- **Jak zacházet se speciálními znaky?** Nastavte `TextEncoding = Encoding.UTF8` na generátoru, aby bylo zajištěno správné vykreslení.  
- **Jaký formát obrázku se vytvoří?** Příklad ukládá soubor PNG, ale můžete přepnout na JPEG, BMP nebo TIFF jednou změnou vlastnosti.  
- **Je vyžadována licence?** Bezplatná zkušební verze funguje pro vývoj; pro produkční nasazení je potřeba komerční licence.

## Co je generovat čárový kód c#?
`generate barcode c#` označuje programové vytvoření vizuálního obrázku čárového kódu pomocí C# kódu. Aspose.BarCode pro .NET převádí libovolný řetězec – ASCII nebo Unicode – na rastrový obrázek, který lze vytisknout, zobrazit na obrazovce nebo vložit do PDF.

## Proč použít Aspose.BarCode pro .NET?
Aspose.BarCode podporuje **30+ symbologií čárových kódů** a může vykreslovat obrázky až do **5000 × 5000 px** bez ztráty kvality. Knihovna zpracuje 1 KB payload za méně než **30 ms** na typickém vývojářském notebooku, což znamená, že generování v reálném čase je proveditelné pro scénáře s vysokým průtokem, jako jsou kiosky pro vstupenky nebo hromadné vytváření štítků.

## Předpoklady

- .NET 6.0 SDK nebo novější (kód také funguje s .NET Core 3.1 a .NET Framework 4.7+)
- Visual Studio 2022 (nebo jakékoli IDE podporující C#)
- **Aspose.BarCode for .NET** NuGet balíček  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Základní znalost syntaxe C#

## Jak nastavit generátor čárových kódů?
Třída `BarcodeGenerator` je jádrová komponenta, která vytváří obrázky čárových kódů na základě zadaných nastavení.  
Vytvořte instanci `BarcodeGenerator`, určete, jaký **typ kódování čárového kódu** potřebujete, a předávejte surový text, který chcete zakódovat. Tento jediný řádek vytvoří plně nakonfigurovaný generátor připravený vykreslit MicroPdf417 čárový kód.

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

Hodnota výčtu `EncodeTypes.MicroPdf417` vybírá kompaktní variantu PDF417, která je ideální pro krátké datové řetězce při zachování minimální velikosti symbolu.

## Jak generovat čárový kód se speciálními znaky?
Když vaše data obsahují ne‑ASCII symboly, musíte zajistit, že generátor používá kódování UTF‑8. Aspose.BarCode automaticky detekuje Unicode, ale můžete explicitně nastavit kódování textu, pokud narazíte na problémy. Nastavení kódování zaručuje, že znaky jako “Å”, “©” a “é” budou ve výsledném obrázku čárového kódu vykresleny správně, čímž se zabrání běžnému problému s poškozenými nebo chybějícími glyfy.

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

Přidání tohoto řádku před jakoukoli jinou konfigurací zaručuje, že **čárový kód se speciálními znaky** bude na jakékoli platformě vykreslen správně.

### Praktický tip
Pokud výstup vypadá poškozeně, ověřte, že písmo použité čtečkou čárových kódů podporuje požadované glyfy. Vlastní TrueType písmo můžete vložit pomocí:

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## Které typy kódování čárových kódů mohu vybrat?
Aspose.BarCode podporuje desítky **typů kódování čárových kódů**, z nichž každý je vhodný pro různé případy použití. Knihovna poskytuje komplexní seznam symbologií, od lineárních kódů používaných v logistice po dvourozměrné maticové kódy pro mobilní aplikace. Výběrem vhodného typu kódování zajistíte optimální čitelnost a datovou hustotu pro váš konkrétní scénář.

| Typ kódování                | Typické použití                     |
|----------------------------|--------------------------------------|
| `EncodeTypes.Code128`      | Expediční štítky, inventář           |
| `EncodeTypes.QR`           | Mobilní platby, URL                  |
| `EncodeTypes.Pdf417`       | Řidičské průkazy, palubní vstupenky |
| `EncodeTypes.MicroPdf417`  | Malé datové náklady, omezený prostor |
| `EncodeTypes.DataMatrix`   | Malé předměty, vysoká datová hustota |

Změna typu kódování je tak jednoduchá jako výměna hodnoty výčtu v konstruktoru:

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

Tato flexibilita vám umožní odpovídat na otázky o **typech kódování čárových kódů** bez opuštění IDE.

## Jak vytvořit PDF417 čárový kód C# – poslední kroky a ověření
Po nakonfigurování generátoru je poslední částí **vytvořit pdf417 čárový kód c#** uložení obrázku a potvrzení výsledku. Musíte zavolat metodu `Save` s cestou k souboru a případně specifikovat formát obrázku. Po zápisu souboru jej otevřete v prohlížeči obrázků nebo naskenujte čtečkou čárových kódů, abyste ověřili, že zakódovaný text odpovídá původnímu vstupu.

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Spusťte program (`dotnet run`) a měli byste vidět zprávu v konzoli podobnou této:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

Otevřete PNG soubor; uvidíte ostrý MicroPdf417 čárový kód, který zakóduje řetězec “Åspóse.Barcóde©”. Naskenování pomocí mobilního skeneru čárových kódů (např. ZXing) vrátí původní text, což dokazuje, že **generovat čárový kód c#** funguje i se speciálními znaky.

## Co se stane s velmi dlouhým textem?
MicroPdf417 má maximální kapacitu dat **1 KB**. Když je payload větší než podporovaná velikost, generátor nemůže vytvořit platný symbol a vyvolá výjimku. Měli byste tuto situaci zachytit a buď data oříznout, rozdělit je do více čárových kódů, nebo přejít na symbologii s vyšší kapacitou, jako je plný PDF417 nebo DataMatrix. Pro elegantní řešení:

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

Pro větší payloady přepněte na plný `EncodeTypes.Pdf417` nebo `EncodeTypes.DataMatrix`, které podporují až **1,5 KB** a **3 KB** respektive.

## Časté úskalí a jak se jim vyhnout

| Problém                               | Příčina                                   | Oprava |
|---------------------------------------|-------------------------------------------|--------|
| Čárový kód se jeví rozmazaný          | XDimension je příliš nízký (např. 1 px)   | Zvyšte `XDimension.Pixels` na 2‑3 px |
| Unicode znaky se mění na `?`          | Výchozí kódování textu je ASCII           | Nastavte `TextEncoding = Encoding.UTF8` |
| Soubor obrázku nebyl vytvořen          | Výstupní adresář neexistuje               | Použijte `Directory.CreateDirectory` před `Save` |
| Scanner nemůže čárový kód přečíst     | Příliš mnoho sloupců pro krátká data      | Snižte `Pdf417.Columns` (např. 3‑4) |

## Kompletní zdrojový kód (připravený ke zkopírování)

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

**Očekávaný výstup:** soubor pojmenovaný `MicroPdf417.png` umístěný ve složce `output`, obsahující čistý MicroPdf417 čárový kód, který zakóduje původní řetězec se speciálními znaky.

## Závěr

Nyní víte, jak **generovat čárový kód c#** pomocí Aspose.BarCode, jak zacházet s **čárovým kódem se speciálními znaky** a jak **vytvořit pdf417 čárový kód c#** s plnou kontrolou nad možnostmi kódování. Úpravou **typů kódování čárových kódů** můžete vytvářet QR kódy, Code128, DataMatrix nebo jakýkoli jiný podporovaný formát.

Dále prozkoumejte následující témata, abyste prohloubili své znalosti o čárových kódech:

- **Jak generovat čárový kód** ve velkém objemu pro tisíce záznamů (použijte `Parallel.ForEach` pro rychlost)
- Přizpůsobení barev a přidání loga do čárového kódu
- Integrace generování čárových kódů do ASP.NET Core API pro okamžité doručování obrázků
- Použití dalších knihoven, jako jsou ZXing.Net nebo IronBarcode, pro open‑source alternativy

Neváhejte experimentovat s různými rozměry, nastavením sloupců a typy kódování. Šťastné programování a ať vaše aplikace skenují bezchybně!

## Co byste se měli naučit dál?
Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, která vám pomohou zvládnout další funkce API a prozkoumat alternativní přístupy ve vašich projektech.

- [Jak vytvořit čárový kód – Kompaktní PDF417 s Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Jak generovat čárový kód – Konfigurace Code 39 s Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [Jak generovat čárový kód – Jednorozměrné typy čárových kódů](/barcode/english/net/one-dimensional-barcode-types/)

## Často kladené otázky

**Q: Mohu tento kód použít v komerční aplikaci?**  
A: Ano, můžete používat Aspose.BarCode v komerčních projektech, pokud máte platnou licenci; pro hodnocení je k dispozici bezplatná zkušební verze.

**Q: Podporuje Aspose.BarCode .NET 6?**  
A: Rozhodně. Knihovna je zkompilována pro .NET Standard 2.0, což ji činí kompatibilní s .NET 6, .NET 5, .NET Core 3.1 a .NET Framework 4.7+.

**Q: Jak změním výstupní formát z PNG na JPEG?**  
A: Nastavte vlastnost `SaveFormat` na `SaveFormat.Jpeg` před voláním `Save`. Zbytek kódu zůstane beze změny.

**Q: Jaká je maximální velikost MicroPdf417 čárového kódu?**  
A: MicroPdf417 může zakódovat až **1 KB** dat; pokus o překročení tohoto limitu vyvolá `ArgumentException`.

**Q: Je možné vložit logo do čárového kódu?**  
A: Ano. Použijte vlastnost `BarcodeGenerator.Image` k načtení obrázku loga a přiřaďte jej `BarcodeGenerator.Image` před uložením.

---

**Poslední aktualizace:** 2026-10-09  
**Testováno s:** Aspose.BarCode 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit PDF417 čárový kód s Aspose Barcode – krok za krokem průvodce](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/)
- [Jak generovat DataMatrix čárové kódy pomocí Aspose.BarCode pro .NET – krok za krokem průvodce](/barcode/net/datamatrix-barcode-configuration/)
- [Generovat PNG čárový kód s Aspose.BarCode pro .NET: Jednorozměrné vyplněné pruhy](/barcode/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}