---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# vám umožňuje snadno přidávat makrodata a
  generovat čárové kódy PDF417. Naučte se krok za krokem, jak přidat makrometadata
  a vytvořit obrázek PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: cs
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# vám ukazuje, jak přidat makro metadata
  a vygenerovat čárový kód PDF417 v několika řádcích kódu.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose Barcode Generator C# – přidat makro a vygenerovat čárový kód PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Jak použít Aspose Barcode Generator v C# pro čárový kód MacroPdf417
url: /cs/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak použít Aspose Barcode Generator C# pro čárový kód MacroPdf417

Pokud potřebujete v C# vytvořit čárový kód MacroPdf417, **Aspose Barcode Generator C#** poskytuje stručné API, které zpracovává jak obrázek čárového kódu, tak požadovaná makro metadata. Tento tutoriál vám přesně ukáže, jak přidat makro informace a vygenerovat obrázek PDF417 čárového kódu během několika kroků.

Naučíte se, jak nakonfigurovat vizuální parametry, vložit makro pole jako ID souboru a časové razítko a uložit výsledek jako PNG. Žádné externí nástroje nejsou potřeba — stačí knihovna Aspose.BarCode a .NET vývojové prostředí.

## Požadavky

* .NET 6.0 nebo novější nainstalovaný  
* Visual Studio 2022 (nebo jakékoli C# IDE)  
* Licencovaná nebo evaluační kopie **Aspose.BarCode for .NET**  

Kód funguje na Windows, Linuxu i macOS, protože knihovna je platformně nezávislá.

## Krok 1: Nainstalujte NuGet balíček Aspose.BarCode

Otevřete svůj projekt ve Visual Studiu a spusťte následující příkaz v **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Tím se do projektu přidá sestavení `Aspose.BarCode` a jeho závislosti.

## Krok 2: Vytvořte instanci generátoru čárových kódů

První řádek vytvoří objekt `BarcodeGenerator` pro symbologii **MacroPdf417** a předá text, který chcete zakódovat.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Proč je to důležité*: Hodnota `EncodeTypes.MacroPdf417` říká knihovně, že má očekávat makro‑související pole, která nastavíte v dalším kroku.

## Krok 3: Definujte vizuální vzhled

Můžete řídit velikost každého modulu (nejmenší černý nebo bílý čtvereček) a počet sloupců v matici PDF417. Úprava `XDimension` ovlivňuje celkové rozlišení obrázku.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Zvětšením `Columns` snížíte výšku čárového kódu, zatímco větší `XDimension` zpřehlední obrázek na obrazovkách s vysokým DPI.

## Krok 4: Přidejte makro metadata (jak přidat makro)

MacroPdf417 vyžaduje několik doplňujících polí, která popisují zdrojový soubor a jeho segmentaci. Následující vlastnosti mapují přímo na specifikace makra PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Proč jsou tato pole*:
* `MacroPdf417FileID` spojuje všechny segmenty dohromady a zajišťuje, že skener může znovu sestavit původní dokument.  
* `MacroPdf417SegmentID` a `MacroPdf417SegmentsCount` informují dekodér o pořadí a celkovém počtu částí.  
* `MacroPdf417FileSize` a `MacroPdf417Checksum` poskytují kontrolu integrity, což je cenné při přenosu velkých dat.

## Krok 5: Uložte obrázek čárového kódu (jak vygenerovat pdf417)

Nakonec zapíšete čárový kód na disk. Metoda `Save` přijímá cestu k souboru a formát obrázku. PNG zachovává ostré hrany čárového kódu bez kompresních artefaktů.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Po spuštění programu najdete **ExtPDF417Meta.png** ve výstupní složce. Otevřením obrázku uvidíte čistý MacroPdf417 čárový kód připravený k tisku nebo vložení do PDF.

### Očekávaný výstup

| Název souboru       | Formát | Rozměry (přibližně) |
|--------------------|--------|----------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (varies with `XDimension`) |

Skenování obrázku čtečkou kompatibilní s PDF417 (např. ZXing, Aspose.BarCode for .NET) vrátí původní text **“Åspóse.Barcóde©”** spolu se všemi makro poli.

## Časté problémy a jak se jim vyhnout

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| **Incorrect `EncodeTypes`** | Použití `EncodeTypes.Pdf417` místo `EncodeTypes.MacroPdf417` zakáže makro pole. | Vždy vytvářejte generátor s `EncodeTypes.MacroPdf417`. |
| **Missing macro fields** | Některé skenery ignorují čárový kód, pokud chybí povinná makro pole. | Vyplňte alespoň `FileID`, `SegmentID`, `SegmentsCount` a `Terminator`. |
| **Too small `XDimension`** | Hodnota pod 1 pixel může vytvořit nečitelné čárové kódy na nízkém rozlišení. | Udržujte `XDimension` ≥ 2 pixely pro většinu scénářů na obrazovce i tisku. |
| **File path errors** | Poskytnutí relativní cesty, která neexistuje, vyvolá výjimku. | Použijte `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` nebo absolutní cestu. |

## Kompletní zdrojový kód

Níže je kompletní, spustitelný příklad, který můžete zkopírovat do nového konzolového projektu.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Spusťte program (`dotnet run`). Po dokončení se v konzoli zobrazí zpráva o úspěchu a soubor PNG se objeví ve výstupní složce projektu.

## Další kroky

* **Encode larger data** – Zvyšte `Columns` nebo upravte `Rows` (pomocí `Pdf417.Rows`) pro více znaků.  
* **Embed in PDF** – Použijte Aspose.PDF k vložení vygenerovaného PNG do dokumentu.  
* **Scan verification** – Využijte `Aspose.BarCode.Reader` k dekódování čárového kódu a programově potvrďte makro pole.  

Prozkoumání těchto témat prohloubí vaše pochopení **jak generovat PDF417** čárové kódy s bohatými makro informacemi a připraví vás na reálné scénáře, jako je hromadné zpracování dokumentů nebo bezpečná výměna dat.

---

*Šťastné programování! Pokud vám tento průvodce přišel užitečný, zvažte jeho sdílení s kolegy nebo přidání hvězdičky do repozitáře Aspose.BarCode na GitHubu.*

## Co byste se měli naučit dál?

Následující tutoriály pokrývají úzce související témata, která staví na technikách předvedených v tomto průvodci. Každý zdroj obsahuje kompletní funkční ukázky kódu s podrobnými vysvětleními, aby vám pomohl zvládnout další funkce API a prozkoumat alternativní implementační přístupy ve vlastních projektech.

- [Jak vytvořit makro PDF417 čárový kód v C# pomocí Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Jak vygenerovat PDF417 čárový kód v C# s Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode příklad: generovat Macro PDF417 v C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}